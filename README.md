<img width="1739" height="941" alt="Screenshot From 2025-07-29 22-45-28" src="https://github.com/user-attachments/assets/a2510d5e-ea48-499f-aed3-fa47c171ee59" />


# 🎨 Ghiblify ✨
*A Studio Ghibli-Inspired AI Art Generator*

Welcome to **Ghiblify**, a full-stack web application that transforms ordinary images or text prompts into enchanting Studio Ghibli-style artwork using the power of the **Stability AI API**. Crafted with a **Spring Boot** backend and a modern **React** frontend, Ghiblify brings the whimsical charm of Ghibli’s aesthetic to your fingertips.

---

## 🚀 Overview

Ghiblify is an innovative platform that leverages AI to generate Studio Ghibli-inspired artwork. Whether you upload an image or provide a text prompt, Ghiblify creates stunning visuals with a seamless and user-friendly interface. This project showcases full-stack development, integrating secure API communication, real-time previews, and responsive design.

---

## ✨ Features

- **🎨 Image-to-Image Transformation**: Upload an image and convert it into Ghibli-style artwork.
- **✍️ Text-to-Image Generation**: Create unique Ghibli-inspired images from text prompts.
- **🔁 Real-Time Previews**: View generated artwork with loading indicators and error fallbacks.
- **📷 Drag-and-Drop Upload**: Intuitive file upload system for images.
- **📦 Responsive UI**: Built with React for a smooth, device-friendly experience.
- **🔐 Secure Backend**: RESTful APIs with robust error handling using Spring Boot.
- **🌐 Deployment**: Frontend hosted on Vercel, backend powered by Spring Boot.

---

## 🧰 Tech Stack

### Frontend
- **React**: For building a dynamic and responsive user interface.
- **Axios**: For seamless HTTP requests to the backend.
- **Tailwind CSS**: For modern, utility-first styling (if used).

### Backend
- **Spring Boot (Java)**: For robust RESTful API development.
- **Feign Client**: For simplified communication with the Stability AI API.
- **RESTful APIs**: To handle image and text processing requests.

### AI Service
- **Stability AI API**: Powers Image-to-Image and Text-to-Image generation.

---

## 📂 Project Structure

```
ghibli-ai/
├── backend/                    # Spring Boot application
│   ├── src/main/java/
│   │   ├── controller/         # REST controllers for API endpoints
│   │   ├── service/            # Business logic for image processing
│   │   ├── client/             # Feign client for Stability AI API
│   │   └── model/              # Data models for requests and responses
│   └── pom.xml                 # Maven dependencies
├── frontend/                   # React application
│   ├── src/
│   │   ├── components/         # Reusable UI components
│   │   ├── pages/              # Page components (e.g., Home, Generate)
│   │   └── services/           # API service for backend communication
│   └── package.json            # Node.js dependencies
└── README.md                   # Project documentation
```

---

## 🛠️ Prerequisites

To set up and run Ghiblify, ensure you have the following installed:

- **Java**: JDK 17 or later (`java -version` to verify).
- **Node.js**: Version 18 or later (`node -v` to verify).
- **Maven**: Included with the Spring Boot project, no separate installation needed.
- **IDE**: IntelliJ IDEA (Community Edition) or Visual Studio Code recommended.
- **Stability AI API Key**: Obtain from [Stability AI](https://stability.ai/) for image generation.

---

## 🚀 Project Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/ghiblify.git
cd ghiblify
```

### 2. Backend Setup
1. **Navigate to the Backend Directory**:
   ```bash
   cd backend
   ```

2. **Configure Spring Boot**:
   - Open `src/main/resources/application.properties` and add your Stability AI API key:
     ```properties
     stability.ai.api-key=your-stability-ai-api-key
     ```
   - Ensure `pom.xml` includes necessary dependencies:
     ```xml
     <dependencies>
         <dependency>
             <groupId>org.springframework.boot</groupId>
             <artifactId>spring-boot-starter-web</artifactId>
         </dependency>
         <dependency>
             <groupId>org.openfeign</groupId>
             <artifactId>feign-core</artifactId>
             <version>${feign.version}</version>
         </dependency>
         <!-- Add other dependencies as needed -->
     </dependencies>
     ```

3. **Run the Backend**:
   - Build and run the Spring Boot application:
     ```bash
     mvn spring-boot:run
     ```
   - The backend will be available at `http://localhost:8080`.

### 3. Frontend Setup
1. **Navigate to the Frontend Directory**:
   ```bash
   cd frontend
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Configure API Endpoint**:
   - Update the API base URL in `frontend/src/services/api.js` (or equivalent) to point to your backend:
     ```javascript
     const API_BASE_URL = 'http://localhost:8080';
     ```

4. **Run the Frontend**:
   - Start the React development server:
     ```bash
     npm run start
     ```
   - Access the application at `http://localhost:3000`.

### 4. Deployment
- **Frontend**: Deploy the React app to Vercel:
  - Push the `frontend` directory to a GitHub repository.
  - Import the repository into Vercel and follow the deployment steps.
- **Backend**: Deploy the Spring Boot application to a cloud provider (e.g., AWS, Heroku) or a local server.
  - Package the backend:
    ```bash
    mvn package
    ```
  - Deploy the generated `.jar` file.

---

## 🌐 REST API Endpoints

### Image-to-Image
- **POST /api/generate/image**:
  - **Description**: Transform an uploaded image into Ghibli-style artwork.
  - **Request**: `multipart/form-data` with image file and optional parameters (e.g., style strength).
  - **Response**: Generated image URL or binary data.

### Text-to-Image
- **POST /api/generate/text**:
  - **Description**: Generate Ghibli-style artwork from a text prompt.
  - **Request**: JSON payload with `prompt` (e.g., "A serene forest with Ghibli-style trees").
  - **Response**: Generated image URL or binary data.

---

## 🧪 Testing

- **Local Testing**:
  - Test API endpoints using Postman or curl with sample images or text prompts.
  - Verify frontend functionality at `http://localhost:3000`.
- **Error Handling**:
  - Ensure proper fallback UI for API errors (e.g., invalid API key, file size limits).
- **Sample Test**:
  - Upload an image via the frontend and check for Ghibli-style output.
  - Submit a text prompt like "A cozy Ghibli village at sunset" and verify the result.

---

**Happy Ghiblifying!** 🎨✨
