
# Jenkins Shared Library – Prasad Pardeshi

Shared libraries in Jenkins Pipelines are **reusable code modules** that help you maintain cleaner, modular, and DRY (Don't Repeat Yourself) pipelines. This repository demonstrates how to structure and use a shared library in Jenkins.

---

## 📦 Project Structure

```
Jenkins_SharedLib/
├── vars/
│   └── <yourGroovyScript>.groovy  # Groovy script with pipeline logic
├── resources/
│   └── <optional-support-files>
```

> ✅ Shared library logic must be placed in the **`vars/`** directory.  
> ✅ Each file should use **Groovy syntax** and end with a **`.groovy`** extension.

---

## 🛠 How to Configure Shared Library in Jenkins

1. Login to your Jenkins dashboard.  
   If Jenkins is not installed, [https://www.jenkins.io/doc/book/installing/]

2. Navigate to:
   ```
   Manage Jenkins → Configure System → Global Pipeline Libraries
   ```

3. Add a new library configuration:
   - **Name**: `Shared`
   - **Default version**: `main`
   - **Project Repository**:  
     `https://github.com/prasad112000/Jenkins_SharedLib.git`
   - Check **"Load implicitly"** (optional)

## 🚀 How to Use This Shared Library in a Jenkins Pipeline

In your Jenkinsfile, add the following at the top:

```groovy
@Library('Shared') _
```

Now, you can directly use any function from your shared library, like:

```groovy
helloWorld()  // If defined in vars/helloWorld.groovy
```

Example:

```groovy
@Library('Shared') _
pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                script {
                    helloWorld()
                }
            }
        }
    }
}

🙌 Author

**Prasad Vinod Pardeshi**  
📧 pardeshiprasad42@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/prasad-pardeshi11/)  
💻 [GitHub](https://github.com/prasad112000)

