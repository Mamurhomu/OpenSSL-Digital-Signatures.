# OpenSSL-Digital-Signatures.
A step-by-step guide to generating RSA key pairs, signing documents, and verifying authenticity using OpenSSL in Kali Linux.
# OpenSSL Digital Signatures - Kali Linux  
This project demonstrates how to generate **public-private key pairs**, sign documents, and verify their authenticity using OpenSSL in Kali Linux.  

## 📌 Topics Covered  
✔ Generating RSA Key Pairs  
✔ Creating & Signing Documents  
✔ Verifying Digital Signatures  
✔ Detecting Unauthorized Modifications  

## 📝 Instructions  

### **1. Generate a Private Key**  
```bash
openssl genpkey -algorithm RSA -out private_key.pem
```

### **2. Extract the Public Key**  
```bash
openssl pkey -in private_key.pem -pubout -out public_key.pem
```

### **3. Create a Contract Document**  
```bash
echo "Hi, my name is Mamurhomu" > contract.txt
cat contract.txt
```

### **4. Sign the Document**  
```bash
openssl dgst -sha256 -sign private_key.pem -out signature contract.txt
```

### **5. Verify the Signature**  
```bash
openssl dgst -sha256 -verify public_key.pem -signature signature contract.txt
```

If the document has **not been altered**, the output will be:  
```
Verified OK
```

### **6. Test for Tampering**  
Modify the document using:  
```bash
vi contract.txt
```
Then, re-run the verification command:  
```bash
openssl dgst -sha256 -verify public_key.pem -signature signature contract.txt
```

If the file has been modified, the output will indicate **Verification Failure**.

## 📎 Attached Files  
📂 **OpenSSL_Digital_Signatures_Updated.pptx** – A PowerPoint presentation explaining the process with diagrams.  

🚀 **Let's discuss how digital signatures protect data integrity in cybersecurity!**  

---  
### **🌍 Connect With Me:**  
👨‍💻 [LinkedIn](https://www.linkedin.com/)  
🐙 [GitHub](https://github.com/)  

#CyberSecurity #OpenSSL #Encryption #DataSecurity #DigitalSignatures
