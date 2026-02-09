---
icon: material/controller
---

# :material-controller: Control Types

Used by:

* :material-account-cog: Character Action Parameters (`system/player/data/{id}/{id}_action`)
    * `ActionInfo` -> `controlTypeHash_`

## General Control Types

### `Control Type 0`

Default Control Type. Plays motion called, no modifiers. Potentially named ExActAtkSingle. Hash Id: F39CFDF5

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Plays when player action is called
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 1`

Plays two motions in order. Potentially named ExActAtkSingleConnection. Hash Id: 4582EE4A

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | First Motion
    | `2`     | Second Motion
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Unknown
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 2`

Unknown. Potentially named ExActAtkCharge. Hash Id: 6C507ED8

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 3`

Stationary, 2 (default) or multi stage charging action. Potentially named ExActAtkChargeSimple. Hash Id: DF037954

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Plays when player action is started, if player releases button, is canceled early. this motion is not included in the charge time
    | `2`     | Plays while button is being held down while charging
    | `3`     | Plays while button is being held down when done charging
    | `4`     | Plays when charging action is completed (Once) before looping motionId03
    | `5`     | Uncharged/Tap, Plays when button is released
    | `6`     | Charged, Plays when button is released
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Time to complete motionId02
    | `2`     | Minimum time, or bool to choose if motionId04 should be played
    | `3`     | Bool for secondary action to call on release instead of motionId05/06
    | `4`     | Action to call when actionFreeWork03 is set to 1 on release whether charged or uncharged if actionFreeWork18 is disabled, and charged if actionFreeWork18 is enabled.
    | `5`     | Unknown
    | `6`     | Unknown
    | `7`     | Bool if a multiple stage charge should be happening. Required for actionFreeWork12 to work.
    | `8`     | Unknown
    | `9`     | Unknown
    | `10`    | Bool to require motionId01 to complete before allowing the release action to play
    | `11`    | Unknown
    | `12`    | Number of Possible charges. Adds 2 to motionId02 and motionId04 once for each loop. ex. 3401 and 3402 go to 3403 and 3404 for stage 2. Release of a multi-stage charge will call a variant number equal to the stage number, starting at 0 for uncharged.
    | `13`    | Unknown
    | `14`    | Unknown
    | `15`    | Unknown
    | `16`    | Unknown
    | `17`    | Action to call when actionFreeWork18 is set to 1 on an uncharged release
    | `18`    | Bool for secondary action to call on uncharged release instead of motionId05

### `Control Type 4`

Unknown. Potentially named ExActAtkRapid. Hash Id: AB6F341B

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 5`

Launch attack. Plays a single motion. Difference from standard single motion controlType (Control Type 0) is that this sets the player as non-grounded, and will cause the player to have a fall reaction after landing. Potentially named ExActAtkUp. Hash Id: 353FD27E

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Plays when action is called
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 6`

Gapcloser. Plays 3 motions in order, adding speed to saveMotId02 for a duration or until within a distance from the opponent. Potentially named ExActAtkRush. Hash Id: 44DFF94D

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Startup Motion
    | `2`     | Lunge/Gapclosing Motion
    | `3`     | Finisher Motion
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Bool to enable speed additions to motionId02
    | `2`     | Speed to travel at during motionId02
    | `3`     | Maximum duration of MotionId02
    | `4`     | Unknown
    | `5`     | Distance from enemy to cancel MotionId02
    | `6`     | Not Seen Used
    | `7`     | Unknown
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 7`

Action that checks for ground contact over the course of 3 motions playing a finisher when ground contact is made. Potentially named ExActAtkFall. Hash Id: 4ABCF8AE

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Startup Motion
    | `2`     | Falling Motion
    | `3`     | Ground Contact Motion
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Bool to complete motionId01 before checking for ground contact
    | `2`     | Not Seen Used
    | `3`     | Bool to enable variable distances for ground checks through actionFreeWork04
    | `4`     | Distance from Ground to begin MotionId03
    | `5`     | Unknown
    | `6`     | Not Seen Used
    | `7`     | Unknown, likely a bool for actionFreeWork08_
    | `8`     | Unknown
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 8`

Chargable air attack. Charged release performs saveMotId03-05 with variantNumber 1. Potentially named ExActAtkFallCharge. Hash Id: 643F288A

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Startup
    | `2`     | Charge
    | `3`     | Release startup
    | `4`     | Release falling
    | `5`     | Release ground contact
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Charge time in seconds
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 9`

