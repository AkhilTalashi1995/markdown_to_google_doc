Markdown to Google Docs Converter
This project converts Markdown content into a formatted Google Doc using the Google Docs API. It is designed to run in Google Colab and supports features like headings, nested lists, checkboxes, and assignee mentions (@name).

Features
Google Docs Integration: Creates a new Google Doc programmatically.

Markdown Parsing: Converts Markdown to HTML and then to Google Docs format.

Formatting:

Headings (#, ##, ###) are converted to Google Docs heading styles.

Nested bullet points are preserved with proper indentation.

Checkboxes (- [ ], - [x]) are converted to Google Docs checkboxes.

Assignee mentions (@name) are styled in bold.

Footer content (after <hr>) is styled distinctly (italic and gray).

Error Handling: Gracefully handles errors during execution.

Setup Instructions
1. Prerequisites
A Google account.

Google Drive to store credentials and token files.

A Google Cloud Platform (GCP) project with the Google Docs API enabled.

2. Google Cloud Platform Setup
Go to the Google Cloud Console.

Create a new project or select an existing one.

Enable the Google Docs API:

Navigate to APIs & Services > Library.

Search for "Google Docs API" and enable it.

Create OAuth 2.0 credentials:

Go to APIs & Services > Credentials.

Click Create Credentials > OAuth client ID.

Choose Desktop App as the application type.

Download the credentials file (credentials.json).

3. Upload Credentials to Google Drive
Upload the credentials.json file to your Google Drive (e.g., in the Colab Notebooks folder).

Ensure the file path is correctly referenced in the code.

4. Run in Google Colab
Open the Google Colab notebook.

Mount Google Drive:

from google.colab import drive
drive.mount('/content/drive')
Run the code cell-by-cell to authenticate and create the Google Doc.

Required Dependencies
google-api-python-client

google-auth

google-auth-httplib2

google-auth-oauthlib

markdown-it-py

beautifulsoup4

Install the dependencies using:

bash

!pip install --upgrade google-api-python-client google-auth google-auth-httplib2 google-auth-oauthlib markdown-it-py beautifulsoup4
How to Run in Colab
Open the Colab notebook.

Mount Google Drive:

from google.colab import drive
drive.mount('/content/drive')
Run the code to authenticate and create the Google Doc:

try:
    docs_service = initialize_docs_api()
    print("Successfully authenticated and initialized Google Docs API")

    doc_id = create_google_doc(docs_service)

    html_content = markdown_to_html(markdown_text)
    print(html_content)

    html_to_google_docs(docs_service, doc_id, html_content)

    print(f"Google Doc created successfully. Access it here: https://docs.google.com/document/d/{doc_id}/edit")

except Exception as e:
    print(f"Error: {e}")

Example Markdown Input
markdown

# Product Team Sync - May 15, 2023

## Attendees
- Sarah Chen (Product Lead)
- Mike Johnson (Engineering)
- Anna Smith (Design)
- David Park (QA)

## Agenda

### 1. Sprint Review
* Completed Features
  * User authentication flow
  * Dashboard redesign
  * Performance optimization
    * Reduced load time by 40%
    * Implemented caching solution
* Pending Items
  * Mobile responsive fixes
  * Beta testing feedback integration

### 2. Current Challenges
* Resource constraints in QA team
* Third-party API integration delays
* User feedback on new UI
  * Navigation confusion
  * Color contrast issues

### 3. Next Sprint Planning
* Priority Features
  * Payment gateway integration
  * User profile enhancement
  * Analytics dashboard
* Technical Debt
  * Code refactoring
  * Documentation updates

## Action Items
- [ ] @sarah: Finalize Q3 roadmap by Friday
- [ ] @mike: Schedule technical review for payment integration
- [ ] @anna: Share updated design system documentation
- [ ] @david: Prepare QA resource allocation proposal

## Next Steps
* Schedule individual team reviews
* Update sprint board
* Share meeting summary with stakeholders

## Notes
* Next sync scheduled for May 22, 2023
* Platform demo for stakeholders on May 25
* Remember to update JIRA tickets

---
Meeting recorded by: Sarah Chen
Duration: 45 minutes
Output
The output is a Google Doc with:

Proper headings (Heading 1, Heading 2, Heading 3).

Nested bullet points with proper indentation.

Checkboxes for action items.

Bold styling for assignee mentions (@name).

Distinct styling for footer content.

License
This project is licensed under the MIT License. See the LICENSE file for details.

