# we-have-tiktok-at-home

This repository and accompanying GitHub projects serve as a blueprint for managing the development of a software product.

In our case, it's a TikTok-like application.

See our [Roadmap](https://github.com/orgs/inno-swp-2025/projects/5/views/4), [Product Backlog](https://github.com/orgs/inno-swp-2025/projects/1), and [Tasks](https://github.com/orgs/inno-swp-2025/projects/2).

## Set up your project

1. [Create](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch) a GitHub organization.
1. [Import](https://docs.github.com/en/migrations/importing-source-code/using-github-importer/importing-a-repository-with-github-importer) or [transfer](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository) your repositories into your organization.
1. Import the [.github](https://github.com/inno-swp-2025/.github) repository into your organization.
1. Create issue types (see [Issue types](#issue-types)).
1. Create issue labels (see [Issue labels](#issue-labels)).
1. Copy our projects (see [Projects](#projects)).
1. Create issues following the [work item hierarchy](#work-item-hierarchy) and using [issue form templates](#issue-form-templates).
1. Set `Priority` and `Story Points` in your type `Backlog` issues (see [Project `Product Backlog`](#project-product-backlog)).
1. If some type `Backlog` issues with label `Backlog: User Story` are too large, convert them into type `Epic` issues and add there smaller type `Backlog` sub-issues.
1. Set `Start` and `Finish` in your type `Epic` issues (see [Project `Roadmap`](#project-roadmap)).
1. Create milestones in the project `Roadmap` and add type `Epic` issues to these milestones.
1. Set `Ideal Hours` and `Priority` in your type `Task` issues (see [Project `Tasks`](#project-tasks)).
1. Set matching `Sprint` in your type `Backlog` issues and their type `Task` sub-issues.
1. Adjust the entry criteria specified in Kanban boards in the `Roadmap` and `Product Backlog` projects. Criteria for a column specify when an issue can be moved to that column.

## Work item hierarchy

We use the following hierarchy of work items that are represented via issues of different types and pull requests [^1].

```mermaid
graph LR
    %% --- Style Definitions ---
    
    classDef styleEpicType fill:#211a18,stroke:#db6d28,color:#db6d28,font-size:15pt
    classDef styleBacklogType fill:#242138,stroke:#ab7df8,color:#ab7df8,font-size:15pt
    classDef styleTaskType fill:#272114,stroke:#c08d20,color:#c08d20,font-size:15pt
    classDef stylePullRequestLabel fill:#238636,stroke:#238636,color:#cccccc,font-size:15pt

    %% --- Main Hierarchy ---

    subgraph Issues ["`**Work items**`"]
        direction LR
        
        subgraph RoadmapItems ["`**Roadmap Items**`"]
            subgraph EpicIssueType ["`**Issue type**`"]
                EpicTypeLabel([Epic]):::styleEpicType
            end
        end

        subgraph ProductBacklogItems ["`**Product Backlog Items**`"]
            subgraph BacklogIssueType ["`**Issue type**`"]
                BacklogType([Backlog]):::styleBacklogType
            end
        end

        subgraph Tasks ["`**Tasks**`"]
            subgraph TaskIssueType ["`**Issue type**`"]
                TaskType([Task]):::styleTaskType
            end
        end

        subgraph PullRequests ["`**Pull Requests**`"]
            PullRequestLabel([fa:fa-code-pull-request Pull Request]):::stylePullRequestLabel
        end

        RoadmapItems -. "`**break down into**`" .-> ProductBacklogItems
        ProductBacklogItems -. "`**break down into**`" .-> Tasks

        Tasks -. "`**are completed by**`" .-> PullRequests
        
    end
```

## Issues

### Sample issues

We created several sample [issues](https://github.com/inno-swp-2025/we-have-tiktok-at-home/issues) in the [inno-swp-2025/we-have-tiktok-at-home](https://github.com/inno-swp-2025) repository.

### Issue types

Each issue has a [type](https://docs.github.com/en/issues/tracking-your-work-with-issues/configuring-issues/managing-issue-types-in-an-organization).

Types:

- `Epic` - An Epic is a container for a major initiative that is too large and complex to be completed in a single sprint. It groups together related Product Backlog Items to achieve a larger goal. This initiative can be a customer-facing feature, a large-scale bug fix, a technical debt reduction plan, or a significant architectural improvement.
- `Backlog` - A Product Backlog Item (PBI) is a unit of work that is small enough to be completed by the team within a single sprint. It represents a concrete step toward completing an Epic. A PBI must deliver a demonstrable increment of value, though that value may be for the end-user (a feature), for the system (stability/performance), or for the development team (enabling future work).
- `Task` - A Task is a specific action required to complete a Product Backlog Item (PBI). It breaks down a PBI into the smallest, most granular steps needed for implementation or completion.

### Issue labels

Issues have meaningful [labels](https://github.com/inno-swp-2025/we-have-tiktok-at-home/labels).

If you plan to have several repositories in your organization, you can [create default issue labels](https://docs.github.com/en/organizations/managing-organization-settings/managing-default-labels-for-repositories-in-your-organization).

### Compatibility of issue types and labels

|                | `Epic` | `Backlog` | `Task` |
| -------------- | :----: | :-------: | :----: |
| `Meta: *`      |   ✅   |    ✅     |   ✅   |
| `Platform: *`  |   ✅   |    ✅     |   ✅   |
| `Scope: *`     |   ✅   |    ✅     |   ✅   |
| `Component: *` |   ✅   |    ✅     |   ✅   |
| `Severity: *`  |   ✅   |    ✅     |   ❌   |
| `Epic: *`      |   ✅   |    ❌     |   ❌   |
| `Backlog: *`   |   ❌   |    ✅     |   ❌   |

Legend:

- Columns - issue types.
- Rows - issue labels.
- ✅ - compatible.
- ❌ - incompatible.
- `*` in issue labels is a placeholder for actual text.

### Issue priority

In our [projects](#projects), we use a custom `Priority` field of type `Number` for setting issue priority and sorting/slicing issues by priority.

`Priority` can have the following values:

- `0` - Highest priority. Requires immediate attention.
- `1` - High priority. Essential to achieving a primary goal for the current sprint or project phase.
- `2` - Medium priority. Important work that provides significant value but is not time-critical.
- `3` - Low priority. Valuable, but non-essential.

## Pull requests

Each pull request should address a particular type `Task` issue.

You should avoid creating pull requests that don't address a particular type `Task` issue (aka "last-minute changes").

The `PR: *` labels are automatically assigned to pull requests when you create pull requests from [templates](#pull-request-templates).

## Templates

We store [default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file) in the [inno-swp-2025/.github](https://github.com/inno-swp-2025/.github) repository.

Our files include issue form templates and pull request templates (see [docs](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms)).

These templates can be used for creating new issues and pull requests in all organization repositories.

### Issue form templates

The following templates are available:

- For type `Epic` issues:
  - [User Story](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/epic-user-story.yml)
  - [Bug Report](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/epic-bug-report.yml)
  - [Enabler](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/epic-enabler.yml)
  - [Investigation](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/epic-investigation.yml)
  - [Tech Debt](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/epic-tech-debt.yml)
- For type `Backlog` issues:
  - [User Story](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/backlog-user-story.yml)
  - [Bug Report](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/backlog-bug-report.yml)
  - [Enabler](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/backlog-enabler.yml)
  - [Investigation](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/backlog-investigation.yml)
  - [Tech Debt](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/backlog-tech-debt.yml)
- For type `Task` issues:
  - [Task](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/task.yml)

### Pull request templates

The following templates are available:

- [For type `Task` issues](https://github.com/inno-swp-2025/.github/blob/main/.github/PULL_REQUEST_TEMPLATE/task.md)
- [For last-minute changes](https://github.com/inno-swp-2025/.github/blob/main/.github/PULL_REQUEST_TEMPLATE/last-minute-changes.md) that don't resolve any particular type `Task` issue.

## Milestones

Milestones are specific, key points within a project that mark progress and completion of significant phases or tasks[^2].

Milestones are not sprints [^3].

We defined two [milestones](https://github.com/inno-swp-2025/we-have-tiktok-at-home/milestones) and provided their goals in descriptions.

## Projects

[GitHub Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects) are a tool for project management on GitHub.

You can [copy](https://docs.github.com/en/issues/planning-and-tracking-with-projects/creating-projects/copying-an-existing-project) our projects and use them as templates.

We [provide](https://github.com/orgs/inno-swp-2025/projects) projects for:

- [Roadmap Items](#project-roadmap)
- [Product Backlog Items](#project-product-backlog)
- [Tasks](#project-tasks)

## Project `Roadmap`

[Link](https://github.com/orgs/inno-swp-2025/projects/5)

This project allows for planning and tracking the progress of type `Epic` issues.

### Limitations

- The `Start` and `Finish` fields must be (manually) synchronized with start and finish dates of related type `Backlog` issues.

### Project settings

#### Custom fields (additional)

- `Start` of type `Date` - (planned) date of starting the work on an issue.
- `Finish` of type `Date` - (planned) date of finishing the work on an issue.
- `Priority` of type `Number` - numeric priority of an issue (see [Issue priority](#issue-priority)).

### View `Timeline`

- Layout: `Roadmap`.
- Configuration:
  - Group by: `Milestone`.
  - Markers: `none`.
  - Sort by: `manual`.
  - Dates: `Start and Finish`.
  - Zoom level: `Month`.
  - Field sum: `Count`.
  - Slice by: `none`.
- User settings:
  - [x] Show date fields.

### View `Status`

- Layout: `Board`.
- Configuration:
  - Fields: `Assignees`, `Status`, `Sub-issues progress`, `Start`, `Finish`, `Priority`.
  - Column by: `Status`.
  - Group by: `Milestone`.
  - Sort by: `Priority` (ascending).
  - Field sum: `Count`
  - Slice by: `Priority`.

#### Columns

There are entry criteria for each column.
An issue can be closed when it reaches the `Done` column.

##### To Do

```text
[Entry Criteria]
* The issue field "Priority" was filled in.
* The issue fields "Start" and "Finish" were filled in.
* The issue was added to a milestone. * Type "Backlog" issues were added as sub-issues of the issue.
```

##### In Progress

```text
[Entry Criteria]
* Some sub-issues were completed.
* A person who would monitor the issue progress was assigned to the issue.
```

##### In Review

```text
[Entry Criteria]
* All sub-issues were completed.
* All changes introduced for this issue were deployed to the staging environment.
* A person who would verify the acceptance criteria was assigned to the issue.
```

##### Done

```text
[Entry Criteria]
* All acceptance criteria were met on the staging version.
* A production version with changes introduced for this issue was deployed.
* All acceptance criteria specified in the issue were met on that version.
```

## Project `Product Backlog`

[Link](https://github.com/orgs/inno-swp-2025/projects/1)

This project allows for estimation, planning, and tracking the progress of type `Backlog` issues.

Additionally, it visualizes connections between type `Backlog` issues and their parent type `Epic` issues.

### Limitations

- The `Sprint` field of a type `Backlog` issue and its type `Task` sub-issue must be (manually) synchronized.

### Project settings

#### Custom fields (additional)

- `Story Points` of type `Number` - estimate of a `Backlog` issue in Story Points.
- `Sprint` of type `Iteration` - a sprint that the issue belongs to.
- `Priority` of type `Number` - numeric priority of an issue (see [Issue priority](#issue-priority)).

### View `Status`

- Provides `Entry Criteria` in Kanban board column descriptions.
- Shows total `Story Points` per sprint.

#### View options

- Layout: `Board`.

- Configuration:
  - Fields: `Assignees`, `Status`, `Sprint`, `Story Points`, `Priority`, `Sub-issues progress`.
  - Column by: `Status`.
  - Group by: `Sprint`.
  - Sort by: `Sprint` (ascending).
  - Field sum: `Count`, `Story Points`.
  - Slice by: `Priority`.
  
#### Columns

There are entry criteria for each column.
An issue can be closed when it reaches the `Done` column.

##### To Do

```text
[Entry Criteria]
* The issue was updated (e.g., via an LLM) to conform a relevant issue form template.
* Relevant labels were assigned to the issue.
* Type "Task" issues were added as sub-issues of the issue.
* The issue field "Story Points" was filled in.
* The issue was added to a sprint.
* Sub-issues of the issue were added to a matching sprint in the "Tasks" project.
```

##### In Progress

```text
[Entry Criteria]
* The issue description was revised to provide missing details.
* The issue was added to the current sprint.
```

##### Ready To Deploy

```text
[Entry Criteria]
* All sub-issues of the issue were completed.
* All changes introduced to complete the issue were deployed to the staging environment.
* All acceptance criteria specified in the issue were met in the staging environment.
```

##### Done

```text
[Entry Criteria]
* All changes introduced to complete the issue were deployed to the production environment.
* All acceptance criteria specified in the issue were met in the production environment.
```

### View `Timeline`

Shows planned schedule of working on type `Backlog` issues.

#### View options

- Layout: `Roadmap`.

- Configuration:
  - Group by: `Sprint`.
  - Markers: `Sprint and Milestone`.
  - Sort by: `Sprint` (ascending), `Priority` (ascending).
  - Dates: `Sprint`.
  - Zoom level: `Month`.
  - Field sum: `Count`, `Story Points`.
  - Slice by: `Parent issue`.

## Project `Tasks`

[Link](https://github.com/orgs/inno-swp-2025/projects/2)

This project allows for estimation, planning, and tracking the progress of type `Task` issues.

Additionally, it visualizes connections between type `Task` issues and their parent type `Backlog` issues.

### Limitations

- The `Sprint` field of a type `Task` issue and its parent type `Backlog` issue must be (manually) synchronized.

### Project settings

#### Custom fields (additional)

- `Ideal Hours` of type `Number` - estimated number of ideal hours required to complete the issue.
- `Sprint` of type `Iteration` - a sprint that the issue belongs to.
- `Priority` of type `Number` - numeric priority of an issue (see [Issue priority](#issue-priority)).
- `Start` of type `Date` - (planned) date of starting the work on an issue.
- `Finish` of type `Date` - (planned) date of finishing the work on an issue.

### View `Status`

- Provides `Entry Criteria` in Kanban board column descriptions.
- Shows total `Ideal Hours` per sprint.

#### Settings

- Layout: `Board`.

- Configuration:
  - Fields: `Assignees`, `Status`, `Sprint`, `Ideal Hours`, `Priority`, `Linked pull requests`.
  - Column by: `Status`.
  - Group by: `Sprint`.
  - Sort by: `Sprint` (ascending), `Priority` (ascending).
  - Field sum: `Count`, `Ideal Hours`.
  - Slice by: `none`.

#### Columns

There are entry criteria for each column.
An issue can be closed when it reaches the `Done` column.

##### To Do

```text
[Entry Criteria]
* The issue was updated (e.g., via an LLM) to conform to the type "Task" issue form template.
* The type "Task" was assigned to the issue.
* Relevant labels were assigned to the issue.
* The issue was made a sub-issue of a type "Backlog" issue.
```

##### In Progress

```text
[Entry Criteria]
* The issue description was revised to provide missing details.
* The issue field "Ideal Hours" was filled in.
* The issue was added to the current sprint.
* The issue was assigned.
* If necessary, a branch for the issue was created via the "create a branch" button on the issue page.
```

##### Ready For Review

```text
[Entry Criteria]
* A pull request for the issue was created using a relevant template.
* Implementation in the pull request was completed.
* The "main" branch was merged into the pull request branch.
* CI pipeline with automated tests succeeded on the pull request branch.
* All sections in the pull request description were updated to match implementation.
* A review of the pull request was requested.
```

##### Ready to Merge

```text
[Entry Criteria]
* All acceptance criteria specified in the issue were met on the pull request branch.
* The pull request was approved.
```

##### Done

```text
[Entry Criteria]
* The pull request was merged into the main branch.
* If no pull request was required to complete the issue: All acceptance criteria specified in the issue were met.
```

### View `With Parents`

- For each type `Backlog` issue, shows to which sprint its type `Task` sub-issues were assigned.
- Shows total `Ideal Hours` for a `Sprint`.
- Shows type `Task` issues sorted by priority within each `Sprint`.

#### Settings

- Layout: `Table`.

- View options:
  - Fields: `Sprint`, `Priority`, `Ideal Hours`, `Status`, `Assignees`, `Parent issue`.
  - Group by: `Sprint`.
  - Sort by: `Priority` (ascending), `Ideal Hours` (ascending).
  - Fields sum: `Count`, `Ideal Hours`.
  - Slice by: `Parent issue`.

### View `Timeline`

- Shows type `Task` issues distributed by sprints on a timeline.
- `Date fields` are set to `Sprint start` and `Sprint end`.
- One can set the `Date fields` to `Start` and `Finish` and adjust them by clicking on the left or on the right side of an issue box on the timeline and dragging it.

#### Settings

- Layout: `Roadmap`

- Configuration:
  - Group by: `Sprint`.
  - Markers: `Sprint`.
  - Sort by: `Sprint` (ascending), `Priority` (ascending).
  - Dates: `Sprint`.
  - Zoom level: `Month`.
  - Field sum: `Count`, `Ideal Hours`.
  - Slice by: `Parent issue`.

- User settings:
  - `Show date fields`

[^1]: Adapted from <https://learn.microsoft.com/en-us/azure/devops/boards/backlogs/define-features-epics?view=azure-devops&tabs=scrum-process#portfolio-backlogs>
[^2]: <https://www.atlassian.com/blog/project-management/project-milestones>
[^3]: <https://pm.stackexchange.com/questions/22510/sprint-vs-milestone-vs-release>