Mobile charge attack. Adds 10 to the release motion Id for each charge stage. ie. 31aa -> 31ba Potentially named ExActAtkChargeMove. Hash Id: 85B80171

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Startup
    | `2`     | Charge Motion
    | `3`     | Uncharged Release Motion
    | `4`     | Walk Animation 1
    | `5`     | Walk Animation 2
    | `6`     | Walk Animation 3
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Duration of Charge time for each stage
    | `2`     | Number of Charge Stages
    | `3`     | Unknown
    | `4`     | Unknown
    | `5`     | Unknown
    | `6`     | Unknown
    | `7`     | Unknown
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 10`

Air attack normal control type. Cancels the action early on contact with the ground into a fall stagger. Potentially named ExActAtkSingleAir. Hash Id: BC35AD81

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Motion
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Unknown
    | `2`     | Unknown
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 11`

In air Charge action. Not tested on other characters, but is hard coded to call specific animations on Percival. Potentially named ExActAtkSingleAirCharge. Hash Id: 8A821683

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Charge start
    | `2`     | Unknown (likely charge)
    | `3`     | Unknown (likely uncharged release)
    | `4`     | Unknown (likely charged release)
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Likely Charge time
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 12`

Unknown. Potentially named ExActCountLoop. Hash Id: 40DD4CF1

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 13`

Unknown. Potentially named ExActTimeLoop. Hash Id: 024A7E51

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 14`

Hold action. Plays a startup animation, then plays a loop animation for a maximum duration or as long as the player holds it for. Plays a finisher animation once complete. Potentially named ExActHoldLoop. Hash Id: BCB2951A

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Startup
    | `2`     | Hold/Loop
    | `3`     | Release/End
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Duration in seconds
    | `2`     | Bool to enable the action to update hold duration UI to properly track the amount of time left in the hold.
    | `3`     | Bool to enable actionFreeWork04
    | `4`     | Overrides the total duration with number of loops of motionId02
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 15`

Control Type to choose from a set of actions based on character system values. Likely requires setup in the exe to function correct on each character. Potentially named ExActUseStackBranch. Hash Id: D6AD09A0

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Placeholder motion, does not play
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Number of possibilities
    | `2`     | Action 1
    | `3`     | Action 2
    | `4`     | Action 3
    | `5`     | Action 4
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 16`

Block. Potentially named ExActGuard. Hash Id: 977B3D2F

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Motion 1
    | `2`     | Motion 2
    | `3`     | Motion 3
    | `4`     | Motion 4
    | `5`     | Motion 5
    | `6`     | Motion 6
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 17`

Parry. Plays a startup motion, idle motion, and a completed parry motion or failed parry motion. Potentially named ExActCounter. Hash Id: 68A701F1

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Parry Startup
    | `2`     | Parry Idle
    | `3`     | Completed Parry
    | `4`     | Failed parry
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Length to Hold motionId02
    | `2`     | bool on whether to activate ActionFreeWork03
    | `3`     | ActionId to transfer to in the case of a successful parry
    | `4`     | Distance for parry gapclosing to stop at from the opponent (gapclosing requires flag1:0 to be active)
    | `5`     | Not Seen Used
    | `6`     | Unknown
    | `7`     | bool on whether to activate ActionFreeWork08
    | `8`     | ActionId to transfer to in the case of a failed parry
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 18`

Unknown. Potentially named ???. Hash Id: 9FC0D703

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 19`

Unknown. Potentially named ???. Hash Id: FF4986F0

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 20`

Unknown. Potentially named ExActAtkComboHoldCharge. Hash Id: 2D277B17

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 21`

Unknown. Potentially named ???. Hash Id: 61FF8ED8

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 22`

Unknown. Potentially named ???. Hash Id: E766D1CA

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 23`

