<div class="markdown prose w-full break-words dark:prose-invert dark">

<h1>Django Channels Chat App</h1>

<p>This repository contains a simple chat application built with Django Channels, a library that extends Django to handle WebSocket and asynchronous tasks.</p>

<h2>Features</h2>

<ul>
<li>Real-time chat messages using WebSockets</li>
<li>Multiple chat rooms with unique URLs</li>
<li>Automatic disconnection of inactive users</li>
</ul>

<h2>Installation</h2>

<ol>
<li><p>Clone the repository:</p><pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><button class="flex ml-auto gap-2"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="h-4 w-4" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg></button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">git <span class="hljs-built_in">clone</span> https://github.com/SaiedZ/django_async_chatroom_channels
<span class="hljs-built_in">cd</span> django-channels-chat-app
</code></div></div></pre></li><li><p>Create and activate a virtual environment:</p><pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><button class="flex ml-auto gap-2"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="h-4 w-4" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg></button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">python3 -m venv <span class="hljs-built_in">env</span>
<span class="hljs-built_in">source</span> <span class="hljs-built_in">env</span>/bin/activate  <span class="hljs-comment"># on Linux/macOS</span>
<span class="hljs-built_in">env</span>\Scripts\activate  <span class="hljs-comment"># on Windows</span>
</code></div></div></pre></li><li><p>Install the dependencies:</p><pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><button class="flex ml-auto gap-2"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="h-4 w-4" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg></button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">pip install -r requirements.txt
</code></div></div></pre></li><li><p>Run the Django development server:</p><pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><button class="flex ml-auto gap-2"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="h-4 w-4" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg></button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">python manage.py runserver
</code></div></div></pre><p>The chat app will be available at <a href="http://localhost:8000/" target="_new">http://localhost:8000/</a>.</p></li></ol><h2>Usage</h2><ol><li><p>Open the chat app in your web browser:</p><pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>http</span><button class="flex ml-auto gap-2"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="h-4 w-4" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg></button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-http">http://localhost:8000/
</code></div></div></pre></li><li><p>Enter a username and click "Join Chat".</p></li><li><p>Create or join a chat room by entering a room name in the text box and clicking "Create/Join Room".</p></li><li><p>Start chatting with other users in the chat room.</p></li><li><p>If you're inactive for more than 5 minutes, you will be automatically disconnected from the chat room.</p></li></ol><h2>Technologies Used</h2><ul><li>Django</li><li>Django Channels</li><li>JavaScript</li><li>HTML/CSS</li><li>Bootstrap</li></ul>

<h2>License</h2>

<p>This project is licensed under the MIT License - see the <a href="LICENSE" target="_new">LICENSE</a> file for details.</p></div>
