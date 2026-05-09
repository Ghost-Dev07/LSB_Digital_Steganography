![Language](https://img.shields.io/badge/Language-C-blue)
![Concept](https://img.shields.io/badge/Concept-Steganography-green)
![Technique](https://img.shields.io/badge/Technique-LSB-orange)
![Type](https://img.shields.io/badge/Type-Binary%20File%20Processing-purple)
![Focus](https://img.shields.io/badge/Focus-Bitwise%20Manipulation-red)

# 🖼️ Image Steganography using LSB (C)

## 🚀 Overview

A C-based image steganography system that hides secret messages inside BMP image files using Least Significant Bit (LSB) manipulation.

The project focuses on binary file processing, bitwise operations, and secure hidden-data extraction while maintaining minimal visual distortion in the image.

---

## 🧠 Problem Statement

Secure communication requires hiding sensitive information in a way that does not attract attention. While encryption protects the content of data, it may still reveal the presence of hidden communication.

A mechanism is required to conceal information inside ordinary media files without visibly altering them.

---

## 💡 Solution

This project embeds secret data into BMP image pixel bytes using LSB modification techniques.

The system supports:

* Secret message embedding
* Password-protected extraction
* Metadata encoding
* Binary file-based hidden communication

---

## 🏗️ System Architecture

```text id="m8q4zx"
Input BMP Image + Secret File
                |
                v
      LSB Encoding Module
                |
                v
         Stego Image Output

Decoding Flow:

Stego Image + Password
                |
                v
      LSB Decoding Module
                |
                v
      Reconstructed Secret Message
```

### 🔄 Encoding & Decoding Flow

```text id="x8d7fa"
Encoding:

[Secret Message]
        ↓
Convert Data → Bit Stream
        ↓
Inject Bits into LSB of Image Bytes
        ↓
Generate Stego Image

Decoding:

[Stego Image]
        ↓
Extract LSB Bits
        ↓
Reconstruct Original Message
```

---

## 🔧 Concepts Used

* Binary File Handling
* Bitwise Operations
* Data Encoding & Decoding
* Memory Management
* Byte-Level Manipulation

---

## 🔍 Feature to Implementation Mapping

| Feature             | Implementation Technique    |
| ------------------- | --------------------------- |
| Data hiding         | LSB Bit Manipulation        |
| File processing     | Binary File Handling        |
| Security            | Password Validation         |
| Data reconstruction | Bit Extraction + Conversion |

---

## ⚙️ LSB Encoding Logic

```c id="w4r9xt"
image_byte = (image_byte & 0xFE) | message_bit;
```

The least significant bit of each image byte is modified to store secret message bits while preserving visual image quality.

---

## 🔄 Working

### 🔐 Encoding Phase

* BMP image is opened in binary mode
* 54-byte BMP header is preserved
* The following information is embedded:

  * Secret file size
  * File extension
  * Password
  * Actual message
* Each message bit is inserted into the LSB of image bytes

### 🔓 Decoding Phase

* Password is validated
* Embedded metadata is extracted
* Hidden message is reconstructed from extracted bits

---

## ⚡ Key Features

* Password-protected decoding
* Minimal visible image distortion
* Supports arbitrary file data
* Command-line based execution
* Binary-safe data handling

---

## 📸 Steganography Results

### 🖼️ Original Image

![Original Image](Images/beautiful.bmp)

---

### 🔐 Stego Image

![Stego Image](Images/beautiful_encoded.bmp)

The hidden data is embedded within the least significant bits of image bytes, resulting in minimal visible to no difference between the original and stego image. 

---

## 📊 Results

* Successfully hid secret data inside BMP images
* Achieved accurate hidden-data reconstruction
* Maintained image integrity after encoding
* No visible distortion observed in output image

---

## ⚠️ Engineering Challenges

* Handling BMP binary file structures correctly
* Ensuring embedded data fits within image capacity
* Maintaining image integrity after encoding
* Managing bit-level data reconstruction accurately

---

## 🔮 Future Improvements

* Support for PNG/JPEG formats
* Encryption before embedding
* GUI-based interface
* Improved data capacity optimization
