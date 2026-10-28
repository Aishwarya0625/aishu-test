program 11111111

# PROGRAM 1: GIT REPOSITORY

## Step 1: Create repository in GitHub
GitHub open maadi → New repository → Repository name: `Program1` → Create repository.

## Step 2: Clone repository to local system
```cmd
cd %USERPROFILE%\Desktop
git clone https://github.com/Aishwarya0625/Program1.git
cd Program1
```

## Step 3: Create a file and write content
```cmd
notepad file.txt
```
Write:
```text
This is the main branch.
```
Save and close.

## Step 4: Commit and push
```cmd
git add .
git commit -m "Add file"
git push origin main
```

## Step 5: Create and switch to branch
```cmd
git checkout -b feature
```

## Step 6: Modify the file in feature branch
```cmd
notepad file.txt
```
Change content to:
```text
This is the feature branch.
```
Save and close.
```cmd
git add .
git commit -m "Update file in feature branch"
git push -u origin feature
```

## Step 7: Show difference between branches
```cmd
git diff main feature
```

## Step 8: Create merge conflict
```cmd
git checkout main
notepad file.txt
```
Change content to:
```text
This is the updated main branch.
```
Save and close.
```cmd
git add file.txt
git commit -m "Update file in main branch"
git checkout feature
git merge main
```

## Step 9: Resolve merge conflict
Conflict bandaga `file.txt` open maadi. Conflict markers remove maadi, final content haaki:
```text
This is the resolved file.
```
Save and close.
```cmd
git add file.txt
git commit -m "Resolve merge conflict"
git push origin feature
```

## Step 10: Create Pull Request
1. GitHub repository open maadu.
2. **Compare & pull request** click maadu.
3. Base: `main`; Compare: `feature`.
4. Add title: `Merge feature branch`.
5. Click **Create pull request**.
6. Review maadi **Merge pull request** click maadu.

7.( or)
# PROGRAM 1: GIT REPOSITORY

### Step 1: Create repository in GitHub
GitHub → New repository → Name: `Program1` → Create repository.

### Step 2: Clone repository
```bash
cd %USERPROFILE%\Desktop
git clone https://github.com/Aishwarya0625/Program1.git
cd Program1
```

### Step 3: Create a file
```bash
notepad file.txt
```
Write: `This is the main branch.` Save and close.

### Step 4: Commit and push
```bash
git add .
git commit -m "Initial commit"
git push origin main
```

### Step 5: Create and switch to branch
```bash
git branch future1
git checkout future1
```

### Step 6: Modify file in future branch
```bash
notepad file.txt
git add .
git commit -m "Future1 branch changes"
git push origin future1
```

### Step 7: Show difference between branches
```bash
git diff main future1
```

### Step 8: Create merge conflict
```bash
git checkout main
notepad file.txt
git add .
git commit -m "Main branch changes"
git merge future1
```
`file.txt` alli main branch-ge bere line add maadi save maadu. Conflict barabekandre same line-na `future1` branch-nalloo different aagi change maadirabeku.

### Step 9: Resolve merge conflict
```bash
notepad file.txt
```
Conflict markers remove maadi, final content save maadu.

```bash
git add .
git commit -m "Resolve merge conflict"
git push origin main
```

### Step 10: Create Pull Request
GitHub → Repository → Compare & pull request → Base: `main` → Compare: `future1` → Create pull request → Merge pull request.


program 2222222
# PROGRAM: DOCKER CONTAINERIZATION

### Step 1: Create project folder

```cmd
"My App 3"
```

### Step 2: Create HTML file

```cmd
notepad index.html
```

```html
<html>
<body>
<h1>Welcome to My App</h1>
<p>This is my first Docker application</p>
</body>
</html>
```

Save and close.

### Step 3: Create Dockerfile

```cmd
notepad Dockerfile
```

```dockerfile
FROM tomcat:10.1-jdk17
COPY index.html /usr/local/tomcat/webapps/myapp/index.html
EXPOSE 8080
```

Save as `Dockerfile` without `.txt` extension.

### Step 4: Build Docker image

