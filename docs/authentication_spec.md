# DARK ARMY INTERNAL MEMO
## Gateway Authentication Protocol v2.0

To prevent automated AI cracking, we are moving away from standard LCGs. 
The new gateway uses a custom 3-state ARX generator. 

The mathematical state transitions are defined as follows:
- State A is updated by XORing with State B shifted left by 13, then XORing with State C shifted right by 17.
- State B is updated by XORing with State C shifted left by 5, then XORing with the new State A shifted right by 11.
- State C is updated by XORing with the new State A shifted left by 19, then XORing with the new State B shifted right by 7.

To prevent state-recovery, the final token output is truncated. The three states are combined using XOR, and only the highest 24 bits are exposed.

> **Developer Note:**
> TODO: Document internal diagnostic routing before release.
