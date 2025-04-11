# Zero-Knowledge Identity Verification

In a digital society, individuals are often required to prove attributes about their identity
(such as their age or the validity of a driving license) without necessarily revealing
more than needed.
For example, someone may need to prove they are over 18
or that they hold a valid driving license,
without disclosing their full identity.

In this project, we propose a privacy-preserving identity verification mechanism
using zero-knowledge proofs ZKPs.
Identity attributes (e.g., name, date of birth, driving license category) are committed
by a trusted authority (e.g., a government) in the form of a cryptographic hash.
These commitments are stored in a public database
such as a blockchain or an online state registry.
Later, individuals can generate ZKPs to prove specific facts about their identity
such as age or license ownership while keeping all other data private.

## Objectives
In this project, you will learn how to implement privacy-preserving identity verification
using ZKPs.
By leveraging a ZKP library, you will prove identity attributes,
such as age or license category,
without revealing any sensitive information,
using data committed in a publicly accessible database.

## Instructions
1. Understand the identity commitment scheme:

Begin by studying how identity attributes are committed using a cryptographic hash.
A trusted issuer publishes a hash of the user’s identity data of the form:

H(name || surname || date_of_birth || license_category || expiration_date || nonce).

Reflect on the implications of revealing this hash publicly:
- What are the privacy benefits of committing data this way?
- What are the risks?
- Under what conditions can this scheme be considered secure?

2. Familiarize yourself with ZKPs:

Before you begin, it is essential to understand the basics of Zero-Knowledge Proofs.
Research and read about how ZKPs work, their cryptographic foundations,
and how they are used to prove statements without revealing underlying data.

3. Select and set up the ZKP library:

Install and configure the ZKP library you will be using.
Familiarize yourself with the toolchain for compiling circuits, generating proofs,
and verifying them.

4. Design and implement the proof system:

Create a ZKP circuit that verifies either an age condition or a license category,
based on committed identity data.
Your circuit must take private inputs (e.g., birthdate, license type, nonce)
and public inputs (e.g., name, surname, commitment, current date),
recompute the hash, and verify the requested condition.
Then, implement the end-to-end proof generation on the user side
and verification on the verifier side.

5. Evaluate and reflect:

- How strong is the privacy guarantee provided by your ZKP-based system?
- What are the limitations of using hash-based commitments for identity verification?
- Could this system realistically scale to national or large-scale identity infrastructures?
- Are there alternative cryptographic approaches that could be better suited for this use case?

## Participants
- Trusted issuer (e.g., government) publishes a hash of the user’s identity attributes
in a publicly available database.
- User proves ownership of an identity and certain attributes without revealing them.
- Verifier (e.g., controller, website) verifies the ZK proof using public data (name, surname, commitment) and accepts or rejects based on the result.

## Constraints/Challenges
- The full identity must remain confidential.
- The proof must ensure:
  - Correct recomputation of the commitment hash.
  - Correct evaluation of predicates (e.g., age > 18, license type = A).
- The verifier must be able to check the proof using only public data.
- The expiration date could be used to invalidate outdated credentials.
