---
icon: material/share-variant-outline
---

# :material-share-variant: FSM (Finite State Machine)

A fair chunk of the game's logic (quests, moves & ai behavior) is scripted using FSMs - [Finite State Machines](https://en.wikipedia.org/wiki/Finite-state_machine).

You can find a fair chunk of these files in `system/fsm` files. They will **always** have the `_fsm_ingame` suffix - for some reason it is required.

!!! tip
    You can preview FSMs using [RelinkToolkit2](https://github.com/Nenkai/RelinkToolkit2).

## Layers

Sometimes FSMs are made up of smaller graphs called layers. When the FSM reaches the end of a layer, execution will go back to **the beginning of it**, not the start of the FSM. For FSM execution to fully complete, nodes that transition to other nodes usually have a transition with `FSMUnderLayerEndCondition`, which waits for the layer to be complete.

---

## File Structure

The FSMs file built in a **depth-first** manner. The game will iterate over every node in the file, link them to conditions and execution components accordingly, and then, build the final tree with the root node.

* The game iterates through all nodes.
  * `FSMNode` declares a new node on the graph. They may point to other nodes with conditions. 
    *  When `childLayerId_` is set, that means this node **points to a new layer**. The first node of that layer is always the root of that layer.
    * `tailIndexOfChildNodeGuids_` is practically the number of nodes in this layer. This is only set for root (and layer root) nodes.
  * `layerNo_` sets the current layer the nodes belong to. Note that layers may be completely empty (leftover metadata) and not necessarily used.
  * `Transition` links a node to another using `fromNodeGuid_` and `toNodeGuid_`. Note that they are in reverse - Cygames mistake. `toNodeGuid_` is the SOURCE node while `fromNodeGuid_` is the TARGET node.
    * `conditionGuids_` links to condition components, aka the specified conditions to check on for this transition to occur while `params_` are how the conditions are linked, i.e OR or AND, and their priority/order of execution. (there should always be one param between two conditions. So 3 conditions = 2 params.)
    * `isEndTransition_` refers to FSM end. It doesn't necessarily point to a node that actually exists in the file, which, doesn't matter.
    * NOTE: Purpose of transitions/branches that do not have `toNodeGuid_` is currently unclear. RelinkToolkit2 shows these as green arrows.
  * `addAllTransition` - TODO
  * `addTransition` - TODO
  * `EnableBaseTransition` - TODO
  * `EnableBaseAllTransition` - TODO
  * **Anything else is an execution or condition**, name is an fsm object engine [reflected](https://en.wikipedia.org/wiki/Reflective_programming) based on its name which internally inherits from `BehaviorTreeComponent`. A list can be found [here](https://github.com/Nenkai/GBFRDataTools/tree/master/GBFRDataTools.FSM/Components).
    * For *conditions* (which must inherit from `ConditionComponent` internally), `isReverseSuccess_` means whether if a condition fails, then it is considered a success. This is equivalent to `if (!success)`.
    * For *actions*, these will be linked up to nodes using `parentGuid_`.
* Then, the tree is built - all nodes will have children linked to. This starts from the first node in the graph, and then recursively to the bottom.



