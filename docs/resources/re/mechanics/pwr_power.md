---
icon: material/arm-flex
---

# :material-arm-flex: PWR / Power

PWR (or power) is a simple metric that the game uses to estimate how powerful a character is, and quests are marked with a recommended PWR as a suggestion.

There are a total of 9 criterias to which PWR is based on:

* Level
* Weapon Level
* Weapon Awakening Level
* Attack (Display value)
* Hp (Display value)
* Total trait levels (capped, sigil booster itself does not count)
* Masteries (total amount of MSP spent on a character)
* Overmastery (total combined rank/stars)
* Mirage Munitions

Two [tables](../../../tables/table_list.md) are used in calculations: `chara_power_adjust` and `chara_power_attenuate`.

* `chara_power_adjust` is used to multiply/adjust an input value. Key is type of input.
* `chara_power_attenuate` is used to attenuate/interpolate the adjusted value. Key is type of input.

### Level

Example input: 100

`LevelValue = <player level> * chara_power_adjust[1]` (`chara_power_adjust[1]` is 10.0)

### Weapon level value

Example input: 150

`WeaponLevelValue = <weapon level> * chara_power_adjust[2]` (`chara_power_adjust[2]` is 5.0)

### Awakening Level

Example input: 150

`AwakeningLevelValue = <weapon level> * chara_power_adjust[3]` (`chara_power_adjust[3]` is 10.0)

### Attack Value

Example input: 20511

`AttackValue = <attack value> * chara_power_adjust[4]` (`chara_power_adjust[4]` is 1.0)

Then, the value is attenuated:

```c
tempAtk = AttackValue

//Then go through each attenuate rank for atk (type 4)
while atk <= current
  value += (next rank value - prev rank value) * next attenuate value
  tempAtk -= (next rank value - prev rank value)
  
// And then last step
AttackValue += (tempAtk * next attenuate value)
```

### Hp Value

Example input: 45000

`HpValue = <hp value> * chara_power_adjust[5]` (`chara_power_adjust[5]` is 1.0)

Then, the value is attenuated:

```c
tempHp = HpValue

//Then go through each attenuate rank for hp (type 5)
while hp <= current
  value += (next rank value - prev rank value) * next attenuate value
  tempHp -= (next rank value - prev rank value)
  
// And then last step
HpValue += (tempHp * next attenuate value)
```

### Trait Levels

Example input: 405

Combined all trait levels, capped to trait's max level if overcapped. SIGIL BOOSTER DOES NOT COUNT!

`AllTraitLevelsValue = <total levels> * chara_power_adjust[6]` (`chara_power_adjust[6]` is 5.0)

### Masteries

Example input: 42189

Total amount of MSP spent in masteries.

`MspValue = <total msp> * chara_power_adjust[7]` (`chara_power_adjust[7]` is 1.0)
Adjust attack with powerAdjustValue7 (value = msp * 1.0)

```c
tempMsp = MspValue

//Then go through each attenuate rank for msp (type 7)
while msp <= current
  value += (next rank value - prev rank value) * next attenuate value
  tempMsp -= (next rank value - prev rank value)
  
// And then last step
MspValue += (tempMsp * next attenuate value)
```

### Overmasteries

Example Input: = 10 + 10 + 10 + 10

Combined rank of all overmasteries.

`OvermasteriesValue = <overmastery rank 1+2+3+4> * chara_power_adjust[8]` (`chara_power_adjust[8]` is 35.0)

### Mirage Munitions

Example input: 99

`MirageMunitionsValue = <munitionNumber> * chara_power_adjust[9]` (`chara_power_adjust[9]` is 10.0)


## Final Calculation

```c
BaseValue = chara_power_adjust[0] // (0.0)
FinalMultiplier = charaPowerAdjust[10] // (1.0)

PWR = (BaseValue 
		+ LevelValue
		+ WeaponLevelValue
		+ AwakeningLevelValue
		+ AttackValue
		+ HpValue
		+ AllTraitLevelsValue
		+ MspValue
		+ OvermasteriesValue
		+ MirageMunitionsValue) * FinalMultiplier + 0.5
	
if (PWR > 99999)
	PWR = 99999
```

