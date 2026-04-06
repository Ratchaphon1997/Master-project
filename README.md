# Hate Speech and Offensive Detection in Thai Esports Chat using Deep Learning

โครงงานวิจัยการพัฒนาและวิเคราะห์ประสิทธิภาพของโมเดล Deep Learning (Transformer-based) เพื่อตรวจจับและจำแนกคำพูดที่ไม่เหมาะสมในแชทการแข่งขัน Esports ภาษาไทย (Valorant, Dota2, และอื่นๆ)

## 📌 บทนำ (Introduction)
ในปัจจุบันวงการ Esports ในประเทศไทยมีการเติบโตอย่างรวดเร็ว อย่างไรก็ตาม ปัญหาการใช้ภาษาที่ไม่เหมาะสม (Offensive Language) และคำพูดที่แสดงถึงความเกลียดชัง (Hate Speech) ในช่องทางแชทระหว่างการสตรีมมิ่งสดเป็นปัญหาที่ส่งผลเสียต่อสังคมออนไลน์ โครงงานนี้จึงมุ่งเน้นการใช้เทคโนโลยีประมวลผลภาษาธรรมชาติ (NLP) มาช่วยจำแนกข้อความเหล่านี้เพื่อสร้างสภาพแวดล้อมที่ดีขึ้นในการรับชม

## 🎯 วัตถุประสงค์
1. เพื่อพัฒนาโมเดล Deep Learning ที่สามารถตรวจจับ Hate Speech และ Offensive Language ในบริบทของ Esports ภาษาไทย
2. เพื่อเปรียบเทียบประสิทธิภาพระหว่างโมเดล Transformer ประเภทต่างๆ
3. เพื่อศึกษาผลกระทบของการจัดการข้อมูลที่ไม่สมดุล (Imbalanced Data) ต่อประสิทธิภาพของโมเดล

## 🛠️ วิธีการดำเนินงาน (Methodology)
![Pipeline ของโครงงาน](pipeline.png)

### 1. ข้อมูลที่ใช้ (Dataset)
* **แหล่งที่มา:** ข้อมูลแชทสดจาก Twitch และ YouTube ในการแข่งขันเกม Valorant และ Dota2
* **ขนาดข้อมูล:** 59,837 ข้อความ
* **การจำแนกประเภท (Labeling):**
    * `Hate Speech`: คำเหยียดหยาม เชื้อชาติ เพศ หรือสร้างความเกลียดชัง
    * `Offensive Language`: คำหยาบคายทั่วไป
    * `Neither`: ข้อความปกติทั่วไป

### 2. การเตรียมข้อมูล (Pre-processing)
* ทำความสะอาดข้อความ (ลบ URLs, Stopwords, และตัวอักษรพิเศษ)
* ใช้ `pythainlp` สำหรับการตัดคำ (Tokenization)
* จัดการ Data Imbalance ด้วยเทคนิค **Oversampling** และ **Undersampling**

### 3. โมเดลที่ใช้เปรียบเทียบ
* **WangchanBERTa**
* **BERT-base-multilingual**
* **DistilBERT**

## 📊 ผลการทดสอบ (Results)
จากการทดสอบพบว่าในสถานการณ์ที่ใช้เทคนิค **Oversampling** โมเดลมีประสิทธิภาพดังนี้:

| Model | F1-Score |
| :--- | :---: |
| **BERT-base** | **0.58** |
| **WangchanBERTa** | **0.57** |
| **DistilBERT** | **0.53** |

*สรุปผล:* โมเดล **BERT** และ **WangchanBERTa** ให้ความแม่นยำสูงสุดในขณะที่ **DistilBERT** ให้ความเร็วในการประมวลผล (Inference time) ที่ดีกว่าโดยที่ความแม่นยำลดลงเพียงเล็กน้อย

## 🚀 งานในอนาคต (Future Work)
* ขยายคลังข้อมูล (Dataset) ให้ครอบคลุมแนวเกมและกลุ่มสังคมที่หลากหลายมากขึ้น
* ปรับปรุง Model Fine-tuning เพื่อเพิ่มค่าความแม่นยำในการจำแนกคำศัพท์แสลงเฉพาะทาง

## 📝 จัดทำโดย
**National Institute of Development Administration (NIDA)** (2022-2024)
* **Program:** Master of Science Program Data analysis and Data science (DADS)
* รัชพล ขุนทิพย์สมบัติ

## 📚 อ้างอิง (References)
* [1] Thomas Davidson et al. (2017). Automated Hate Speech Detection and the Problem of Offensive Language.
* [2] Peerat Pookpanich, Thitirat Siriborvornratanakul (2023). Offensive language and hate speech detection in football news live streaming...
