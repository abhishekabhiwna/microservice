<h3>README</h3>
<hr>
<h1>Video to MP3 Conversion Microservice</h1>
<h2>Overview</h2>
<p>This project provides a microservice architecture for converting video files into MP3 audio files. It includes user authentication, video storage, asynchronous processing, and notification services.</p>
<h2>Architecture</h2>
<ul>
<li>
<strong>Auth Service</strong>: Manages user authentication using JWT and stores user details in MySQL.</li>
<li>
<strong>Gateway Service</strong>: Facilitates communication between services and the message queue.</li>
<li>
<strong>Video Upload API</strong>: Handles video uploads and stores them in MongoDB using GridFS.</li>
<li>
<strong>Video to MP3 Converter Service</strong>: Converts video files to MP3 and stores them in MongoDB.</li>
<li>
<strong>Notification Service</strong>: Sends email notifications to users after conversion.</li>
<li>
<strong>Download API</strong>: Allows users to download the converted MP3 files.</li>
</ul>
<h2>Tech Stack</h2>
<ul>
<li>
<strong>Python</strong>
</li>
<li>
<strong>Flask</strong>
</li>
<li>
<strong>Docker</strong>
</li>
<li>
<strong>Kubernetes</strong>
</li>
<li>
<strong>RabbitMQ</strong>
</li>
<li>
<strong>MongoDB</strong>
</li>
<li>
<strong>MySQL</strong>
</li>
<li>
<strong>JWT</strong>
</li>
<li>
<strong>SMTP</strong>
</li>
</ul>
<h2>Setup and Installation</h2>
<h3>Prerequisites</h3>
<ul>
<li>Docker</li>
<li>Kubernetes</li>
<li>RabbitMQ</li>
<li>MongoDB</li>
<li>MySQL</li>
</ul>
<h3>Steps</h3>
<ol>
<li>
<p>
<strong>Clone the Repository</strong>:</p>
<pre dir="ltr" class="w-full"><div class="dark bg-black mb-4 rounded-md">

<div class="p-4 overflow-y-auto">
<code id="code-content" class="!whitespace-pre hljs language-sh">git <span class="hljs-built_in">clone</span> https://github.com/yourusername/video-to-mp3-microservice.git
<span class="hljs-built_in">cd</span> video-to-mp3-microservice
</code>
</div>
</div>
</pre>
</li>
<li>
<p>
<strong>Build Docker Images</strong>:</p>
<pre dir="ltr" class="w-full"><div class="dark bg-black mb-4 rounded-md">

<div class="p-4 overflow-y-auto">
<code id="code-content" class="!whitespace-pre hljs language-sh">docker build -t auth-service ./auth
docker build -t gateway-service ./gateway
docker build -t video-upload-service ./video-upload
docker build -t converter-service ./converter
docker build -t notification-service ./notification
docker build -t download-service ./download
</code>
</div>
</div>
</pre>
</li>
<li>
<p>
<strong>Deploy to Kubernetes</strong>:</p>
<pre dir="ltr" class="w-full"><div class="dark bg-black mb-4 rounded-md">

<div class="p-4 overflow-y-auto">
<code id="code-content" class="!whitespace-pre hljs language-sh">kubectl apply -f k8s/auth-deployment.yaml
kubectl apply -f k8s/gateway-deployment.yaml
kubectl apply -f k8s/video-upload-deployment.yaml
kubectl apply -f k8s/converter-deployment.yaml
kubectl apply -f k8s/notification-deployment.yaml
kubectl apply -f k8s/download-deployment.yaml
</code>
</div>
</div>
</pre>
</li>
<li>
<p>
<strong>Start Minikube Tunnel</strong>:</p>
<pre dir="ltr" class="w-full"><div class="dark bg-black mb-4 rounded-md">

<div class="p-4 overflow-y-auto">
<code id="code-content" class="!whitespace-pre hljs language-sh">minikube tunnel
</code>
</div>
</div>
</pre>
</li>
<li>
<p>
<strong>Configure RabbitMQ and Databases</strong>:</p>
<ul>
<li>Set up RabbitMQ queues for video and audio processing.</li>
<li>Configure MongoDB for GridFS.</li>
<li>Set up MySQL database for user authentication.</li>
</ul>
</li>
</ol>
<h2>Usage</h2>
<ol>
<li>
<p>
<strong>Authenticate User</strong>:</p>
<ul>
<li>Call the Auth Service to authenticate and get a JWT token.</li>
</ul>
</li>
<li>
<p>
<strong>Upload Video</strong>:</p>
<ul>
<li>Use the Video Upload API to upload a video file and get a video ID.</li>
</ul>
</li>
<li>
<p>
<strong>Video Conversion</strong>:</p>
<ul>
<li>The video ID is sent to the video queue. The Converter Service processes the video and converts it to MP3.</li>
</ul>
</li>
<li>
<p>
<strong>Notification</strong>:</p>
<ul>
<li>The Notification Service sends an email to the user once the conversion is complete.</li>
</ul>
</li>
<li>
<p>
<strong>Download MP3</strong>:</p>
<ul>
<li>Call the Download API, authenticate, and download the converted MP3 file.</li>
</ul>
</li>
</ol>
<h2>Contributing</h2>
<p>Contributions are welcome! Please create an issue or submit a pull request.</p>
<h2>License</h2>
<p>This project is licensed under the MIT License.</p>
<hr>
</div>