## Example

### Gear

* Character: Seofon, Level 100
* Stats: 45000 HP, 20511 Atk, 99% Crit, 200 Stun
* Weapon: Sette di Spade, Level 150, 0 Mirage Munitions, 0 Awakening Level
    * Greater Aegis 25
    * Stronghold 15
    * Uplift 5
* Masteries: Maxed (weapon included)
* Overmasteries: All 4 Rank 10
* Sigils:
    * Stamina / Cascade 15
    * Combo Booster / Quick Cooldown 15
    * Critical Hit Rate / Tyranny 15
    * DMG Cap / Nimble Onslaught 15
    * DMG Cap / Potion Hoarder 15
    * DMG Cap / Tyranny 15
    * DMG Cap / Improved Dodge 15
    * Berserker Echo / Autorevive 15
    * War Elemental / Nimble Onslaught 15
    * Seven-Star Boundary / Regen 15
    * Spirit Edge's Warpath / Stun Power 15
    * Spirit Edge's Rally / Spirit Edge's Fury 15 (Awakening)

Trait Levels:
```
SKILL_166_00	Greater Aegis	       48A95B8D 25/25
SKILL_144_00	Stronghold	           74AA75D6 15/30
SKILL_072_00	Uplift	               B5FF9FD3  5/45
SKILL_006_00	Stamina	               2FC8FBFF 15/30
SKILL_070_00	Cascade	               05F2ECDC 15/20
SKILL_024_00	Combo Booster	       F17850B9 15/30
SKILL_069_00	Quick Cooldown	       318D12E9 15/45
SKILL_003_00	Critical Hit Rate	   8D78A19B 15/45
SKILL_027_00	Tyranny	               71F11A9B 30/30
SKILL_020_00	DMG Cap	               DC584F60 60/65
SKILL_106_00	Nimble Onslaught	   D2C8E10A 30/30
SKILL_073_00	Potion Hoarder	       24883AF3 15/15
SKILL_063_00	Improved Dodge	       8B3BF60C 15/15
SKILL_233_00	Berserker Echo	       EE85CD1F 15/15
SKILL_068_00	Autorevive	           95F3FA86 15/20
SKILL_170_00	Spirit Edge's Rally	   77C809F5 15/15
SKILL_146_00	War Elemental	       4C588C27 15/15
SKILL_170_03	Seven-Star Boundary	   EF05EC4D 15/15
SKILL_066_00	Regen	               6085DA25 15/45
SKILL_170_02	Spirit Edge's Warpath  7B4FC47A 15/15
SKILL_004_00	Stun Power	           CEB700EE 15/45
SKILL_170_01	Spirit Edge's Fury	   9230E3F5 15/15
```

### Calculation
Level = 100. `100 * 10` => Adjusted to **1000**

Weapon Level = 150. `150 * 5` => Adjusted to **750**

Awakening Level = 0. `0 * 10.0` = Adjusted to **0**

Attack = 20511. `20511 * 1.0` = Adjusted to **20511**. Attenuated to **3971**

Hp = 45000. `45000 * 1.0` = Adjusted to **45000**. Attenuated to **3450**

Trait Level: 405. `405 * 5` =>  Adjusted to **2025**

Masteries/MSP = 42189. `42189 * 1.0` = Adjusted to **42189**. Attenuated to **8737**

Overmasteries = 10+10+10+10. `(10+10+10+10) * 35.0` = Adjusted to **1400**.

Mirage Munitions = 0. `40 * 10.0` = Adjusted to **0**.


```
Summary:
BaseValue = 0
FinalMultiplier = 1.0

PWR = (0 
		+ 1000
		+ 750
		+ 0
		+ 3971
		+ 3450
		+ 2025
		+ 8737
		+ 1400
		+ 0) * FinalMultiplier + 0.5
	
if (PWR > 99999)
	PWR = 99999
```

PWR = **~21334**. (Numbers are floats so it will be very very slightly inaccurate for the sake of this page). 