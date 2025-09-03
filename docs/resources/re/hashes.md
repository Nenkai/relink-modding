---
icon: octicons/hash-16
---

# Hashes

The vast majority of the game and its executable uses hashed strings. This makes any reverse-engineering work tedious as strings cannot always be recovered, and decompilation work can be complicated without a hash list of sorts.

Hashes can be found just about everywhere - in table files, in the executable as compile-time constants, inside model files, `prfb`/`matb`... and more.

---

## Algorithm

The algorithm is XXHash32 with some odd twist.

C# code for it can be found [here](https://github.com/Nenkai/GBFRDataTools/blob/master/GBFRDataTools.Hashing/XXHash32Custom.cs).

#### Tester

An empty string `""` is always equal to `887AE0B0` / `B0 E0 7A 88`.

<div>
    <input
        class="md-input"
        placeholder="Input string here..."
        id="hash-str" name="hash-str"
        required min="0" maxlength="64" size="20"
        style="width: 500px;"
    />
    <span></span>
    <label name="hash-value" id="hash-value">N/A</label>
</div>

---

## Hash List

You can grab a zipped hash list [here](hashlist.7z) (updated Sept 3rd 2025).

It contains:

* Hashes for the majority of english words
* Hashes for most strings for all game files gathered with `strings2`
* Hashes for most strings gathered from the executable with `strings2`
* Hashes for most strings gathered from NierAutomata.exe with `strings2`
* Hashes for strings such as `object_` => `Object`, useful for UI file component properties

<script>
document.getElementById("hash-str").addEventListener("input", (event) => {
  var str = document.getElementById("hash-str").value;
  if (str.length == 0)
  {
    document.getElementById("hash-value").innerHTML = "N/A";
    return;
  }

  var hash = XXHash32Custom(document.getElementById("hash-str").value);
  hash >>>= 0; // Convert to unsigned
  document.getElementById("hash-value").innerHTML = hash.toString(16).toUpperCase();
});

var PRIME32_1 = 0x9e3779b1;
var PRIME32_2 = 0x85EBCA77;
var PRIME32_3 = 0xC2B2AE3D;
var PRIME32_4 = 0x27D4EB2F;
var PRIME32_5 = 0x165667B1;

function XXHash32Custom(str)
{
    var array = asciiToUint8Array(str);
    var inputLength = array.length;

    var h32 = 0x178A54A4;
    if (str.length >= 16)
    {
        var v1 = 0x2557311B;
        var v2 = 0x871FB76A;
        var v3 = 0x0133ECF3;
        var v4 = 0x62FC7342;

        do
        {
            v1 = XXH32_round(v1, getInt32(array));
            v2 = XXH32_round(v2, getInt32(array.subarray(4)));
            v3 = XXH32_round(v3, getInt32(array.subarray(8)));
            v4 = XXH32_round(v4, getInt32(array.subarray(12)));

            array = array.subarray(16);
        }
        while (array.length > 16);

        h32 = XXH32_rotl(v1, 1)
            + XXH32_rotl(v2, 7)
            + XXH32_rotl(v3, 12)
            + XXH32_rotl(v4, 18);
    }

    h32 += inputLength;

    while (array.length >= 4)
    {
        h32 = Math.imul(XXH32_rotl(h32 + Math.imul(getInt32(array), PRIME32_3), 17), PRIME32_4);
        array = array.subarray(4);
    }

    while (array.length > 0)
    {
        h32 = Math.imul(XXH32_rotl(h32 + Math.imul(array[0], PRIME32_5), 11), PRIME32_1);
        array = array.subarray(1);
    }

    h32 ^= h32 >>> 15;
    h32 = Math.imul(h32, PRIME32_2);
    h32 ^= h32 >>> 13;
    h32 = Math.imul(h32, PRIME32_3);
    h32 ^= h32 >>> 16;

    return h32;
}

function XXH32_round(seed, inputVal)
{
    return Math.imul(XXH32_rotl(seed + Math.imul(inputVal, PRIME32_2), 13), PRIME32_1);
}

function getInt32(uint8Arr)
{
    var val = uint8Arr[0] | (uint8Arr[1] << 8) | (uint8Arr[2] << 16) | (uint8Arr[3] << 24);
    return val;
}

function XXH32_rotl(x, r)
{
    return x << r | x >>> 32 - r;
}

//// JS Utils
function asciiToUint8Array(str){
  var chars = [];
  for (var i = 0; i < str.length; ++i){
    chars.push(str.charCodeAt(i));
  }
  return new Uint8Array(chars);
}

function convert(Uint8Arr) {
    var length = Uint8Arr.length;

    let buffer = Buffer.from(Uint8Arr);
    var result = buffer.readUIntBE(0, length);

    return result;
}

function decimalToHexString(number)
{
  if (number < 0)
  {
    number = 0xFFFFFFFF + number + 1;
  }

  return number.toString(16).toUpperCase();
}
</script>