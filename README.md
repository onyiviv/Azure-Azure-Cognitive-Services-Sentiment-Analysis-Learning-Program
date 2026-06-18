[azure cognition.txt](https://github.com/user-attachments/files/29090840/azure.cognition.txt)
# A# 🤖 Azure AI Sentiment & Opinion Mining Tool

An AI-powered Python application that connects securely to Microsoft Azure Cognitive Services to extract sentiment scores and targeted feature opinions from text documents. Security compliance is enforced by keeping all API endpoints and authentication keys stored safely inside an isolated Azure Key Vault instance.

---

## 🏗️ Project Architecture

This application utilizes a secure cloud-to-local decoupled architecture:
1. **Azure Language Service:** Provisions the underlying NLP machine learning model to parse input text.
2. **Azure Key Vault:** Keeps our operational credentials locked down using standard Access Policies.
3. **Local Python Application:** Authenticates against the vault with `DefaultAzureCredential` via local CLI environments to extract keys dynamically without hardcoding data strings into production repository code files.

---

## 🛠️ Step-by-Step Environment Deployment

### Task 1: Initialize Your Vault Permission Settings
If your active Azure account features restrictive admin rules or is a student tier subscription, you must shift your vault's structural permissions off standard RBAC controls over to explicit policies:

```powershell
# Force Key Vault to leverage Access Policies instead of RBAC
az keyvault update --name "sentiment-ai-engine" --enable-rbac-authorization false

Next, register my user identity to grant creation access limits using my Azure profile object ID:
# Attach full key and secret query access configurations to your unique user identity
az keyvault set-policy --name "sentiment-ai-engine" --object-id "68b769a9-ae9a-4a7a-b911-4680b148fb08" --secret-permissions get list set

Task 2: Inject Operational Secrets via CLI
With deployment configurations verified, upload my active Language Service endpoint strings and key strings to my key vault container safely:
# Register the Language Service endpoint URL
az keyvault secret set --vault-name "sentiment-ai-engine" --name "AZURE-LANGUAGE-ENDPOINT" --value "[https://lang-sentiment-eval-01.cognitiveservices.azure.com/](https://lang-sentiment-eval-01.cognitiveservices.azure.com/)"

# Register your secure AI API validation Key
az keyvault secret set --vault-name "sentiment-ai-engine" --name "AZURE-LANGUAGE-KEY" --value "7mc608lUoXQnDZVtWfl4ThUrvWFSbt2MSYLu7eLyTKoR3Kpa4XFtJQQJ99CFACYeBjFXJ3w3AAAaACOGYtBm"

Task 3: Local System Code Setup
1. Clone this project repository folder locally onto my workspace.

2. Initialize my target package extensions inside my running terminal shell environment:
pip install azure-ai-textanalytics azure-identity azure-keyvault-secrets
3. Establish your secure profile token binding link:

PowerShell
az login

🚀 Execution & Verification
To launch the secure execution loop workflow, run the script launcher command:

PowerShell
python app.py

Expected Output Report Structure
Plaintext
[1/4] Connecting to Key Vault: sentiment-ai-engine...
[2/4] Sending your text to Azure AI Service...

=============================================
        SENTIMENT & OPINION MINING REPORT     
=============================================

📄 Text 1:
   Overall Vibe: MIXED
   Scores: Positive: 0.50 | Negative: 0.39
   ↳ Targeted Aspect: Users feel 'positive' about the 'battery life'
   ↳ Targeted Aspect: Users feel 'negative' about the 'keyboard'
---------------------------------------------



🔍 Troubleshooting Notes Shared in This Build
ImportError (Module Core Mismatch): Always ensure that AzureKeyCredential is imported from azure.core.credentials instead of the higher-tier azure.ai.textanalytics library file space.

IndentationError (Python Formatting): Double-check that your runtime execution lines inside your entry block function if __name__ == "__main__": are indented consistently by 4 spaces or 1 tab.

SecretNotFound / Connection Adapters Failure: Verify that you have uploaded actual configuration values into your Key Vault variables, rather than default placeholder template strings.zure-Azure-Cognitive-Services-Sentiment-Analysis-Learning-Program
All cloud computing related work-Azure Azure Cognitive Services Sentiment Analysis Learning Program
