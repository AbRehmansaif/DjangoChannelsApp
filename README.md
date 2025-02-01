# Django Channels Chat App

A real-time chat application built using **Django Channels** and **WebSockets**. This app supports multiple chat rooms, real-time messaging, and is backed by **Redis** as a message broker.

## 📌 Features
- ✅ Real-time messaging using WebSockets
- ✅ Multiple chat rooms
- ✅ User authentication (Login/Signup)
- ✅ Django Channels with Redis
- ✅ Asynchronous consumers for better performance
- ✅ Scalable architecture with Docker support

---

## 🚀 Getting Started

Follow these steps to set up and run this project on your local machine.

### **1️⃣ Clone the Repository**
```bash
https://github.com/AbRehmansaif/DjangoChannelsApp.git
```

### **2️⃣ Create a Virtual Environment**
```bash
python -m venv venv
source venv/bin/activate  # For macOS/Linux
venv\Scripts\activate     # For Windows
```

### **3️⃣ Install Dependencies**
```bash
pip install -r requirements.txt
```

### **4️⃣ Configure Environment Variables**
Create a `.env` file in the root directory and add:

```ini
SECRET_KEY=your_secret_key
DEBUG=True
ALLOWED_HOSTS=127.0.0.1,localhost
REDIS_URL=redis://127.0.0.1:6379/1
```

> **Note:** Make sure Redis is running. If not, start it using:
```bash
redis-server
```

---

## 🛠️ **Database Migration**
```bash
python manage.py migrate
python manage.py createsuperuser  # Create an admin user
```

---

## 🔌 **Running the Server**
Run Django server:
```bash
python manage.py runserver
```

Run Django Channels worker:
```bash
daphne -b 0.0.0.0 -p 8001 config.asgi:application
```

---

## 📡 **How It Works**
1. Users register and log in.
2. Users join chat rooms and send messages.
3. Messages are delivered in **real-time** using WebSockets.
4. **Redis** is used as the **channel layer** to manage WebSocket connections efficiently.

---

## 📂 **Project Structure**
```
django-chat-app/
│── chat/                 # Chat application
│   ├── consumers.py      # Handles WebSocket connections
│   ├── routing.py        # WebSocket routes
│   ├── models.py         # Chat models
│   ├── views.py          # Chat views
│   ├── urls.py           # Chat URLs
│── users/                # User authentication
│── config/               # Project settings
│── requirements.txt      # Dependencies
│── manage.py             # Django management file
│── .env                  # Environment variables
```

---

## 📌 **API Endpoints**
| Endpoint           | Method | Description           |
|--------------------|--------|-----------------------|
| `/api/chat/`      | GET    | Get all chat rooms   |
| `/api/chat/<id>/` | GET    | Get chat messages    |
| `/api/chat/send/` | POST   | Send a message       |

---

## 🛠️ **Why Use Redis as a Database?**
Redis is used in **Django Channels** as a message broker and for WebSockets because:
- **Speed:** Redis is an in-memory database, making real-time messaging much faster.
- **Pub/Sub Mechanism:** Redis supports **publish-subscribe (Pub/Sub)** messaging, perfect for chat applications.
- **Scalability:** Multiple Django workers can communicate efficiently using Redis as a channel layer.
- **Persistence (Optional):** Redis can store messages for a short time if needed, ensuring reliability.

---

## 🐳 **Docker Setup (Optional)**

If you want to run this project with Docker, use the provided `docker-compose.yml` file.

### **1️⃣ Build & Start Containers**
```bash
docker-compose up --build
```

### **2️⃣ Stop Containers**
```bash
docker-compose down
```

---

## 💡 **Contributing**
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m "Added new feature"`).
4. Push to your branch (`git push origin feature-branch`).
5. Open a Pull Request.

---

## 🎯 **License**
This project is licensed under the **MIT License**.

---

## 💬 **Contact**
For any queries, feel free to reach out:  
📧 Email: abdulrehmanarain713@gmail.com  
🔗 GitHub: [yourusername](https://github.com/yourusername)

