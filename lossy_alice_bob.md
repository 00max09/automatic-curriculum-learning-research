## ALICE_AND_BOB_LEAKED_SQUARED

r_alice = 1-r_bob
r_ued = r_alice + (r_bob*alpha)^2 

tested alpha 0.9 (promising), 0.5(worse than 0.9 at the beginning then fall to 0)

## ALICE_ONLY

r_alice = 1-r_bob

r_ued = r_alice

tested (not tragic start, then fall to 0)
## ALICE_MID

r_alice = 1-r_bob

r_ued = |alpha-r_alice|

tested alpha 0.5 (very good start sudden fall, maybe good to do some pre learning)


## Usunięcie dodatkowej entropii potrzebenej w paired. 

