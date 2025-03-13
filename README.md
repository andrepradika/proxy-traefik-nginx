# 🌍 Traefik + Nginx Reverse Proxy  

## 📌 About  

This project sets up a **Traefik v2.5 reverse proxy** 🛡️ and an **Nginx container** 🌐 to manage traffic and securely route requests to your services. It uses **Let's Encrypt SSL certificates** 🔐 for secure HTTPS connections and makes it easy to handle domain-based routing.  

---

## 🚀 Features  

✅ **Traefik as Reverse Proxy** – Handles incoming traffic efficiently.  
✅ **Let's Encrypt SSL** – Automatic HTTPS with free SSL certificates.  
✅ **Dockerized Setup** 🐳 – Easily deploy and manage with Docker Compose.  
✅ **Domain-based Routing** 🌍 – Routes requests to different services.  
✅ **Nginx for Custom Proxying** – Acts as a secondary proxy for specific requests.  

---

## 📦 Services  

### 🔹 **Traefik (Reverse Proxy & SSL)**  
- Manages HTTP(S) traffic.  
- Automatically generates SSL certificates via **Let's Encrypt**.  
- Routes requests to services based on domain names.  

### 🔹 **Nginx (Custom Reverse Proxy)**  
- Serves as an additional proxy layer.  
- Configurable via `nginx.conf`.  
- Routes requests to `https://damarsalaka.com`.  

---

## 🛠️ Setup  

### 1️⃣ **Clone the Repository**  

```bash
git clone https://github.com/yourusername/proxy-traefik-nginx.git
cd proxy-traefik-nginx
```

### 2️⃣ **Create & Configure `nginx.conf`**  

Make sure your `nginx.conf` file exists in the project directory and is properly configured.  

### 3️⃣ **Run the Containers**  

```bash
docker-compose up -d
```

This will:  
✅ Start **Traefik** to handle traffic.  
✅ Start **Nginx** as a secondary reverse proxy.  
✅ Enable **SSL certificates** via Let's Encrypt.  

---

## 🔧 Configuration  

### 🌍 **Domain & SSL Configuration**  
Modify the `traefik` service labels in `docker-compose.yml` to match your **domain** and **email**:  

```yaml
- "traefik.http.routers.api.rule=Host(`traefik.yourdomain.com`)"
- "traefik.http.routers.salaka-proxy.rule=Host(`yourdomain.com`)"
- "--certificatesresolvers.myresolver.acme.email=your@email.com"
```

### 📄 **Custom Nginx Configuration**  
Update the `nginx.conf` file to customize the proxy behavior.  

---

## 📂 File Structure  

```
traefik-nginx-proxy/
│── letsencrypt/         # Stores SSL certificates
│── nginx.conf           # Nginx configuration
│── docker-compose.yml   # Docker Compose configuration
│── README.md            # Documentation
```

---

## 🏷️ Topics  

🔹 **Reverse Proxy** – Efficient traffic handling and load balancing.  
🔹 **Traefik** – Dynamic reverse proxy for Docker.  
🔹 **Nginx** – High-performance web server and proxy.  
🔹 **SSL & Security** – Automatic HTTPS with Let's Encrypt.  
🔹 **Docker & DevOps** – Containerized deployment.  

---

## 🛑 Stop & Remove Containers  

To stop and remove the services, run:  

```bash
docker-compose down
```

---

## 📜 License  

This project is **open-source** under the **MIT License**.  

---

Would you like any modifications or additions? 🚀😊