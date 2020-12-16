## Azure Pipelines to Github Actions Comparison

Azure Pipelines has been a leader in CI\CD for a while and is rich in capabilities. Microsoft is focusing their efforts on GitHub actions which is an evolution of the Azures Pipelines architecture. 

This site is to help you,
* understand what the differences are
* choose which platform your should pick 
* migrate to GitHub Actions as that is the future

The official documentation can be found here [Migrating from Azure Pipelines to GitHub Actions](https://docs.github.com/en/free-pro-team@latest/actions/learn-github-actions/migrating-from-azure-pipelines-to-github-actions)

### Feature

Lets start with a simple feature to feature comparison

|Azure Pipelines |Notes| Github Actions |Notes	| Link to roadmap|
|-|-|-|-|-|
Variables|Setting environment variables for scripts	|[Environment Variables](https://docs.github.com/en/free-pro-team@latest/actions/reference/environment-variables) 
Variables|Variables in expressions	|[Environment Variables](https://docs.github.com/en/free-pro-team@latest/actions/reference/environment-variables)|Use $Variable or ${{env.variable}} syntax
[System Variables](https://docs.microsoft.com/en-us/azure/devops/pipelines/build/variables?view=azure-devops&tabs=yaml)||[Default Environment Variables](https://docs.github.com/en/free-pro-team@latest/actions/reference/environment-variables#default-environment-variables)| Totally different naming for variables.
[Secret variables](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops&tabs=yaml%2Cbatch#secret-variables)||[Encrypted secrets](https://docs.github.com/en/free-pro-team@latest/actions/reference/encrypted-secrets)
Agents||Runners|Its the same agent being used by both Azure Devops and Git Hub Actions
[Scaling build agents](https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/scale-set-agents?view=azure-devops)||roadmap|[Actions: Multiple hosted runner sizes, custom networking, and custom images · Issue #95](https://github.com/github/roadmap/issues/95)
Deployment Groups||[Runners with labels](https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/using-self-hosted-runners-in-a-workflow_)|Target based on matching ALL labels	Using self-hosted runners in a workflow - GitHub Docs
Environments||[Environments beta](https://docs.github.com/en/free-pro-team@latest/actions/reference/environments#about-environments)| Can only be used for public repos<br>Does allow assigning resources to the environment	
[Expressions](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/expressions?view=azure-devops)||[Context and Expressions](https://docs.github.com/en/free-pro-team@latest/actions/reference/context-and-expression-syntax-for-github-actions)|Looks slightly nicer than azure devops, access to richer context objects|
[Condition](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/conditions?view=azure-devops&tabs=yaml)|Executing a task based on a condition, is a first class attribute of a step, job or stage|[Conditional Expression](https://docs.github.com/en/free-pro-team@latest/actions/reference/context-and-expression-syntax-for-github-actions#job-status-check-functions)|Use the `if`  along with expression|
[Stages](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/stages?view=azure-devops&tabs=yaml)|Multiple jobs  chained together|[Workflows chained](https://docs.github.com/en/free-pro-team@latest/actions/reference/events-that-trigger-workflows)| Environments with checks will also provide a stage approach but at the job level
[Stage Approval](https://docs.microsoft.com/en-us/azure/devops/pipelines/process/approvals?view=azure-devops&tabs=check-pass)|As with azure |[Reviewing Deployments - beta](https://docs.github.com/en/free-pro-team@latest/actions/managing-workflow-runs/reviewing-deployments)||[Actions: Manual approvals in workflows · Issue #99](https://github.com/github/roadmap/issues/99)
[Release Gates](https://docs.microsoft.com/en-us/azure/devops/pipelines/release/approvals/gates?view=azure-devops)| Azure pipelines yml doesn't support gates either, only the classic release|[Custom Action](https://github.com/marketplace?type=actions)| Actions can be used for some gates, polling/retry/timeout thats something to build into the action and thus will be using a runner for that time
[Logging Commands](https://docs.microsoft.com/en-us/azure/devops/pipelines/scripts/logging-commands?view=azure-devops&tabs=bash)||[Workflow commands](https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-commands-for-github-actions#about-workflow-commands)|Very similar
[Set variable at runtime](https://docs.microsoft.com/en-us/azure/devops/pipelines/scripts/logging-commands?view=azure-devops&tabs=powershell#overview)||[Workflow commands](https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-commands-for-github-actions#about-workflow-commands)|use ::set-env|
Fine grained repo controls||roadmap||[Role-based Access Control (RBAC) - Custom Roles with fine-grained repo permissions · Issue #111](https://github.com/github/roadmap/issues/111)
Auto merge PRs|Be able to auto merge a PR once checks have passed|roadmap|||[Automerge Pull Requests · Issue #107](https://github.com/github/roadmap/issues/107)
Pipeline templates||[Sharing Workflows](https://docs.github.com/en/free-pro-team@latest/actions/learn-github-actions/sharing-workflows-with-your-organization)||[Actions: Centrally managed workflow templates · Issue #98](https://github.com/github/roadmap/issues/98)<br>
Template control|Be able to inject template and enforce policy	roadmap	|||	[Actions: Organization and enterprise workflows · Issue #52](https://github.com/github/roadmap/issues/52)
TaskGroup		||Custom Action|	???	
VariableGroup|||Variables have to be defined as secrets or in the yml			



