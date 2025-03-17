
<h1 align="center">GitHub Advanced Security Bootcamp - GitHub Advanced Security Administration</h1>

> This bootcamp is designed to help familiarize you with the GitHub Advanced Security (GHAS) administration features so that you can better understand how to use them in your own repositories.

## 🏫 Exercise

### GitHub Advanced Security Administration
1. Enable GHAS using the GitHub Enterprise Cloud UI.
      1. Click on "Settings" at the top of the repository home page and then click on "Code security" on the left under the "Security" section.
      2. Click the "Enable" button next to "GitHub Advanced Security" and then "Enable GitHub Advanced Security for this repository".
      3. Scroll down and observe that you can now enable and configure both secret scanning and code scanning.
2. Define a security policy at the enterprise level.
      1. Click on your avatar in the upper right-hand corner of the GitHub UI and click "Your enterprises".
      2. Click "Settings" next to the "Coveros, Inc.," enterprise.
      3. Click "Policies" and then "Code Security" on the left-hand side of the page.
      4. Under "GitHub Advanced Security policies", observe the available "Allowed / Not allowed" options.
      5. Note that under "GitHub Advanced Security availability" that it is possible to allow GHAS only for selected organizations.
3. Define a security policy at the repository level.
      1. Press the back button in your browser until you are back in the ghas-certification-bootcamp repository.
      2. Click "Security" at the top of the page and then "Policy" on the left.
      3. Click "Start setup".
      4. Review the existing template and add information about supported versions and reporting vulnerabilities for a hypothetical project.
      5. Click "Commit changes...", add a descriptive commit message, and then click "Commit changes".
      6. Click on "Settings" at the top of the page.
      7. Scroll down and check the box next to "Issues" to enable this feature.
      8. Click on the "Issues" tab at the top of the repository.
      9. Click "New issue" and select "Blank issue".
      10. Observe that there is now a link to the security policy at the bottom of the issue creation modal. Click on it to view the security policy that you just established.
4. Give additional teams and users access to code scanning, secret scanning, and Dependabot alerts.
      1. Click on "Settings" at the top of the repository home page and then click on "Code security" on the left under the "Security" section.
      2. Scroll down to the bottom of the page to see the "Access to alerts" section.
      3. Grant another person or team access to view and manage security-related alerts.
      4. Observe that the person or team that you added has been appended to the list of those who have access.
5. Invoke an example GH API endpoint for code scanning, secret scanning, and dependency analysis.
      1. You will first need to generate a Personal Access Token (PAT) that you will use to invoke the GitHub API. Click on your avatar in the upper right-hand corner of the GitHub UI and then on "Settings".
      2. Scroll down and then click on "Developer settings" on the left.
      3. Click "Personal access tokens" and then "Tokens (classic)".
      4. Click the "Generate new token" button and then select "Generate new token (classic)".
      5. Give your token a name and check the box next to "security_events", which appears under the "repo" section. Scroll down to the bottom of the page and click the "Generate token" button.
      6. Copy the generated PAT and store it in a safe location.
      7. Open a new browser tab and visit reqbin.com.
      8. Click on "Headers" and then add a header for each of the following "key / value" pairs, replacing <YOUR-TOKEN> with the PAT that you generated earlier.
           1. Accept / application/vnd.github+json
           2. Authorization / Bearer <YOUR-TOKEN>
           3. X-GitHub-Api-Version / 2022-11-28
      9. Enter each of the following URLs into the address bar with "https://google.com or CURL command" as the placeholder text, replace the placeholder repo name with the name of your fork of the bootcamp repo, and click the "Send" button. Review the information returned on code scanning, secret scanning, and Dependabot alerts, respectively.
           1. https://api.github.com/repos/Coveros-External/<YOUR-REPO-NAME>/code-scanning/alerts
           2. https://api.github.com/repos/Coveros-External/<YOUR-REPO-NAME>/secret-scanning/alerts
           3. https://api.github.com/repos/Coveros-External/<YOUR-REPO-NAME>/dependabot/alerts
6. Set up CodeQL analysis using the default workflow.
      1. Click on "Settings" at the top of the repository home page and then click on "Code security" on the left under the "Security" section.
      2. Scroll down to the "Code scanning" section. Click "Set up" next to CodeQL Analysis and then select "Default".
      3. Review the defaults for languages, scan settings, and scan events.
      4. Click the "Edit" button.
      5. Update the languages and scan settings if needed.
      6. Click "Enable CodeQL".
      7. Click on the "Actions" tab and then wait 1-2 minutes until the CodeQL workflow completes.
      8. Once the initial CodeQL scan has completed, you should be able to view the results under the "Code scanning" section of the "Security" tab.
