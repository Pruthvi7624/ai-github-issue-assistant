Seedling Labs: AI-Powered GitHub Issue Assistant
Project Overview
Welcome to the Seedling Labs AI-Powered GitHub Issue Assistant! This project embodies Seedling's core philosophy of "Agentic Thinking in a Box" by creating a small, useful AI agent that integrates different components (GitHub API, LLM) to solve a concrete development workflow problem.

Problem Statement
At Seedling Labs, maintaining quality and speed in our development workflow is paramount. Efficiently understanding and prioritizing new GitHub issues is crucial for this. This application addresses that challenge by leveraging AI to quickly analyze and summarize GitHub issues.

Core Features
This web application provides the following functionalities:

Input UI: A simple and intuitive user interface to input a public GitHub repository URL and an issue number.

GitHub Data Fetching: Fetches the title, body, and all comments of the specified GitHub issue using the GitHub Public API.

AI Analysis Core: Utilizes a Large Language Model (LLM) (specifically, Google Gemini 2.0 Flash) to process the fetched issue information.

Structured Output Generation: The AI generates a structured summary of the issue in a predefined JSON format.

Output Display: Presents the AI-generated analysis in a clean, readable format directly within the web page.

Copy JSON: A convenient button to copy the raw AI-generated JSON output to the clipboard.

User-Friendly Messages: Custom modal pop-ups for confirmations (like copying JSON) and error messages, avoiding disruptive browser alert() calls.

Tech Stack
Frontend: HTML, CSS (Tailwind CSS via CDN), JavaScript

APIs:

GitHub Public API (for fetching issue data)

Google Gemini API (for AI analysis)

Setup and Run Instructions
This project is designed for simplicity and rapid deployment. It's a single HTML file that runs directly in your browser, making setup incredibly fast.

Estimated Setup Time: Under 1 minute.

Save the Code:

Copy the entire HTML code provided in the project.

Create an HTML File:

Open a plain text editor (e.g., Notepad, TextEdit, VS Code, Sublime Text).

Paste the copied HTML code into the editor.

Save the File:

Save the file with an .html extension (e.g., github_issue_assistant.html).

Important: Ensure your editor's "Save as type" or "Format" is set to "All Files" or "Plain Text" to prevent it from adding a .txt extension.

Open in Browser:

Navigate to the directory where you saved github_issue_assistant.html.

Double-click the file. Your default web browser will open the application.

That's it! The application is now running locally in your browser.

Usage
Enter a GitHub Repository URL (e.g., https://github.com/facebook/react).

Enter an Issue Number (e.g., 28860 for a sample issue in the React repository).

Click the "Analyze Issue" button.

The AI-generated analysis will appear below the input fields. You can also click "Copy Raw JSON" to get the full structured output.

Required AI-Generated JSON Output Format
The AI is engineered to produce output strictly in the following JSON format:

{
  "summary": "A one-sentence summary of the user's problem or request.",
  "type": "Classify the issue as one of the following: bug, feature_request, documentation, question, or other.",
  "priority_score": "A score from 1 (low) to 5 (critical), with a brief justification for the score. For example: '3 (Medium) - Affects a small number of users.'",
  "suggested_labels": ["An array of 2-3 relevant GitHub labels (e.g., 'bug', 'UI', 'login-flow')."],
  "potential_impact": "A brief sentence on the potential impact on users if the issue is a bug."
}

Project Structure and Dependencies
Project Structure: The entire application is contained within a single github_issue_assistant.html file, simplifying deployment and local execution. All HTML, CSS (via Tailwind CDN), and JavaScript are self-contained.

Dependency Management: As this is a pure frontend application, there are no traditional backend dependency management files (like requirements.txt or pyproject.toml). All external libraries (Tailwind CSS, Google Gemini API) are loaded via CDNs or direct API calls within the JavaScript.

Handling Edge Cases
Invalid GitHub URL: The application includes basic validation for the GitHub URL format.

Issue Not Found (404): If an issue number does not exist for the given repository, a specific error message is displayed.

GitHub API Rate Limits (403): The application informs the user if GitHub API rate limits are encountered.

Issues with No Body/Comments: The prompt handles cases where the issue body or comments might be empty by providing default "No body provided." or "No comments." strings to the LLM.

LLM Output Deviations: The JavaScript includes a robust JSON parsing mechanism with a regex to extract the JSON block, making it more resilient if the LLM includes extra text or markdown formatting around the JSON. Error logging to the browser console is also implemented to aid debugging if the AI response is malformed.

Going the Extra Mile
"Copy Raw JSON" Button: Allows users to easily copy the complete structured JSON output generated by the AI, which is useful for integration or further analysis.

Custom Modals for Messages: Instead of using intrusive browser alert() or confirm() functions, custom HTML/CSS modals are implemented for displaying success (e.g., "JSON copied!") and error messages, providing a smoother user experience.

Pre-filled Example: The input fields are pre-filled with a sample GitHub repository URL and issue number (https://github.com/facebook/react and 28860) to allow for immediate testing upon loading the page.

Clear Loading Indicator: A clear loading message is displayed while the AI analysis is in progress, improving user feedback.

This project demonstrates a practical application of AI in a development workflow, aligning with Seedling Labs' mission to productize and scale AI innovations for real-world impact.
