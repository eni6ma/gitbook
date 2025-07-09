# RWP v. RSA

RSA and Rosario-Wang both offer a proof of knowledge, but they differ significantly in their approach. RSA relies on the hardness of prime factorization, a complex task for humans, while Rosario-Wang uses secret membership in projection, a concept easier for humans to verify. The key difference lies in the underlying computational complexity. 
RSA's security hinges on mathematical difficulty, while Rosario-Wang simplifies the process by focusing on set membership, making it more accessible while achieving similar proof-of-knowledge capabilities.

RSA relies on difficult modular exponentiation and integer factorization, with the security assumption being the infeasibility of factoring large numbers. Its proof system uses a non-interactive signature where a witness is derived from prime factors or the private exponent. In contrast, Rosario-Wang uses cognitive map-like membership in discrete sets, featuring interactive rounds. Its security stems from the inability to guess

#### Similar Proof Basis of (RSA v. RWP)

In the language of modern cryptography, every *proof-of-knowledge* protocol starts with a public statement, call it **public**, and a secret datum, the **witness** $\Omega$.  These two objects live in a binary relation $\mathcal R$: whenever $(\text{public},\Omega)\in\mathcal R$, the witness “explains” why the public statement is valid.  
When we say  "the prover possesses a witness $\Omega$ such that $(\text{public},\Omega)\in\mathcal R$ ", we mean much more than the prover’s word.  The protocol they run with the verifier must let an ideal extractor, given black-box access to any convincing prover, actually pull out a concrete $\Omega$ in polynomial time.  
In other words, success in the protocol is computational evidence that the prover truly *knows* the secret, not just that the statement is true in an abstract sense.  At the same time, properly designed protocols (e.g. RSA signatures, Rosario–Wang interactive rounds) can reveal nothing about $\Omega$ itself; they only convince the verifier that some such witness exists.  
This dual guarantee, soundness “with knowledge” and zero knowledge, underpins higher-level constructions like authentication systems, anonymous credentials, and secure multiparty computation: any component that sees a valid transcript is entitled to act as though the hidden witness really exists, while remaining oblivious to its actual content.

In formal terms, a proof-of-knowledge concerns a polynomial-time decidable relation 
$\mathcal{R} \subseteq \{0,1\}^{\*} \times \{0,1\}^{\*}$

, where each pair $(x,\Omega)\in\mathcal R$ certifies that the bit-string $x$, the **public statement**, belongs to the language $L_{\mathcal R}=\{x\mid\exists\,\Omega:(x,\Omega)\in\mathcal R\}$.  The second component $\Omega$ is the **witness**, a secret that “explains” why $x$ is valid.  
Thus, when we assert "  the prover possesses a witness $\Omega$ such that $(\text{public},\Omega)\in\mathcal R$ " , we are claiming that the prover actually holds data that, together with the visible statement, satisfies the relation’s predicate.  A proper proof-of-knowledge protocol strengthens this claim: it guarantees the existence of an efficient **extractor** that can, by rewinding any prover who convinces the verifier with non-negligible probability, output a concrete $\Omega$ for which the pair lies in $\mathcal R$.  Consequently, a successful transcript is not merely evidence that the public statement is true; it is computational evidence that the prover truly *knows* the hidden witness.  Crucially, well-designed protocols achieve this while revealing nothing about $\Omega$ itself, thereby combining *soundness with knowledge* and *zero knowledge*.  This combination is foundational for higher-level tools, authentication tokens, anonymous credentials, and secure multiparty computation, because any system component that accepts a valid proof may safely behave as though the unseen witness exists, yet remains ignorant of its actual content.

Both satisfy the same ideal statement:

> \#\# *The prover possesses a witness $\Omega$ such that* $(\text{public},\Omega)\in\mathcal R$.

Yet they reach that goal by opposite means, one numeric, one geometric, offering comparable proof-of-knowledge capability while catering to different threat and usability profiles.

## Side by Side RSA v. RWP

