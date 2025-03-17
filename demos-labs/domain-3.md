# Demos and Labs - Domain 3

## Configure and use dependency management


### Enable dependency graph:
1. Go to repository Settings.
2. Select Code security.
3. Select Enable in the dependency graph section.


### View dependency graph:
1. Go to repository Insights.
2. Select Dependency graph.
3. Select the Dependencies or Dependents tab from the Dependency graph view.


### Export SBOM:
1. Go to dependency graph.
2. Click Export SBOM button.


### Enable Dependabot alerts:
1. Go to repository Settings.
2. Select Code security.
3. Select Enable for Dependabot alerts.


### Grant access to Dependabot alerts:
1. Go to repository Settings.
2. Select Code security.
3. In the Access to alerts section, type the name of the person or team that you would like to be able to manage Dependabot alerts in the search bar. Make your selection.
4. Select Save changes.


### Inside a Dependabot alert:
1. Go to repository Security > Dependabot.
2. Select a Dependabot alert to view.
3. Review info and metadata about the vulnerable dependency.


### Enable grouped security updates:
1. Go to repository Settings.
2. Select Code security.
3. Select Enable for Grouped security updates.


### Inside a Dependabot PR:
1. Go to repository Pull requests.
2. Select a PR opened by dependabot.
3. Review info and metadata about the change/fix.


### Create `dependabot.yml` config file:
1. Go to dependency graph > Dependabot.
2. Click Create config file button.
3. Edit and commit `dependabot.yml` file.


### Configure notifications for Dependabot alerts:
1. Go to your [Settings > Notifications](https://github.com/settings/notifications)
3. Find System section
4. Use dropdowns to make selections


### View and triage notifications:
1. Go to your [Notifications inbox](https://github.com/notifications)
2. Try various Filters
3. Try various Group by options


### Create a custom Dependabot rule:
1. Go to repository Settings
2. Select Code security
3. Select gear icon for Dependabot rules
4. Select New rule
5. Enter a Rule name
6. Complete Rule configuration
7. Select Create rule


### Configure `dependency-review.yml` workflow:
1. Go to repository Actions > New workflow
2. Enter "dependency review" in the search field
3. Select Configure for the Dependency Review workflow
4. Edit and commit the `dependency-review.yml` file in the `.github/workflows` directory


### Dependency Review in action:
1. Open a PR with a dependency change
2. Wait for dependency-review action to complete
3. Check dependency-review summary in the PR
> --OR-- find how other repos leverage the [dependency-review-action](https://github.com/actions/dependency-review-action/network/dependents)  
> [GH Marketplace > Dependency Review](https://github.com/marketplace/actions/dependency-review)


### Explore GitHub Advisory Database:
1. Go to [github.com/advisories](https://github.com/advisories)
2. Try various filters
3. Try search functionality
4. Open a couple advisories for more detail


### Enable Dependabot security updates:
1. Go to repository Settings.
2. Select Code security.
3. Select Enable for Dependabot security updates.


### Dismiss an alert:
1. Select an alert and click Dismiss
2. Select a reason to dismiss
3. Enter a dismissal comment
4. Click Dismiss Alert


### Resolve an alert:
1. Automated - review, test, and merge PRs opened by dependabot
2. Manual - create your own PR to update/remove the dependency
3. Dismiss - use the dismiss feature to close the alert