Unknown. Potentially named ???. Hash Id: C581097E

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 24`

Unknown. Potentially named ExActChargeMagic. Hash Id: 70B0D7BC

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 25`

Control Type for multistage charge attack, using the aiming system used by Io's stargaze, which handles ONLY charging, and transitions to other actions based off of which stage was reached. Charge time for each stage can be set individually. Potentially named ExCastSpell. Hash Id: 72E1B055

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Action Startup
    | `2`     | Stage 1 Charging
    | `3`     | Stage 1 Complete
    | `4`     | Stage 2 Charging
    | `5`     | Stage 2 Complete
    | `6`     | Stage 3 Charging
    | `7`     | Stage 3 Complete
    | `8`     | Stage 4 Charging
    | `9`     | Stage 4 Complete
    | `10`    | Stage 4 Complete Hold

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Highest stage reachable. NOTE: tested using stargaze. lowering number to 2 from 4 allowed the action to reach Stage 3 complete, but still called Stage 2 complete release action when released.
    | `2`     | Charge Time to reach Stage 1 Complete
    | `3`     | Charge Time to reach Stage 2 Complete
    | `4`     | Charge Time to reach Stage 3 Complete
    | `5`     | Charge Time to reach Stage 4 Complete
    | `6`     | Uncharged Release Action
    | `7`     | Stage 1 Complete Release Action
    | `8`     | Stage 2 Complete Release Action
    | `9`     | Stage 3 Complete Release Action
    | `10`    | Stage 4 Complete Release Action
    | `11`    | Unknown, setting to positive value breaks the action.
    | `12`    | Unknown
    | `13`    | If Set to 1, disables auto targetting
    | `14`    | Default Aim Circle size
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 26`

Unknown. Potentially named ???. Hash Id: 06A5C0D6

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 27`

Unknown. Potentially named ExActAbilityBuffer. Hash Id: 39B891B6

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 28`

Unknown. Potentially named ???. Hash Id: 90F79D40

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 29`

Unknown. Potentially named ExActAbilityHealArea. Hash Id: D88ADFF1

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 30`

Unknown. Potentially named ???. Hash Id: 2B5B1FFA

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 31`

Unknown. Potentially named ???. Hash Id: 28FF53ED

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 32`

Unknown. Potentially named ???. Hash Id: 0C89C1BD

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 33`

Unknown. Potentially named ???. Hash Id: 02B1E0C0

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 34`

Unknown. Potentially named ???. Hash Id: EEE1E975

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 35`

Unknown. Potentially named ???. Hash Id: 81EEC3A4

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 36`

Unknown. Potentially named ???. Hash Id: 2FA01F95

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 37`

Unknown. Potentially named ExActWarp. Hash Id: ABCBB5FF

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 38`

Unknown. Potentially named ExActAtkFall. Hash Id: 8B3E61E4

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 39`

Unknown. Potentially named ExActStick5Way. Hash Id: 2D0AD1CA

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 40`

Unknown. Potentially named ExActAtkSingle. Hash Id: 89551EA9

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 41`

Unknown. Potentially named ExActAtkSingle. Hash Id: E8E3062A

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 42`

Unknown. Potentially named ExActAtkSingle. Hash Id: 1CDB3304

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 43`

Unknown. Potentially named ExActAtkSingle. Hash Id: E103B6D1

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 44`

Unknown. Potentially named ExActAtkFall. Hash Id: 250822E7

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 45`

Unknown. Potentially named ???. Hash Id: 14D16F20

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 46`

Unknown. Potentially named ???. Hash Id: FCF2E873

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 47`

Unknown. Potentially named ???. Hash Id: 012A6DA6

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 48`

Unknown. Potentially named ???. Hash Id: D93A4BED

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 49`

Unknown. Potentially named ExActAtkSingle. Hash Id: 92FB916F

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 50`

Unknown. Potentially named ???. Hash Id: 21F24002

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 51`

Unknown. Potentially named ExActAtkRushBlendAnim. Hash Id: BB4C142F

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type -1`

Unknown. Potentially named ???. Hash Id: 8149886E

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

## Character Unique Control Types

### `Control Type 52 - [Np0000]`

Unknown. Potentially named ???. Hash Id: 70515C84

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 53 - [Np0000]`

