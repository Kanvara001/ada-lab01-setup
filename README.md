# ada-lab01-setup

โปรเจกต์ Lab 01 สำหรับการตั้งค่าสภาพแวดล้อม Python ด้วย venv และการจัดการโค้ดด้วย Git & GitHub

## 1. ข้อมูลโปรเจกต์และผู้จัดทำ

| หัวข้อ | รายละเอียด |
|---|---|
| รายวิชา | SC 677 704 การวิเคราะห์ข้อมูลขั้นสูง (Advanced Data Analytics) |
| ภาคการศึกษา | ภาคการศึกษาปลาย ปีการศึกษา 2569 |
| ภาควิชา | ภาควิชาสถิติและวิทยาการข้อมูล คณะวิทยาศาสตร์ มหาวิทยาลัยขอนแก่น |
| ผู้จัดทำ | นางสาวกัญญ์วรา ถาวโรฤทธิ์ |
| รหัสนักศึกษา | 695020018-8 |

### โครงสร้างโปรเจกต์

```
ada-lab01-setup/
├── .gitignore
├── README.md
└── requirements.txt
```

## 2. วิธีการติดตั้งและจำลองสภาพแวดล้อมโปรเจกต์

### 2.1 ติดตั้ง Python และ Git

- ติดตั้ง Python เวอร์ชัน 3.10 ขึ้นไปจาก [python.org](https://www.python.org)
- ติดตั้ง Git จาก [git-scm.com](https://git-scm.com)
- ตรวจสอบการติดตั้งด้วยคำสั่ง

```bash
python --version   # macOS/Linux ใช้ python3 --version
git --version
```

### 2.2 Clone โปรเจกต์ลงเครื่อง

```bash
git clone https://github.com/<username>/ada-lab01-setup.git
cd ada-lab01-setup
```

### 2.3 สร้าง Virtual Environment

Windows:

```bash
python -m venv .venv
```

macOS / Linux:

```bash
python3 -m venv .venv
```

### 2.4 เปิดใช้งาน Virtual Environment

Windows (Command Prompt):

```cmd
.venv\Scripts\activate
```

Windows (PowerShell):

```powershell
.venv\Scripts\Activate.ps1
```

macOS / Linux:

```bash
source .venv/bin/activate
```

เมื่อเปิดสำเร็จ จะเห็น `(.venv)` อยู่หน้าบรรทัดคำสั่ง

> ถ้า PowerShell ขึ้นข้อความว่า scripts are disabled ให้รัน `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` หนึ่งครั้ง แล้วเปิดใช้งานใหม่

### 2.5 ติดตั้งไลบรารีจาก requirements.txt

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## 3. คำสั่ง venv และ pip ที่เกี่ยวข้อง

| คำสั่ง | หน้าที่ |
|---|---|
| `python -m venv .venv` | สร้าง Virtual Environment ชื่อ `.venv` ในโฟลเดอร์โปรเจกต์ |
| `.venv\Scripts\Activate.ps1` / `source .venv/bin/activate` | เปิดใช้งาน venv ทำให้คำสั่ง `python` และ `pip` ทำงานในสภาพแวดล้อมนี้ |
| `deactivate` | ปิดการใช้งาน venv กลับไปใช้ Python ของระบบ |
| `pip install --upgrade pip` | อัปเกรด pip เป็นเวอร์ชันล่าสุด |
| `pip install <package>` | ติดตั้งแพ็กเกจลงใน venv ที่เปิดอยู่ |
| `pip list` | แสดงรายการแพ็กเกจที่ติดตั้งแล้ว |
| `pip freeze > requirements.txt` | บันทึกรายการแพ็กเกจพร้อมเวอร์ชันลงไฟล์ requirements.txt |
| `pip install -r requirements.txt` | ติดตั้งแพ็กเกจทั้งหมดตามไฟล์ requirements.txt |

## 4. คำสั่ง Git ที่เกี่ยวข้อง

| คำสั่ง | หน้าที่ |
|---|---|
| `git init` | เริ่มต้น Git repository ในโฟลเดอร์ปัจจุบัน |
| `git clone <url>` | ดาวน์โหลด repository จาก GitHub มาไว้ในเครื่อง |
| `git status` | ตรวจสถานะไฟล์ที่แก้ไข, ไฟล์ที่ add แล้ว และไฟล์ที่ยังไม่ถูกติดตาม |
| `git add <file>` / `git add .` | เลือกไฟล์เข้าสู่ staging area เพื่อเตรียม commit |
| `git commit -m "ข้อความ"` | บันทึกการเปลี่ยนแปลงที่อยู่ใน staging area เป็น commit |
| `git branch -M main` | เปลี่ยนชื่อ branch ปัจจุบันเป็น `main` |
| `git remote add origin <url>` | เชื่อม repository ในเครื่องกับ repository บน GitHub |
| `git push -u origin main` | ส่ง commit ขึ้น GitHub และตั้ง `origin/main` เป็น upstream |
| `git pull` | ดึงการเปลี่ยนแปลงล่าสุดจาก GitHub มารวมกับงานในเครื่อง |
