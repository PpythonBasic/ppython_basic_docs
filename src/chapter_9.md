# บทที่ 9: การพัฒนาเว็บแอปพลิเคชันด้วย Python และ Flask Framework

## 1. แนะนำ Flask Framework

Flask เป็นเฟรมเวิร์กที่ใช้สำหรับสร้างเว็บแอปพลิเคชันด้วยภาษา Python ซึ่งมีความเรียบง่ายและเหมาะสำหรับผู้เริ่มต้น เราจะมาเรียนรู้วิธีการสร้างเว็บแอปพลิเคชันง่ายๆ ที่แสดงข้อมูล พร้อมทั้งสอนเรื่อง routing และ template

## 2. ติดตั้ง Flask

ก่อนอื่นเราต้องติดตั้ง Flask ก่อน โดยใช้คำสั่งต่อไปนี้ใน terminal:

```bash
pip install Flask
```

## 3. สร้างเว็บแอปพลิเคชันง่ายๆ

### 3.1 โครงสร้างโปรเจค

```
my_flask_app/
│
├── app.py
├── templates/
│   └── index.html
└── static/
    └── style.css
```

### 3.2 สร้างไฟล์ `app.py`

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html', title="หน้าแรก", message="สวัสดีเด็กๆ!")

@app.route('/about')
def about():
    return render_template('index.html', title="เกี่ยวกับเรา", message="นี่คือหน้าเกี่ยวกับเรา")

if __name__ == '__main__':
    app.run(debug=True)
```

### 3.3 สร้างไฟล์ `templates/index.html`

```html
<!DOCTYPE html>
<html lang="th">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>{{ title }}</title>
    <link
      rel="stylesheet"
      href="{{ url_for('static', filename='style.css') }}"
    />
  </head>
  <body>
    <h1>{{ message }}</h1>
  </body>
</html>
```

### 3.4 สร้างไฟล์ `static/style.css`

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  text-align: center;
  padding: 50px;
}

h1 {
  color: #333;
}
```

## 4. การทำงานของ Routing

Routing คือการกำหนดเส้นทาง URL ไปยังฟังก์ชันที่เราต้องการให้ทำงาน เช่น:

- `/` จะเรียกฟังก์ชัน `home()`
- `/about` จะเรียกฟังก์ชัน `about()`

## 5. การใช้ Template

Template เป็นไฟล์ HTML ที่เราสามารถส่งข้อมูลจาก Python ไปแสดงผลได้ โดยใช้ `render_template` และส่งข้อมูลผ่านตัวแปร เช่น `title` และ `message`

## 6. ตัวอย่างการทำงาน

```mermaid
graph TD
    A[ผู้ใช้เข้าถึง URL] --> B{URL คืออะไร?}
    B -->|/| C[เรียกฟังก์ชัน home()]
    B -->|/about| D[เรียกฟังก์ชัน about()]
    C --> E[แสดงหน้าแรก]
    D --> F[แสดงหน้าเกี่ยวกับเรา]
```

## 7. โจทย์ฝึกหัด

### โจทย์ 1: สร้างหน้าใหม่

ให้สร้างหน้าใหม่ที่ชื่อ `/contact` และแสดงข้อความ "ติดต่อเรา" เมื่อผู้ใช้เข้าถึง URL นี้

### โจทย์ 2: เพิ่มข้อมูลใน Template

ให้เพิ่มข้อมูลใน `index.html` เพื่อแสดงชื่อและอายุของเด็กๆ โดยส่งข้อมูลจาก `app.py` ไปยัง template

**คำแนะนำ:** สำหรับเด็กอนุบาล ควรใช้รูปภาพและสีสันที่สดใสเพื่อดึงดูดความสนใจ และใช้คำพูดที่เข้าใจง่ายในการอธิบายแต่ละขั้นตอน
