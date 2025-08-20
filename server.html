const express = require("express");
const bodyParser = require("body-parser");
const cors = require("cors");
const sqlite3 = require("sqlite3").verbose();
const path = require("path");

const app = express();
const PORT = 5000;

// Middleware
app.use(cors());
app.use(bodyParser.json());
app.use(express.static(path.join(__dirname, "public"))); // serve frontend

// SQLite DB
const db = new sqlite3.Database("./orders.db", (err) => {
  if (err) console.error("Error opening DB:", err.message);
  else {
    db.run(
      `CREATE TABLE IF NOT EXISTS orders (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        name TEXT,
        mobile TEXT,
        item TEXT,
        quantity INTEGER,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
      )`
    );
  }
});

// Save order
app.post("/order", (req, res) => {
  const { name, mobile, item, quantity } = req.body;
  db.run(
    `INSERT INTO orders (name, mobile, item, quantity) VALUES (?, ?, ?, ?)`,
    [name, mobile, item, quantity],
    function (err) {
      if (err) {
        res.status(500).json({ success: false, error: err.message });
      } else {
        res.json({ success: true, orderId: this.lastID });
      }
    }
  );
});

// Get all orders
app.get("/orders", (req, res) => {
  db.all(`SELECT * FROM orders ORDER BY created_at DESC`, [], (err, rows) => {
    if (err) {
      res.status(500).json({ success: false, error: err.message });
    } else {
      res.json(rows);
    }
  });
});

app.listen(PORT, () =>
  console.log(`✅ Server running at http://localhost:${PORT}`)
);
