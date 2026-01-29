# React Hello World: Dockerization Guide

This guide covers the end-to-end process of setting up your environment, cloning the project, and deploying it inside a **Node v24.13.0** Docker container.

---

## 🛠 1. Environment Setup

Before starting, install the following essential tools:

* **VS Code:** [Download](https://code.visualstudio.com/) — Your primary IDE.
* **Node.js (v24.13.0):** [Download](https://nodejs.org/) — The JavaScript runtime.
* **Docker Desktop:** [Download](https://www.docker.com/products/docker-desktop/) — To build and run containers.
* **Git:** [Download](https://git-scm.com/) — For version control and cloning.

---

## 2. Getting the Code

### Forking the Repository
1.  Navigate to the original repository on GitHub.
2.  Click the **Fork** button (top-right) to create a copy under your account.

### Cloning to Local Machine
Open **PowerShell** or **Git Bash** and run the following commands:

```powershell
# Navigate to your projects folder
cd C:\Users\Stjam\fullstack

# Clone your forked repository
git clone [https://github.com/YOUR_USERNAME/ReactHelloWorld.git](https://github.com/YOUR_USERNAME/ReactHelloWorld.git)

# Enter the project directory
cd ReactHelloWorld

## 3. Project Structure
The repository is organized as follows:

ReactHelloWorld/ (Root)

HelloWorldReact/ (The React application folder)

Dockerfile

.dockerignore # files to exclude from docker

package.json

src/

public/

#### 4. Running Locally without Docker
# Follow the below commands in your teminal
cd HelloWorldReact
npm install
npm start

### 5.Building and Running with Docker
Ensure you are in the C:\Users\Stjam\fullstack\ReactHelloWorld\HelloWorldReact. The . at the end tells Docker to look in the current folder.
Run the below command in the terminal
docker build -t my-react-app .
Step 2: Run the Container
Map port 3000 of the container to port 3000 on your local machine:

Run the below command in the terminal
docker run -it -p 3000:3000 my-react-app
Step 3: Access the App
Open your browser and navigate to: http://localhost:3000

6. Common Troubleshooting
Error: "no such file or directory": Ensure your terminal is inside the HelloWorldReact folder before running docker build.

Error: "pull access denied": You likely forgot the . at the end of the build command or are trying to run an image name that hasn't been built yet.

Port in use: If port 3000 is taken, try -p 8080:3000 and visit localhost:8080.