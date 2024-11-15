# MakeMySheet 🎹

Welcome to **MakeMySheet**, an AI-powered tool designed to convert music audio into sheet music. Whether you input a music file or a YouTube link, our tool seamlessly generates music sheets that are easy to download, share, and play back.

MakeMySheet was developed as part of the NUS Orbital 2024 program, and we are excited to offer this service to musicians, hobbyists, and students alike.

### [Visit MakeMySheet](https://makemysheet.com) | [Try our Telegram Bot](https://t.me/makemysheet_bot)

## What It Does

MakeMySheet provides a streamlined experience for converting music into professional-quality piano sheet music. Here are some of the key features:

- **🎶 Music to Sheet Conversion**: Upload an audio file or enter a YouTube link to generate a downloadable music sheet in multiple formats (PDF, MIDI, MusicXML).
- **🎧 MIDI Playback**: Listen to the generated MIDI to assess the quality of the transcription and verify its accuracy.
- **🎸 Instrument Selection**: Choose the instrument of your preference for conversion. We leverage state-of-the-art machine learning models like **Pop2Piano** and **Spotify's Basic Pitch** for high-quality output.
- **🌍 Shareable Sheets**: Once converted, you can choose to share your music sheets with others or keep them private.
- **🤖 Telegram Bot**: Perform conversions right from your Telegram app using our [companion bot](https://t.me/makemysheet_bot).

## Architecture Overview

The architecture of MakeMySheet is designed with a modular approach, where services communicate with each other through APIs and message queues. Below is an overview of the key components:

### 1. Frontend (React, Next.js)
The frontend is built with **React** and **Next.js** to offer a smooth and responsive user experience. Users can upload files, manage their sheet music, and preview or download outputs. Additionally, our web app supports authentication through **Auth0**.

### 2. Backend (Node.js API Gateway)
The API gateway is implemented with **Node.js**, handling user requests and routing them to the appropriate services. It ensures secure communication between the frontend, machine learning service, and the database.

- **Authentication**: Managed via **Auth0** for secure access and user management.
- **Service Orchestration**: Handles requests and forwards them to the machine learning service for processing.

### 3. Machine Learning Service (Python)
This is the core of our conversion logic, where we integrate machine learning models such as **Pop2Piano** and **Spotify's Basic Pitch** to transform audio into sheet music.

- **ML Models**: Converts audio files into music sheets based on the chosen instrument.
- **Formats**: Outputs are available in **PDF**, **MIDI**, and **MusicXML** formats.
- **Self-hosted**: The service is containerized and deployed on **AWS EC2**, ensuring scalability.

### 4. Telegram Bot (Telegraf, Node.js)
We provide a **Telegram bot** for users who want to perform conversions without visiting the website. The bot interfaces with the backend to handle requests and deliver results directly to the user on Telegram.

### Additional Infrastructure
- **RabbitMQ**: Used for message queuing between the backend and the machine learning service to handle task distribution efficiently.
- **PostgreSQL (CockroachDB)**: Our database system is designed for reliability and scalability.
- **AWS S3**: Stores uploaded files and generated sheet music securely.
- **Docker Compose**: All services are containerized and orchestrated using **Docker Compose**.
- **Nginx**: Manages traffic and acts as a reverse proxy for load balancing.
- **CI/CD Pipeline**: Deployed using **GitHub Actions** for continuous integration and delivery.

## Acknowledgements
We are grateful for the mentorship and guidance provided by **[Santosh Jayamurugan](https://www.linkedin.com/in/santosh-jayamurugan-1066017/)** and **[Aishwarya Hariharan Iyer](https://www.linkedin.com/in/aishwarya-h-iyer/)**, who supported us throughout the development of this project.
