# ProVerif-Analyse-of-FRBAKA

The recent manuscript revision on 2026-05 does not affect the ProVerif verification code.

The revision only changes the concrete construction of the masked value \(pb_i\), replacing the reversible XOR form \(pb_i = r^t_v \oplus r^t_i\) with a hash-based form bound to a relay verification key \(rk_i\). The message flow, communication rounds, authentication events, and session-key derivation are unchanged.

ProVerif verifies secrecy and authentication in the symbolic Dolev--Yao model, where both the XOR mask and the hash mask are abstracted as non-invertible one-way constructors and treated identically. The attack fixed in this revision exploits the algebraic invertibility of XOR in the computational model (\(r^t_v = pb_m \oplus r^t_m\)), which lies outside the symbolic abstraction. Since the two constructions are equivalent at the symbolic level, the verification results (session-key secrecy and mutual authentication) remain unchanged. Thus, the earlier modification time of the code does not indicate any inconsistency with the manuscript.

