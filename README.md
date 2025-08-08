<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>PortPro TMS Generator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 2rem;
      background-color: #f4f4f4;
    }
    h1 {
      color: #333;
    }
    button {
      margin: 1rem;
      padding: 1rem 2rem;
      font-size: 1rem;
      cursor: pointer;
      border: none;
      border-radius: 5px;
      background-color: #007bff;
      color: white;
    }
    button:hover {
      background-color: #0056b3;
    }
  </style>
</head>
<body>
  <h1>🚛 PortPro TMS Excel Generator</h1>
  <button id="connectionTest">🧪 Test Download</button>
  <button id="simpleTest">📄 Generate Simple TMS</button>
  <button id="fullBtn">📊 Generate Complete TMS</button>

  <script>
    function connectionTest() {
      alert("Connection test successful!");
    }

    function simpleTestFile() {
      const csvContent = "data:text/csv;charset=utf-8,Load ID,Customer,Status\n1234,Acme Corp,Delivered";
      const encodedUri = encodeURI(csvContent);
      const link = document.createElement("a");
      link.setAttribute("href", encodedUri);
      link.setAttribute("download", "simple_tms.csv");
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }

    function generateCompleteTMS() {
      const csvContent = "data:text/csv;charset=utf-8,Load ID,Customer,Status,Driver,ETA\n5678,Globex Inc,In Transit,John Doe,2025-08-10";
      const encodedUri = encodeURI(csvContent);
      const link = document.createElement("a");
      link.setAttribute("href", encodedUri);
      link.setAttribute("download", "complete_tms.csv");
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }

    document.addEventListener("DOMContentLoaded", function () {
      document.getElementById("connectionTest").addEventListener("click", connectionTest);
      document.getElementById("simpleTest").addEventListener("click", simpleTestFile);
      document.getElementById("fullBtn").addEventListener("click", generateCompleteTMS);
    });
  </script>
</body>
</html>
