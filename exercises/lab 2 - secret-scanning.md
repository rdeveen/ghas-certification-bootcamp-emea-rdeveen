
<h1 align="center">GitHub Advanced Security Bootcamp - Secret Scanning</h1>

> This bootcamp is designed to help familiarize you with the GitHub Advanced Security (GHAS) secret scanning feature so that you can better understand how to use it in your own repositories.

## 🏫 Exercise

### Secret Scanning
1. Enable secret scanning.
      1. Copy the URL for this repository and open it in a new tab so you can complete this and the remaining steps while following the instructions in this README.
      2. Click on the "Settings" option toward the top of the page and then scroll down and click on "Code security" on the left-hand side of the page.
      3. Scroll down and note that GitHub Advanced Security is currently disabled. Click "Enable" and then "Enable GitHub Advanced Security for this repository".
      4. Scroll down to the "Secret scanning" section that now appears and observe that a button is available for enabling this feature. Click "Enable".
      5. Scroll down once more and observe that secret scanning is enabled.
2. Commit a secret to the repository.
      1. Click on "Code" toward the top of the page.
      2. Click "Add file > Create new file".
      3. Name the file "credentials.yml".
      4. Add the following (inactive) secret to the file:
           ```github-token: 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```
      5. Click "Commit changes" and then "Commit changes" again to commit the new file and secret directly to the main branch.
3. Review secrets that have been identified by secret scanning.
      1. Click on "Security" toward the top of the page and then "Secret scanning > Default" on the left-hand side.
      2. Review the list of detected secrets. You should see the secret that you just added as well as several others. Explore using the filters in the table header to narrow down the results.
      3. Select the secret that you just added. View the information available for the secret, to include the remediation steps, detection location, and secret type. Click the "Verify secret" button to see whether this secret can actually be exploited.
4. Close a secret scanning alert.
      1. Click the "Close as" dropdown for the secret and "Revoked" as the dismissal reason.
      2. Review the other types of reasons for closing the secret.
      3. Add a comment explaining why the alert is being closed.
      4. Click "Close alert".
      5. Observe that there is now a "Reopen alert" button where the "Close as" button used to be. This button can be used to mark the alert as open again if you change your mind later.
      6. Click the "Secret scanning alerts" link toward the top of the page and observe that the secret no longer appears in the list. Click "Closed" to see the secret that you just dismissed.
5. Enable secret scanning push protection to prevent secrets from being written to the repository.
      1. Click on the "Settings" option toward the top of the page and then scroll down and click on "Code security" on the left-hand side of the page.
      2. Scroll down to the "Secret scanning" section.
      3. Click the "Enable" button next to "Push protection".
      4. Scroll back down to the secret scanning section and observe that it is now possible to configure who can bypass push protection. Review the available options but leave this setting unchanged.
6. Attempt to commit a secret, but have that commit stopped by push protection.
      1. Click on "Code" toward the top of the page.
      2. Click the "credentials.yml" file.
      3. Click the edit button, which is represented by a pencil icon.
      4. Add the following (inactive) secret to the file:
           ```github-token-2: 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```
      5. Click "Commit changes...", enter a descriptive commit message, and then click "Commit changes" again.
      6. You should be presented with a message indicating that you are attempting to commit a secret and that the push has been blocked.
7. Bypass push protection
      1. Review the information in the push protection modal.
      2. Select "I'll fix it later" to acknowledge the risk and and then click "Allow secret".
      3. Click "Commit changes...", add a descriptive commit message, and then click "Commit changes" again.
      4. Click on "Security" toward the top of the page and then "Secret scanning > Default" on the left-hand side.
      5. Review the list of detected secrets. You should see the newly-committed secret.
