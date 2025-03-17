## Dependabot

### Contents

- [Enabling Dependabot alerts](#enabling-dependabot-alerts)
- [Reviewing the dependency graph](#reviewing-the-dependency-graph)
- [Viewing and managing results](#viewing-and-managing-results)
- [Enabling Dependabot security updates](#enabling-dependabot-security-updates)
- [Configuring Dependabot security updates](#configuring-dependabot-security-updates)

### _**Lab 1**_

#### Enabling Dependabot alerts
Dependabot can be enabled in the settings of an organization or a repository.

- Go to the repository settings and enable Dependabot alerts in the `Code security and analysis` section. You will be prompted to enable the dependency graph if it's not enabled already.

#### Reviewing the dependency graph
Dependabot uses the dependency graph to determine which dependencies are used by your project.

- Verify in the dependency graph that it found dependencies for:
    - The frontend service.
    - The authentication service.
    - The gallery service.
    - The storage service.

The dependency graph can be accessed from the `Insights` tab in your repository.

#### Viewing and managing results

After a few minutes, the `Security` tab in the repository will indicate that there are new security alerts. (**Note**: If this not the case, we can trigger an analysis by updating `authn-service/requirements.txt`) In this section we will create a security update for a single dependency, while the next section will show you how to enable security updates for all applicable Dependabot alerts.

1. Go to the Dependabot alerts section to view the detected dependency issues.

For each dependency alert, we have the option to create a security update or to dismiss the alert with a reason.

2. For one of the alerts, create a Dependabot security update. If Dependabot can update the dependency automatically, it will create a pull request (PR).

3. For one of the alerts, dismiss it.

#### Enabling Dependabot security updates

Dependabot can automatically create PRs to upgrade vulnerable dependencies to non-vulnerable versions. Please note that there may be some Dependabot alerts that don't have patches. In those cases, a security update is not available.

- Go to the repository settings and enable Dependabot security updates in the *Code security* section.

After a few minutes multiple PRs will be created that will upgrade vulnerable dependencies.

#### Configuring Dependabot version updates

You can enable Dependabot [*version updates*](https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/enabling-and-disabling-version-updates) by checking in a dependabot.yml file into your repository's `.github` directory. Dependabot security updates uses this configuration as well. To successfully integrate version updates into the SDLC, it is possible to configure various aspects such as:

- When version updates are created.
- What labels are assigned to enable filtering options.
- Who is assigned to the PR and who should review it.
- Which dependencies are updated and how they are updated.

Create the `.github/dependabot.yml` file in your repository and configure the `pip` dependency manager to:
  1. Look for dependency information in the `authn-service` directory.

  2. Schedule daily version updates.

  3. Prefix the commit message with the `pip` package manager.

  4. Assign the PR to yourself and a person from your workshop team as a reviewer. When specifying GitHub handles in the yml, do so without the `@` symbol. Please see the below solution as an example.

  5. Add the custom label `triage-required` to enable filtering of the PRs.

  6. Verify your changes by adding a [vulnerable dependency](https://github.com/advisories?query=severity%3Ahigh+ecosystem%3Apip) to `authn-service/requirements.txt`. For example:

    ```requirements.txt
    ...
    django==2.1.0
    ```

<details>
<summary>Solution</summary>

```yaml
version: 2
updates:
  - package-ecosystem: "pip"
    directory: "/authn-service"
    schedule:
      interval: "daily"
    labels:
      - "triage-required"
    assignees:
      - "dungeonstechlead"
    reviewers:
      - "dragonsengineer"
    commit-message:
      prefix: "pip"
```
</details>

#### Working with Dependency Review

If a PR has dependency changes, you can [review](https://docs.github.com/en/github/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-dependency-changes-in-a-pull-request) them and see if there are known vulnerabilities with the dependency changes.

   1. Add a vulnerable dependency to `authn-service/requirements.txt` and commit to a new branch. For example, here's a vulnerable dependency:

    ```requirements.txt
    ...
    django-piston==0.2.0
    ```
   2. Create a PR, and click on `Files changed`.
   3. Click on the `Display the rich diff` button (it looks like a sheet of paper) on the `requirements.txt` file to review dependency changes.
