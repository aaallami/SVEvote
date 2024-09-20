# SVEvote: Secure and Verifiable Voting System
This repository contains a basic implementation of a secure voting system using secret sharing techniques. The code is written using the MP-SPDZ library, which provides secure multi-party computation (MPC) functionality.
## Overview
The system aims to ensure the privacy of voter choices while enabling a verifiable and accurate count of votes. The core functionality includes:

1. Registration: Voters register and receive unique IDs (RID).
2. Voting: Voters submit their encrypted votes (cID) using a homomorphic encryption scheme.
3. Verification: A verifiable counting process ensures the integrity of the votes and the accuracy of the final result.
4. Aggregation: Votes are securely aggregated, and the final count is revealed.
## Implementation Details
### The code utilizes the following concepts:
- Secret Sharing: Voter IDs (RID) and votes (cID) are split into multiple shares. Each share is distributed to a different party, ensuring that no single party can access the complete information.
- Homomorphic Encryption/OT: Encryption allows for operations on encrypted data without decryption, preserving the privacy of votes.
- Verifiable Counting: The vcst function incorporates verification steps to ensure that the counting process is accurate and cannot be tampered with.
- Multi-threading: The @for_range_opt_multithread decorator enables parallel execution of voter registration and voting steps for improved performance.
Code Structure
- reg(ID): Generates a unique voter ID (RID) and a random secret key (k) for each voter.
- voter_validate(RID, cID, k): Verifies the validity of a vote based on the voter's secret key (k).
- vcst(RID, cID, k, m): Performs verifiable counting of votes, ensuring that the count cannot be manipulated.
- VAgg(): (Not fully implemented) A function that will aggregate the votes and reveal the final count while preserving the privacy of individual votes.
### Limitations
- Incomplete VAgg() Function: The code currently lacks the full implementation of the vote aggregation function (VAgg()) which would need to securely combine the shares of votes and reveal the final count.
- Simple Voting Model: The current implementation assumes a simple scenario with only one candidate and the voters casting their vote for the first candidate.
Performance Optimization: The code can be further optimized for speed and efficiency, especially for handling large numbers of voters and candidates.
### Future Work
- Complete VAgg() implementation: Finish the vote aggregation function to securely combine the votes and reveal the final count.
- Support for Multiple Candidates: Extend the system to handle multiple candidates and allow voters to choose among them.
- Performance Optimization: Optimize the code for efficiency and scalability to handle large numbers of voters and votes.
# Installation

Install the required MP-SPDZ library:
```
```
Download the repository and navigate to the directory.
Compile the script:
```
```