| RSA | ROSARIO-WANG |
| :-- | :-- |
| **Hard problem securing the scheme** |  |
|  |  |
| *RSA* — Integer factorisation: recover the hidden primes $p,q$ from $n=pq$. | *Rosario-Wang* — Exponential search in a foliated manifold: guess the prover’s private hyper-plane map and symbol vector $\boldsymbol{\Omega}=(\lambda_1,\dots,\lambda_m)$ chosen from an alphabet ring $\Sigma$. |
| **Private witness** |  |
| Prime pair $(p,q)$ **or** secret exponent $d$ with $e\,d\equiv1\pmod{\lambda(n)}$; the two are equivalent knowledge. | A purely mental mnemonic: the round-indexed positions of each $\lambda_i\in\Sigma$ after a hidden morphism $H:\Sigma\!\to\!\Phi$ and XOR mask $\xi$. Nothing ever leaves human memory. |
| **Public data seen by verifier** |  |
| Modulus $n$ and public exponent $e$. | Session basis $B_i$ (how rings are shuffled) and the one-bit answers $r_i$ indicating whether the challenged leaf contains $\lambda_i$. |
| **Statement actually proved** |  |
| “I know $d$ such that $m^{ed}\equiv m\pmod n$.” Formally $R_{\mathrm{RSA}}=\{(m,\sigma):\sigma^{e}\equiv m\}$. | “For every round $i$, my symbol $\lambda_i$ lies in the current leaf $\ell_i(B_i)$.” Relation $R_{\mathrm{RW}}=\{(B,r): r_i=\chi_{\ell_i}(\lambda_i)\}$. |
| **Prover algorithm (high-level)** |  |
| Compute $\sigma = m^{\,d}\bmod n$ (one modular exponentiation). | For each round $i$: locate $\lambda_i$ in the shuffled ring, mentally XOR with $\xi$, emit bit $r_i$. No big-integer arithmetic. |
| **Verifier check** |  |
| Raise signature: $\sigma^{e}\stackrel{?}=m\pmod n$. | Verify each $r_i$ against the public leaf $\ell_i(B_i)$; accept if $\bigwedge_{i=1}^{m} r_i$ is true (accumulator $\Lambda$). |
| **Interaction style** |  |
| *Non-interactive*: one message (signature or ciphertext). | *Interactive, multi-round*: challenge–response repeated $m\approx72$ times; each round refreshes entropy, so transcripts leak negligible information. |
| **Leakage if transcript recorded** |  |
| Transcript is $\sigma$. Anyone can replay it, but cannot extract $d$ without factoring $n$. | Each $r_i$ is uniform given unknown $\xi$; mutual information $I(\lambda_i;r_i)=0$. Recording all rounds reveals no bias toward the mnemonic. |
| **Human cognitive burden** |  |
| None—the secret lives in silicon. | ≤ $7\pm2$ symbols in working memory, matching biological limits. |
| **Post-quantum outlook** |  |
| Shor’s algorithm factors large $n$ ⇒ RSA collapses. | Brute force cost ≈ $(2^{,m\log\_2 ( \Sigma ) });$ Grover only gives a square-root speed-up, so with $(m=72, \| \Sigma \| =6)$ security stays ≥ 128-bit. |

#### Mathematical snapshot of each witness

### *RSA*:


$$
\begin{aligned}
\text{Witness } \Omega_{\mathrm{RSA}} = d 
\quad \text{s.t.} \quad 
e\,\Omega_{\mathrm{RSA}} \equiv 1 \pmod{\lambda(n)},\qquad  \\
\lambda(n)={lcm}(p-1,q-1).
\end{aligned}
$$



### *Rosario-Wang*:

Let $Σ$ be the private alphabet ring and $B_i$ the public shuffle for round $i$.

$$
\begin{aligned}
ω_{\text{RW}} &= (\lambda_1,\dots,\lambda_m)\in Σ^{m},\\
r_i &= χ_{ℓ_i(B_i)}(\lambda_i)\oplus ξ_i,\quad ξ_i\stackrel{\$}{←}\{0,1\},\\
Λ &= \bigwedge_{i=1}^{m} (r_i = χ_{ℓ_i(B_i)}(\lambda_i)).
\end{aligned}
$$

If $Λ=\text{true}$ the verifier accepts; knowledge of $ω_{\text{RW}}$ is thus established without revealing any $\lambda_i$.

**Interpretation**

* In RSA the “agent” must **demonstrate a trapdoor** (modular inverse) rooted in two primes stored somewhere outside the mind.
* In Rosario-Wang the agent must **demonstrate correct spatial intuition** inside a high-entropy manifold whose coordinates exist only cognitively; every proof round merely shows that the prover always lands on the right leaf.

