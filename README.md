# we-have-tiktok-at-home

This repository and accompanying GitHub projects serve as a blueprint for organizing and tracking the development of a TikTok-like product.

See our [Product Backlog](https://github.com/orgs/inno-swp-2025/projects/1).

## GitHub Organization

We created the GitHub Organization called [inno-swp-2025](https://github.com/inno-swp-2025) to use organization-specific features.

You can [create](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch) an organization and [transfer](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository) your repositories there.

## Issues

We created several sample [issues](https://github.com/inno-swp-2025/we-have-tiktok-at-home/issues) in the [inno-swp-2025/we-have-tiktok-at-home](https://github.com/inno-swp-2025) repository.

If you plan to have several repositories in your organization, you can [create default issue labels](https://docs.github.com/en/organizations/managing-organization-settings/managing-default-labels-for-repositories-in-your-organization).

### Issue types

Each issue has a [type](https://docs.github.com/en/issues/tracking-your-work-with-issues/configuring-issues/managing-issue-types-in-an-organization).

Types:

- `Epic` - a large user story.
- `Backlog` - a Product Backlog Item (PBI).
- `Task` - a task related to a PBI.

### Issue labels

Additionally, issues have meaningful [labels](https://github.com/inno-swp-2025/we-have-tiktok-at-home/labels).

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

### Tips

- If you specify the `Scope: *`, specify the `Component: *`.

### Issue hierarchy

The following diagram shows connections between issues types and certain labels.

```mermaid
graph LR
    %% --- Style Definitions ---
    
    classDef styleEpicType #211a18,stroke:#db6d28,color:#db6d28,font-size:15pt
    classDef styleBacklogType fill:#242138,stroke:#ab7df8,color:#ab7df8,font-size:15pt
    classDef styleTaskType #272114,stroke:#c08d20,color:#c08d20,font-size:15pt
    
    classDef styleUserStoryLabel #193b27,stroke:#4ff66b,color:#4ff66b,font-size:15pt
    classDef styleBugReportLabel #371a1d,stroke:#f8988e,color:#f8988e,font-size:15pt
    classDef styleTechDebtLabel #153437,stroke:#2bd0cb,color:#2bd0cb,font-size:15pt
    classDef styleEnablerLabel #2c2222,stroke:#c9907c,color:#c9907c,font-size:15pt
    classDef styleInvestigationLabel #2a1b35,stroke:#ce94d4,color:#ce94d4,font-size:15pt

    %% --- Main Hierarchy ---

    subgraph Issues ["`**GitHub Issues**`"]
        direction LR

        subgraph Roadmap ["`**Roadmap**`"]
            direction LR

            subgraph EpicIssueType ["`**Issue type**`"]
                EpicTypeLabel([Epic]):::styleEpicType
            end
        end

        subgraph ProductBacklog ["`**Product Backlog**`"]
            direction TB
            
            subgraph BacklogIssueType ["`**Issue type**`"]
                BacklogType([Backlog]):::styleBacklogType
            end

            subgraph BacklogIssueLabels ["`**Issue labels**`"]
                direction LR

                UserStoryLabel([Backlog: User Story]):::styleUserStoryLabel
                BugReportLabel([Backlog: Bug Report]):::styleBugReportLabel
                TechDebtLabel([Backlog: Tech Debt]):::styleTechDebtLabel
                EnablerLabel([Backlog: Enabler]):::styleEnablerLabel
                InvestigationLabel([Backlog: Investigation]):::styleInvestigationLabel
            end

            BacklogIssueType -. "`**is detailed by**`" .-> BacklogIssueLabels
        end

        subgraph Tasks ["`**Tasks**`"]
            subgraph TaskIssueType ["`**Issue type**`"]
                TaskType([Task]):::styleTaskType
            end
        end

        Roadmap -. "`**breaks down into**`" .-> ProductBacklog
        ProductBacklog -. "`**is realized by**`" .-> Tasks

    end
```

### Issue Form templates

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

Projects can be [copied](https://docs.github.com/en/issues/planning-and-tracking-with-projects/creating-projects/copying-an-existing-project) and used as templates.

We provide [own projects](https://github.com/orgs/inno-swp-2025/projects) for each issue type:

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
