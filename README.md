# HTML Template for Radiant Wrapper

This repository contains a simple HTML template that can be used with Radiant to create mobile applications from your HTML web pages.

## Project Structure

This is a basic HTML project with the following files:

- `index.html`: The main HTML file that serves as the entry point for your application
- Additional HTML, CSS, and JavaScript files can be added as needed

## Configuration

### .p4a File

The `.p4a` file in the root directory must be filled with the following configuration:

```
--package org.example.html_app
--name "My WebView HTML Application"
--dist_name my_app
--version 0.1
--port 5005
--icon assets/icon.png
--presplash assets/icon_w.png
--presplash-color #ff6439
--requirements python3,hostpython3,sqlite3,sqlparse,asgiref,pytz,pyjnius
```

This configuration specifies:

- `--package`: The Java package name for your Android application
- `--name`: The display name of your application
- `--dist_name`: The distribution name for your application
- `--version`: The version number of your application
- `--port`: The port number your HTML application will run on
- `--icon`: Path to the application icon image file
- `--presplash`: Path to the splash screen image shown during app launch
- `--presplash-color`: Background color for the splash screen in hex format
- `--requirements`: Python packages required for your application

## Getting Started

1. Clone this repository
2. Make sure the `.p4a` file is properly configured
3. Develop your HTML application by modifying the `index.html` file and adding other assets as needed
4. Use Radiant to build and deploy your mobile application

## GitHub Workflow

This repository includes a GitHub workflow file (`.github/workflows/radiant_wrapper.yml`) that automatically generates an installable APK for Android. The workflow is triggered:

- On every push to the repository
- Manually through the GitHub Actions interface

The workflow performs the following steps:
1. Sets up the build environment
2. Installs necessary dependencies
3. Configures the application based on your project structure
4. Builds an Android APK for ARM64 architecture
5. Uploads the generated APK as a GitHub artifact

After the workflow completes, you can download the APK from the GitHub Actions page of your repository.
