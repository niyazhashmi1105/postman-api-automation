# Postman API Automation for Booking API

This project is an automated testing setup for the **Booking API** using **Postman** collections and the **Newman** CLI. The project contains the necessary collections, environments, and global variables for testing Booking API endpoints. The automation runs in CI/CD pipelines using GitHub Actions and generates detailed HTML reports for test results.

---

## Prerequisites

Before running the tests, ensure you have the following installed:

1. **Node.js** (v16 or later)
2. **npm** (comes with Node.js)
3. **Newman** (Postman collection runner)

You can install Newman globally using npm:
npm install -g newman

Project Structure
.github/workflows/postman.yaml: Contains the GitHub Actions workflow for running Newman tests automatically in CI/CD.
newman/: Directory for storing generated reports (e.g., report.html).
postman/: Contains the Postman collection, environment variables, and globals for the Booking API:
BookingAPIsCollection.json: Postman collection for Booking API requests.
BookingAPIsEnvironmentVariables.json: Environment file for setting specific values such as base URLs or API keys.
BookingAPIsGlobals.json: Global variables used across the collection.
package.json: Defines the project’s metadata and dependencies.
package-lock.json: Locks the versions of dependencies to ensure consistency.
.gitignore: Ignores certain files like node_modules/ and temporary files.

Installation
Clone the Repository:

git clone https://github.com/niyazhashmi1105/POSTMAN-API-AUTOMATION.git
cd POSTMAN-API-AUTOMATION
Install Dependencies: After cloning the repository, install the required Node.js dependencies:

npm install
Install Newman (if not installed globally):

npm install -g newman
Running the Postman Collection Locally
To run the Postman collection manually using Newman, use the following command:

newman run postman/BookingAPIsCollection.json --environment postman/BookingAPIsEnvironmentVariables.json --globals postman/BookingAPIsGlobals.json -r htmlextra --reporter-htmlextra-export newman/report.html

This command will run the BookingAPIsCollection.json collection.
Use BookingAPIsEnvironmentVariables.json as the environment.
Use BookingAPIsGlobals.json for global variables.
Output results in both CLI and HTML formats, saving the HTML report to newman/report.html.
Running Tests in GitHub Actions
This project is configured to run the Postman collection automatically using GitHub Actions. The workflow is defined in .github/workflows/postman.yaml.

Whenever changes are pushed to the main branch or a pull request is made, the tests will run automatically, and an HTML report will be generated and uploaded as an artifact.

Viewing Test Reports
After running the tests, you can view the generated HTML report:

Locally: Open newman/report.html in your browser.

From GitHub Actions:

Navigate to the "Actions" tab in your GitHub repository.
Select the workflow run.
Download the HTML report artifact named newman-report.

Email Notifications:

The attached HTML Report should be sent to the relevant stakeholders as an attached and body of the email.
