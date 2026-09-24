# Computer Vision AI Workshop

บทเรียนภาษาไทย 8 หัวข้อ พร้อม Prompt สำหรับ AI โค้ดตัวอย่างที่รันได้ แบบฝึกหัด ภาพผลลัพธ์ และสไลด์ประกอบ

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bluebox-dev/Prompt-Computer-Vision/blob/main/Computer_Vision_AI_Workshop.ipynb)

## สำหรับผู้เรียน

1. กด **Open in Colab** ด้านบน แล้วเชื่อมต่อ runtime (CPU ก็เพียงพอ)
2. เลือก **Runtime → Run all** หรือรันเซลล์ **เตรียมข้อมูลอัตโนมัติ** ก่อนเริ่มเรียน หาก Colab ถามยืนยันการรัน notebook ให้ตรวจแหล่งที่มาแล้วดำเนินการต่อ
3. เมื่อเห็น `พร้อมเรียน: ตรวจภาพครบ 16 ไฟล์` สามารถรันตัวอย่างและทำแบบฝึกหัดได้ ทุก Prompt ใช้ `dataset/ชื่อไฟล์`

ระบบดาวน์โหลดข้อมูลให้เอง ไม่ต้องอัปโหลด dataset หรือ mount Google Drive รันซ้ำได้โดยใช้ไฟล์เดิมที่ตรวจผ่าน และดาวน์โหลดไฟล์ที่ขาดหรือเสียใหม่ เมื่อเปลี่ยนหรือรีเซ็ต runtime ให้รันเซลล์เตรียมข้อมูลอีกครั้ง

โค้ดตัวอย่าง 8 บทพร้อมรัน ส่วนเซลล์แบบฝึกหัดตั้งใจเว้นไว้ให้ผู้เรียนส่ง Prompt ให้ AI แล้วนำโค้ดมาทดลอง หากต้องการเก็บคำตอบของตัวเอง ให้เลือก **File → Save a copy in Drive**

## สำหรับผู้สอน: ไฟล์ที่ต้องอัปโหลด

อัปโหลดทั้งโครงสร้างนี้ไปยัง **public repository `bluebox-dev/Prompt-Computer-Vision` บน branch `main`** โดยคงชื่อและตัวพิมพ์เล็ก/ใหญ่:

```text
Computer_Vision_AI_Workshop.ipynb
README.md
dataset/                 # ภาพประมวลผล 16 ไฟล์
assets/notebook/         # ภาพประกอบและเฉลย 36 ไฟล์
scripts/verify_workshop.py
.gitignore
```

**ต้องมี `assets/` ด้วย** การอัปโหลดเฉพาะ notebook กับ dataset จะยังขาดภาพประกอบ Markdown รูปเหล่านี้ใช้ URL ของ `raw.githubusercontent.com` เพื่อแสดงใน Colab และ GitHub โดยไม่อาศัย path บนเครื่องผู้สอน และต้องใช้อินเทอร์เน็ตเพื่อแสดงรูป

ลิงก์แจกผู้เรียนหลังอัปโหลด:

[เปิด Computer Vision AI Workshop บน Colab](https://colab.research.google.com/github/bluebox-dev/Prompt-Computer-Vision/blob/main/Computer_Vision_AI_Workshop.ipynb)

การเปิด notebook จาก GitHub ไม่ได้เตรียมไฟล์ข้างเคียงไว้ใน runtime ให้โดยอัตโนมัติ เซลล์แรกจึงดาวน์โหลดรูปจาก GitHub และตรวจ SHA-256 ก่อนใช้งาน ดู [Colab FAQ](https://research.google.com/colaboratory/faq.html) และรูปแบบลิงก์จาก [Open in Colab](https://github.com/googlecolab/open_in_colab)

หากเปลี่ยนเจ้าของ repository ชื่อ repository หรือ branch ต้องแก้ `REPO`, `BRANCH`, URL ของภาพทั้ง notebook และลิงก์ Colab ใน notebook/README ให้ตรงกัน หากเปลี่ยนไฟล์ dataset ต้องอัปเดต `EXPECTED_SHA256` ในเซลล์เตรียมข้อมูลด้วย เพื่อไม่ให้ผู้เรียนใช้ภาพคนละรุ่นกับบทเรียน

## ใช้บนเครื่อง / ตรวจสอบก่อนเผยแพร่

เปิด Jupyter จากโฟลเดอร์ repository แล้วรันเซลล์เตรียมข้อมูล ระบบใช้ dataset ที่มีอยู่ได้โดยไม่ดาวน์โหลดซ้ำเมื่อ checksum ตรงกัน รูปประกอบ Markdown ยังโหลดจาก GitHub

สำหรับติดตั้งเครื่องมือทดสอบบนเครื่องผู้สอน:

```bash
python3 -m pip install numpy matplotlib opencv-python-headless nbformat
python3 scripts/verify_workshop.py
```

ชุดตรวจสอบครอบคลุมโครงสร้าง notebook รูปประกอบทุกไฟล์ ลิงก์ภายใน path ข้อมูล การดาวน์โหลดจำลองในโฟลเดอร์ว่าง การรันซ้ำ การกู้ไฟล์ที่หาย/เสีย ข้อผิดพลาดเครือข่าย และผลการประมวลผลของตัวอย่างทั้ง 8 บท การทดสอบนี้ไม่ต้องเชื่อมต่อ GitHub และไม่แทนการทดลองใน Colab จริงหลังเผยแพร่

หลังอัปโหลด ให้เปิดลิงก์ Colab จากหน้าต่างใหม่ ตรวจว่ารูปประกอบแสดง แล้วเลือก Runtime → Run all ใน runtime ใหม่ ต้องเห็นตรวจภาพครบ 16 ไฟล์และผลลัพธ์ตัวอย่างครบ 8 บทโดยไม่มี error

## สิ่งที่แก้ไขจากไฟล์เดิม

- เปลี่ยน path `../dataset/` ให้เป็น `dataset/` ทั้งโค้ดและ Prompt
- เพิ่มการเตรียมข้อมูลอัตโนมัติ ตรวจ checksum และทดสอบเปิดภาพครบ 16 ไฟล์
- ย้ายภาพฝังแบบ `attachment:` จำนวน 36 ภาพไปเป็น `assets/notebook/` และอ้างด้วย raw GitHub URL
- เพิ่มโค้ดตัวอย่างที่รันได้ทั้ง 8 บท รวมการวางภาพ PNG โปร่งใสบนพื้นขาว และการแปลง BGR เป็น RGB ก่อนแสดงผล
- ตัดลิงก์ PDF ที่ชี้ path ส่วนตัวบนเครื่องผู้สอน ภาพสไลด์ที่ฝังไว้เดิมและเครดิตยังอยู่ครบ ไม่ได้รวม PDF ต้นฉบับทั้งฉบับ
- ล้าง metadata TIFF ที่ผิดรูปแบบของ `cameraman.tif` โดยตรวจว่าค่าพิกเซลทุกค่าตรงกับต้นฉบับ เพื่อไม่ให้ OpenCV แสดงคำเตือนระหว่างเตรียมข้อมูล

เครดิตสไลด์: Asst. Prof. Dr. Anakkapon Saenthon, KMITL, *Day1_1_BasicImageProcessing.pdf* รายละเอียดอ้างอิงอยู่ท้าย notebook
