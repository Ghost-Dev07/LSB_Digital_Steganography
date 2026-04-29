![Language](https://img.shields.io/badge/Language-C-blue)
![Concept](https://img.shields.io/badge/Concept-Steganography-green)
![Technique](https://img.shields.io/badge/Technique-LSB-orange)
![File Handling](https://img.shields.io/badge/Type-Binary%20Files-purple)


# 🖼️ Image Steganography using LSB (C)

## 🚀 Overview

A C-based implementation of image steganography that hides secret messages inside BMP images using Least Significant Bit (LSB) manipulation.

---

## 🧠 Problem Statement

Secure communication requires hiding sensitive data in a way that does not attract attention. Traditional encryption alone may reveal the presence of hidden data.

---

## 💡 Solution

This project embeds a secret message into a BMP image by modifying the least significant bits of pixel data, ensuring minimal visual distortion.

---

## 🏗️ System Architecture

Input Image (.bmp) + Secret File
↓
Encoding Module (LSB Injection)
↓
Output Image (Stego Image)

Decoding:
Stego Image + Password → Extract Message

```text id="vkhkjk"
Encoding:

[Secret Message] → Convert to Bits → Inject into LSB of Image Bytes
                                      ↓
                              [Stego Image]

Decoding:

[Stego Image] → Extract LSB Bits → Reconstruct Message


```


---

## 🔧 Concepts Used

* File Handling (Binary)
* Bitwise Operations
* Data Encoding/Decoding
* Memory Management

---

## 🔍 Feature to Implementation Mapping

| Feature             | Implementation Technique    |
| ------------------- | --------------------------- |
| Data hiding         | LSB Bit Manipulation        |
| File processing     | Binary File Handling        |
| Security            | Password Validation         |
| Data reconstruction | Bit Extraction + Conversion |

## ⚙️ LSB Encoding (Snippet)

```c id="kch2xj"
image_byte = (image_byte & 0xFE) | message_bit;
```



## 🔄 Working

### 🔐 Encoding

* Read BMP image (skip 54-byte header)
* Embed:

  * Message size
  * File extension
  * Password
  * Actual message
* Each bit stored in LSB of image bytes

### 🔓 Decoding

* Validate password
* Extract metadata (size, extension)
* Reconstruct original message

---

## ⚡ Key Features

* Password-protected decoding
* Lossless visual output
* Supports arbitrary file data
* Command-line based execution

---

## 📊 Results

* Successfully hid data within BMP images
* No visible distortion in output image
* Accurate recovery of hidden message

---

## ⚠️ Engineering Challenges

* Handling binary file structures correctly
* Ensuring data size fits within image capacity
* Maintaining image integrity after encoding

---

## 🔮 Future Improvements

* Support for PNG/JPEG formats
* GUI interface
* Encryption before embedding
