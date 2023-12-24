
<div style="text-align: center;"><img src="deployment.lab.png" alt="Deployment Lab Logo" /></div>

## **Introduction**

**Deployment Lab** is a project that automates the build image process using GitHub Actions and Docker. It's designed for
developers who want to streamline their deployment workflows.

## **Installation**

To install Deployment Lab, you'll need to have Docker and Node.js installed on your machine. Clone the repository and
run `yarn install` to install the necessary dependencies.

## **Usage**

To use Deployment Lab, follow these steps:

1. Set your environment variables in the repository's secrets.
2. Push a new tag to trigger the `create.release.yml` workflow.
3. The `deployment.lap.yml` workflow will be triggered when a new release is created.


## **Contact**

If you have any questions or feedback, please reach out to us
at [contact@deploymentlab.com](mailto:contact@deploymentlab.com).

---

## 🚀 **Requirements to Run Workflows Correctly**

Before you can run the workflows correctly, make sure you have the following requirements set up:

---

1. **🔧 GitHub Actions**:

   Ensure that GitHub Actions is enabled for your repository. The workflows are defined in the `.github/workflows`
   directory of your repository.

---

2. **🐳 Dockerfile**:

   The Dockerfile is used to build a Docker image of your application. It should be located in the root directory of
   your repository.


---

3. **🔑 Environment Variables**:

   The workflows require certain environment variables to be set. These are:

    - `DOCKER_USERNAME`: Your Docker Hub username.
    - `DOCKER_PASSWORD`: Your Docker Hub password.
    - `REGISTRY_NAME`: The name of your Docker registry.
    - `ACCESS_TOKEN`: A GitHub token with the necessary permissions to create a release.

   These should be set in the repository's secrets.

---

4. **📁 Workflow Files**:

   There are two workflow files that need to be present in the `.github/workflows` directory:

    - `deployment.lap.yml`: This workflow is triggered when a new release is created. It builds a Docker image from the
      Dockerfile and pushes it to Docker Hub.

    - `create.release.yml`: This workflow is triggered when a new tag is pushed. It checks for tag changes and creates a
      new release if a new tag is detected.

---

5. **🏷️ Tagging**:

   The `create.release.yml` workflow is triggered by pushing a new tag. So, to create a new release and trigger
   the `deployment.lap.yml` workflow, you need to push a new tag.

---

6. **🐳 Docker Hub**:

   You need to have a Docker Hub account where the Docker image will be pushed. The `DOCKER_USERNAME`
   and `DOCKER_PASSWORD` should correspond to this account.

---

7. **🔑 GitHub Token**:

   The `ACCESS_TOKEN` should be a GitHub token with the necessary permissions to create a release. You can create a new
   token in your GitHub account settings.

---

8. **🧶 Yarn**:

   The Dockerfile uses Yarn to install dependencies. Make sure that all dependencies are correctly listed in
   your `package.json` and `yarn.lock` files.

---

9. **🟢 Node.js**:

   The Dockerfile uses the Node.js 18 Alpine image. Your application should be compatible with this version of Node.js.

---

10. **🌐 Serve**:

The Dockerfile installs the `serve` package globally. This package is used to serve your application.

---

Please ensure all these requirements are met for the workflows to run correctly.