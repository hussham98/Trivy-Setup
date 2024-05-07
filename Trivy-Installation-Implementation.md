## Installation Steps

```bash
sudo apt-get install wget apt-transport-https gnupg lsb-release

wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | gpg --dearmor | sudo tee /usr/share/keyrings/trivy.gpg > /dev/null

echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main" | sudo tee -a /etc/apt/sources.list.d/trivy.list

sudo apt-get update

sudo apt-get install trivy

## Commands

- `trivy image imagename`: Scan a Docker image for vulnerabilities.
- `trivy fs --security-checks vuln,config Folder_name_OR_Path`: Scan a file system for vulnerabilities and configuration issues.
- `trivy image --severity HIGH,CRITICAL image_name`: Scan a Docker image for vulnerabilities with specified severity levels.
- `trivy image -f json -o results.json image_name`: Output the scan results in JSON format to a file.
- `trivy repo repo-url`: Scan a container image repository.
- `trivy k8s --report summary cluster`: Scan a Kubernetes cluster for vulnerabilities and generate a summary report.


This document provides installation steps for Trivy, a vulnerability scanner for containers and container images, along with various commands to scan images, file systems, repositories, and Kubernetes clusters. Each command is explained with its usage and purpose.
