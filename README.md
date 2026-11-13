# React Lab Exercise 12(B): Simulate an Asynchronous Operation Using React
## Name: LOGESH S
## Roll no: 2305001014
## Department: CSE

## AIM
To develop a React application that simulates an asynchronous operation using setTimeout() and displays a loading message while the operation is in progress.

## PROGRAM

### i) App.jsx

```javascript
import { useState } from "react";
import "./App.css";

function App() {
  const [loading, setLoading] = useState(false);
  const [message, setMessage] = useState("");

  const startOperation = () => {
    setLoading(true);
    setMessage("");

    setTimeout(() => {
      setLoading(false);
      setMessage(
        "Student Name: Aravindan T\nDepartment: CSE\nYear: IV\nStatus: Data Loaded Successfully"
      );
    }, 3000);
  };

  return (
    <div className="container">
      <h1>Asynchronous Operation</h1>

      <button onClick={startOperation} disabled={loading}>
        {loading ? "Fetching..." : "Fetch Student"}
      </button>

      {loading && (
        <div className="loading">
          Fetching student information...
        </div>
      )}

      {!loading && message && (
        <div className="result">
          {message.split("\n").map((line, index) => (
            <p key={index}>{line}</p>
          ))}
        </div>
      )}
    </div>
  );
}

export default App;
```

### ii) App.css

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #f1f5f9;
}

.container {
  max-width: 600px;
  margin: 80px auto;
  padding: 30px;
  text-align: center;
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 4px 12px #0000001a;
}

h1 {
  color: darkblue;
}

button {
  padding: 12px 24px;
  background-color: #2563eb;
  color: white;
  border: none;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
}

button:hover {
  background-color: #1d4ed8;
}

button:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.loading {
  margin-top: 25px;
  color: #d97706;
  font-size: 17px;
}

.result {
  margin-top: 25px;
  padding: 20px;
  text-align: left;
  background-color: #dcfce7;
  border: 1px solid #86efac;
  border-radius: 8px;
}

.result p {
  margin: 10px 0;
  color: #166534;
  font-size: 16px;
}
```

## OUTPUT
<img width="970" height="436" alt="image" src="https://github.com/user-attachments/assets/15294069-d2a2-4f1c-aa1d-0da046a685c6" />
<img width="987" height="615" alt="image" src="https://github.com/user-attachments/assets/425be8cf-e93c-4a68-a8ac-29551ef3721a" />

## RESULT

Thus, a React application was developed successfully using Axios to retrieve sample user information from a REST API and display the details with loading and error handling.
