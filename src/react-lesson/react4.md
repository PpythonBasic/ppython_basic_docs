# React : รู้เบื้องต้นเกี่ยวกับ JSX

เราจะไม่สามารถพูดถึง React ได้เลยหากไม่อธิบาย JSX ก่อน

คุณได้พบกับ React คอมโพเนนต์ แรกของคุณไปแล้ว ซึ่งเป็น คอมโพเนนต์ ของแอปที่กำหนดไว้ในแอปพลิเคชันเริ่มต้นที่เราสร้างโดยใช้ Vite

โค้ดของมันคือ:

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

ก่อนหน้านี้เราได้ละเลยทุกสิ่งที่อยู่ในคำสั่ง return และในส่วนนี้ เราจะพูดถึงมัน

เราจะเรียก `JSX` ทุกอย่างที่อยู่ภายใน `return (..)` มาให้แบบนี้ ว่าอะไรคือสิ่งที่เราเรียกว่า `JSX` กันแน่

```jsx
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
```

ลักษณะดูเหมือน HTML แต่ก็ไม่ใช่ HTML จริงๆ เพราะมันแตกต่างออกไปเล็กน้อย

และมันก็แปลกนิดหน่อยที่จะมีโค้ด HTML ลักษณะนี้อยู่ในไฟล์ JavaScript นี่ดูไม่เหมือน JavaScript เลย!

ภายใต้หลังคาของ React จะทำการประมวลผล JSX จากนั้นก็จะแปลงไปเป็น JavaScript ที่เบราว์เซอร์สามารถเข้าใจได้

ในขณะที่เราเขียน `JSX` ไปแต่ยังไงในท้ายที่สุดแล้ว ก็จะมีขั้นตอนการแปลที่ทำให้สามารถย่อยเป็น JavaScript

React ให้เราเราแบบนี้ก็ด้วยเหตุผลเดียวคือ `การสร้างอินเทอร์เฟซ UI โดยใช้ JSX นั้นง่ายกว่า`

เมื่อคุณจะคุ้นเคยกับมันมากขึ้นแล้วแน่นอนว่า

ในหัวข้อถัดไป เราจะพูดถึงวิธีที่ JSX ช่วยให้คุณสร้าง UI ได้อย่างง่ายดาย จากนั้นเราจะมาดูความแตกต่างกับ `HTML ปกติ` ที่คุณต้องรู้กัน
