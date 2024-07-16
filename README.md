# Tag_based_CICD

This project demonstrates a Tag-based Continuous Integration and Continuous Deployment (CI/CD) workflow using GitHub Actions. It automates the process of versioning and deploying your application based on Git tags.
Features

- Automatic version tagging based on package.json version
- Tag-based deployment workflow
- Content verification of index.html for each version (if used )

## Workflow Details


### 1. Tagging Workflow (tagging.yml)

This workflow is triggered manually with commit ID and you select branch:

Checks out the code
Reads the version from package.json
Creates a new Git tag if it doesn't already exist
Pushes the new tag to the repository

### 2. Tag-based CI/CD Workflow (deploy.yml)

This workflow is triggered when a new tag is pushed:

Checks out the code at the tagged commit
Extracts the version number from the tag
Simulates a deployment for that version
Echoes the content of index.html for verification
Completes the deployment process

### Usage

Update your application code and increment the version in package.json.
Commit and push your changes to the main branch.
The Tagging Workflow will automatically create and push a new tag.
The Tag-based CI/CD Workflow will then deploy the new version.

### Setup

Clone this repository.
Ensure you have a package.json file with a version field.
Create an index.html file in the root of your repository.
Set up any necessary secrets in your GitHub repository settings:

Go to Settings > Secrets and variables > Actions
Add any required secrets (e.g., PAT for Personal Access Token)