```cmd
cd "%USERPROFILE%\Desktop\My App 3"
docker build -t myapp3 .
docker images
```

### Step 5: Run Docker container

```cmd
docker run -d -p 8081:8080 --name my-tomcat-container myapp3
```

### Step 6: Verify running container

```cmd
docker ps
```

### Step 7: View output

Open Chrome and enter:

```text
http://localhost:8081/myapp/
```

### Step 8: Stop the container

```cmd
docker stop my-tomcat-container
```

### Optional: Remove container

```cmd
docker rm my-tomcat-container
```
program 333333333
# PROGRAM 3: JENKINS CI PIPELINE

### Step 1: Create GitHub repository
GitHub → New repository → Name: `Jenkins-CI` → Create repository.

### Step 2: Create Jenkins job
Open `http://localhost:8080` → New Item → Name: `Jenkins-CI` → Freestyle project → OK.

### Step 3: Configure GitHub repository
Jenkins job → Configure → Source Code Management → Git.

Repository URL:
```text
https://github.com/Aishwarya0625/Jenkins-CI.git
```

Build Triggers:
- Select **GitHub hook trigger for GITScm polling**.
- Click Save.

### Step 4: Configure build command
Job → Configure → Build Steps → Add build step → Execute Windows batch command.

```cmd
echo Build started
```

Click Save.

### Step 5: Start Cloudflare tunnel
Open Command Prompt:

```cmd
cloudflared tunnel --url http://localhost:8080
```

Copy the HTTPS URL displayed in the terminal. Keep the terminal running.

### Step 6: Add GitHub webhook
GitHub repository → Settings → Webhooks → Add webhook.

Payload URL:
```text
https://YOUR-CLOUDFLARE-URL/github-webhook/
```

Replace `YOUR-CLOUDFLARE-URL` with the actual HTTPS URL from the terminal.

Content type: `application/json`

Select **Just the push event** → Add webhook.

### Step 7: Test the webhook
Make a change in the GitHub repository, then commit and push it.

```cmd
git add .
git commit -m "Test Jenkins webhook"
git push origin main
```

GitHub webhook Jenkins-ge notification kalisutte; configuration correct iddare Jenkins automatically build trigger maadutte.

### Step 8: Check the output
1. Open Jenkins.
2. Select `Jenkins-CI` job.
3. Open the latest build number.
4. Click **Console Output**.
5. Check for:

```text
Build started
Finished: SUCCESS
```
program 44444444
# PROGRAM 4: DOCKER IMAGE WITH JENKINS PIPELINE

### Step 1: Verify Docker installation

Docker Desktop open maadi, CMD alli:

```cmd
docker version
```

### Step 2: Create project folder and Python file

```cmd
(folder) "Program 10"
notepad app.py(file)
```

`app.py` content:

```python
print("Hello from Docker")
```

Save and close.

### Step 3: Create Dockerfile

```cmd
notepad Dockerfile
```

Dockerfile content:

```dockerfile
FROM python:3.12
WORKDIR /app
COPY app.py .
CMD ["python", "app.py"]
```

Save as `Dockerfile` without `.txt` extension.

### Step 4: Build and run Docker image

```cmd
cd "%USERPROFILE%\Desktop\Program 10"
docker build -t program10 .
docker images
docker run --rm program10
```

### Step 5: Tag and push image to Docker Hub

```cmd
docker login
docker tag program10 aishwarya0625/program10:latest
docker push aishwarya0625/program10:latest
```

### Step 6: Push project code to GitHub

First, GitHub alli `Program10` repository create maadu.

```cmd
git init
git add .
git commit -m "Add Docker image project"
git branch -M main
git remote add origin https://github.com/Aishwarya0625/Program10.git
git push -u origin main
```

### Step 7: Create Docker Hub access token

1. Open `https://hub.docker.com/`
2. Account Settings → Personal access tokens.
3. Click Generate New Token.
4. Token name: `jenkins-token`.
5. Select Read & Write permissions.
6. Generate and copy the token securely.

### Step 8: Create Jenkinsfile

Project folder alli:

```cmd
notepad Jenkinsfile
```

