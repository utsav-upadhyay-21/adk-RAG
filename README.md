# RAG Agent with Google ADK and Vertex AI

## Overview

The Vertex AI RAG Agent allows you to:

- Query document corpora with natural language questions
- List available document corpora
- Create new document corpora
- Add new documents to existing corpora
- Get detailed information about specific corpora
- Delete corpora when they're no longer needed


## Setting Up Google Cloud Authentication

Before running the agent, you need to set up authentication with Google Cloud:

1. **Install Google Cloud CLI**:
   - Visit [Google Cloud SDK](https://cloud.google.com/sdk/docs/install) for installation instructions for your OS

2. **Initialize the Google Cloud CLI**:
   ```bash
   gcloud init
   ```
   This will guide you through logging in and selecting your project.

3. **Set up Application Default Credentials**:
   ```bash
   gcloud auth application-default login
   ```
   This will open a browser window for authentication and store credentials in:
   `~/.config/gcloud/application_default_credentials.json`

4. **Verify Authentication**:
   ```bash
   gcloud auth list
   gcloud config list
   ```

5. **Enable Required APIs** (if not already enabled):
   ```bash
   gcloud services enable aiplatform.googleapis.com
   ```

## Installation

1. **Set up a virtual environment**:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Using the Agent

The agent provides the following functionality through its tools:

### 1. Query Documents
Allows you to ask questions and get answers from your document corpus:
- Automatically retrieves relevant information from the specified corpus
- Generates informative responses based on the retrieved content

### 2. List Corpora
Shows all available document corpora in your project:
- Displays corpus names and basic information
- Helps you understand what data collections are available

### 3. Create Corpus
Create a new empty document corpus:
- Specify a custom name for your corpus
- Sets up the corpus with recommended embedding model configuration
- Prepares the corpus for document ingestion

### 4. Add New Data
Add documents to existing corpora or create new ones:
- Supports Google Drive URLs and GCS (Google Cloud Storage) paths
- Automatically creates new corpora if they don't exist

### 5. Get Corpus Information
Provides detailed information about a specific corpus:
- Shows document count, file metadata, and creation time
- Useful for understanding corpus contents and structure

### 6. Delete Corpus
Removes corpora that are no longer needed:
- Requires confirmation to prevent accidental deletion
- Permanently removes the corpus and all associated files

## Note:
Deprecated may not be included in requirements , you have to install it seperately.
```bash
   pip install deprecated
   ```

## Additional Resources

- [Vertex AI RAG Documentation](https://cloud.google.com/vertex-ai/generative-ai/docs/rag-overview)
- [Google Agent Development Kit (ADK) Documentation](https://github.com/google/agents-framework)
- [Google Cloud Authentication Guide](https://cloud.google.com/docs/authentication)
