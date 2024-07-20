---
icon: material/motion-play
---

# :material-motion-play: Motions (Seq)

Motions can be broken down into a variety of BXM files located in the `{model_prefix}/{model_id}` folders.

```
{model_id}_{mot_number}_{variant_number}_seq_edit_{type}.bxm
```

!!! example "File Example"
    `pl2000_0015_0_seq_edit_effect.bxm`

* `mot_number` - This will match the number of the motion assigned in the [action file](../player/action_parameter.md)
* `variant_number` - This will be "versions" of the attack that can be utilized depending on the character's progress in their specific gimmick.
An example of this would be Ghandagoza's Raging fist. Depending on the amount of Eternal Rage he has, it will go from 0 (0 stacks) to 4 (10 stacks)
This allows the motion to be used multiple times, but have different `AttackRate`, `BreakRate`, `SpArtsRate` values, as well as other effects or things affected by BXMs
* `type`
    * `effect` - Controls visual effects
    * `facialmotion` - Controls facial animations
    * `flags` - Controls flags needed to be called during the animation (see below for flag values)
    * `ik` - Controls inverse kinematics
    * `mesh` - Unknown
    * `attack` - Controls hitboxes that the animation will spawn, note that these hitboxes will not hit automatically, the amount of times the character can hit and when is controlled by flags
    * `se` - Controls sound effects
    * `camera` - Controls camera movements
    * `speed` - Controls the speed of the ANIMATION. this does not affect VFX, but does affect hitboxes and flags. i am not aware if it affects camera or sound effects
    * `cloth` - ?

---

## Flags File

### `Flag0` Values

??? abstract "Flags"

    | Bit/Value | Name |
    |-----------|------|
    | `0 (1)`     | Allows walking to cancel the current action
    | `1 (2)`     | Allows chaining to the Next Action (includes starting an SBA and chaining SBAs)
    | `2 (4)`     | Allows the player to dodge
    | `3 (8)`     | Allows Jumping to cancel the current Action
    | `4 (16)`    | Unknown
    | `5 (32)`    | Allows the player to hit an additional time, so long as a hitbox is activated after the call. (this should be called for each hit, including the first). **`Config` is set to 1.** An action seems to always be allowed 1 hit per session, so long as no additional hit flags are called. if the action is performed twice in a session, the second+ will not hit.
    | `6 (64)`    | Unknown
    | `7 (128)`   | Unknown
    | `8 (256)`   | Unknown
    | `9 (512)`   | Unknown
    | `10 (1024)`   | Unknown
    | `11 (2048)`   | Unknown
    | `12 (4096)`   | Unknown
    | `13 (8192)`   | Unknown
    | `14 (16324)`   | Unknown
    | `15 (32768)`   | Unknown
    | `16 (65536)`   | Unknown
    | `17 (131072)`  | Allows the player to activate Skills
    | `18 (262144)`   | Perfect Window (does not actually perform the attack, just allows the input)
    | `19 (524288)`   | Perfect Attack (does not allow input, only calls the action). **`Config` is set to 1.**
    | `20 (1048576)`   | Unknown
    | `21 (2097152)`   | Unknown
    | `22 (4194304)`   | Unholster/equip weapon. **`Config` is set to 1**.
    | `23 (8388608)`   | Unknown
    | `24 (16777216)`  | Unknown
    | `25 (33554432)`  | Unknown
    | `26 (67108864)`  | Unknown
    | `27 (134217728)`  | Unknown
    | `28 (268435456)`  | Unknown
    | `29 (536870912)`  | Unknown
    | `30 (1073741824)` | Closes the window on follow-up attacks. **`Config` is set to 1**, Generally set through `Flag1`, functions fine in `Flag0`

### `Flag1` Values

??? abstract "Flags"

    | Bit/Value | Name |
    |-----------|------|
    | `0 (1)`     | Unknown.
    | `1 (2)`     | Unknown.
    | `2 (4)`     | Cast Buff. **Config is set to 1**.
    | `3 (8)`     | Unknown.
    | `4 (16)`    | Calls the FSM associated with the move. **Config is set to 1**.
    | `5 (32)`    | Unknown.
    | `6 (64)`    | Unknown.
    | `7 (128)`   | Consume Skill Charge. **Config is set to 1**.
    | `8 (256)`   | Unknown.
    | `9 (512)`   | Unknown.
    | `10 (1024)`   | Unknown.
    | `11 (2048)`   | Unknown.
    | `12 (4096)`   | Unknown.
    | `13 (8192)`   | Unknown.
    | `14 (16324)`   | Unknown.
    | `15 (32768)`   | Unknown.
    | `16 (65536)`   | Unknown.
    | `17 (131072)`  | Unknown.
    | `18 (262144)`   | Unknown.
    | `19 (524288)`   | Unknown.
    | `20 (1048576)`   | Unknown.
    | `21 (2097152)`   | Unknown.
    | `22 (4194304)`   | Allows blocking.
    | `23 (8388608)`   | Unknown.
    | `24 (16777216)`  | Unknown.
    | `25 (33554432)`  | Unknown.
    | `26 (67108864)`  | Unknown.
    | `27 (134217728)`  | Unknown.
    | `28 (268435456)`  | Unknown.
    | `29 (536870912)`  | Unknown.
    | `30 (1073741824)` | Unknown.

---

*Credits: MidnightAugur*