Paste this code:

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Aishwarya0625/Program10.git'
            }
        }

        stage('Build Image') {
            steps {
                bat 'docker build -t aishwarya0625/program10:latest .'
            }
        }

        stage('Login to Docker Hub') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-password', variable: 'TOKEN')]) {
                    bat 'echo %TOKEN% | docker login -u aishwarya0625 --password-stdin'
                }
            }
        }

        stage('Push Image') {
            steps {
                bat 'docker push aishwarya0625/program10:latest'
            }
        }
    }
}
```

Save maadi, GitHub-ge push maadu:

```cmd
git add .
git commit -m "Add Jenkins pipeline"
git push origin main
```

### Step 9: Add Docker Hub credentials in Jenkins

1. Jenkins → Manage Jenkins → Credentials.
2. Global credentials → Add Credentials.
3. Kind: **Secret text**.
4. Secret: Docker Hub access token.
5. ID: `dockerhub-password`.
6. Click Create.

### Step 10: Build the pipeline

1. Jenkins → New Item.
2. Name: `Docker-Pipeline`.
3. Select Pipeline → OK.
4. Definition: **Pipeline script from SCM**.
5. SCM: Git.
6. Repository URL: `https://github.com/Aishwarya0625/Program10.git`
7. Branch: `*/main`
8. Script Path: `Jenkinsfile`.
9. Save → Build Now.
10. Build complete aadmele Console Output open maadi `Finished: SUCCESS` check maadu.

program555555555555
# PROGRAM 5: MAVEN PROJECT USING VS CODE AND GITHUB ACTIONS

### Step 1: Install Maven Integration Plugin in Jenkins

1. Open `http://localhost:8080`
2. Manage Jenkins → Plugins → Available plugins.
3. Search `Maven Integration`.
4. Install the plugin.

### Step 2: Create Maven Project in VS Code

1. Open VS Code.
2. Install extensions:
   - Extension Pack for Java
   - Maven for Java
3. Press `Ctrl + Shift + P`.
4. Search `Maven: Create Maven Project`.
5. Select `maven-archetype-quickstart`.
6. Select the available archetype version.
7. Group Id: `com.example`
8. Artifact Id: `demo`
9. Select a location, such as Desktop.
10. Open the created `demo` folder in VS Code.

### Step 3: Check pom.xml

Project structure:

```text
demo/
├── pom.xml
├── src/
│   ├── main/java/com/example/
│   └── test/java/com/example/
└── .github/
    └── workflows/
        └── maven.yml
```

Ensure `pom.xml` exists in the `demo` root folder.

### Step 4: Create GitHub Actions workflow

Create `.github/workflows/maven.yml`.

```yaml
name: Maven CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Set up JDK
        uses: actions/setup-java@v4
        with:
          java-version: '21'
          distribution: temurin
          cache: maven

      - name: Build with Maven
        run: mvn -B package
```

### Step 5: Create New.java

Create `src/main/java/com/example/New.java`.

```java
package com.example;

public class New {
    public static void main(String[] args) {
        System.out.println("Hello Aishwarya!");
        System.out.println("Maven CI/CD Pipeline");
    }
}
```

Save all files. Check that the Java compiler version in `pom.xml` is configured for Java 21.

### Step 6: Test Maven project

Open VS Code terminal → Terminal → New Terminal.

```cmd
mvn -version
mvn clean package
```

If Maven is not installed, install Maven and configure PATH first.

### Step 7: Push project to GitHub

Create an empty GitHub repository named `Maven`.

Run these commands in the `demo` project folder:

```cmd
git init
git add .
git commit -m "Add Maven CI CD workflow"
git branch -M main
git remote add origin https://github.com/Aishwarya0625/Maven.git
git push -u origin main
```

If `origin` already exists:

```cmd
git remote set-url origin https://github.com/Aishwarya0625/Maven.git
git push -u origin main
```

### Step 8: Verify GitHub Actions

1. Open `https://github.com/Aishwarya0625/Maven`.
2. Click **Actions**.
3. Select `Maven CI`.
4. Open the latest workflow run.
5. Check **Build with Maven**.
6. Green tick means success; red cross means an error occurred.
7. 
