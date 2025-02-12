## เครื่องมือที่จำเป็น

- [Python](https://www.python.org/)
- [VSCode](https://code.visualstudio.com/)
- [Python Extensions](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Git](https://git-scm.com/)
- [GitHub](https://github.com/)

## คำสั่งรัน Python

```bash
python main.py
```

## เชื่อม Git กับ GitHub.com

- ตั้งค่า Git เปิด cmd หรือ terminal ใช้คำสั่ง

```bash
git config --global user.name "ชื่อ username ของคุณใน github.com"
git config --global user.email "อีเมล ของคุณใน github.com"
```

## คำสั่ง git เบื้องต้น

- สร้าง branch

```bash
git checkout -b main
```

- บันทึกเวอร์ชั่นโค้ด

```bash
git add .
git commit -m "ข้อความ commit"
```

- อัปโหลดเวอร์ชั่นโค้ดขึ้น github.com

```bash
git push origin main
```

- ดึงข้อมูลจาก Repository

```bash
git pull origin main
```

- โคลน Repository จาก github.com

```bash
git clone git@github.com:username/repository-name.git
```

- เชื่อมต่อกับ Repository ที่มีอยู่

```
git remote add origin git@github.com:username/repository-name.git
```

- ตรวจสอบสถานะ

```bash
git status
```
