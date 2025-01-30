# Markdown to Google Docs Converter

A Python script that converts markdown-formatted meeting notes into well-formatted Google Docs, running in Google Colab. The script maintains document structure, formatting, and special elements like checkboxes and @mentions.

## Features

- Converts markdown to Google Docs format
- Maintains heading hierarchy (H1, H2, H3)
- Preserves nested bullet points with proper indentation
- Converts markdown checkboxes to Google Docs checkboxes
- Highlights @mentions in bold and color
- Applies distinct styling to footer information
- Handles authentication and authorization automatically in Colab

## Prerequisites

- Google Account
- Google Colab access
- Google Drive mounted in Colab
- Necessary API permissions enabled

## Required Dependencies

```python
google-api-python-client
google-auth
google-auth-httplib2
google-auth-oauthlib
markdown-it-py
beautifulsoup4
```

## Setup Instructions

1. Clone the Repository

To get started, clone the repository to your local machine or Google Colab environment:

```bash
git clone https://github.com/AkhilTalashi1995/markdown_to_google_doc.git
cd markdown_to_google_doc
```
2. Open the Notebook in Google Colab

   1. Upload the ```markdown_to_google_doc.ipynb``` file to Google Colab.
   
   2. Open the notebook in Colab.

3. Mount Google Drive
   
Run the following code in Colab to mount Google Drive:

```python
from google.colab import drive
drive.mount('/content/drive')
```
4. Install Required Packages

Install the necessary dependencies by running:

```python
!pip install --upgrade google-api-python-client google-auth google-auth-httplib2 google-auth-oauthlib markdown-it-py beautifulsoup4
```
5. Enable Google Docs API
   
      1. Go to the Google Cloud Console.
      
      2. Enable the Google Docs API for your project.
      
      3. Create OAuth 2.0 credentials and download the credentials.json file.
      
      4. Upload the credentials.json file to your Google Drive (e.g., in the Colab Notebooks folder).

## Usage

1. Copy the notebook to your Google Drive
2. Open it in Google Colab
3. Run all cells to install dependencies and authenticate
4. Modify the `markdown_text` variable with your own markdown content
5. Run the conversion script
6. Access the created Google Doc via the provided link

## Error Handling

The script includes comprehensive error handling for:
- Authentication failures
- API quota limits
- Permission issues
- Invalid markdown format
- Network connectivity problems

## Formatting Details

- Title: Heading 1 style
- Section headers: Heading 2 style
- Sub-section headers: Heading 3 style
- Nested bullets: Proper indentation
- Checkboxes: Converted to Google Docs checkboxes
- @mentions: Bold and colored text
- Footer: Distinct styling with smaller, gray text

## Limitations

- Requires Google Colab environment
- Needs Google Drive mounting
- API quota limitations apply
- Some markdown features might not have exact Google Docs equivalents

## License

This project is licensed under the MIT License - see the LICENSE file for details.
