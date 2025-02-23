# **Examcrypt: A Cryptographic Exam Protection System**  

## **Overview**  
**ExamCrypt** is a secure and cryptography-powered examination system designed to protect the integrity of digital exams by ensuring confidentiality, authenticity, and controlled access to exam content. The system leverages **AES-256 encryption** to encrypt exam questions, preventing unauthorized access. To regulate the timing of question availability, it implements **time-lock puzzles**, ensuring that questions can only be decrypted after a specific time. Additionally, **Shamir’s Secret Sharing** is used to distribute encryption keys among multiple examiners, preventing a single point of failure in key management. The project also incorporates **public-key cryptography** using Solana’s web3.js and TweetNaCl to verify the authenticity of exam data and digitally sign communications. With these techniques combined, **ExamCrypt** provides a robust and tamper-proof environment for conducting secure online examinations. 🚀

## **Features**  
-> AES-256 encryption for exam questions and options  
-> Shamir's Secret Sharing for encryption key protection  
-> Solana-based Public-Key Cryptography for authentication  
-> CLI-based execution for efficient encryption/decryption  

## **Project Structure**  
```
exam-crypto-main/
│── 1-examiner-problem-encryptor/
│   ├── index.ts   # AES encryption/decryption logic
│── 3-examiner-shamir-generation/
│   ├── index.js   # Shamir's Secret Sharing for encryption key
│── 4-public-key-crypto/
│   ├── index.ts   # Public-Key Cryptography with Solana
│── package.json   # Dependencies and scripts
│── README.md      # Project Documentation
```

---
## **Workflow**  
### **1️⃣ AES Encryption (1-examiner-problem-encryptor)**  
- Encrypts exam questions and multiple-choice options using **AES-256-CBC**.  
- Stores the **ciphertext**, which can be later decrypted using the correct key and IV.  

#### **Sample Output (Encrypted & Decrypted Data)**  
```sh
Problem statement (Encrypted): 3fa2e4c9b6...
Option 1 (Encrypted): 67bd8a2ff1...
Decrypted Problem: What is 2 + 2?
Decrypted Option 1: 4
```

### **2️⃣ Key Protection with Shamir’s Secret Sharing (3-examiner-shamir-generation)**  
- The AES encryption key is **split into multiple parts** using **Shamir’s Secret Sharing (SSS)**.  
- Only a required threshold of shares can reconstruct the key.  

#### **Sample Output (Secret Shares & Recovery)**  
```sh
Shares: ["4a5f...", "b6c8...", "d9e3..."]
Recovered Key: Encryption key
```

### **3️⃣ Public-Key Cryptography (4-public-key-crypto)**  
- Uses **Solana Web3.js** and **TweetNaCl** for **digital signatures and verification**.  
- Ensures authenticity of exam-related data.  

#### **Sample Output (Signing & Verification)**  
```sh
Signature: 39af8b7c...
Verification Result: true
```
#### **Go Through this presentation for better understanding**
[ExamCrypt](https://www.canva.com/design/DAGf5mflEkQ/0KphuLz8UWxB0XriPbUraA/view?utm_content=DAGf5mflEkQ&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h4a82ca5c9a)

