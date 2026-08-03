# Jenkins Shared Libraries

This repository contains reusable Jenkins Shared Library scripts written in Groovy. These libraries help simplify Jenkins pipelines by providing common functions that can be reused across multiple projects.

## Repository Structure

```
jenkins-shared-libraries/
└── vars/
    ├── clone.groovy
    ├── docker_build.groovy
    └── hello.groovy
```

## Available Shared Library Functions

### `clone.groovy`

Provides a reusable function to clone a Git repository within a Jenkins pipeline.

Example:

```groovy
@Library('jenkins-shared-libraries') _

clone(
    repoUrl: 'https://github.com/username/project.git',
    branch: 'main'
)
```

---

### `docker_build.groovy`

Builds a Docker image using a reusable Jenkins Shared Library function.

Example:

```groovy
@Library('jenkins-shared-libraries') _

docker_build(
    imageName: 'my-app',
    tag: 'latest'
)
```

---

### `hello.groovy`

A simple sample shared library used for testing.

Example:

```groovy
@Library('jenkins-shared-libraries') _

hello()
```

## How to Configure

1. Open **Jenkins Dashboard**.
2. Go to **Manage Jenkins → System**.
3. Scroll to **Global Pipeline Libraries**.
4. Add a new library:

   * **Name:** `jenkins-shared-libraries`
   * **Default Version:** `main` (or your branch name)
   * **Retrieval Method:** Modern SCM
   * **SCM:** Git
   * **Repository URL:** `https://github.com/anil2211/jenkins-shared-libraries.git`

## Using the Library

Import the shared library at the top of your Jenkinsfile:

```groovy
@Library('jenkins-shared-libraries') _

pipeline {
    agent any

    stages {
        stage('Example') {
            steps {
                hello()
            }
        }
    }
}
```

## Technologies Used

* Jenkins
* Groovy
* Jenkins Shared Libraries
* Git

## Author

**Anil**
