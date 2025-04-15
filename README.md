# image-processing-system
Asynchronous image processing system that accepts CSV uploads, compresses images by 50%, stores product data, and provides status updates and final output via APIs. Bonus: Webhook support for completion notification.
# 📸 SDE 1 Backend Assignment – Image Processing System

## 🚀 Overview

This backend system efficiently handles image data submitted via CSV files. It supports asynchronous image compression, status tracking, and provides the final result in a downloadable CSV format. Ideal for large-scale image processing workflows.

---

## 📂 Features

- 🔄 *CSV Upload API* – Accept CSV files with image URLs.
- ✅ *Validation* – Ensure proper CSV formatting.
- 🖼 *Image Compression* – Compress input images to 50% quality asynchronously.
- 🗃 *Database Integration* – Track processing status and store data.
- 🔍 *Status API* – Check processing status via request ID.
- 🛎 *Webhook Support* (Bonus) – Optional webhook triggered after processing completes.
- 📤 *Output CSV* – Input image URLs matched with output URLs in the same order.

---

## 📥 Input CSV Format

| S. No. | Product Name | Input Image URLs |
|--------|--------------|------------------|
| 1      | SKU1         | https://image1.jpg, https://image2.jpg, https://image3.jpg |

---

## 📤 Output CSV Format

| S. No. | Product Name | Input Image URLs | Output Image URLs |
|--------|--------------|------------------|-------------------|
| 1      | SKU1         | https://image1.jpg, ... | https://compressed1.jpg, ... |

---

## 🧩 System Architecture

### 🔧 Components

- *Upload API* – Accepts and validates CSV, returns a request ID.
- *Status API* – Returns current job status using the request ID.
- *Async Worker(s)* – Compress images in the background.
- *Database* – Stores:
  - Request status
  - Input and output image mappings
- *Webhook Endpoint* (Optional) – Notifies once all processing is complete.

### 🗂 Example Flow

1. Upload CSV → Receive request_id
2. Backend asynchronously:
   - Validates CSV
   - Compresses images
   - Stores data
3. User:
   - Polls Status API or
   - Gets notified via webhook
4. Final CSV generated with input and output image URLs

---

## ⚙ Tech Stack

- *Backend*: Node.js or Python
- *Database*: SQL or NoSQL
- *Postman*: For API testing
- *Draw.io*: System Design Diagrams

---
