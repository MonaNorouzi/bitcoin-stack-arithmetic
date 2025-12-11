# Theoretical Analysis: Taproot & Script Flexibility

## 1. Introduction to Taproot (BIP 341)
Taproot is a significant upgrade to the Bitcoin protocol that improves privacy, efficiency, and flexibility. It introduces Schnorr signatures and MAST (Merkelized Abstract Syntax Trees).

## 2. The Problem with Legacy Scripts (Pre-Taproot)
In the script implemented in this repository (`script.btc`), we utilize `OP_IF` and `OP_ELSE`. In legacy P2SH (Pay-to-Script-Hash) transactions:
* **Full Disclosure:** When spending, the entire script—including the branches that were NOT executed—must be revealed on the blockchain.
* **Privacy Leak:** If the script has a complex condition (e.g., "Student ID check OR Manager Backup Key"), revealing the unused backup key condition leaks security info.
* **Cost:** Larger scripts mean more bytes, leading to higher transaction fees.

## 3. The MAST Solution
With MAST, the script is structured as a Merkle Tree.
* **Efficiency:** Only the path used to spend the coins (e.g., the "False" branch in our logic) is revealed.
* **Privacy:** The network observes only the executed condition. In our project's case, if the logic evaluates to `False`, the "True" branch (Single Hash logic) remains cryptographically hidden forever.

## 4. Conclusion
For this specific assignment, implementing the logic in a Taproot-compatible output would allow us to keep the `OP_IF` logic private, revealing only the specific hash operation that finalized the transaction.