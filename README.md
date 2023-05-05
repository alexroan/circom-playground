# WTF Is ZK and ZK Proofs?

ZK stands for Zero-Knowledge or Zero Knowledge Proofs. It's the idea that you can prove you know something without giving that something away.

Let's say you want to prove that you're over 18 but don't want to give away your birthdate. You can use Zero Knowledge Proofs to do this.

## Step-by-step example

Alice is color-blind and sees Blue and Red as the same shade.
Bob is not color blind.

Bob tries to convince Alice that two sheets of paper are different colors (red and blue), but Alice doesn't believe him. So, Bob uses a simple Zero Knowledge proof:

1. Bob places the red piece of paper in Alice's right hand and tells her this is red.
2. Bob places the blue piece of paper in Alice's left hand and tells her this is blue.
3. Alice places her hands behind her back, with paper in each, without Bob seeing. She swaps them over any number of times she likes, keeping track of how many times she swaps to know which paper was originally in each hand.
4. Periodically, she presents the papers to Bob, one in each hand, and asks him which is red and which is blue.
5. Each time Bob guesses correctly, Alice is more confident that Bob is correct when he says which is red and which is blue.

This is an _interactive_ Zero Knowledge proof since the prover (Bob), and the verifier (Alice) interact with each other at each step (when Alice presents the papers to Bob).

Crucially, when we talk about zk-SNARKS, we speak about Non-Interactive proofs (Zero-Knowledge Succinct Non-Interactive Argument of Knowledge). These use fancy math, cryptography, and a "trusted setup" to avoid being interactive at each step. In other words, it enables the prover to generate a one-time single proof. And the verifier can verify that proof without periodically interacting with the prover.

## [1. Multiplier](./1-multiplier/)

This is a raw manual version of the following steps:

1. Compiling the circuit using circom
2. Long-winded trusted setup using Groth-16 and Powers of Tau
3. Generating the proof
4. Verifying the proof locally
5. Generating a smart contract verifier
6. Generating raw call to the verifier contract to copy-paste into a Remix call

## [2. Hardhat Integration](./2-hardhat-integration/)

This is a simplified version of the many manual steps above, integrated into a hardhat project, using the same circuit.

It has a hardhat test file that tests the constraints of the circuit.

## [3. Quadratic Equation Proofs](./3-quadratic/)

A hardhat project with quadratic equation provers. Prove that you know the root of an equation without revealing it.