Both are proofs of knowledge, yet the nature of the witness differs radically:

* *RSA*: numeric secret hard for humans but easy for silicon.
* *Rosario-Wang*: geometric mnemonic easy for humans, infeasible for silicon-based brute force.



| **RSA** | **Rosario–Wang** |
| :-- | :-- |
|  |  |
| **Hardness core** |  |
| Integer factorisation: recover primes $p,q$ from $n = p q$. | Exponential search: guess the secret symbol vector $\boldsymbol{\Omega} = (\lambda_1,\dots,\lambda_m)\in\Sigma^{m}$ hidden in a foliated manifold. |
| **Private witness** $\Omega$ |  |
| Either $(p,q)$ or the inverse exponent $d$ with $e d \equiv 1 \pmod{\lambda(n)}$. | Pure mnemonic: the round-indexed positions of each $\lambda_i$ after a secret morphism $H:\Sigma\!\to\!\Phi$ and XOR mask $\boldsymbol{\xi}$. |
| **Prover’s work** |  |
| One modular exponentiation $\sigma = m^{\,d}\bmod n$. | For each round $i$: find $\lambda_i$ in the shuffled ring, compute $r_i = \chi_{\ell_i(B_i)}(\lambda_i)\oplus\xi_i$. |
| **Interaction** |  |
| *Non-interactive* (Fiat–Shamir collapses a Σ-protocol to one message). | *Interactive*, ≈ 72 challenge/response rounds; entropy refreshes every round. |
| **Leakage on transcript** |  |
| Transcript is $\sigma$; re-playable but useless without factoring $n$. | Bits $r_i$ are uniform given unknown $\xi_i$; $I\!\bigl(\lambda_i\!:\!r_i\bigr)=0$. |
| **Cognitive burden** |  |
| None for humans; the secret lives in silicon. | ≤ $7\!\pm\!2$ symbols—fits human working memory. |
| **Post-quantum fate** |  |
| Shor’s algorithm factors $n$ → scheme breaks. | Grover only halves the search: cost (               $\| \Sigma \| ^{m/2}). With ((m, \| \Sigma \| )=(72,6))$ we retain ≥ 128-bit security. |

#### 1 · Why each is a genuine proof of knowledge

* **RSA.**  A classic Σ-protocol:
*Commit* $a=m^{k}$, *challenge* $c=e$, *response* $r=k-d$.
Two accepting transcripts with the same commitment but different challenges let an extractor solve $e d \equiv 1 \pmod{\lambda(n)}$, hence recover $d$.
* **Rosario–Wang.**  In round $i$ the verifier sends a random basis $B_i$.
Two accepting transcripts with identical $B_i$ but differing masks $\xi_i$ cancel the XOR, revealing $\lambda_i$.  Rewinding over all rounds extracts $\boldsymbol{\Omega}$.  A simulator that chooses $\xi_i = r_i \oplus \chi_{\ell_i}$ yields honest-verifier zero knowledge.

Thus both relations admit Σ-protocols and satisfy completeness, special soundness, and zero-knowledge—formal proofs of knowledge.

#### 2 · Where “hardness” lives

* **RSA:** arithmetic trapdoor in $(\mathbb{Z}/n\mathbb{Z})^{\!*}$; asymptotic attack ≈ $e^{\tilde{O}\bigl((\log n)^{1/3}\bigr)}$ (number-field sieve).
* **Rosario–Wang:** no algebraic trapdoor; security is combinatorial. Brute force needs $|\Sigma|^{m}$ steps; quantum Grover ⇒ $|\Sigma|^{m/2}$.


#### 3 · Human vs. silicon ergonomics

$$
\boxed{\text{RSA: "silicon-friendly" trapdoor arithmetic, human-opaque}}
$$

$$
\boxed{\text{Rosario–Wang: "cognition-friendly" trapdoor geometry, silicon-hard}}
$$

Both satisfy the same ideal statement:

> \#\# *The prover possesses a witness $\Omega$ such that* $(\text{public},\Omega)\in\mathcal R$.

Yet they reach that goal by opposite means—one numeric, one geometric—offering comparable proof-of-knowledge capability while catering to different threat and usability profiles.

