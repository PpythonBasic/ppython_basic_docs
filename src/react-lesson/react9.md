# React: Component props พร็อพของคอมโพเนนต์

เราเรียก `props` เป็นค่าเริ่มต้นที่ส่งไปยังคอมโพเนนต์

ทำการสร้างคอมโพเนนต์ `WelcomeMessage` ได้ในลักษณะดังนี้:

```jsx
function WelcomeMessage() {
  return <p>Welcome!</p>;
}
```

หรือแบบนี้ก็ได้

```jsx
const WelcomeMessage = () => {
  return <p>Welcome!</p>;
};
```

และเราจะใช้งานได้ด้วย

```jsx
<WelcomeMessage />
```

ซึ่งคอมโพเนนต์นี้ไม่มีค่าเริ่มต้นอะไรและมันก็ไม่มี `props` ด้วยเหมือนกัน
แต่ว่า `props` สามารถส่งโดยมันเข้ามาได้โดยผ่าน attributes ใน JSX ได้ในลักษณะแบบนี้:

```jsx
<WelcomeMessage myprop={"somevalue"} />
```

และภายในคอมโพเนนต์ตรงสร้างที่สร้างขึ้นเป็นฟังก์ชันเราจะรับ`props`เป็นอาร์กิวเมนต์แบบนี้:

```jsx
function WelcomeMessage(props) {
  return <p>Welcome!</p>;
}
```

หรือแบบนี้ก็ได้

```jsx
const WelcomeMessage = (props) => {
  return <p>Welcome!</p>;
};
```

แต่ว่าใน jsx เราจะต้องรับเข้ามาโดยจะใช้เป็น `object destructuring` เพื่อรับ`props`ตามชื่อนั้นๆ:

```jsx
function WelcomeMessage({ props }) {
  return <p>Welcome!</p>;
}
```

หรือแบบนี้ก็ได้

```jsx
const WelcomeMessage = ({ props }) => {
  return <p>Welcome!</p>;
};
```

ตอนนี้ `myprop` เป็นหนึ่งใน`props`ที่มีอยู่ใน`props object` เช่นนี้: `{ myprop: 'test' } ` การใช้ syntax นี้จะเป็นการแยกเฉพาะ `myprop` ออกมา

ตอนนี้เรามี `prop` เรียบร้อยแล้ว เราก็จะสามารถใช้มันภายในส่วนของคอมโพเนนต์ได้ เช่น เราสามารถพิมพ์ค่าของมันลงใน JSX ได้ในลักษณะนี้:

```jsx
function WelcomeMessage({ myprop }) {
  return <p>{myprop}</p>;
}
```

หรือแบบนี้ก็ได้

```jsx
const WelcomeMessage = ({ props }) => {
  return <p>{myprop}</p>;
};
```

วงเล็บปีกกาในที่นี้มีความหมายได้หลากหลาย แต่ในกรณีของอาร์กิวเมนต์ฟังก์ชัน วงเล็บปีกกาจะใช้เป็นส่วนหนึ่งของ syntax `object destructuring`

จากนั้นเราสามารถใช้มันในการกำหนดบล็อกโค้ดฟังก์ชันได้
และในท้ายที่สุดใน JSX สามารถใช้มันเมื่อเราต้องการค่าอะไรก็ตามใน JavaScript ออกมาแสดงผลได้

การส่งผ่าน`props`ไปยังคอมโพเนนต์ เป็นวิธีที่ดีในการส่งผ่านค่าต่างๆ ภายในแอปพลิเคชันของคุณ

นอกจากนี้เรายังสามารถส่งฟังก์ชันที่ผ่าน`props`ได้อีกด้วยดังนั้นคอมโพเนนต์ลูกจึงสามารถเรียกใช้ฟังก์ชันในคอมโพเนนต์แม่ได้

`props`พิเศษที่ชื่อ `children` จะค่าของข้อมูลที่ถูกส่งเข้ามาในช่องระหว่างแท็กเปิดและแท็กปิดของคอมโพเนนต์ เช่น:

```jsx
<WelcomeMessage>ข้อความอะไรสักอย่าง</WelcomeMessage>
```

ในกรณีนี้ ภายใน `WelcomeMessage` เราสามารถเข้าถึงค่าข้อมูลของคำว่า `ข้อความอะไรสักอย่าง` โดยใช้ `props`พิเศษที่ชื่อว่า `children` ได้:

```jsx
function WelcomeMessage({ children }) {
  return <p>{children}</p>;
}
```

หรือแบบนี้ก็ได้

```jsx
const WelcomeMessage = ({ children }) => {
  return <p>{children}</p>;
};
```
