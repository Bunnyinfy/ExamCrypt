# **Examcrypt: A Cryptographic Exam Protection System**  

## **Overview**  
Examcrypt is a cryptographic system designed to **secure exam questions and answers** using **AES encryption, Shamir’s Secret Sharing, and Public-Key Cryptography**. This project ensures that exam questions are encrypted, securely stored, and can only be accessed by authorized individuals.  

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

## **Installation Guide**  
### **Step 1: Clone the Repository**  
```sh
git clone https://github.com/your-username/SecureExam.git
cd SecureExam
```

### **Step 2: Install Dependencies**  
```sh
npm install
```

For TypeScript support, install `ts-node` globally:  
```sh
npm install -g ts-node
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