8. Allow Copilot Secret Scanning to detect generic secrets using AI.
      1. Click on the "Settings" option toward the top of the page and then scroll down and click on "Code security" on the left-hand side of the page.
      2. Scroll down to the "Secret scanning" section.
      3. Click the checkbox next to "Scan for generic passwords".
      4. Scroll to the top of the page and click "Security", expand the secret scanning dropdown on the left, and then click "Experimental".
      5. Observe that several potential secrets have been detected. Click on an alert and observe that it looks similar to a "standard" secret scanning alert. It may take some time for the secret scanning run to be performed, so it may make sense to move on to the remaining secret scanning exercise steps while waiting.
9. Enable validity checks for detected secrets.
      1.  Click on the "Settings" option toward the top of the page and then scroll down and click on "Code security" on the left-hand side of the page.
      2.  Scroll down to the "Secret scanning" section.
      3.  Click the "Enable" button for "Validity checks".
      4.  Validity checks are now enabled for partner-supported patterns.
      5.  Click on "Security" at the top of the page and then "Default" under the "Secret scanning" section on the left. View the detail page for a few secrets and observe that for some verification could not be performed and for others there is text indicating when verification was last performed. The red text above the secret in the alert will indicate whether or not it is valid and active.
10. Enable scans for non-provider patterns.
      1. Click on the "Settings" option toward the top of the page and then scroll down and click on "Code security" on the left-hand side of the page.
      2. Scroll down to the "Secret scanning" section.
      3. Click the "Enable" button for "Non-provider patterns".
      4. Click on "Code" toward the top of the page.
      5. Click on the "credentials.yml" file.
      6. Click the edit button, which is represented by a pencil icon.
      7. Add the following (invalid) HTTP basic auth token to the file:
           ```Authorization: Basic ZGVtbzpwQDU1dzByZA==```
      8. Click "Commit changes" and then "Commit changes" again to commit the new file directly to the main branch.
      9. Scroll to the top of the page and click "Security", expand the secret scanning dropdown on the left, and then click "Experimental".
      10. Observe that a finding for the secret that you added is in the list.
11. Set up a custom pattern.
      1. Click on the "Settings" option toward the top of the page and then scroll down and click on "Code security" on the left-hand side of the page.
      2. Scroll down to the "Secret scanning" section.
      3. Click the "New pattern" button for the Custom patterns section.
      4. Give the pattern the name "My Custom Pattern".
      5. Use "my_custom_secret_[a-z]{3}" as the secret format.
      6. Expand "More options" to view the additional options that are available for configuring secret scanning, although we won't be changing these.
      7. In the "Test string" field enter one or more sample secrets, separated by newlines. You should include examples that you expect to match as well as ones that you do not expect to match. An example of an example that should match is "my_custom_secret_abc", and one that shouldn't match is "my_custom_secret_123".
      8. Click "Save and dry run", and after the page refreshes scroll back down to the "Dry run" section and click the refresh button in the upper right-hand corner of the table.
      9. There should be no pre-existing matches for this secret in the repository, which is expected. You should then click "Publish pattern".
      10. Click on "Code" toward the top of the page.
      11. Click on the "credentials.yml" file.
      12. Click the edit button, which is represented by a pencil icon.
      13. Add a secret matching the custom pattern to the file. For example, "my_custom_secret_zcm".
      14. Click "Commit changes" and then "Commit changes" again to commit the new file directly to the main branch.
      15. Scroll to the top of the page and click "Security", expand the secret scanning dropdown on the left, and then click "Default".
      16. Observe that a finding for the secret matching the custom pattern is in the list.
12. Review the organization-level secret scanning settings.
      1. Click on your avatar in the upper right-hand corner of the GitHub UI and click on "Your oganizations".
      2. Click the "Settings" button for the Coveros-External organization.
      3. Scroll down and expand the "Code security" dropdown on the left. Click "Configurations".
      4. Click the green "New configuration" button.
      5. Scroll down to the secret scanning section. Observe the policies that can be set for a repository to which this configuration is applied.
      6. Scroll down and click "Cancel".
      7. Click on "Global Settings" under "Configurations".
      8. Scroll down to the Secret scanning section.
      9. Observe the options available for scanning for generic secrets, adding a resource link for push protection, and defining custom patterns.
