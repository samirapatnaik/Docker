<h1 style="font-size:28px;">Frontend Web Application Deployment using Docker on AWS EC2</h1>

<h2 style="font-size:22px;">Project Overview</h2>
<p style="font-size:16px;">
This project demonstrates the deployment of a static frontend web application using Docker on an AWS EC2 instance. The application is served through an Nginx container, providing a lightweight, scalable, and production-ready environment without requiring a traditional backend server.
</p>

<h2 style="font-size:22px;">Architecture</h2>
<p style="font-size:16px;">
User Browser → EC2 Instance → Docker Container → Nginx → Static Files (HTML, CSS, JavaScript)
</p>

<h2 style="font-size:22px;">Technologies Used</h2>
<ul style="font-size:16px;">
<li>Docker – Containerization platform</li>
<li>Nginx – Web server for serving static content</li>
<li>AWS EC2 – Cloud compute service</li>
<li>HTML, CSS, JavaScript – Frontend technologies</li>
<li>Git – Version control</li>
</ul>

<h2 style="font-size:22px;">Project Structure</h2>

<pre style="font-size:15px;">
frontend-app/
│── Dockerfile
│── index.html
│── style.css
│── script.js
</pre>

<h2 style="font-size:22px;">Docker Configuration</h2>

<pre style="font-size:15px;">
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
</pre>

<h2 style="font-size:22px;">Deployment Steps</h2>

<h3 style="font-size:18px;">1. Clone Repository</h3>
<pre style="font-size:15px;">
git clone https://github.com/samirapatnaik/Docker.git
cd Docker/frontend-app
</pre>

<h3 style="font-size:18px;">2. Build Docker Image</h3>
<pre style="font-size:15px;">
sudo docker build -t frontend-app .
</pre>

<h3 style="font-size:18px;">3. Run Container</h3>
<pre style="font-size:15px;">
sudo docker run -d -p 80:80 --name frontend-container frontend-app
</pre>

<h3 style="font-size:18px;">4. Access Application</h3>
<pre style="font-size:15px;">
http://&lt;EC2-PUBLIC-IP&gt;
</pre>

<h2 style="font-size:22px;">AWS Configuration</h2>
<table style="font-size:16px;">
<tr><th>Type</th><th>Port</th><th>Source</th></tr>
<tr><td>HTTP</td><td>80</td><td>0.0.0.0/0</td></tr>
</table>

<h2 style="font-size:22px;">Features</h2>
<ul style="font-size:16px;">
<li>Lightweight deployment using Docker</li>
<li>No backend server required</li>
<li>Fast and scalable architecture</li>
<li>Responsive and clean UI</li>
<li>Easy to deploy and maintain</li>
</ul>

<h2 style="font-size:22px;">Troubleshooting</h2>

<h3 style="font-size:18px;">Website not loading</h3>
<pre style="font-size:15px;">
sudo docker ps
</pre>

<h3 style="font-size:18px;">CSS not applied</h3>
<pre style="font-size:15px;">
sudo docker exec -it frontend-container ls /usr/share/nginx/html
</pre>

<h3 style="font-size:18px;">Changes not reflecting</h3>
<pre style="font-size:15px;">
sudo docker build --no-cache -t frontend-app .
</pre>

<h2 style="font-size:22px;">Future Enhancements</h2>
<ul style="font-size:16px;">
<li>Implement CI/CD using GitHub Actions</li>
<li>Integrate custom domain with HTTPS</li>
<li>Use Docker Compose for multi-container setup</li>
<li>Add backend services</li>
</ul>

<h2 style="font-size:22px;">Author</h2>
<p style="font-size:16px;">
Behera Samira Patnaik<br>
BTech ECE | Cloud and DevOps Enthusiast
</p>

<h2 style="font-size:22px;">License</h2>
<p style="font-size:16px;">
This project is intended for educational and learning purposes.
</p>
