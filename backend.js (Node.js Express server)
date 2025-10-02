import express from "express";
import fetch from "node-fetch";
import cors from "cors";

const app = express();
app.use(cors());
app.use(express.json());

const OPENAI_KEY = "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";

app.post("/chat", async (req, res) => {
  const userMessage = req.body.message;

  const response = await fetch("https://api.openai.com/v1/chat/completions", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      "Authorization": `Bearer ${OPENAI_KEY}`
    },
    body: JSON.stringify({
      model: "gpt-4o-mini",
      messages: [{ role: "user", content: userMessage }]
    })
  });

  const data = await response.json();
  res.json(data);
});

app.listen(3000, () => console.log("Server running on http://localhost:3000"));