Unknown. Potentially named ???. Hash Id: 311A2112

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl0300]`

Unknown. Potentially named ???. Hash Id: 1AA997BF

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 53 - [Pl0300]`

Unknown. Potentially named ???. Hash Id: 8A5E6986

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl0400]`

Unknown. Potentially named ???. Hash Id: A26FA186

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl0500]`

Unknown. Potentially named ???. Hash Id: 41CDD741

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 53 - [Pl0500]`

Unknown. Potentially named ???. Hash Id: D188F8A5

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 54 - [Pl0500]`

Unknown. Potentially named ???. Hash Id: 8A5E6986

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 55 - [Pl0500]`

Unknown. Potentially named ???. Hash Id: 653F2C1E

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl0700]`

Unknown. Potentially named ???. Hash Id: 9DCCB9D9

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl0800]`

Unknown. Potentially named ???. Hash Id: 80DEECB3

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl1000]`

Unknown. Potentially named ???. Hash Id: E76CF662

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl1100]`

Unknown. Potentially named ???. Hash Id: E7A6C785

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl1200]`

Unknown. Potentially named ???. Hash Id: 9D2009D2

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl1300]`

Unknown. Potentially named ???. Hash Id: 0DF28A72

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl1400]`

Unknown. Potentially named ???. Hash Id: E414D859

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 53 - [Pl1400]`

Unknown. Potentially named ???. Hash Id: 1CACF3D2

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl1600]`

Unknown. Potentially named ???. Hash Id: ECAD3459

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 53 - [Pl1600]`

Unknown. Potentially named ???. Hash Id: C1844E56

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 54 - [Pl1600]`

Unknown. Potentially named ???. Hash Id: E5C1591A

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 55 - [Pl1600]`

Unknown. Potentially named ???. Hash Id: E6CF4647

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 56 - [Pl1600]`

Unknown. Potentially named ???. Hash Id: 7061384B

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 57 - [Pl1600]`

Control action for a multi animation lunge. Specific to Zeta. Plays all actions in order. Has significantly more forward momentum than in motions alone. Potentially named ???. Hash Id: 957D988C

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Startup
    | `2`     | Second Motion
    | `3`     | Third Motion
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Unknown
    | `2`     | Unknown
    | `3`     | Unknown
    | `4`     | Unknown
    | `5`     | Unknown
    | `6`     | Unknown
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl1900]`

Unknown. Potentially named ???. Hash Id: 1631D5DA

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl2100]`

Unknown. Potentially named ???. Hash Id: 1D966CE1

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 53 - [Pl2100]`

Unknown. Potentially named ???. Hash Id: 3E72D93F

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 54 - [Pl2100]`

Unknown. Potentially named ???. Hash Id: 0DF28A72

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 55 - [Pl2100]`

Unknown. Potentially named ???. Hash Id: DC174DD8

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 56 - [Pl2100]`

Unknown. Potentially named ???. Hash Id: ED671C81

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 52 - [Pl2200]`

Unknown. Potentially named ???. Hash Id: 6DC82AD5

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used

### `Control Type 53 - [Pl2200]`

Unknown. Potentially named ???. Hash Id: B6F3299A

??? abstract "saveMotId"

    | saveMotIdNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used

??? abstract "actionFreeWork"

    | actionFreeworkNumber | Description |
    |-----------|------|
    | `1`     | Not Seen Used
    | `2`     | Not Seen Used
    | `3`     | Not Seen Used
    | `4`     | Not Seen Used
    | `5`     | Not Seen Used
    | `6`     | Not Seen Used
    | `7`     | Not Seen Used
    | `8`     | Not Seen Used
    | `9`     | Not Seen Used
    | `10`    | Not Seen Used
    | `11`    | Not Seen Used
    | `12`    | Not Seen Used
    | `13`    | Not Seen Used
    | `14`    | Not Seen Used
    | `15`    | Not Seen Used
    | `16`    | Not Seen Used
    | `17`    | Not Seen Used
    | `18`    | Not Seen Used
