# React : React คอมโพเนนต์ (Component)

React เป็นไลบรารี JavaScript ที่ใช้สำหรับสร้าง user interfaces (UIs) แบบ declarative คอมโพเนนต์เป็นส่วนประกอบพื้นฐานของแอปพลิเคชัน React แต่ละคอมโพเนนต์เป็นฟังก์ชัน JavaScript ที่รับข้อมูล (props) และส่งคืนสิ่งที่จะแสดงบนหน้าจอ (JSX)

และคุณเพิ่งได้เห็นวิธีการสร้างแอปพลิเคชัน React แรกของคุณ.

แอปพลิเคชั่นนี้มาพร้อมกับไฟล์หลายชุดที่ทําสิ่งต่างๆ ส่วนใหญ่เกี่ยวข้องกับการกําหนดค่าต่างๆ แต่ว่ามีไฟล์หนึ่งไฟล์ที่โดดเด่นก็คือ: `App.jsx`

`App.jsx` จะเป็น react คอมโพเนนต์แรกของคุณที่คุณจะได้พบ โค้ดจะเป็นในลักษณะนี้

```jsx
import { useState } from "react";
import reactLogo from "./assets/react.svg";
import "./App.css";

function App() {
  const [count, setCount] = useState(0);

  return (
    <div className="App">
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src="/vite.svg" className="logo" alt="Vite logo" />
        </a>
        <a href="https://reactjs.org" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.jsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Vite and React logos to learn more
      </p>
    </div>
  );
}

export default App;
```

แต่อย่าพึ่งตกใจและกลัวไปแค่เอามาแสดงให้ดูเฉยๆ 😎

เอาหล่ะ แอปพลิเคชันที่สร้างขึ้นโดยใช้ React หรือหนึ่งในเฟรมเวิร์ก frontend ยอดนิยมอันอื่นๆ เช่น `Vue` และ `Svelte` เหล่านี้ถูกสร้างขึ้นโดยใช้คอมโพเนนต์หลายสิบรายการ

แต่เพื่อให้เริ่มต้นในการวิเคราะห์คอมโพเนนต์แรกนี้ง่ายขึ้น เราจะทําให้โค้ดนี้ง่ายขึ้นดังนี้:

```jsx
function App() {
  return; /* ทำอะไรบางอย่าง */
}
```

คุณจะเห็นว่าเรากําหนดฟังก์ชั่นที่เรียกว่า `App`

`App` นั้นเป็นฟังก์ชั่นที่ติดตัวมาและตัวอย่างที่โปรแกรมให้มาทำการ `return` อะไรที่มันดูแปลกๆ

ดูเหมือนว่าจะทั้ง `HTM`L แล้วก็มี `JavaScript` ฝังอยู่ในนั้นด้วย

เพื่อง่ายขึ้นเราจะทำเป็นแบบนี้กันเริ่ม:

```jsx
function App() {
  return <p>test</p>;
}
```

นั่นคือ `JSX` ซึ่งเป็นภาษาพิเศษที่เราใช้ในการสร้างเอาต์พุตของคอมโพเนนต์

และเราจะพูดถึง `JSX` เพิ่มเติมในหัวข้อถัดไป

และที่จริงแล้วคอมโพเนนต์ก็คือฟังก์ชัน ดังนั้นคุณสามารถใช้ Arrow Function (ฟังก์ชันลูกศร) เพื่อกำหนดมันได้แบบนี้:

```
const App = () => {
  return <p>test</p>
}
```

ข้อแตกต่างหลักตรงนี้คืออย่าแรกคือฟังก์ชั่นแต่ละตัวจะมีชื่อเป็นของตัวเอง ดังนั้นเมื่อคุณพบข้อผิดพลาด คุณจะเห็นชื่อของคอมโพเนนต์ในข้อความแสดงข้อผิดพลาด ซึ่งเป็นสิ่งที่ดีไม่กลัวไป

นอกเหนือจากการกำหนด `JSX` เพื่อใช้ return แล้วคอมโพเนนต์ยังมีลักษณะอื่นๆ อีกหลายประการ

คอมโพเนนต์ สามารถมี `สถานะ (state)` ของตัวเองได้ ซึ่งหมายความว่ามันอาจจะห่อหุ้มด้วยตัวแปรบางตัวจากคอมโพเนนต์อื่น ที่จะไม่สามารถเข้าถึงได้หากคอมโพเนนต์นี้ไม่ได้เปิดเผย `สถานะ (state) `นี้ให้กับแอปพลิเคชันอื่นๆ

คอมโพเนนต์ ยังสามารถรับข้อมูลจากคอมโพเนนต์อื่นๆ ได้ ในกรณีนี้ ที่เราพูดถึงตือ `พร็อพส์ (props)`

อย่ากังวลไป เราจะพาเข้าไปดูรายละเอียดของคำศัพท์เหล่านั้นทั้งหมดทั้ง (JSX, State และ Props) ในเร็วๆนี้
