---
icon: material/network
---

# :material-network: Networking

## Encryption

Packets are encrypted before being passed to Steam's [ISteamNetworkingSockets](https://partner.steamgames.com/doc/api/ISteamnetworkingSockets)

OpenSSL is used, with EVP_CIPHER = EVP_chacha20.

Relevant functions:

* `EVP_EncryptInit`/ `EVP_EncryptUpdate`/`EVP_EncryptFinal`
* `EVP_DecryptInit`/ `EVP_DecryptUpdate`/`EVP_DecryptFinal`


### Keys
Key (32 bytes):
```
0F 8B 00 17 F6 19 90 48 9D 96 90 61 75 1B 18 58
D0 02 27 F1 B2 2C 25 A8 5D 6E 42 DA 52 65 AF B0
```

IV (12 bytes):
```
4E 15 6B 43 8F B4 88 F2 D6 71 BC A3
```

### Useful Signatures

* SteamSockets::EncryptAndSendMessage: `55 41 57 41 56 41 55 41 54 56 57 53 48 83 EC ? 48 8D 6C 24 ? 48 C7 45 ? ? ? ? ? 45 89 CE 4C 89 C6 41 89 D7 48 89 CF`
* ProcessIncomingPackets: `55 41 57 41 56 41 55 41 54 56 57 53 48 81 EC ? ? ? ? 48 8D AC 24 ? ? ? ? C5 F8 29 BD ? ? ? ? C5 F8 29 B5 ? ? ? ? 48 83 E4 ? 48 89 E3 48 89 AB ? ? ? ? 48 C7 85 ? ? ? ? ? ? ? ? 48 89 C8`
* ReadPacketMaybe: `55 41 57 41 56 41 54 56 57 53 48 83 EC ? 48 8D 6C 24 ? C5 F8 29 75 ? 48 C7 45 ? ? ? ? ? 48 89 D6 48 89 CB`
* EncryptInit: `B8 ? ? ? ? E8 ? ? ? ? 48 2B E0 48 8B 44 24 ? C7 44 24 ? ? ? ? ? 48 89 44 24 ? E8 ? ? ? ? 48 83 C4 ? C3 CC CC CC CC CC CC CC B8`
* DecryptInit: `B8 ? ? ? ? E8 ? ? ? ? 48 2B E0 48 8B 44 24 ? C7 44 24 ? ? ? ? ? 48 89 44 24 ? E8 ? ? ? ? 48 83 C4 ? C3 CC CC CC CC CC CC CC 48 89 74 24`