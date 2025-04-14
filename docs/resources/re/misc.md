---
icon: material/wrench
---

# :material-wrench: Misc

* SBA Chain Chance (3 seconds) is hardcoded. Signature: `48 B8 ? ? ? ? ? ? ? ? 48 89 83 ? ? ? ? 48 C7 83 ? ? ? ? ? ? ? ? 48 8B 05`
* Chest Claim Time period (30s) - Signature: `48 B8 ? ? ? ? ? ? ? ? 48 89 87 ? ? ? ? C5 FA 10 05`
* Color Pack 10 Face Sigil render call - Signature: `49 8B 45 ? 4C 39 F0 0F 84 ? ? ? ? 4C 89 E9`

---

* `ui::component::ControllerResultReward`'s vtable @ 0xE8 increments quest repeat by 1 on close.
* `ui::fsm::condition::ResultRetryCountCheck::Execute` checks quest repeat count < 10 (hardcoded)