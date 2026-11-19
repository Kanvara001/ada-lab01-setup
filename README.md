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

### ขั้นที่ 1: ติดตั้ง Python และ Git

1. ดาวน์โหลด Python เวอร์ชัน 3.10 ขึ้นไปจาก [python.org](https://www.python.org) และติดตั้ง โดยติ๊กช่อง **Add python.exe to PATH** ตอนติดตั้ง (Windows)
2. ดาวน์โหลด Git จาก [git-scm.com](https://git-scm.com) และติดตั้งด้วยค่าเริ่มต้น
3. เปิด Terminal ใหม่ แล้วรันคำสั่งตรวจสอบ

   ```bash
   python --version   # macOS/Linux ใช้ python3 --version
   git --version
   ```

   ถ้าขึ้นเลขเวอร์ชันแสดงว่าติดตั้งสำเร็จ ถ้าไม่ขึ้นให้ปิดแล้วเปิด Terminal ใหม่

### ขั้นที่ 2: Clone โปรเจกต์ลงเครื่อง

1. เปิด Terminal แล้วไปยังโฟลเดอร์ที่ต้องการเก็บโปรเจกต์
2. รันคำสั่ง clone

   ```bash
   git clone https://github.com/Kanvara001/ada-lab01-setup.git
   ```

3. เข้าไปในโฟลเดอร์โปรเจกต์

   ```bash
   cd ada-lab01-setup
   ```

### ขั้นที่ 3: สร้าง Virtual Environment

รันคำสั่งภายในโฟลเดอร์ `ada-lab01-setup`

```bash
python -m venv .venv      # Windows
python3 -m venv .venv     # macOS / Linux
```

ผลลัพธ์: จะมีโฟลเดอร์ `.venv` ปรากฏขึ้นในโปรเจกต์

### ขั้นที่ 4: เปิดใช้งาน Virtual Environment

เลือกคำสั่งให้ตรงกับ Terminal ที่ใช้

- **Windows PowerShell**

  ```powershell
  .venv\Scripts\Activate.ps1
  ```

  ถ้าขึ้นข้อความ scripts are disabled ให้รันคำสั่งนี้หนึ่งครั้ง แล้วกลับไปทำข้อนี้ใหม่

  ```powershell
  Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
  ```

- **Windows Command Prompt**

  ```cmd
  .venv\Scripts\activate
  ```

- **macOS / Linux**

  ```bash
  source .venv/bin/activate
  ```

ตรวจสอบ: ถ้าเห็น `(.venv)` อยู่หน้าบรรทัดคำสั่ง แสดงว่าเปิดใช้งานสำเร็จ

> ทุกครั้งที่เปิด Terminal ใหม่ ต้องทำขั้นที่ 4 ซ้ำก่อนใช้งาน

### ขั้นที่ 5: ติดตั้งไลบรารี

1. อัปเกรด pip

   ```bash
   python -m pip install --upgrade pip
   ```

2. ติดตั้งไลบรารีทั้งหมดตามไฟล์ `requirements.txt`

   ```bash
   pip install -r requirements.txt
   ```

3. ตรวจสอบรายการแพ็กเกจที่ติดตั้ง

   ```bash
   pip list
   ```

### ขั้นที่ 6: ออกจาก Virtual Environment

เมื่อเลิกใช้งาน ให้รันคำสั่ง

```bash
deactivate
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
