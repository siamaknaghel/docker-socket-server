
# ⚡️ Socket Server (Dockerized)

A simple **Socket.IO + Express.js** server containerized with **Docker**. This project enables real-time communication between clients via WebSockets.

---

## 📁 Project Structure

```
socket-app/
├── docker-compose.yml       # Docker Compose service definition
└── socket-server/
    ├── Dockerfile           # Node.js Docker image config
    ├── index.js             # Main server code
    ├── package.json         # Dependencies list
    └── package-lock.json    # NPM lock file
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone git@github.com:siamaknaghel/docker-socket-server.git
cd socket-app
```

### 2. Build & Run with Docker Compose

```bash
docker-compose up --build
```

Once running, the server will be available at:

```
http://localhost:3000
```

---

## 🧠 Tech Stack

- [Node.js](https://nodejs.org/)
- [Express](https://expressjs.com/)
- [Socket.IO](https://socket.io/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

---

## 🛠️ Scripts

Inside `package.json`:

```json
"scripts": {
  "start": "node index.js"
}
```

---

## ⚙️ Docker Configuration

### `Dockerfile`

```dockerfile
FROM node:18

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000
CMD ["npm", "start"]
```

### `docker-compose.yml`

```yaml
version: '3'
services:
  socket-server:
    build:
      context: ./socket-server
      dockerfile: Dockerfile
    ports:
      - "3000:3000"
    volumes:
      - ./socket-server:/app
    working_dir: /app
    command: npm start
```

---

## 💬 Quick Test

You can test it using Postman or a basic Socket.IO client to connect to `localhost:3000`.

---

## 📄 License

This project is licensed under the MIT License.

---

## 🙌 Contributing

Feel free to open issues or submit pull requests. Contributions are welcome!

---

---

# ⚡️ سرور Socket (داکرایز شده)

یک سرور ساده با استفاده از **Socket.IO** و **Express.js** که با **Docker** کانتینرایز شده. این پروژه امکان ارتباط لحظه‌ای (real-time) بین کلاینت‌ها را فراهم می‌کند.

---

## 📁 ساختار پروژه

```
socket-app/
├── docker-compose.yml       # تعریف سرویس‌ها با Docker Compose
└── socket-server/
    ├── Dockerfile           # پیکربندی image برای Node.js
    ├── index.js             # کد اصلی سرور
    ├── package.json         # لیست وابستگی‌ها
    └── package-lock.json    # لاک فایل npm
```

---

## 🚀 شروع سریع

### ۱. کلون کردن مخزن

```bash
git clone git@github.com:siamaknaghel/docker-socket-server.git
cd socket-app
```

### ۲. ساخت و اجرای پروژه با Docker Compose

```bash
docker-compose up --build
```

بعد از اجرا، سرور روی آدرس زیر در دسترس خواهد بود:

```
http://localhost:3000
```

---

## 🧠 تکنولوژی‌های استفاده‌شده

- [Node.js](https://nodejs.org/)
- [Express](https://expressjs.com/)
- [Socket.IO](https://socket.io/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

---

## 🛠️ اسکریپت‌ها

در فایل `package.json`:

```json
"scripts": {
  "start": "node index.js"
}
```

---

## ⚙️ پیکربندی Docker

### فایل `Dockerfile`

```dockerfile
FROM node:18

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000
CMD ["npm", "start"]
```

### فایل `docker-compose.yml`

```yaml
version: '3'
services:
  socket-server:
    build:
      context: ./socket-server
      dockerfile: Dockerfile
    ports:
      - "3000:3000"
    volumes:
      - ./socket-server:/app
    working_dir: /app
    command: npm start
```

---

## 💬 تست سریع

می‌تونی با Postman یا کلاینت ساده‌ی Socket.IO به `localhost:3000` وصل بشی و تست کنی.

---

## 📄 مجوز

این پروژه تحت مجوز MIT ارائه شده است.

---

## 🙌 مشارکت

اگر مایل به همکاری هستی، خوشحال می‌شم Pull Request بزنی یا issue باز کنی.
