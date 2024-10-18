<h1>AI ChatApp</h1>

<p>A modern AI-driven chat application built using React that leverages the Gemini API for natural language processing. 
   <br>The app provides dynamic conversations and real-time responses, enhancing user interaction through an intuitive interface.</p>

<h2>Features</h2>
<ul>
  <li>Interactive chat interface for seamless communication.</li>
  <li>Utilizes the Gemini API for intelligent responses.</li>
  <li>Dynamic pages that adjust based on user input.</li>
  <li>Responsive design for optimal user experience across devices.</li>
</ul>

<h2>Technologies Used</h2>
<ul>
  <li><strong>React</strong> – Frontend framework for building user interfaces.</li>
  <li><strong>Gemini API</strong> – AI-powered API for processing natural language.</li>
  <li><strong>CSS/HTML</strong> – For styling and layout.</li>
</ul>

<h2>Prerequisites</h2>
<p>Make sure you have the following installed on your machine:</p>
<ul>
  <li><a href="https://nodejs.org">Node.js</a> (v12+)</li>
  <li><a href="https://www.npmjs.com/">npm</a> (Node package manager, usually installed with Node.js)</li>
</ul>

<h2>Installation</h2>
<ol>
  <li>Clone the repository:
    <pre><code>git clone https://github.com/your-username/ai-chatapp.git
cd ai-chatapp</code></pre>
  </li>
  <li>Install dependencies:
    <pre><code>npm install</code></pre>
  </li>
  <li>Set up your environment variables:
    <p>Create a <code>.env</code> file in the root of the project and add your Gemini API key:</p>
    <pre><code>REACT_APP_GEMINI_API_KEY=your_gemini_api_key</code></pre>
  </li>
</ol>

<h2>Usage</h2>
<ol>
  <li>Run the application:
    <pre><code>npm start</code></pre>
  </li>
  <li>Open your browser and navigate to <code>http://localhost:3000</code> to start chatting with the AI.</li>
</ol>

<h2>Example Output</h2>
<pre><code>User: Hello, how are you?
AI: I'm just a computer program, but I'm here to help you! How can I assist you today?</code></pre>

<h2>Project Structure</h2>
<pre><code>ai-chatapp/
│
├── public/              # Public assets and index.html
├── src/                 # Main application source code
│   ├── components/      # Reusable components
│   ├── pages/           # Dynamic pages
│   ├── App.js           # Main app component
│   └── index.js         # Entry point
├── .env                 # Environment variables
├── package.json         # Node.js dependencies and scripts
└── README.md            # Documentation</code></pre>

<h2>Code Overview</h2>
<p>Here’s a simple example of how to use the Gemini API in your chat application:</p>
<pre><code>import React, { useState } from 'react';
import axios from 'axios';

const ChatComponent = () => {
  const [message, setMessage] = useState('');
  const [responses, setResponses] = useState([]);

  const sendMessage = async () => {
    const res = await axios.post('https://api.gemini.com/v1/chat', {
      message: message,
    });
    setResponses([...responses, { user: message, ai: res.data.response }]);
    setMessage('');
  };

  return (
    <div>
      <div>
        {responses.map((res, index) => (
          <div key={index}>
            <strong>User:</strong> {res.user}<br />
            <strong>AI:</strong> {res.ai}
          </div>
        ))}
      </div>
      <input 
        type="text" 
        value={message} 
        onChange={(e) => setMessage(e.target.value)} 
      />
      <button onClick={sendMessage}>Send</button>
    </div>
  );
};</code></pre>

<h2>Contributing</h2>
<p>Contributions are welcome! Feel free to open an issue or submit a pull request for improvements.</p>

<h2>License</h2>
<p>This project is licensed under the MIT License. See the <code>LICENSE</code> file for more details.</p>

<h2>Contact</h2>
<p>Created by <a href="https://github.com/jenasuraj">Suraj jena</a></p>

