# Security Policy

This is an academic Machine Learning project. Security matters primarily regarding dependency vulnerabilities and data privacy. 

## Supported Versions
Security updates are provided only for the latest version on the `main` branch.

## Reporting a Vulnerability

If you find a security issue, please **do not open a public issue** right away.

Please report vulnerabilities privately using GitHub's **Private Vulnerability Reporting** feature:

1. Navigate to the **Security** tab of this repository.
2. Click on **Report a vulnerability**.
3. Provide details including:
   - Clear reproduction steps
   - Traceback or error logs (if applicable)
   - Environment context (Python version, OS, CUDA setup)

Maintainers will review the report and respond directly within the private advisory thread.

## Scope (Machine Learning / Data Science)

### In scope
- **Malicious Weights Execution:** Issues regarding insecure deserialization of `best.pt` files (e.g., PyTorch pickle vulnerabilities) if we ever host model checkpoints on a public bucket.
- **API Key Leakage:** Scripts that expose sensitive keys (e.g., Roboflow API keys) during automated runs.
- **Dependency vulnerabilities:** Known critical CVEs in our pinned libraries (e.g., Ultralytics, OpenCV).

### Out of scope
- **Data poisoning:** If a malicious actor alters the public Roboflow dataset itself (this is managed by the dataset provider).
- **Physical hardware access** to the GPUs running the training.

## Secure Development Guidelines
- **Never commit your Roboflow API Key or local paths.**
- Validate external datasets and model weights before executing them locally.