---
icon: material/api
---

# API

The game reaches to some very basic API when booting up the game.

---

## HTTP Client Setup

Setup through [`ISteamHTTP::CreateHTTPRequest`](https://partner.steamgames.com/doc/api/ISteamHTTP#CreateHTTPRequest)

### Base URL

```
https://                             # Protocol
gameapi-relink.granbluefantasy.jp/v1 # Domain
api                                  # Type
sys/get_terms                        # Endpoint
```

Example: 
* `https://gameapi-relink.granbluefantasy.jp/v1/api/index.php/sys/get_terms`
* `https://beta-gameapi-relink-er.granbluefantasy.jp/sys/get_terms`

---

### Request Headers

Setup through [`ISteamHTTP::SetHTTPRequestHeaderValue`](https://partner.steamgames.com/doc/api/ISteamHTTP#SetHTTPRequestHeaderValue)

??? abstract "`App-Info` (Mandatory)"

    `{}/{}.{}.{} ({}) language/{} region/{} platform/{}"`

    * `{1}` - Game
        * Always `relink`
    * `{2/3/4}` - Version
        * Version from [User Attributes](user_attributes.md), so `major.minor.patch`
    * `{5}` - Platform String
        * `STEAM`
        * `PLAYSTATION_4`
        * `PLAYSTATION_5`
    * `{6}` - Language Value
        * `1` = en
    * `{7}` - Region Value
    * `{8}` - Platform Value
        * 1 = PS4
        * 2 = PS5
        * 3 = STEAM

    !!! example
        * `relink/1.1.1 (STEAM) language/1 region/0 platform/3"`
        * `relink-cbt/2.0.0 (STEAM) language/1 region/0 platform/3 product_type/4`

??? abstract "`Signature` (Mandatory)"

    Key: `9xcleSD8efksogsz` (Steam), `id83dfsSlvg2Lo` (PS4)

    input: Current timestamp ms i.e 1711640120000 to string

    Signature = `Base64(input + ";" + ToString(HMACSHA256(input, key)))`

---

### Errors

Signature lasts for one minute or so, otherwise error (403):

```json
[[1], [4]]
```

---

## Endpoints

### [POST] `sys/get_terms`

When correct:
```json
[[0], [0,1,1]]
```

(ER)
```json
{
  "meta": {
    "error_code": 0
  },
  "common": [],
  "data": {
    "pp_version": 1,
    "playlog": 1,
    "sc": 0
  },
  "responseCode": 0
}
```

---

### [POST] `sys/get_news`

!!! example "Sample Result (json)"
    ```json
    [[0],[0,7,[[7,"This Just In!","Ver. 1.1.0 is now available!\nThis patch features a new quest addition, bug fixes, and other updates.","cmn_imgnews_0110_00",2,"https:\/\/relink.granbluefantasy.jp\/en\/news\/detail?id=uudl9p4so98",1],[6,"Ready for The Final Vision?","O \"proud\" skyfarers, victors of the highest order, Supreme Primarch Sandalphon\nhas a request for you. Join him in a battle against the ultimate foe, Lucilius!","cmn_imgnews_0110_03",2,"https:\/\/relink.granbluefantasy.jp\/en\/news\/detail?id=uudl9p4so98",1],[5,"New Emote Set: Let's Chat!","Come on, it's time to express yourself!\nLiven up the party with 3 new unique emotes that all characters can use!","cmn_imgnews_0110_01",2,"https:\/\/store.steampowered.com\/app\/2782160\/GRANBLUE_FANTASY_Relink\/",1],[4,"Item Packs On Sale Now!","Gear up for your adventure in Zegagrande with helpful, powerful sigils!\nThese packs also come with resources for enhancing characters and gear!\nSo get stronger and crush your foes!","cmn_imgnews_0110_02",2,"https:\/\/store.steampowered.com\/dlc\/881020\/GRANBLUE_FANTASY_Relink\/",1],[3,"Upgrade Pack On Sale Now!","Get all the goodies of the Special Edition with this upgrade pack!\nNow's the chance to pick up even more Relink goodness!\n*This product is intended for those who have purchased the digital Standard Edition.","cmn_imgnews_0110_04",2,"https:\/\/store.steampowered.com\/app\/2799850\/GRANBLUE_FANTASY_Relink\/",0],[2,"Color Packs On Sale Now!","Get more character colors with three additional color packs!\n*Color packs 1, 2 and 3 can be purchased individually or as a set of three.\n*The three-pack set is also included in the Deluxe Edition, Collector's Edition, and Digital Deluxe Edition.\n*The Special Edition only includes color packs 2 and 3.","cmn_imgnews_0110_05",2,"https:\/\/store.steampowered.com\/dlc\/881020\/GRANBLUE_FANTASY_Relink\/",0],[1,"Official Site Information","Check the official site for the latest information on Granblue Fantasy: Relink!","cmn_imgnews_0110_00\t",2,"https:\/\/relink.granbluefantasy.jp\/en\/",0]]]]
    ```

### [POST] `sys/user_auth` (ER)

`IClientUser::GetAuthTicketForWebApi( "server_auth_key_001", )`

TODO (`https://beta-gameapi-relink-er.granbluefantasy.jp/sys/user_auth`)

```json
{
  "meta": {
    "error_code": 0
  },
  "common": [],
  "data": {
    "auth_token": "634393291.c37b5854c94e4a3b70b8b9e3c52ebccd",
    "ws_url": "wss://beta-ws-relink-er.granbluefantasy.jp",
    "ws_api_key": "0enY0oJXcR9HsCIukiIrH1e2z0pFXwDa1ZNsRDtI"
  },
  "responseCode": 0
}
```

### [POST] `activity/get_invite_list` (ER)

TODO (`https://beta-gameapi-relink-er.granbluefantasy.jp/activity/get_invite_list`)

```json
{
  "meta": {
    "error_code": 0
  },
  "common": [],
  "data": {
    "invite_list": []
  },
  "responseCode": 0
}
```

### [POST] `activity/get_presence_list` (ER)

TODO (`https://beta-gameapi-relink-er.granbluefantasy.jp/activity/get_presence_list`)

```json
{
  "meta": {
    "error_code": 0
  },
  "common": [],
  "data": {
    "platform_friend_presence_list": [],
    "entity_id_presence_list": []
  },
  "responseCode": 0
}
```

---

## Playlog Endpoints

Playlog is used for quest reports/telemetry. 

It is fired on:

* Quest clear (after the results screen)
* Quest abandon (immediately on abandon)

Url: 
* `https://main-playlog-relink.granbluefantasy.jp/playlog/main`
* `https://playlog-relink-er.granbluefantasy.jp/playlog/beta`

### [POST]

[:material-code-json: Sample Request Data](playlog_request.json)

!!! note
    Steam ID is hashed, it is not possible to refer back to the original steam profile that sent the result. Refer to generation below.

    Pseudo-code of uid generation:

    ```csharp
    string key = "kdu7JfwdKDu3";
    string str = "STEAM:" + id; // id is SteamID64
    for (int i = 0; i < 17; i++)
       str = HMACSHA256ToStr(str, key); // HMACSHA256 str + convert to hex string (lowercase)
    ```

(ER)

```json
{
  "Encrypted": false,
  "RecordId": "Bmm2/kfx0ccS+SaCyJ6vawHFQKh7zsB4oNf8XlXi/l+N4Tazxjx6ymfLeJIPjHCP8urJUDLaShS8ArRzT/C10UTMtAi4COSygfBqwnY6zvXOl9kRv9lEZiJYs8d3EJVJ8OsV0gbtfS2o0neOGwifpZYrO83U2dT7v88A/UExW9r9QL9SRkUusB8vL17g1xGoT/rahRfK6UWszOuVSFLIK5OSitW3I7tP"
}
```

## Closed Beta Config

Url: `conf-f3btg-relink.granbluefantasy.jp`
Endpoint: `data/config/{hash}.json`

!!! note "Hash generation (C#)"

    ```csharp
    string input = $"{"config-relink"}-{"cbt"}-{"m"}";
    string key = "fksheryrms";
    byte[] hash = HMACSHA256.HashData(Encoding.ASCII.GetBytes(key), Encoding.ASCII.GetBytes(input));
    Console.WriteLine(Convert.ToHexStringLower(hash));
    ```

!!! example

    ```json
    {
        "PlayfabTitleId": "1AC1AD",
        "PlaylogUrl": "https://playlog-relink-er.granbluefantasy.jp/playlog/beta",
        "NetworkStatsUrl": "https://playlog-relink-er.granbluefantasy.jp/playlog/network-stats-beta",
        "GameapiUrl": "https://beta-gameapi-relink-er.granbluefantasy.jp",
        "WebsocketUrl": "wss://beta-ws-relink-er.granbluefantasy.jp/",
        "CidpUrl": "x",
        "PrivacyPolicyUrl": "x",
        "SurveyUrl": "https://forms.cygames.com/GBFRER/E-ITVCoAQoQgSkU-AKXO798Q",
        "ActivateDateSec": 1773385200,
        "DeactivateDateSec": 1773644399,
        "SearchWaitTimeMinSec": 0,
        "SearchWaitTimeMaxSec": 0,
        "RemainingMaxCounter": 0
    }
    ```