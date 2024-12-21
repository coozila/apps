# mcrouter Docker Image Build Instructions

This document provides instructions for building the Docker image for `mcrouter`.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Docker
- Docker Compose

## Instructions

1. **Clone the Repository** (if you haven't already):

   If you haven't cloned the repository, do so by running:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Check Script Permissions**:

   Ensure that the `deps.sh` script in your `scripts` directory has the proper execution permissions:
   ```bash
   chmod +x scripts/deps.sh
   ```

3. **Verify Dockerfile Context**:

   Ensure that the `scripts` directory is correctly structured in relation to your Dockerfile. The `source=scripts` in the `--mount` option should point to the correct path where the `scripts` directory resides.

4. **Run Docker with Sufficient Privileges**:

   To avoid needing `sudo` every time you run Docker commands, add your user to the `docker` group:
   ```bash
   sudo usermod -aG docker $USER
   ```
   After running this command, log out and log back in for the changes to take effect.

5. **Check Docker Version**:

   Ensure your Docker version is up to date. The `--mount` option requires a version that supports it:
   ```bash
   docker --version
   ```

6. **Build the Docker Image**:

   Use the following command to build the Docker image for `mcrouter`:
   ```bash
   sudo docker compose build
   ```

7. **Inspect the Dockerfile**:

   If you encounter issues during the build process, double-check the contents of your Dockerfile and ensure that the script is correctly referenced in the build context. Verify that paths and commands are correct.

## Troubleshooting

- **Permission Denied Errors**: If you encounter a permission denied error, ensure that all necessary scripts have the correct execution permissions.

- **Network Issues**: If there are problems fetching packages, ensure that your Docker container has proper network access. You can also try using alternative Ubuntu mirrors.

- **Inspect Build Logs**: Look for warning or error messages in the build logs to identify issues with dependencies or configurations.

## Additional Notes

- The `mcrouter` configuration can be modified in the `Dockerfile` and the `docker-compose.yml` file as needed.
- For further assistance, feel free to reach out or consult the official [mcrouter documentation](https://github.com/facebook/mcrouter) for more details.

Happy coding!

This `README.md` file provides a comprehensive guide for users looking to build the `mcrouter` Docker image, with clear steps and troubleshooting tips included. You can customize the `<repository-url>` and `<repository-directory>` placeholders with your actual project details. If you need any further modifications or additional content, feel free to ask!