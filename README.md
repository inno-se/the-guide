# we-have-tiktok-at-home

We swipe issues to the right.

## GitHub Organization

The GitHub Organization [inno-swp-2025](https://github.com/inno-swp-2025) was created to:

- group multiple related repos under a single organization name.
- use organization-specific features.

## Default community health files

We store [default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file) in the [inno-swp-2025/.github](https://github.com/inno-swp-2025/.github) repository,

## Issues

We created several [issues](https://github.com/inno-swp-2025/we-have-tiktok-at-home/issues) related to development of a TikTok-like product.

Issues have meaningful [labels](https://github.com/inno-swp-2025/we-have-tiktok-at-home/labels).

## Issue types

Each issue has a [type](https://docs.github.com/en/issues/tracking-your-work-with-issues/configuring-issues/managing-issue-types-in-an-organization).

<!-- TODO improve wording -->
A type allows to inspect all issues of that type across the organization.

The `Backlog` type is for issues representing Product Backlog Items (PBIs).
The `Task` type is for issues representing tasks related to PBIs.

## The GitHub Projects

The [Projects](https://github.com/orgs/inno-swp-2025/projects) in this organization connect type `Task` issues and type `Backlog` issues.

## Project `Product Backlog`

This project shows the product backlog consisting of type `Backlog` issues.

### Limitations

- The `Iteration` field of a type `Backlog` issue and its type `Task` sub-issue must be (manually) synchronized.

### Project settings

#### Custom fields (additional)

- `Story Points` of type `Number` - estimate of a `Backlog` issue in Story Points.
- `Iteration` of type `Iteration` - iteration that the issue belongs to.
- `Priority` of type `Number` - numeric priority of an issue that equals to the `<number>` in the `Priority: <number>` label of that issue.

### View `Definition of Done`

- Provides `Definition of Done` in Kanban board column descriptions.
- Shows total `Story Points` per iteration.

#### View options

- Layout: `Board`.

- Configuration:
  - Fields: `Assignees`, `Status`, `Story Points`, `Iteration`, `Sub-issues progress`.
  - Column by: `Status`.
  - Group by: `Iteration`.
  - Sort by: `Iteration` (ascending).
  - Field sum: `Count`, `Story Points`.
  - Slice by: `none`.

### View `Roadmap`

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

## Project `Tasks`

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

### View `Definition of Done`

- Provides `Definition of Done` in Kanban board column descriptions.
- Shows total `Ideal Hours` per iteration.

#### Settings

- Layout: `Board`.

- Configuration:
  - Enabled fields: `Assignees`, `Status`, `Ideal Hours`, `Iteration`, `Priority`, `Linked pull requests`.
  - Column by: `Status`.
  - Group by: `Iteration`.
  - Sort by: `Iteration` (ascending), `Priority` (ascending).
  - Field sum: `Count`, `Ideal Hours`.
  - Slice by: `none`.

### View `With Parents`

- For each type `Backlog` issue, shows to which sprint its type `Task` sub-issues were assigned.
- Shows total `Ideal Hours` for an `Iteration`.
- Shows type `Task` issues sorted by priority within each `Iteration`.

#### Settings

- Layout: `Table`.

- View options:
  - Enabled fields: `Iteration`, `Priority`, `Ideal Hours`, `Status`, `Assignees`, `Parent issue`.
  - Group by: `Iteration`.
  - Sort by: `Priority` (ascending), `Ideal Hours` (ascending).
  - Fields sum: `Count`, `Ideal Hours`.
  - Slice by: `Parent issue`.

### View `Roadmap`

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
