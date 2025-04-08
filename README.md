# my-assignment
import { useState } from "react";
import "./App.css"; 

export default function App() {
  const [items, setItems] = useState([]);
  const [input, setInput] = useState("");

  const addItem = () => {
    if (input.trim() === "") return;
    setItems([...items, input]);
    setInput("");
  };

  return (
    <div className="container">
      <h1 className="title">Dynamic List Manager</h1>
      <div className="inputcontainer">
        <input
          type="text"
          value={input}
          onChange={(e) => setInput(e.target.value)}
          placeholder="Enter an item..."
          className="inputfield"
        />
        <button onClick={addItem} className="addbutton">
          Add Item
        </button>
      </div>
      <div className="listwrapper">
        <ul>
          {items.map((item, index) => (
            <li key={index} className="list-item">
              {item}
            </li>
          ))}
        </ul>
      </div>
    </div>
  );


  body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f4f4f4;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container {
  background-color: white;
  padding: 30px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  width: 500px;
  max-width: 100%;

}

.title {
  margin-bottom: 20px;
  color: #009688;
  text-align: left;
  font-size: 24px;
}

.inputcontainer {
  display: flex;
  margin-bottom: 15px;
  border-color: aqua;
}

.inputfield {
  flex: 1;
  padding: 10px;
  text-emphasis-color: black;
  border: 1px solid #00bfa5;
  border-radius: 5px 0 0 5px;
  outline: none;
  background-color: white;
  color: #333;
  font-size: 16px;
  font-weight: 500;
}

.addbutton {
  padding: 10px 16px;
  background-color: #00bfa5;
  color: white;
  cursor: pointer;
  font-weight: 500;
  border-radius: 0 5px 5px 0;
  outline: none;
  font-size: 16px;
  transition: background-color 0.3s ease;
  border: 1px solid #00bfa5;
  }

.addbutton:hover {
  background-color: #009688;
}


.listwrapper {
  background-color: #f0fefc;
  border: 1px solid #00bfa5;
  border-radius: 5px;
  padding: 10px;
  height: 200px;
  overflow-y: auto;
}

.list-item {
  color: hsl(173, 100%, 24%);
  margin-bottom: 8px;
  font-weight: 500
}
