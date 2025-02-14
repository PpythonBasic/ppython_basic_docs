# React: Data flow (การไหลของข้อมูล)

ในแอปพลิเคชัน React การส่งข้อมูลจากอคอมโพเนนต์หลักไปยังคอมโพเนนต์ลูก โดย props ดังที่เราเห็นในส่วนก่อนหน้านี้แบบนี้:

```jsx
<WelcomeMessage name={"Flavio"} />
```

หากคุณส่งฟังก์ชันไปยังคอมโพเนนต์ลูก คุณยังสามารถเปลี่ยนตัวแปร state ที่ถูกกำหนดขึ้นจากคอมโพเนนต์หลักจากคอมโพเนนต์ลูกได้เหมือนกันด้วยลักษณะแบบนี้:

```jsx
<Counter setCount={setCount} count={count} />
```

สิ่งนี้มีประโยชน์เมื่อคอมโพเนนต์หลักทำหน้าที่ในการจัดการตัวแปร state หรือจะใช้ตัวแปร state ด้วยเหมือนกัน

ภายในคอมโพเนนต์ `Counter` ตอนนี้เราสามารถเรียก `setCount` ได้จาก `prop` และเรียกใช้เพื่ออัปเดตสถานะของ `count` ที่แสดงอยู่ในคอมโพเนนต์หลักได้:

```jsx
const Counter = ({ count, setCount }) => {
  return (
    <div>
      <p>คุณคลิกไปแล้ว {count} ครั้ง</p>
      <button
        onClick={() => {
          setCount(count + 1);
        }}
      >
        คลิกที่นี่
      </button>
    </div>
  );
};
```

นี่คือตัวอย่างแบบเต็ม:

```jsx
import { useState } from "react";

const Counter = ({ count, setCount }) => {
  return (
    <div>
      <button onClick={() => setCount(count + 1)}>คลิกที่นี่</button>
    </div>
  );
};

function App() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>คุณคลิกไปแล้ว {count} ครั้ง</p>
      <Counter setCount={setCount} count={count} />
    </div>
  );
}

export default App;
```

คุณจำเป็นต้องรู้ว่ามีวิธีการจัดการข้อมูลขั้นสูงกว่านี้

เริ่มต้นจาก `Context API` แต่ยังรวมถึงไลบรารีเช่น `Jotai` และ `Easy Peasy`
