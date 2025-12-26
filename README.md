<!DOCTYPE html>
<body>

<h1>🧠 RAG Assistant (FastEmbed + FAISS + Groq)</h1>

<p>
A <strong>Retrieval-Augmented Generation (RAG)</strong> application built with
<strong>Streamlit</strong>, <strong>FAISS</strong>, <strong>FastEmbed</strong>, and
<strong>Groq LLMs</strong>.  
It allows users to upload documents or provide links and ask questions that are answered
<strong>strictly from the provided content</strong>.
</p>

<hr />

<h2>🚀 Features</h2>
<ul>
  <li>📄 Supports multiple input types:
    <ul>
      <li>Web links</li>
      <li>PDF files</li>
      <li>DOCX files</li>
      <li>TXT files</li>
      <li>Raw text</li>
    </ul>
  </li>
  <li>🔍 Semantic search using FAISS</li>
  <li>🧩 Local embeddings via FastEmbed (Nomic Embed v1.5)</li>
  <li>⚡ Ultra-fast inference using Groq LLMs</li>
  <li>🛡️ Context-grounded answers (hallucination controlled)</li>
  <li>🧹 Clear session reset support</li>
  <li>🌐 Cloud deployable (Render / Fly.io / Railway)</li>
</ul>

<hr />

<h2>🏗️ Architecture Overview</h2>

<pre>
User Input
   ↓
Document Loader (Web / PDF / DOCX / TXT)
   ↓
Text Chunking (RecursiveCharacterTextSplitter)
   ↓
Embeddings (FastEmbed – Local)
   ↓
FAISS Vector Store
   ↓
Retriever (Top-K chunks)
   ↓
Groq LLM
   ↓
Answer (Context-only)
</pre>

<hr />

<h2>🧠 Tech Stack</h2>

<table>
  <tr>
    <th>Component</th>
    <th>Technology</th>
  </tr>
  <tr>
    <td>Frontend</td>
    <td>Streamlit</td>
  </tr>
  <tr>
    <td>Embeddings</td>
    <td>FastEmbed (nomic-embed-text-v1.5)</td>
  </tr>
  <tr>
    <td>Vector Database</td>
    <td>FAISS</td>
  </tr>
  <tr>
    <td>LLM</td>
    <td>Groq (LLaMA 3 / Mixtral)</td>
  </tr>
  <tr>
    <td>Language</td>
    <td>Python</td>
  </tr>
</table>

<hr />

<h2>📦 Installation (Local)</h2>

<h3>1️⃣ Clone the repository</h3>
<pre>
git clone https://github.com/&lt;your-username&gt;/rag-assistant.git
cd rag-assistant
</pre>

<h3>2️⃣ Install dependencies</h3>
<pre>
pip install -r requirements.txt
</pre>

<h3>3️⃣ Set Groq API key</h3>
<pre>
export GROQ_API_KEY=your_groq_api_key
</pre>

<p><strong>Windows (PowerShell)</strong></p>
<pre>
setx GROQ_API_KEY "your_groq_api_key"
</pre>

<h3>4️⃣ Run the app</h3>
<pre>
streamlit run app.py
</pre>

<p>Open in browser:</p>
<pre>
http://localhost:8501
</pre>

<hr />

<h2>☁️ Deployment (Render)</h2>

<div class="note">
This version is cloud-deployable because it does <strong>not</strong> depend on
Whisper, ffmpeg, or local model servers.
</div>

<h3>Render Configuration</h3>

<p><strong>Build Command</strong></p>
<pre>
pip install -r requirements.txt
</pre>

<p><strong>Start Command</strong></p>
<pre>
streamlit run app.py --server.port $PORT --server.address 0.0.0.0
</pre>

<p><strong>Environment Variable</strong></p>
<pre>
GROQ_API_KEY=your_groq_api_key
</pre>

<hr />

<h2>🧪 Supported Inputs</h2>

<table>
  <tr>
    <th>Input Type</th>
    <th>Supported</th>
  </tr>
  <tr>
    <td>Web URLs</td>
    <td>✅</td>
  </tr>
  <tr>
    <td>PDF</td>
    <td>✅</td>
  </tr>
  <tr>
    <td>DOCX</td>
    <td>✅</td>
  </tr>
  <tr>
    <td>TXT</td>
    <td>✅</td>
  </tr>
  <tr>
    <td>Raw Text</td>
    <td>✅</td>
  </tr>
  <tr>
    <td>YouTube / Audio</td>
    <td>❌ (not in this version)</td>
  </tr>
</table>

<hr />

<h2>🔐 Hallucination Control</h2>

<p>
The model is instructed to answer <strong>only</strong> from retrieved context.
If information is missing, it explicitly states that the answer is not available.
</p>

<hr />

<h2>⚠️ Limitations</h2>
<ul>
  <li>FAISS index is in-memory (resets on restart)</li>
  <li>Not suitable for very large documents</li>
  <li>Free cloud tiers may sleep after inactivity</li>
</ul>

<hr />

<h2>📈 Future Improvements</h2>
<ul>
  <li>Persistent vector storage</li>
  <li>User authentication</li>
  <li>Multi-document indexing</li>
  <li>Streaming responses</li>
  <li>YouTube/audio support (Whisper-based variant)</li>
</ul>

<hr />

<h2>👨‍💻 Author</h2>
<p>
<strong>Jagadeeswar Pattupogula</strong><br />
GitHub: <a href="https://github.com/JagadeeswarP" target="_blank">github.com/JagadeeswarP</a><br />
LinkedIn: <a href="https://www.linkedin.com/in/jagadeeswar-pattupogula" target="_blank">
linkedin.com/in/jagadeeswar-pattupogula</a>
</p>

<hr />

<h2>⭐ If you like this project</h2>
<ul>
  <li>Give it a ⭐ on GitHub</li>
  <li>Fork and experiment</li>
  <li>Use it as a base for advanced RAG systems</li>
</ul>

<div class="note">
<strong>Interview Tip:</strong><br />
This project demonstrates RAG fundamentals, vector search, prompt grounding,
and cloud-ready system design — ideal for AI / ML / Backend roles.
</div>

</body>
</html>
