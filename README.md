<!-- TOC ignore:true -->
# The Guide

This repository provides a guide for managing the development of a software project as a team using modern software engineering knowledge and tools to pass several Innopolis University courses.

<!-- TOC ignore:true -->
## Table of contents

<!-- TODO re-generate with huntertran.auto-markdown-toc -->

<details><summary>Click to view</summary>

<!-- TOC -->

- [Courses](#courses)
  - [Target auditory](#target-auditory)
  - [Passing the course vs completing the project](#passing-the-course-vs-completing-the-project)
  - [Grading](#grading)
  - [Industrial project](#industrial-project)
- [Setup](#setup)
  - [Glossary](#glossary)
    - [Our project](#our-project)
    - [Set up repositories](#set-up-repositories)
    - [Prepare the knowledge base](#prepare-the-knowledge-base)
    - [Extend the knowledge base](#extend-the-knowledge-base)
    - [Add a Project Charter](#add-a-project-charter)
    - [Collect initial requirements from stakeholders](#collect-initial-requirements-from-stakeholders)
    - [Capture Architecturally Significant Requirements ASRs](#capture-architecturally-significant-requirements-asrs)
    - [Design architecture](#design-architecture)
    - [Automation](#automation)
    - [Break down the work](#break-down-the-work)
  - [Scrum](#scrum)
    - [Theory](#theory)
    - [Sprints](#sprints)
    - [Meetings](#meetings)
    - [Recordings](#recordings)
    - [Tasks](#tasks)
    - [Free riders](#free-riders)
  - [Work item hierarchy](#work-item-hierarchy)
  - [Issues](#issues)
    - [Sample issues](#sample-issues)
    - [Issue types](#issue-types)
      - [Epic](#epic)
      - [Backlog](#backlog)
      - [Task](#task)
    - [Issue labels](#issue-labels)
    - [Compatibility of issue types and labels](#compatibility-of-issue-types-and-labels)
    - [Issue priority](#issue-priority)
  - [Pull requests](#pull-requests)
  - [Templates](#templates)
    - [Issue form templates](#issue-form-templates)
    - [Pull request templates](#pull-request-templates)
  - [Milestones](#milestones)
  - [Projects](#projects)
    - [Kanban boards](#kanban-boards)
  - [Project Roadmap](#project-roadmap)
    - [Limitations](#limitations)
    - [Project settings](#project-settings)
      - [Custom fields additional](#custom-fields-additional)
    - [View Timeline](#view-timeline)
      - [View options](#view-options)
    - [View Kanban](#view-kanban)
      - [View options](#view-options)
      - [Columns](#columns)
        - [To Do](#to-do)
        - [In Progress](#in-progress)
        - [In Review](#in-review)
        - [Done](#done)
  - [Project Product Backlog](#project-product-backlog)
    - [Limitations](#limitations)
    - [Project settings](#project-settings)
      - [Custom fields additional](#custom-fields-additional)
    - [View Kanban](#view-kanban)
      - [View options](#view-options)
      - [Columns](#columns)
        - [To Do](#to-do)
        - [In Progress](#in-progress)
        - [Ready To Deploy](#ready-to-deploy)
        - [Done](#done)
    - [View Timeline](#view-timeline)
      - [View options](#view-options)
  - [Project Tasks](#project-tasks)
    - [Limitations](#limitations)
    - [Project settings](#project-settings)
      - [Custom fields additional](#custom-fields-additional)
    - [View Kanban](#view-kanban)
      - [Settings](#settings)
      - [Columns](#columns)
        - [To Do](#to-do)
        - [In Progress](#in-progress)
        - [Ready For Review](#ready-for-review)
        - [Ready to Merge](#ready-to-merge)
        - [Done](#done)
    - [View With Parents](#view-with-parents)
      - [Settings](#settings)
    - [View Timeline](#view-timeline)
      - [Settings](#settings)

<!-- /TOC -->
</details>

# Glossary

- **assumption** (noun)

  Something that you accept as true without question or proof [[Cambridge Dictionary](https://dictionary.cambridge.org/dictionary/english/assumption)].

- **Definition of Done** (noun)

  A formal description of the state of the Increment when it meets the quality measures required for the product. The moment a Product Backlog item meets the Definition of Done, an Increment is born. The Definition of Done creates transparency by providing everyone a shared understanding of what work was completed as part of the Increment. If a Product Backlog item does not meet the Definition of Done, it cannot be released or even presented at the Sprint Review [^GlossaryOfScrumTerms].

- **fact** (noun)

  Something that is known to have happened or to exist, especially something for which proof exists, or about which there is information [[Cambridge Dictionary](https://dictionary.cambridge.org/dictionary/english/fact)].

- **The Pyramid Principle** (noun)

  A tool to give your (written) communication more clarity and efficiency. Lead with the conclusion, then provide key arguments and finally support them with detailed information [^MintoPyramid].

- **quality attribute** or **QA** (noun)

  A measurable or testable property of a system that is used to indicate how well the system satisfies the needs of its stakeholders beyond the basic function of the system [^Bck].

- **record** (verb)

  To keep information for the future, by writing it down or storing it on a computer [[Cambridge Dictionary](https://dictionary.cambridge.org/dictionary/english/record)].

- **record** (noun)

  A piece of information or a description of an event that is written on paper or stored on a computer [[Cambridge Dictionary](https://dictionary.cambridge.org/dictionary/english/record)].

- **repo** (noun)
  
  A Git repository [[What are code repositories?](https://github.com/resources/articles/software-development/what-are-code-repositories)].
  
  See also [[About repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories)].

- **stakeholders** (noun)
  
  All individuals and groups affected by the Scrum project, both within and outside the organization (e.g., all [core](#core-roles) and [non-core](#non-core-roles) roles, vendors, internal groups, experts, and so on) [^SbokGuide].

- **validation** (noun)
  
  The process of providing evidence that a deliverable meets the needs of the user [^ApmGlossary].

- **verification** (noun)

  Proof of compliance with specified requirements. Verification may be determined by test, analysis, inspection or demonstration [^ApmGlossary].

- Other terms:
  - [[Agile Glossary](https://agilealliance.org/agile101/agile-glossary/)]

# Courses

This chapter explains what you should know about University courses covered by this guide.

## Target auditory

The target auditory of this guide are BS and MS students of the Innopolis University atteding the courses:

- ***SWP*** (Software Project) - BS, 1st year, Summer semester;
- ***ITPD*** (IT Product Development) - MS, 1st year, Fall semester;
- ***Industrial Project*** - MS, 1st year, Spring and Summer semesters.

In each course, students are distributed into teams of 4-6 people. Each team develops a project for a customer from the University or an outside company.

Most points in this guide apply to all courses.

## Passing the course vs completing the project

- The [Setup](#setup) chapter of this guide explains how to create a working environment that can help you complete your project successfully.
- However, to pass the course, you need to meet requirements and expectations of the key project stakeholders, not just complete the project. Key project stakeholders are usually course instructors (primary instructor, TAs, mentors) and your customer.
- Identify key stakeholders and learn about stakeholders' requirements and expectations as soon as possible. You need to have enough time to manage and meet their requirements and expectations.
- You should communicate to the stakeholders how you met their requirements and expectations in a way that the stakeholders expect.
- You should explicitly explain all discrepancies.

## Grading

- Grading is usually subjective.
- You won't know the complete grading scheme because it's assumed that if you know the complete grading scheme:
  - you may produce less creative work;
    - Assumption: [***Goodhart's law***](https://en.wikipedia.org/wiki/Goodhart's_law) holds.
  - you may pay less attention to important parts of an assignment that have small weight in the grade.
    - Assumptions:
      - You're going to balance required effort/time and grade.
      - If you don't know the scheme, you'll treat all parts of an assignment as almost equally important.
- Learn in advance the conditions of individual grading.
- Don't demand individual grading when you experience [teamwork problems](#potential-challenges-and-lessons-learned).
  Instead, ask course instructors to help normalize the team work.

## Feedback loop

A feedback loop helps you continually improve [^ContinualImprovementProcess] an artifact or process to achieve specific goals based on evaluation of (changes to) your artifact or process using specific metrics (connected to the goals).

See also [the GQM method](#the-gqm-approach), [the PDSA cycle](#the-pdsa-cycle).

### Use case

You can use a feedback loop to get and process feedback:

- on your progress with assignment tasks from your TA (e.g., during a lab);
- on your product from your customer (e.g., during a Sprint Review);
- on your deliverables for an assignment from your TA or mentor (e.g., during office hours).

### Phases

> [!NOTE]
> This section was generated by Gemini 2.5 Pro and revised by at least one author.

> [!NOTE]
> **What to do** parts should be adapted to your situation.

#### Phase 1: Preparation

Good preparation helps you get the most out of the feedback session.

1. **Define your goal**
    - **What to do:** Know *why* you need feedback. Are you checking a new idea, looking for usability problems, or asking about a technical decision? Clearly state what you want feedback on. Also, mention what is *not* ready for feedback (what is out of scope).
    - **Why it helps:** This focuses the conversation and respects the other person's time. It also prevents discussion about parts of the project you are not ready to show.

2. **Show your work and give context**
    - **What to do:** Present the thing you want feedback on, for example, a user story, a design, some code, or a live demo. Briefly explain the background. For a customer, you could remind them of the sprint goal. For a TA, you could state the requirements of the lab task.
    - **Why it helps:** To give good feedback, people need to see what you are talking about. The context helps them use the right criteria to evaluate your work.

3. **Show what you did with previous feedback**
    - **What to do:** If you have received feedback before, briefly show how you used their last suggestions. For example: "Last time, you said the login was slow. We have now improved it. Here is the new speed."
    - **Why it helps:** This shows that you listen and value their opinion. It builds trust and makes them more willing to help you in the future.

#### Phase 2: The conversation

During the conversation, your goal is to get clear, honest, and detailed feedback.

4. **Ask open-ended questions**
    - **What to do:** Avoid "yes/no" questions or questions that suggest an answer.
        - Instead of: "Is this easy to use?"
        - Ask: "Could you show me how you would use this to complete [a specific task]?"
        - Instead of: "What do you think?"
        - Ask: "What is your first impression of this feature?" or "Was there any point where you felt confused?"
    - **Why it helps:** This encourages people to explain the "why" behind their opinions. You will get much better information than a simple "yes" or "no."

5. **Listen to understand**
    - **What to do:** Your main goal is to listen and learn. Take good notes. Notice if they seem confused or hesitate. Do not argue or defend your work. If you have to explain how something is *supposed* to work, it often means the design is not clear enough.
    - **Why it helps:** If you act defensively, people will stop giving honest feedback. By listening quietly, you can understand their true experience.

6. **Confirm your understanding**
    - **What to do:** When they finish speaking, repeat their main points in your own words. This makes sure you understood them correctly. For example: "So, if I understand correctly, the main problem is that you expected the message to be at the top of the screen, not the bottom. Is that right?"
    - **Why it helps:** This prevents confusion and shows that you were listening. It helps you make sure you are solving the right problem.

#### Phase 3: Turn feedback into action

Good feedback should lead to improvements. Here is how to make that happen.

7. **Analyze and prioritize feedback**
    - **What to do:** After the session, review your notes with your team. Group similar comments together to find the main problems or themes. Decide what to do first. Think about the effort needed for each change versus the benefit it gives. Not all feedback must be implemented.
    - **Why it helps:** This helps your team focus on the most important changes first.

8. **Create clear, actionable tasks**
    - **What to do:** Turn the feedback you decided to work on into specific tasks or user stories in your backlog. Every task needs clear acceptance criteria to show when it is "done."
        - *Example:* "As a user, I want the confirmation button to be green and in the top-right corner so it is more visible."
        - *Acceptance Criteria:* 1. Button color is #28a745. 2. Button is in the top-right of the modal. 3. Clicking the button closes the modal.
    - **Why it helps:** This turns general comments into clear work that you can track in your scrum process.

9. **Implement and close the loop**
    - **What to do:** Implement the changes. After you implement and test the changes, show the person who gave the feedback what you did. You can do this at the next sprint review or lab session.
    - **Why it helps:** This improves the product, which is the main goal. It also shows the person that their feedback was valuable, which completes the loop.

## Questions and answers about the course

### Official answers

Only the course instructors give official answers to questions about the course.

### Asking questions

- Before asking a question, search fo an answer in the official course chat history and course materials.
- Ask questions in the official course chat so that both the question and the answer are visible to everyone.
- Ask one question per message. A reply to that message will clearly be related to that question.
  - Adapted from [this advice](https://www.kadansky.com/files/newsletters/2024/2024_04_30.html).
- If an answer isn't acceptable, reply to it if necessary and ask clarifying questions. Define your own acceptance criteria for answers.
- Continue asking until you get acceptable answers.
- Mark messages that contain acceptable answers with a reaction (e.g, "👍" or "👌").
  - Adapted from [this StackOverflow rule](https://stackoverflow.com/help/someone-answers).

## Potential challenges and lessons learned

This section is based on the study *Software engineering team project courses with industrial customers: Students’ insights on challenges and lessons learned* [^SETeamProjectProblems].

Researchers identified various [challenges](#challenges-themes) and [lessons learned](#lessons-learned-themes) from students' reports.

Courses attended by the [target auditory](#target-auditory) of this guide are similar to the courses covered by the study.
Therefore, challenges

### Challenges (themes)

[Sec 5](https://www.sciencedirect.com/science/article/pii/S0164121225001098#tbl7)

- Working in a team
- Working in a remote and hybrid setting
- Working with an industrial customer
- Working with new technology
- Managing the project
- Maintaining self-confidence and motivation

#### Sub-themes of *Working in a team*

[Sec 5.1](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec5.sec5.1)

- Communication issues within team
- Contribution issues within team
- Forming a team with unfamiliar people
- Managing changes within team
- Poor team dynamics
- Coordination issues within team
- Developing the team mindset
- Managing conflicts within team
- Keeping track of team progress
- Skill gap between team members
- Different ambition levels within team
- Adapting to diverse working styles
- Other difficulties working in a team
- No prior experience working in a team

#### Sub-themes of *Working in a remote and hybrid setting*

[Sec 5.2](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec5.2)

- Communicating with the team remotely
- Fostering team dynamics in remote setting
- Staying motivated while working remotely
- Tracking team progress in remote setting
- Maintaining team efficiency in remote setting
- Inability to work in customer premises
- Adapting to online working mode
- Keeping focus while working from home
- Managing sickness
- Maintaining work-life balance
- Working on-site during the pandemic
- Maintaining wellbeing

#### Sub-themes of *Working with an industrial customer*

[Sec 5.3](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec5.3)

- Understanding requirements
- Managing technical complexity in the project
- Managing the project scope
- Understanding customer’s system
- Working in the customer technical environment
- Communicating with the customer
- Integrating different parts of the project
- Lack of experience in project domain
- High expectations of the customer
- Working on outdated parts of the system

#### Sub-themes of *Working with new technology*

[Sec 5.4](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec5.4)

- Lack of experience with tools & technology
- Lack of support in chosen technologies
- Making appropriate technology choices
- Lack of experience with version control SW
- Equipment-related challenges

#### Sub-themes of *Managing the project*

[Sec 5.5](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec5.5)

- Making correct effort estimates
- Making initial plans
- Lack of clear work distribution
- Lack of initiative to take project management roles
- Lack of project management experience
- Even distribution of tasks
- Ineffective time management

#### Sub-themes of *Maintaining self-confidence and motivation*

[Sec 5.6](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec5.6)

- Doubts in ability to achieve project goals
- Difficulty staying motivated

### Lessons learned (themes)

[Sec 6](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec5)

- Working in a team
- Managing the project
- Working with an industrial customer
- Working in a remote and hybrid setting
- Managing the product quality
- Setting personal values and ethics
- Formalizing the processes
- Working with new technology
- Taking advice from the mentors

#### Sub-themes of *Working in a team*

[Sec 6.1](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.1)

- Ensure good team communication
- Create a conducive team environment
- Create good team dynamics
- Manage team meetings effectively
- Develop a team mindset
- Share knowledge within team
- Create sub-groups in large teams
- Appoint a team leader
- Ensure good coordination within team
- Set clear goals for the team
- Encourage reflection and feedback
- Define a code of conduct for the team

#### Sub-themes of *Managing the project*

[Sec 6.2](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.2)

- Invest time in planning
- Manage work distribution effectively
- Manage requirements & changes efficiently
- Invest time in effort estimation
- Make informed choices for the project
- Focus more on risk management
- Use project management tools effectively

#### Sub-themes of *Working with an industrial customer*

[Sec 6.3](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.3)

- Communicate effectively with the customer
- Understand requirements from customers' perspective
- Conduct effective meetings with customer
- Keep commitments with customer
- Optimize learning in customer environment

#### Sub-themes of *Working in a remote and hybrid setting*

[Sec 6.4](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.4)

- Make good use of collaboration tools for remote work
- Working on-site is better
- Working remotely is better
- Setup team schedule for remote work
- Use camera in online meetings

#### Sub-themes of *Managing the product quality*

[Sec 6.5](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.5)

- Focus more on testing
- Focus more on code quality
- Focus more on design and architecture
- Take into account product usability

#### Sub-themes of *Setting personal values and code of ethics*

[Sec 6.6](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.6)

- Try new technologies without hesitation
- Have confidence and a positive attitude
- Maintain self discipline
- Be respectful to others
- Voice your opinion
- Have breaks from work to refresh
- Ask questions and take initiatives
- Keep record of time spent
- Keep your commitments
- React early if subjected to bullying
- Be proactive to solve problems
- Identify your own skillset

#### Sub-themes of *Formalizing the processes*

[Sec 6.7](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.7)

- Follow agile practices
- Document the project and the process
- Maintain shared repository of documents

#### Sub-themes of *Working with new technology*

[Sec 6.8](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.8)

- Invest time in learning new technologies
- Make good use of version control system
- Learn one new technology at a time

#### Sub-themes of *Taking advice from the mentors*

[Sec 6.9](https://www.sciencedirect.com/science/article/pii/S0164121225001098#sec6.9)

- Take advice from the mentors

## Telegram

Create a group with topics to have focused streams of messages in each topic.

Suggested topics:

- `Important` - for important information such as:
  - team member names, Telegram and GitHub usernames, roles.
  - links to the:
    - repository;
    - the most important boards on GitHub Projects;
    - CONTRIBUTING.md;
    - docs;
    - deployed product;
    - Google Drive;
    - etc.
- `Recordings` - for storing recordings.
  <!-- TODO video and audio recording + raw transcripts? -->
  - You may want to create a backup of recordings in another group because they're evidence against free riders (see [Free riders](#free-riders)).
- `Pull requests` - for pinging people about pull requests, e.g., when asking for a review.
- `Tasks` - for pinging people about tasks, e.g., when assigning a task or asking about the task status.
- `Assignments` - for discussing assignments, presentations, etc.
- `General` - for all other discussions.

### Assignments

- Make a copy of the assignment and save it on Google Drive.
- Write in comments to the file who will do which part of the assignment.
- Agree when everything must be done.
- Leave buffer time.
  - If the course deadline is on Sunday, 23:59, you may want to set a soft deadline on Saturday morning and a hard deadline on Saturday evening. Then, you'll have a calm Sunday or at least a day of buffer time to finish remaining parts of the assignment.


# Setup

## Glossary

- ***repo*** - [repository](https://github.com/resources/articles/software-development/what-are-code-repositories)

### Example project

The goal of the software project in this repository is to develop a TikTok-like application.

Nothing will be developed, but we have neat [GitHub Projects](#projects) for [Roadmap Items](https://github.com/orgs/inno-swp-2025/projects/5/views/4), [Product Backlog Items](https://github.com/orgs/inno-swp-2025/projects/1), and [Tasks](https://github.com/orgs/inno-swp-2025/projects/2).

### Set up repositories

1. [Create](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch) a GitHub organization.
1. [Import](https://docs.github.com/en/migrations/importing-source-code/using-github-importer/importing-a-repository-with-github-importer) or [transfer](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository) your repositories into your organization.
1. Consider switching to a [monorepo](https://graphite.dev/guides/polyrepo-to-monorepo-migrations-guide).
1. Create issue types similar to ours (see [Issue types](#issue-types)).
1. Create issue labels similar to ours (see [Issue labels](#issue-labels)).
1. Copy our projects (see [Projects](#projects)).
1. Import the [.github](https://github.com/inno-swp-2025/.github) repo into your organization.
1. Update templates in the `.github` repo.
    - In [issue form templates](#issue-form-templates), update:
      - `projects:` - to automatically add issues to your projects;
      - `labels:` - to automatically create issues with your labels.
1. Copy this `README` (that you read now) somewhere into your repo and modify it as necessary.
1. Update all links (e.g., in `Project details` in your projects) to this `README` to point to your version.
1. Adjust entry criteria specified in Kanban boards (see [Kanban boards](#kanban-boards)).

## Prepare the knowledge base

Having a well-structured knowledge base for your project will help you share the information about the project with stakeholders and LLMs.

### Choose a multi-modal LLM service

Examples:

- [Google AI Studio](https://aistudio.google.com)
- [ChatGPT](https://chatgpt.com/)

### Collect textual materials

Collect textual materials and images that provide relevant information about your project, e.g.:

- Description of stakeholders;
- Project description and documentation;
- Diagrams (as code);
- User stories;
- Discussions with the customer on Telegram etc.;
- Competing products and their properties;
- GitHub issues.

### Collect video and audio materials

Collect all video and audio materials relevant to the project, e.g., recordings of:

- Interviews with the customer;
- Usability sessions;
- Sprint planning and sprint review [meetings](#meetings).

### Produce high-quality transcripts

1. (Optional) Remove sensitive information from recordings.
1. For video and audio materials, get high-quality transcripts with speaker labels and timestamps.
1. (Optional) Convert video to audio.
1. For each recording:
    1. load it together with its transcript into a chat with the LLM.
    1. Ask the LLM to improve transcript text using the recording.
    1. (Optional) Ask the LLM to remove sensitive information.
    1. Check the [diff](https://en.wikipedia.org/wiki/Diff) between the original transcript and improved transcript (e.g. using the [Compare files](https://code.visualstudio.com/docs/editing/codebasics#_compare-files) feature in [VS Code](#vs-code)) to identify hallucinations.
    1. Fix hallucinations.
    1. Ask the LLM to translate the transcript to English if necessary.
    1. Check the translation to identify hallucinations.

### Discuss the knowledge base with the LLM

1. Load relevant materials into the chat with the LLM.
1. Tell the LLM that you're working on a small software project in a team.
1. Discuss with the LLM these questions grouped by topics:
    - Versioning:
      - What is versioning?
      - How does `git` help version files?
      - Why should `git` be used when using LLMs?
    - Interaction with LLMs:
      - How can a developer interact with LLMs?
      - What are benefits and challenges of each interaction way?
    - Agents:
      - What are agents?
      - How to control them?
      - Which types of agents do you need in your project?
      - What can be prompts for these agents?
        - Check <https://github.com/contains-studio/agents> to see prompts for various agents.
    - Knowledge base structure:
      - How to optimally structure materials for loading into a chat with an LLM?
      - What should be the file structure in the knowledge base directory?
      - How to let LLM know the structure of the knowledge base so that the LLM can select relevant parts for chats on particular topics?
    - LLM hallucinations:
      - How to prevent LLM hallucinations?
      - How to minimize LLM hallucinations when loading parts of the knowledge base?
    - Improving search in the knowledge base:
      - Are custom embeddings necessary in your project?
      - How to work with embeddings?
    - Processing recordings:
      - What are the best practices for extracting information from videos and audios using an LLM?
    - Knowledge base location:
      - Where to store the knowledge base so that it can be versioned, accessed by team members, and edited locally on your machine?
        - Most probably, a single `docs` directory in your repo will be enough to store textual materials and images.
    - Diagrams as code:
      - How to store PlantUML, Mermaid, Draw.io diagrams so that they can be loaded into a chat with an LLM and provide useful information?
    - Tooling for the knowledge base:
      - Which VS Code extensions can help you work with the knowledge base?
      - Which automation can you have for your knowledge base?

### Publish the knowledge base

Publish the knowledge base to [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages) as a site generated via a ***static site generator*** such as [mdBook](https://rust-lang.github.io/mdBook/), [MkDocs](https://www.mkdocs.org/), [Docusaurus](https://docusaurus.io/), etc.

You may want to automate the publishing process via [GitHub Actions](https://docs.github.com/actions) (see [Marketplace](https://github.com/marketplace?type=actions)).

### Extend the knowledge base

- Skim the ***SWEBOK*** [^Swebok] - a comprehensive guide for "generally accepted knowledge" in software engineering.
- Come up with good questions about a particular topic, e.g., Software Requirements (Chapter 1 of [^Swebok]).
- Load relevant parts of the knowledge base to a chat with an LLM.
- Ask the LLM to come up with more questions and prompts for a chat on that topic.
- Discuss the topic.
- Add new relevant verified no-fluff information to your knowledge base.

## Add a Project Charter

<!-- TODO anything else? -->

A ***Project Charter*** [^ProjectCharter] is a document that captures:

- ***Project Purpose***: Clearly defines the project's objectives and the problem it aims to solve.
- ***Scope and Deliverables***: Outlines what is included in the project scope and the expected deliverables.
- ***Roles and Responsibilities***: Specifies the roles of everyone involved in the project, from team members to sponsors.
- ***Budget and Resources***: Details the budget, including financial limits and available resources.
- ***Timeline***: Provides a high-level timeline or milestones for the project.
- ***Risk Management***: Identifies potential risks and strategies for mitigating them.

Add a basic Project Charter to your knowledge base.


### Capture Architecturally Significant Requirements (ASRs)

***Architecturally Significant Requirements*** (ASRs) are any requirements that may affect the architecture of a software system [^BckCh19] [^Swebok] [^AdrOrg] [^AdrTemplates]. They are derived from:

- Functional requirements;
- Quality attribute requirements (aka nonfunctional requirements);
- Business goals;
- Constraints (what you can't change and can only mitigate);

ASRs must be prioritized and accounted for when designing the system architecture, i.e., near the start of the project. You may not be able to change the architecture later due to high cost of change.

If your architecture doesn't allow satisfying the most significant ASRs, stakeholders for whom these ASRs are important will probably consider your project a failure.

Thus, you should take your ASRs seriously.

- Identify project stakeholders.
- Identify relevant quality attributes.
  - Check the ***ISO 25010*** quality model [^Iso25010] for generic definitions of quality attributes (aka ***quality characteristics*** and ***quality sub-characteristics***).
  - Check the ***Q42*** quality model [^Q42] for a wider range of quality attributes (aka *qualities*) and quality requirement examples.
- Identify primary functional requirements, business goal, and constraints.
- Read the ***Chapter 19 - Architecturally Significant Requirements*** [^BckCh19] of the book ***Software Architecture in Practice, 4th Edition by L. Bass, P. Clements, and R. Kazman*** [^Bck] to learn about the Utility Tree concept, eliciting ASRs, and refining them to unambiguous, testable, relevant ASR scenarios.
- Create a Utility Tree and add it to your knowledge base.
  - Write ASR scenarios in the quality attribute scenario format (source - stimulus - artifact - environment - response - response measure) [^Bck] [^QASofSoftwareArchitecture] [^QualityScenarios].
  - For each ASR, measure its:
    - business value - how important the ASR is for the business;
    - technical risk - how hard it'll be to achieve that ASR.
  - You may use the `H` (High) - `M` (Medium) - `L` (Low) scale for these metrics.
    - The most significant ASRs (with (H,H)) must be addressed first. When there are many such ASRs, it's necessary to negotiate simplifying the system to make it achievable.
  - ASR scenarios should be linkable or at least have unique identifiers so that these scenarios can be referenced elsewhere.
  - Tabular form is recommended [^UtilityTreeTabular].
  - Here's an example of a Utility Tree in the tabular form (p. 285 of the book [^Bck]).
    - "Quality Attribute" denotes quality sub-characteristics [^Iso25010] or qualities [^Q42];
    - ASR Scenarios:
      - contain (business value, technical risk) tuples;
      - are partially in the quality attribute scenario format.

    ![Utility Tree](./assets/BckUtilityTree.png)
- Merge similar scenarios (see The Quality Attribute Workshop [^BckCh19]).
- For each ASR scenario, explain how exactly you're going to test it.

### Design architecture

<!-- TODO write here -->
![Design Concepts](./assets/BckDesignConcepts.png)

### Break down the work

1. Load necessary context into a chat with an LLM.
1. Load relevant [issue form templates](#issue-form-templates).
1. Extract epics and Product Backlog Items. Sample prompt:

    ```text
    Extract all requirements, features, technical details, investigations from the context.
    
    I use the following structure of issues:
    Epic -> Product Backlog Item (PBI) -> Task
    - An Epic is a container for a major initiative that is too large and complex to be completed in a single sprint.
    - A PBI is a unit of work that is small enough to be completed by the team within a single sprint.
    - A Task is a specific action required to complete a PBI.
        
    Write text for Epics and related Product Backlog Items (PBIs).
    For both Epics and PBIs, write an index and type before the title.
    Don't generate Tasks for now.
    
    Epics and PBIs have types "User Story", "Enabler", "Investigation".
    
    Check issue form templates and write texts in corresponding format.
    You may skip comments and other unnecessary sections.
    ```

1. Check the output against the loaded materials; identify hallucinations; re-generate dubious parts.

1. (Optional) Ask LLM to generate:
    - A new use case diagram using PlantUML.
    - Project architecture using mermaid (see [Architecture Diagrams Documentation](https://mermaid.js.org/syntax/architecture.html)).
    - Tasks for each product backlog item. Each task must have a brief description, a checklist of sub-tasks, and a checklist of corresponding task acceptance criteria.
1. (Optional) Save the chat into a Markdown doc in the repo so that you can use it in subsequent chats.

1. In the chat with all materials and analysis, ask the LLM to plan the work as a [Gantt chart](https://mermaid.js.org/syntax/gantt.html) and open the obtained diagram in the [editor](https://mermaid.live/edit). Sample prompt:

    ```text
    Assume the work must be done in two months, in 1-week sprints.
    Epic can span several sprints.
    PBI must fit into a single sprint.
    Provide a Gantt chart for epics and corresponding PBIs as a mermaid diagram.
    ```

1. Don't trust this plan and build your own instead.
1. Create issues following the [work item hierarchy](#work-item-hierarchy) (see [Issues](#issues)).
1. Set `Priority`,  `Start` and `Finish` fields in your type `Epic` issues (see [Project `Roadmap`](#project-roadmap)).
1. Set `Priority` and `Story Points` fields in your type `Backlog` issues (see [Project `Product Backlog`](#project-product-backlog)).
1. If some type `Backlog` issues with label `Backlog: User Story` are too large to be completed during a single sprint, create new type `Epic` issues with the content of those large type `Backlog` issues and add there smaller type `Backlog` sub-issues.
1. For type `Epic` issues that must be worked on in the nearest sprints, set relevant `Sprint` field in their type `Backlog` sub-issues.
1. Create milestones for `MVP v2`, `MVP v3`, `Demo` in your repo.
1. Add type `Epic` and type `Backlog` issues to these milestones.
1. For type `Backlog` issues scheduled for the nearest sprints, create type `Task` sub-issues and set corresponding `Sprint` field there.
1. For each type `Backlog` issue, `Sprint` in that issue and in its type `Task` sub-issues must be the same.
1. Set `Ideal Hours` and `Priority` in your type `Task` issues (see [Project `Tasks`](#project-tasks)).
## The PDSA cycle

The **PDSA cycle**, or the **Plan-Do-Study-Act cycle**, or the **Deming cycle** is a systematic process for gaining valuable learning and knowledge for the continual improvement of a product, process, or service [^ThePdsaCycle].

The PDSA cycle is rooted in the scientific method [^CirclingBack] [^ScientificMethodWiki]. The cycle steps are similar to the steps of the empirical cycle [^EmpiricalCycleWiki] but the ultimate goal is specifically continual improvement.

### Theory

- [Theory of Knowledge/PDSA](https://www.youtube.com/watch?v=dgazCOz_IIY)
- *Circling Back* [^CirclingBack]

### Application

Follow the cycle steps if you have an idea on how to change a process in your project to improve that process. As a result of going through the cycle, you'll have data and will be able to decide:

- whether your idea worked as expected;
- whether you should keep the change;
- whether you need to update your mental model [^TheoryAsModelWiki] [^MentalModel] of the process to come up with more accurate predictions and more feasible improvement ideas;

### The PDSA cycle and the Model for Improvement

![PDSA](./assets/PdsaCycleAndModelForImprovement.png)
Sources: [^CirclingBack] [^TheImprovementGuide]

### Steps

1. **Plan**
    - We propose changes based on our goals.
    - We make falsifiable hypotheses [^FalsifiabilityWiki] (testable predictions) about the results of changes based on our theory [^TheoryWiki].
    - We introduce metrics that let us reason whether a change led to an improvement.
    - We design (controlled) experiments [^ExperimentTypesWiki] to test these hypotheses [^DesignExperimentWiki].
1. **Do**
    - We conduct experiments (preferably on a small scale).
    - We perform necessary measurements [^MeasurementWiki] [^QuantificationWiki] to collect data (empirical evidence) [^EmpiricalEvidenceWiki].
1. **Study**
    - We check the validity of the experiments.
    - We identify hypotheses that were not confirmed.
1. **Act**
    - If necessary, we revise our goals, the theory, experimentation methods based on the new data.
    - We adopt the change if it led to improvement.
    - We abandon the change otherwise.

### Example

#### The Three Questions (Model for Improvement)

1. **What are we trying to accomplish?**
    We want to improve the clarity and completeness of new GitHub issues so maintainers can understand them faster.

2. **How will we know that a change is an improvement?**
    We will measure improvement with these metrics:
    - An increase in the maintainer-rated "readability score" (1-5 scale).
    - A decrease in the average number of follow-up comments asking for information.

3. **What change can we make that will result in improvement?**
    Our theory is that implementing structured issue form templates for specific categories (like "Bug Reports" and "Feature Requests") will guide contributors to provide better information from the start.

#### The Test Cycle (PDSA)

1. **Plan:** To test our theory, we will create and enable the two new templates ("Bug Report" and "Feature Request"). We will run this test for one month and collect data on our chosen metrics.

1. **Do:** We implemented the plan by enabling the new templates in the GitHub repository.

1. **Study:** We analyzed the data after one month.
    - The "Bug Report" template was a clear success: readability scores went up, and follow-up comments decreased as predicted.
    - **Unexpected Discovery:** For "Feature Requests," contributors almost exclusively used the "Brief description" field, ignoring the other detailed prompts. This suggested the template was too rigid for creative ideas.

1. **Act:** Based on our learning, we made the following decisions:
    - **Adopt:** We will keep the detailed "Bug Report" template as the new standard.
    - **Adapt:** We will significantly simplify the "Feature Request" template, making it less formal. This new, simpler template will be the subject of our next PDSA cycle to see if it performs better.

### Alternative approaches

- PDCA [^PdcaVsPdsa] [^TheoryOfKnowledgePdsa]
- See [[^TheImprovementGuide], Appendix C]


## Development tools

> [!NOTE]
> VS Code extensions are given in the `<publisher>.<extension name>` format.
>
> Browse and install them from the [Extension Marketplace](https://code.visualstudio.com/docs/configure/extensions/extension-marketplace).

> [!NOTE]
> See [Settings JSON file](https://code.visualstudio.com/docs/configure/settings#_settings-json-file).

> [!NOTE]
> Sections are listed in a subjective order of importance.

## Development environment as code

- Describe development environment configuration using code.
- Make the environment reproducible so that each developer has the same tools and project-related environment variables in their shell.
- Commit configuration and lock files to the repo so that the environment can be versioned and shared among all developers.

### VS Code

VS Code is a code editor that features numerous extensions and integrates well with GitHub and LLMs.

#### Recommended tools

Formatting

- [`treefmt`](https://github.com/numtide/treefmt)
- [`treefmt-nix`](https://github.com/numtide/treefmt-nix)

#### Recommended extensions

- Errors:
  - `usernamehw.errorlens`
- Git and GitHub:
  - `eamodio.gitlens`
  - `github.vscode-pull-request-github`
  - `github.vscode-github-actions`
- Collaboration:
  - `ms-vsliveshare.vsliveshare`
- Containers:
  - `ms-azuretools.vscode-containers`
  - `ms-vscode-remote.remote-containers`
  - `docker.docker`
  - `ms-vscode-remote.vscode-remote-extensionpack`
- Formatting:
  - `esbenp.prettier-vscode`
- Other:
  - See tools in `trunk.io`

#### Recommended VS Code settings

```json
{
  "editor.formatOnSave": true,
  "files.autoSave": "afterDelay",
  "workbench.sideBar.location": "right"
}
```


#### Agents

- Set up [Copilot](https://code.visualstudio.com/docs/copilot/overview).

### Markdown

> [!NOTE]
> You're going to use [GitHub-flavored Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

#### Recommended VS Code extensions

- `bierner.github-markdown-preview`
- `yahyabatulu.vscode-markdown-alert`
- `davidanson.vscode-markdownlint`
- `takumii.markdowntable`

### Drawing

#### Recommended tools and VS Code Extensions

- [Excalidraw](https://github.com/excalidraw/excalidraw) - Virtual whiteboard for sketching hand-drawn like diagrams.
  - `pomdtr.excalidraw-editor`
- [Draw.io](https://github.com/jgraph/drawio) - a JavaScript, client-side editor for general diagramming.
  - `hediet.vscode-drawio`
- [Tldraw](https://github.com/tldraw/tldraw) - very good whiteboard SDK / infinite canvas SDK.
  - `tldraw-org.tldraw-vscode`
  
### Diagrams as code

#### Recommended tools and VS Code extensions

- [`Mermaid`](https://mermaid.js.org/)
  - `bierner.markdown-mermaid`
- [`PlantUML`](https://plantuml.com/)
  - `jebbs.plantuml`

#### Tools for visualizing architecture

- [`Mermaid`](https://mermaid.js.org/)
  - `bierner.markdown-mermaid`
- [`PlantUML`](https://plantuml.com/)
  - `jebbs.plantuml`
- [`C4`](https://c4model.com/)
- [`LikeC4`](https://github.com/likec4/likec4)
  - `likec4.likec4-vscode`
- [other](https://c4model.com/tooling)

### Direnv

See [Direnv docs](https://direnv.net/).

When you enter a directory (e.g., via a terminal), `direnv` runs the `.envrc` file if it's present in the directory.

`direnv` can load your [Nix-based devshells](#nix-based-devshells) (see [nix-direnv](https://github.com/nix-community/nix-direnv)).

#### Recommended VS Code extensions

- `mkhl.direnv`

### Nix

#### Recommended tools

- Formatting (one of these):
  - [`nixfmt`](https://github.com/NixOS/nixfmt) (official)
  - [`alejandra`](https://github.com/kamadorueda/alejandra)
- Language server (one of these):
  - [`nil`](https://github.com/oxalica/nil)
  - [`nixd`](https://github.com/nix-community/nixd)

#### Recommended VS Code extension

- `jnoortheen.nix-ide`

#### Resources

- [NixOS.org](https://nixos.org/) - official NixOS Foundation site.
- [Nix docs](<https://nix>
.dev/index.html) - official documentation.
- [awesome-nix](https://github.com/nix-community/awesome-nix) - A curated list of the best resources in the Nix community.
- [Windows Subsystem for Linux (WSL)](https://nixos.wiki/wiki/Nix_Installation_Guide#Windows_Subsystem_for_Linux_.28WSL.29)

#### NixOS

- [Trilby](https://github.com/ners/trilby) - 👒 Trilby is a NixOS-based operating system that is modeled after Fedora Linux. It provides new users with sensible defaults and a great out-of-the-box experience.
- [NixOS-WSL](https://github.com/nix-community/NixOS-WSL).

#### Telegram chats

- <https://t.me/nix_org>
- <https://t.me/nixos_en>
- <https://t.me/ru_nixos>

#### Nix flakes

It's strongly recommended to [enable flakes](https://nixos.wiki/wiki/Flakes#Other_Distros.2C_without_Home-Manager) so that you can get a `flake.lock` file that pins all inputs of your flake.

You must commit both `flake.nix` and `flake.lock` to your repo.

See [NixOS & Flakes Book](https://nixos-and-flakes.thiscute.world).

#### Nix-based devshells

- [Devenv](https://devenv.sh/) - Fast, Declarative, Reproducible and Composable Developer Environments using Nix.
- [devshell](https://github.com/numtide/devshell) - Per project developer environments.
- [flox](https://github.com/flox/flox) - Developer environments you can take with you.
- [Xome](https://github.com/jeff-hykin/xome) - Xome ("Zome") brings the power of Nix's home-manager to projects -- meaning fancy customized team-shared reproducible shell environments.

#### GitHub Actions

- [cache-nix-action](https://github.com/nix-community/cache-nix-action/)

#### Nix alternatives

- [Lix](https://lix.systems/)
- [Nickel](https://github.com/tweag/nickel)
- [hnix](https://github.com/haskell-nix/hnix)
- [twix](https://github.com/tvlfyi/tvix)

### Python

See:

- [Python](https://www.python.org/)
- [awesome-python](https://github.com/vinta/awesome-python)
- [pyproject.toml](https://packaging.python.org/en/latest/guides/writing-pyproject-toml/)

#### Recommended tools

- Formatting (one of these):
  - [`ruff`](https://docs.astral.sh/ruff/) -  An extremely fast Python linter and code formatter, written in Rust.
  - [`black`](https://black.readthedocs.io/en/stable/) -  The uncompromising Python code formatter.
- Type checking (one of these):
  - [`pyrefly`](https://github.com/facebook/pyrefly) - A fast type checker and IDE for Python.
  - [`ty`](https://docs.astral.sh/ty/) - An extremely fast Python type checker and language server, written in Rust.
  - [`mypy`](https://mypy.readthedocs.io/en/stable/) -  Optional static typing for Python.
    - Try to [disallow dynamic typing](https://mypy.readthedocs.io/en/stable/config_file.html#disallow-dynamic-typing).
- Linters (one of these):
  - [`ruff`](https://docs.astral.sh/ruff/) - An extremely fast Python linter and code formatter, written in Rust.
  - [`pylint`](https://pylint.reappydthedocs.io/en/stable/) -  It's not just a linter that annoys you!
- Packaging (one of these):
  - [`Poetry`](https://python-poetry.org/)
    - Configuration and lock files:
      - [`pyproject.toml`](https://python-poetry.org/docs/pyproject/)
      - [`poetry.toml`](https://python-poetry.org/docs/configuration/#local-configuration) with [in-project = true](https://python-poetry.org/docs/configuration/#virtualenvsin-project)
      - [`poetry.lock`](https://python-poetry.org/docs/libraries#lock-file)
  - [`uv`](https://docs.astral.sh/uv/)
    - Configuration and lock files:
      - [`pyproject.toml`](https://docs.astral.sh/uv/concepts/configuration-files/)
      - [`uv.lock`](https://docs.astral.sh/uv/concepts/projects/layout/#the-lockfile)
  - [`pip`](https://pip.pypa.io/en/stable/)
    - Lock file:
      - [`requirements.txt`](https://pip.pypa.io/en/stable/reference/requirements-file-format/)

#### Recommended VS Code extensions

Choose relevant extensions based on tools from the previous section that you selected previously.

- Language server:
  - `ms-python.python`
    - See also [Python Interactive window](https://code.visualstudio.com/docs/python/jupyter-support-py).
- Formatting (one of these):
  - `charliermarsh.ruff`
  - `ms-python.black-formatter`
- Type checking (one of these):
  - `meta.pyrefly`
  - `astral-sh.ty`
  - `matangover.mypy`
- Linting (one of these):
  - `charliermarsh.ruff`
  - `ms-python.pylint`

### TypeScript

#### Recommended tools

- Compiler:

  - [`tsc`](https://github.com/microsoft/TypeScript)
    - Configuration file:
      - [tsconfig.json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)

- Packaging (one of these):

  - [`bun`](https://github.com/oven-sh/bun)
    - Configuration and lock files:
      - [package.json](https://docs.npmjs.com/cli/v11/configuring-npm/package-json)
      - [bun.lock](https://bun.com/docs/install/lockfile)
  - [`npm`](https://github.com/nodejs/node/tree/main/deps/npm)
    - Configuration and lock files:
      - [package.json](https://docs.npmjs.com/cli/v11/configuring-npm/package-json)
      - [package-lock.json](https://docs.npmjs.com/cli/v11/configuring-npm/package-lock-json)

### LaTeX

See [LaTeX](https://www.latex-project.org/).

#### Recommended tools

- [`TeX Live`](https://www.tug.org/texlive/) (full)
- `xetex` (included into `TeX Live` as `texlive-xetex`)
- `biber` (included into `TeX Live`)

#### Recommended VS Code extensions

- `james-yu.latex-workshop`

#### Recommended VS Code settings

See [LaTeX recipes](https://github.com/james-yu/latex-workshop/wiki/compile#latex-recipes).

```jsonc
{
  "latex-workshop.formatting.latex": "latexindent",
  "latex-workshop.latex.recipes": [
    {
      "name": "xelatex -> biber -> xelatex * 2",
      "tools": ["xelatex", "biber", "xelatex", "xelatex"]
    }
  ],
  "latex-workshop.latex.tools": [
    {
      "args": ["%DOCFILE%"],
      "command": "biber",
      "name": "biber"
    },
    {
      "args": [
        "-shell-escape",
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ],
      "command": "xelatex",
      "env": {},
      "name": "xelatex"
    }
  ]
}
```

<!-- TODO 
dockerfile - hadolint

awesome-linters?
 -->

### Bash

See [Bash](https://www.gnu.org/software/bash/).

#### Recommended VS Code extensions

- `mads-hartmann.bash-ide-vscode`
- `timonwong.shellcheck`

### Extensions and tools for formal languages

<!-- TODO add stately -->

See [Formal languages](https://en.wikipedia.org/wiki/Formal_language), [Chomsky hierarchy](https://en.wikipedia.org/wiki/Chomsky_hierarchy).

### Containers

See [awesome-containers](https://github.com/pditommaso/awesome-containers).

- [`Docker Compose`](https://docs.docker.com/compose/) - Docker Compose is a tool for defining and running multi-container applications.
- [`Kubernetes`](https://kubernetes.io/) - Kubernetes, also known as K8s, is an open source system for automating deployment, scaling, and management of containerized applications.
- [`Pulumi`](https://www.pulumi.com/) - Infrastructure as Code in any programming language 🚀.
  - See [State & backends](https://www.pulumi.com/docs/iac/concepts/state-and-backends/).
- [Distrobox](https://github.com/89luca89/distrobox) - Use any Linux distribution inside your terminal. Enable both backward and forward compatibility with software and freedom to use whatever distribution you’re more comfortable with.

### Virtualization

See [awesome-virtualization](https://github.com/Wenzel/awesome-virtualization).

- [VirtualBox](https://www.virtualbox.org/) - a hosted hypervisor for x86 virtualization.
- [Proxmox](https://www.proxmox.com/en/) - Proxmox Virtual Environment is a complete open-source platform for enterprise virtualization.
- [nixos-shell](https://github.com/Mic92/nixos-shell) -  Spawns lightweight NixOS VMs in a shell.

### Secrets

- [SOPS](https://getsops.io/) - Simple And Flexible Tool For Managing Secrets.
- [agenix](https://github.com/ryantm/agenix) - age-encrypted secrets for NixOS and Home manager.
- [sops-nix](https://github.com/Mic92/sops-nix) - Atomic secret provisioning for NixOS based on SOPS.

## Agile

### Agile and architecture

The table below (adapted from [[^Bck], Chapter 24, TABLE 24.2]) shows Principles [^AgileManifestoPrinciples] behind the Agile Manifesto [^AgileManifesto] and architecture-centric point of view on these principles.

Table: *Agile Principles and Architecture-centric View*

| Agile Principle                                                                                                                               | Agree? | Architecture-centric View                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The best architectures, requirements, and designs emerge from self-organizing teams.                                                          | No!    | No, they don’t. The best architectures are consciously designed by skilled, talented, trained, and experienced architects, as we describe in Chapter 20                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.               | No!    | This is nonsense for nontrivial systems. Humans invented writing because our brains can’t remember everything we need to remember. Interfaces, protocols, architectural structures, and more need to be written down, and the inefficiencies and ineffectiveness of repeated instruction and resulting errors from misunderstanding belie this principle. According to this argument, nobody should produce user manuals, but should just publish the developers’ phone numbers with an open invitation to call them anytime. This is also nonsense for any system that has a maintenance phase (that’s pretty much every system) in which the original team is nowhere to be found. With whom are you going to have that face- to-face conversation to learn important details? See Chapter 22 for our guidance in this matter. |
| Business people and developers must work together daily throughout the project.                                                               | Mostly | Business goals lead to quality attribute requirements, which the architecture’s primary duty is to fulfill, as we discussed in Chapter 19.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.             | Mostly | While we agree in principle, many developers are inexperienced. So make sure to include a skilled, experienced, and motivated architect to help guide these individuals.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Working software is the primary measure of progress.                                                                                          | Mostly | Yes, as long as “primary” is not taken to mean “only,” and as long as this principle is not used as an excuse to eliminate all work except coding.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Simplicity — the art of maximizing the amount of work not done — is essential.                                                                | Mostly | Yes, of course, as long as it is understood that the work we are not doing can actually be jettisoned safely without detriment to the system being delivered.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Deliver working software frequently, from a couple of weeks to a couple of months, with a preference for the shorter time scale.              | Yes!   | Absolutely, as long as this principle is not seen as precluding a thoughtful architecture. DevOps has a large role to play here, and we have seen, in Chapter 5, how architectures can support DevOps.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Welcome changing requirements, even late in development. Agile processes harness change for the customer’s competitive advantage.             | Yes!   | Absolutely. This principle is served by architectures that provide high degrees of modifiability (Chapter 8) and deployability (Chapter 5).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.                                   | Yes!   | Absolutely.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely. | Yes!   | Absolutely.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Continuous attention to technical excellence and good design enhances agility.                                                                | Yes!   | Absolutely.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| At regular intervals, the team reflects on how to become more effective, and then tunes and adjusts its behavior accordingly.                 | Yes!   | Absolutely.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

Legend:

- *Agree?* - whether the book [^Bck] authors agree with the principle.
- *Agile Principle* - a principle [^AgileManifestoPrinciple] behind the Agile Manifesto [^AgileManifesto].
- *Architecture-centric View* - the book [^Bck] authors' comment on the principle from the architecture-centric point of view.

## Scrum


From [^WhatIsScrum]:

Scrum is a way to get work done as a team in small pieces at a time, with continuous experimentation and feedback loops along the way to [learn and improve](#relation-to-pdsa) as you go. Scrum helps people and teams deliver value *incrementally* in a collaborative way. As an [Agile](#agile) framework, Scrum provides just enough structure for people and teams to integrate into how they work, while adding the right practices to optimize for their specific needs.

Scrum is an empirical process, where decisions are based on observation, experience and experimentation. Scrum has three pillars: transparency, inspection and adaptation. This supports the concept of working *iteratively*. Think of Empiricism as working through small experiments, learning from that work and adapting both what you are doing and how you are doing it as needed.

From [^TheThreePillarsOfEmpiricismScrum]:

Scrum works not because it has three [roles](#roles), five [events](#events), and three [artifacts](#artifacts-and-commitments) but because it adheres to the underlying [Agile](#agile) principles of iterative, value-based incremental delivery by frequently gathering customer feedback and embracing change. This results in faster time to market, better delivery predictability, increased customer responsiveness, ability to change direction by managing changing priorities, enhanced software quality, and improved risk management.

### Theory

- [Scrum in a Nutshell](https://youtu.be/502ILHjX9EE) (~15 minutes);
- [What is Professional Scrum](https://youtu.be/BYlv7eP9zgg) (~7 minutes);
- *The 2020 Scrum Guide* [^ScrumGuide];
- *Using Agile in Project Management* [^UsingAgileInProjectManagement];
- *SBOK® (Scrum Body of Knowledge) Guide* [^SbokGuide];

### Process

![What is Scrum?](./assets/WhatIsScrum.png)

<!-- 
This image was chosen because:
- It has a better resolution than the one at https://www.scrum.org/learning-series/what-is-scrum/what-is-scrum
- It shows both artifacts and commitments
 -->

Source: [^WhatIsScrumGfg]

Legend:

- *Dev* - Developer
- *SM* - Scrum Master
- *PO* - Product Owner

### Relation to PDSA

Scrum incorporates a [PDSA cycle](#the-pdsa-cycle).

Adapted from [^ScrumPdca]:

- *Plan* is the sprint planning meeting
- *Do* is the sprint execution (together with Daily Scrum)
- *Study* is the sprint review and retrospective, and
- *Act* is the feedback result of the sprint review and retrospective, which is reflected in the specific requirements and process improvement activities.

### Roles

#### Core roles

From [^SbokGuide]:

1. **Product Owner** is the person responsible for maximizing business value for the project. He or she is responsible for articulating customer requirements and maintaining business justification for the project. The Product Owner represents the *Voice of the Customer*.

1. **Scrum Master** is a facilitator who ensures that the Scrum Team is provided with an environment conducive to completing the product’s development successfully. The Scrum Master guides, facilitates, and teaches Scrum practices to everyone involved in the project; clears impediments for the team; and ensures that Scrum processes are being followed.

    Note that the Scrum Master role is vastly different from the role played by the Project Manager in a traditional Waterfall model of project management, in which the Project Manager works as a manager or leader for the project. The Scrum Master only works as a facilitator and he or she is at the same hierarchical level as anyone else in the Scrum Team — any person from the Scrum Team who learns how to facilitate Scrum projects can become the Scrum Master for a project or for a Sprint.

1. **Scrum Team** is a group or team of people who are responsible for understanding the business requirements specified by the Product Owner, estimating User Stories, and final creation of the project deliverables.

#### Non-core roles

- **Business Stakeholder(s)**, which is a collective term that includes customers, users, and sponsors who frequently interface with the Scrum Core Team and also influence the project throughout the project’s development. Most importantly, it is for the business stakeholders that the project produces collaborative benefits [^SbokGuide].

- **Course Stakeholders** - course instructors (primary instructor, TAs, mentors).


### Artifacts and commitments

There are three required artifacts in Scrum.

From [^ScrumGuide]:

Scrum’s artifacts represent work or value. They are designed to maximize transparency of key information. Thus, everyone inspecting them has the same basis for adaptation.

Each artifact contains a *commitment* to ensure it provides information that enhances transparency and focus against which progress can be measured:

- For the *Product Backlog* it is the *Product Goal*.
- For the *Sprint Backlog* it is the *Sprint Goal*.
- For the *Increment* it is the *Definition of Done*.

These commitments exist to reinforce empiricism and the Scrum values for the Scrum Team and their stakeholders.


## Work item hierarchy

We use the following hierarchy of work items that are represented via issues of different types and pull requests [^WorkItemHierarchy].

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

We created several sample [issues](https://github.com/inno-swp-2025/we-have-tiktok-at-home/issues) in the [inno-swp-2025/we-have-tiktok-at-home](https://github.com/inno-swp-2025/we-have-tiktok-at-home) repo.

### Issue types

Each issue has a [type](https://docs.github.com/en/issues/tracking-your-work-with-issues/configuring-issues/managing-issue-types-in-an-organization).

The types are [`Epic`](#epic), [`Backlog`](#backlog), [`Task`](#task).

#### `Epic`

An Epic is a container for a major initiative that is too large and complex to be completed in a single sprint. It groups together related Product Backlog Items to achieve a larger goal. This initiative can be a customer-facing feature, a large-scale bug fix, a technical debt reduction plan, or a significant architectural improvement.

#### `Backlog`

A Product Backlog Item (PBI) is a unit of work that is small enough to be completed by the team within a single sprint. It represents a concrete step toward completing an Epic. A PBI must deliver a demonstrable increment of value, though that value may be for the end-user (a feature), for the system (stability/performance), or for the development team (enabling future work).

#### `Task`

A Task is a specific action required to complete a Product Backlog Item (PBI). It breaks down a PBI into the smallest, most granular steps needed for implementation or completion.

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

In our [projects](#projects), we use the custom `Priority` field of type `Single select` for setting issue priority and sorting/slicing issues by priority.

`Priority` can have the following values:

- `P0` - Highest priority. Requires immediate attention.
- `P1` - High priority. Essential to achieving a primary goal for the current sprint or project phase.
- `P2` - Medium priority. Important work that provides significant value but is not time-critical.
- `P3` - Low priority. Valuable, but non-essential.

## Pull requests

Each pull request should address a particular type `Task` issue.

You should avoid creating pull requests that don't address a particular type `Task` issue (aka "last-minute changes").

The `PR: *` labels are automatically assigned to pull requests when you create pull requests from [templates](#pull-request-templates).

## Templates

We store [default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file) in the [inno-swp-2025/.github](https://github.com/inno-swp-2025/.github) repo.

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

Milestones are specific, key points within a project that mark progress and completion of significant phases or tasks[^Milestones].

Milestones are not sprints [^MilestonesVsSprints].

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
- `Priority` of type `Single select` - priority of an issue (see [Issue priority](#issue-priority)).

### View `Timeline`

Shows planned schedule of working on type `Epic` issues.

#### View options

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

### View `Kanban`

- Provides `Entry Criteria` in Kanban board column descriptions.
- Shows status of type Epic issues.

#### View options

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
* A person who would monitor the issue progress was assigned to the issue.
* Some sub-issues were completed.
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
- `Priority` of type `Single select` - priority of an issue (see [Issue priority](#issue-priority)).

### View `Kanban`

- Provides `Entry Criteria` in Kanban board column descriptions.
- Shows total `Story Points` per sprint.

#### View options

- Layout: `Board`.

- Configuration:
  - Fields: `Assignees`, `Status`, `Sprint`, `Story Points`, `Priority`, `Sub-issues progress`.
  - Column by: `Status`.
  - Group by: `Sprint`.
  - Sort by: `Priority` (ascending).
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
- `Priority` of type `Single select` - priority of an issue (see [Issue priority](#issue-priority)).
- `Start` of type `Date` - (planned) date of starting the work on an issue.
- `Finish` of type `Date` - (planned) date of finishing the work on an issue.

### View `Kanban`

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
  - Sort by: `Priority` (ascending), `Ideal Hours` (descending).
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

## References

[^WorkItemHierarchy]: Adapted from <https://learn.microsoft.com/en-us/azure/devops/boards/backlogs/define-features-epics?view=azure-devops&tabs=scrum-process#portfolio-backlogs>
[^Milestones]: What are project milestones: benefits and examples <https://www.atlassian.com/blog/project-management/project-milestones>
[^MilestonesVsSprints]: Sprint vs milestone vs release <https://pm.stackexchange.com/questions/22510/sprint-vs-milestone-vs-release>
[^Bck]: Software Architecture in Practice, 4th Edition by L. Bass, P. Clements, and R. Kazman. ([File](./assets/SoftwareArchitectureInPracticeEdition4.pdf))
[^QASofSoftwareArchitecture]: Quality attributes of software architectures <https://www.cs.unibo.it/cianca/wwwpages/as/5.pdf#page=26>
[^QualityScenarios]: Lecture on Quality Scenarios <https://greg4cr.github.io/courses/spring21dit635/Lectures/Spring21-Lecture3-QualityScenarios.pdf>
[^Swebok]: SWEBOK v4: Guide to the Software Engineering Body of Knowledge v4.0 <https://ieeecs-media.computer.org/media/education/swebok/swebok-v4.pdf>
[^UtilityTreeTabular]: Tabular form is recommended at <https://docs.arc42.org/tips/10-2/>
[^Iso25010]: The ISO/IEC 25010 quality model <https://iso25000.com/index.php/en/iso-25000-standards/iso-25010>
[^Q42]: The arc42 quality model <https://quality.arc42.org/>
<!-- TODO rename to Sap -->
[^BckCh19]: ***Software Architecture in Practice*** [^Bck], Chapter 19 ([file](./assets/BckCh19.pdf))
[^ProjectCharter]: How To Write A Good Project Charter: Templates and Examples <https://planyway.com/blog/project-charter-elements>
[^ProjectManagementGuide]: <https://planyway.com/blog/project-management-guide>
[^TheMomTest]: Summary of the book ***The Mom Test*** <https://durmonski.com/book-summaries/the-mom-test/>
[^AosaBook]: The Architecture of Open Source Applications
 <https://aosabook.org/en/>
[^AdrTemplates]: Architecture decision record (ADR) examples for software planning, IT leadership, and template documentation <https://github.com/joelparkerhenderson/architecture-decision-record>
[^AdrOrg]: Architectural Decision Records <https://adr.github.io/>
[^RequirementsAgile]: Agile approach and PEGS <https://requirements.university/faq.html#agile>
[^HandbookRequirements]:  Handbook of Requirements and Business Analysis <https://link.springer.com/book/10.1007/978-3-031-06739-6>
[^UserStoriesWiki]: User Story on Wikipedia <https://en.wikipedia.org/wiki/User_story>
[^GivenWhenThen]: Given-When-Then format for acceptance criteria <https://en.wikipedia.org/wiki/Given-When-Then>
[^SETeamProjectProblems]: Software engineering team project courses with industrial customers: Students’ insights on challenges and lessons learned <https://www.sciencedirect.com/science/article/pii/S0164121225001098>
[^MidSprintReview]: <https://www.scrum.org/resources/blog/whats-wrong-mid-sprint-check-or-mid-sprint-review>
[^SoftwareQualityModels]: Software Quality Models: A Systematic Mapping Study <https://ieeexplore.ieee.org/document/8812848>
[^ApmGlossary]: APM glossary of project management terms <https://www.apm.org.uk/resources/glossary>
[^ThePdsaCycle]: The PDSA Cycle <https://deming.org/explore/pdsa/>
[^CirclingBack]: Circling Back <https://deming.org/wp-content/uploads/2020/06/circling-back.pdf>
[^TheoryWiki]: Scientific theory <https://en.wikipedia.org/wiki/Scientific_theory>
[^TheImprovementGuide]: Langley GL, Moen R, Nolan KM, Nolan TW, Norman CL, Provost LP. The Improvement Guide: A Practical Approach to Enhancing Organizational Performance (2nd Edition). San Francisco: Jossey-Bass Publishers; 2009. ([File](./assets/TheImprovementGuideEdition2.pdf))
[^DesignExperimentWiki]: Design of experiments <https://en.wikipedia.org/wiki/Design_of_experiments>
[^ExperimentTypesWiki]: Experiment types <https://en.wikipedia.org/wiki/Experiment#Types>
[^TheoryAsModelWiki]: Theories as models <https://en.wikipedia.org/wiki/Scientific_theory#Theories_as_models>
[^MentalModel]: Mental model <https://en.wikipedia.org/wiki/Mental_model>
[^FalsifiabilityWiki]: Falsifiability <https://en.wikipedia.org/wiki/Falsifiability>
[^ScientificMethodWiki]: Scientific method <https://en.wikipedia.org/wiki/Scientific_method>
[^EmpiricalCycleWiki]: Empirical cycle <https://en.wikipedia.org/wiki/Empirical_research#Empirical_cycle>
[^EmpiricalEvidenceWiki]: Empirical evidence <https://en.wikipedia.org/wiki/Empirical_research>
[^QuantificationWiki]: Quantification (science) <https://en.wikipedia.org/wiki/Quantification_(science)>
[^MeasurementWiki]: Measurement <https://en.wikipedia.org/wiki/Measurement>
[^PdcaVsPdsa]: Plan Do Check Act (PDCA) vs. Plan Do Study Act (PDSA): What’s the Difference? <https://qualityandinnovation.com/2011/08/26/pdca-vs-pdsa-whats-the-difference/>
[^TheoryOfKnowledgePdsa]: Theory of Knowledge/PDSA <https://www.youtube.com/watch?v=dgazCOz_IIY>
