# Mini-UDP Bonn

A minimal Urban Data Platform prototype using [Civitas Core](https://github.com/m-u-s-t-a-f-a/civitas-core), Django, Docker, and simulated IoT sensor data.

This project was built to demonstrate hands-on skills in fullstack development and open data integration, using real-world smart city tools.

---

## 🎯 Purpose

This is a self-contained demo app simulating an urban data stream (e.g., temperature), forwarding it to Civitas Core, and displaying the data via a Django web interface.

---

## 🛠️ Tech Stack

- Docker & Docker Compose
- Civitas Core (data platform)
- Django (backend & visualization)
- PostgreSQL (database)
- Python (sensor simulator)
- Chart.js (frontend chart rendering)

---

## 📦 Setup

### 1. Clone the repository

```bash
git clone https://github.com/rompio/mini-udp-bonn.git
cd mini-udp-bonn
```

### 2. Start all services

```bash
docker-compose up --build
```

### 3. Run migrations and create admin user

```bash
docker exec -it web python manage.py migrate
docker exec -it web python manage.py createsuperuser
```

### 4. Start sensor simulation

```bash
python sensor_sim.py
```

## 🌡️ Features

- Simulates a temperature sensor (randomized values every 10 seconds)

- Pushes data to Civitas Core via REST API

- Django app fetches and visualizes data:

    - Line chart (Chart.js)

    - Data table

    - Django admin for database access

## 🧠 Learning Outcomes

- Integration of third-party open data tools (Civitas Core)

- Docker-based deployment of a multi-container environment

- Fullstack data flow: simulation → ingestion → visualization

- Chart.js integration with Django for live-like dashboards

### 📈 Future Improvements

- Add real sensor data (e.g., via MQTT)

- Multiple sensor types (noise, air quality, traffic)

- Real-time updates using Django Channels or WebSockets

- Add authentication (Keycloak, OAuth)

- Monitoring setup (Prometheus, Grafana)

📁 Project Structure

```bash
mini-udp-bonn/
├── django_backend/       # Django project
├── civitas_core/         # Civitas Core (submodule or cloned service)
├── sensor_sim.py         # Python script simulating sensor data
├── docker-compose.yml    # Multiservice orchestration
├── README.md
```

## 👨‍💻 Author

Roman Piontek
📧 piontekroman@googlemail.com
🛠️ July 2025
🔒 Disclaimer

This is a prototype built for educational and presentation purposes only. It is not intended for production use.