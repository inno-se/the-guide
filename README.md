# we-have-tiktok-at-home

This repository and accompanying GitHub projects serve as a blueprint for managing the development of a software product.

In our case, it's a TikTok-like application.

See our [Roadmap](github.com/orgs/inno-swp-2025/projects/5/views/4), [Product Backlog](https://github.com/orgs/inno-swp-2025/projects/1), and [Tasks](https://github.com/orgs/inno-swp-2025/projects/2).

## Set up your project

1. [Create](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch) a GitHub organization.
1. [Import](https://docs.github.com/en/migrations/importing-source-code/using-github-importer/importing-a-repository-with-github-importer) or [transfer](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository) your repositories into your organization.
1. Import the [.github](https://github.com/inno-swp-2025/.github) repository into your organization.
1. Create issue types (see [Issue types](#issue-types)).
1. Create issue labels (see [Issue labels](#issue-labels)).
1. Copy our projects (see [Projects](#projects)).
1. Create issues following the [work items hierarchy](#work-items-hierarchy) and using [issue form templates](#issue-form-templates).
1. Set `Priority` and `Story Points` in your type `Backlog` issues (see [Project `Product Backlog`](#project-product-backlog)).
1. If some type `Backlog` issues with label `Backlog: User Story` are too large, convert them into type `Epic` issues and add there smaller type `Backlog` sub-issues.
1. Set `Start` and `Finish` in your type `Epic` issues (see [Project `Roadmap`](#project-roadmap)).
1. Create milestones in the project `Roadmap` and add type `Epic` issues to these milestones.
1. Set `Ideal Hours` and `Priority` in your type `Task` issues (see [Project `Tasks`](#project-tasks)).
1. Set matching `Sprint` in your type `Backlog` issues and their type `Task` sub-issues.
1. Adjust the entry criteria specified in Kanban boards in the `Roadmap` and `Product Backlog` projects. Criteria for a column specify when an issue can be moved to that column.

See our [Product Backlog](https://github.com/orgs/inno-swp-2025/projects/1).

## GitHub Organization

We created the GitHub Organization called [inno-swp-2025](https://github.com/inno-swp-2025) to use organization-specific features.

You can [create](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch) an organization and [transfer](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository) your repositories there.

## Work items hierarchy

We use the following hierarchy of work items represented via different types of issues and pull requests.

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

We created several sample [issues](https://github.com/inno-swp-2025/we-have-tiktok-at-home/issues) in the [inno-swp-2025/we-have-tiktok-at-home](https://github.com/inno-swp-2025) repository.

### Issue types

Each issue has a [type](https://docs.github.com/en/issues/tracking-your-work-with-issues/configuring-issues/managing-issue-types-in-an-organization).

Types:

- `Epic` - a large user story.
- `Backlog` - a Product Backlog Item (PBI).
- `Task` - a task related to a PBI.

### Issue labels

Additionally, issues have meaningful [labels](https://github.com/inno-swp-2025/we-have-tiktok-at-home/labels).

If you plan to have several repositories in your organization, you can [create default issue labels](https://docs.github.com/en/organizations/managing-organization-settings/managing-default-labels-for-repositories-in-your-organization).

### Compatibility of issue types and labels

|                | `Epic` | `Backlog` | `Task` |
| -------------- | :----: | :-------: | :----: |
| `Priority: *`  |   ✅   |    ✅     |   ✅   |
| `Meta: *`      |   ✅   |    ✅     |   ✅   |
| `Platform: *`  |   ✅   |    ✅     |   ✅   |
| `Backlog: *`   |   ❌   |    ✅     |   ❌   |
| `Severity: *`  |   ❌   |    ✅     |   ❌   |
| `Scope: *`     |   ❌   |    ❌     |   ✅   |
| `Component: *` |   ❌   |    ❌     |   ✅   |

Legend:

- Columns - issue types.
- Rows - issue labels.
- ✅ - compatible
- ❌ - incompatible

### Epics and Product Backlog Items

Epics break down into Product Backlog Items (see [Work items hierarchy](#work-items-hierarchy)).

Each sub-issue of a type `Epic` issue must have one of these labels:

- `Backlog: User Story`
- `Backlog: Enabler`
- `Backlog: Investigation`

### Tips

- If you specify the `Scope: *`, specify the `Component: *`.

## Templates

We store [default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file) in the [inno-swp-2025/.github](https://github.com/inno-swp-2025/.github) repository.

These files include [Issue Form](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms) templates.
These templates can be used for creating new issues in all organization repositories.

The following templates are available:

- [Epic](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/epic.yml)
- [Bug report](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/bug-report.yml)
- [Task](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/task.yml)
- [User Story](https://github.com/inno-swp-2025/.github/blob/main/.github/ISSUE_TEMPLATE/user-story.yml)

## The GitHub Projects

[GitHub Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects) let one organize issues, estimate them, and plan work on them.

You can [copy](https://docs.github.com/en/issues/planning-and-tracking-with-projects/creating-projects/copying-an-existing-project) projects and use them as templates.

We [provide](https://github.com/orgs/inno-swp-2025/projects) projects for each issue type:

- [Roadmap](#project-roadmap)
- [Product Backlog](#project-product-backlog)
- [Tasks](#project-tasks)

## Project `Roadmap`

[Link](https://github.com/orgs/inno-swp-2025/projects/5)

This project shows when the team plans to work on type `Epic` issues and by which milestone they will be completed.

### Limitations

- The `Start` and `Finish` fields must be (manually) synchronized with start and finish dates of related type `Backlog` issues.

### Project settings

#### Custom fields (additional)

- `Start` of type `Date` - (planned) date of starting the work on an issue.
- `Finish` of type `Date` - (planned) date of finishing the work on an issue.

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
  
## Project `Product Backlog`

[Link](https://github.com/orgs/inno-swp-2025/projects/1)

This project shows the product backlog consisting of type `Backlog` issues.

### Limitations

- The `Iteration` field of a type `Backlog` issue and its type `Task` sub-issue must be (manually) synchronized.

### Project settings

#### Custom fields (additional)

- `Story Points` of type `Number` - estimate of a `Backlog` issue in Story Points.
- `Iteration` of type `Iteration` - iteration that the issue belongs to.
- `Priority` of type `Number` - numeric priority of an issue that equals to the `<number>` in the `Priority: <number>` label of that issue.

### View `Status`

- Provides `Entry Criteria` in Kanban board column descriptions.
- Shows total `Story Points` per iteration.

#### View options

- Layout: `Board`.

- Configuration:
  - Fields: `Assignees`, `Status`, `Iteration`, `Story Points`, `Priority`, `Sub-issues progress`.
  - Column by: `Status`.
  - Group by: `Iteration`.
  - Sort by: `Iteration` (ascending).
  - Field sum: `Count`, `Story Points`.
  - Slice by: `Priority`.

### View `Timeline`

Shows planned schedule of working on type `Backlog` issues.

#### View options

- Layout: `Roadmap`.

- Configuration:
  - Group by: `Iteration`.
  - Markers: `Iteration`.
  - Sort by: `Iteration` (ascending), `Priority` (ascending).
  - Dates: `Iteration`.
  - Zoom level: `Month`.
  - Field sum: `Count`, `Story Points`.
  - Slice by: `Parent issue`.

#### Columns

There are entry criteria for each column.
An issue is done when it reaches the `Done` column.

##### To Do

```text
[Entry Criteria]
* The issue isn't large enough for an Epic.
* The issue was updated (e.g., via an LLM) to conform a relevant issue form template.
* Relevant labels were assigned to the issue.
* Issues with type "Task" were added as sub-issues of the issue.
* The issue field "Story Points" was filled.
* The issue was added to a milestone and to a sprint.
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
* All sub-issues were completed.
* For a user story issue, all acceptance criteria for the issue were met in the staging environment.
```

##### Done

```text
[Entry Criteria]
* A new version of the product with changes introduced by the issue was deployed.
* Usability session tasks were completed successfully on that product version.
```

## Project `Tasks`

[Link](https://github.com/orgs/inno-swp-2025/projects/2)

This project shows connections between type `Task` issues, their parent type `Backlog` issues, and `Iterations`.

### Limitations

- The `Iteration` field of a type `Task` issue and its parent type `Backlog` issue must be (manually) synchronized.

### Project settings

#### Custom fields (additional)

- `Ideal Hours` of type `Number` - estimated number of ideal hours required to complete the issue.
- `Iteration` of type `Iteration` - iteration that the issue belongs to.
- `Priority` of type `Number` - numeric priority of an issue that equals to the `<number>` in the `Priority: <number>` label of that issue.
- `Start` of type `Date` - (planned) date of starting the work on an issue.
- `Finish` of type `Date` - (planned) date of finishing the work on an issue.

### View `Status`

- Provides `Entry Criteria` in Kanban board column descriptions.
- Shows total `Ideal Hours` per iteration.

#### Settings

- Layout: `Board`.

- Configuration:
  - Fields: `Assignees`, `Status`, `Iteration`, `Ideal Hours`, `Priority`, `Linked pull requests`.
  - Column by: `Status`.
  - Group by: `Iteration`.
  - Sort by: `Iteration` (ascending), `Priority` (ascending).
  - Field sum: `Count`, `Ideal Hours`.
  - Slice by: `none`.

#### Columns

There are entry criteria for each column.
An issue is done when it reaches the `Done` column.

##### To Do

```text
[Entry Criteria]
* The issue was updated (e.g., via an LLM) to conform to the "Task" issue form template.
* The type "Task" was assigned to the issue.
* Relevant labels were assigned to the issue.
* The issue was made a sub-issue of a type "Backlog" issue.
```

##### In Progress

```text
[Entry Criteria]
* The issue description was revised to provide missing details.
* The issue field "Ideal Hours" was filled.
* The issue was added to the current sprint.
* The issue was assigned to a developer.
* A branch for the issue was created via the "create a branch" button on the issue page.
```

##### Ready For Review

```text
[Entry Criteria]
* A pull request for the issue was created using a relevant template.
* The pull request was linked to the issue.
* Implementation in the pull request was completed.
* The "main" branch was merged into the pull request branch.
* CI pipeline with automated tests succeeded on the pull request branch.
* Subtasks in the pull request description were updated.
* A review of the pull request was requested.
```

##### Ready to Merge

```text
[Entry Criteria]
* All issue Acceptance Criteria were met on the pull request branch.
* The pull request was approved.
```

##### Done

```text
[Entry Criteria]
* The pull request that closes the issue was merged.
```

### View `With Parents`

- For each type `Backlog` issue, shows to which sprint its type `Task` sub-issues were assigned.
- Shows total `Ideal Hours` for an `Iteration`.
- Shows type `Task` issues sorted by priority within each `Iteration`.

#### Settings

- Layout: `Table`.

- View options:
  - Fields: `Iteration`, `Priority`, `Ideal Hours`, `Status`, `Assignees`, `Parent issue`.
  - Group by: `Iteration`.
  - Sort by: `Priority` (ascending), `Ideal Hours` (ascending).
  - Fields sum: `Count`, `Ideal Hours`.
  - Slice by: `Parent issue`.

### View `Timeline`

- Shows type `Task` issues distributed by `Iteration`s on a timeline.
- `Date fields` are set to `Iteration start` and `Iteration end`.
- One can set the `Date fields` to `Start` and `Finish` and adjust them by clicking on the left or on the right side of an issue box on the timeline and dragging it.

#### Settings

- Layout: `Roadmap`

- Configuration:
  - Group by: `Iteration`.
  - Markers: `Iteration`.
  - Sort by: `Iteration` (ascending), `Priority` (ascending).
  - Dates: `Iteration`.
  - Zoom level: `Month`.
  - Field sum: `Count`, `Ideal Hours`.
  - Slice by: `Parent issue`.

- User settings:
  - `Show date fields`
