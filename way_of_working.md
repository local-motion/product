## LOCAL MOTION WAY OF WORKING

### TOOLS

1. Register at ZenHub and install the Chrome plugin -- https://www.zenhub.com/
1. Google Meet (former Hangouts) -- https://meet.google.com
1. Slack -- https://localmotionworkspace.slack.com
1. Office365 -- https://outlook.office.com/owa/?realm=localmotioncommunity.onmicrosoft.com
1. Github 
    1. Organization page -- https://github.com/local-motion
    1. Product page -- https://github.com/local-motion/product
    1. Development bootstrap -- https://github.com/local-motion/bootstrap
1. Meeting egg timer -- https://e.ggtimer.com/10minutes


### SCHEDULE

- 2 week sprints starting on Wednesday
- 1x grooming session per week
- Stand-ups are done daily
- 1x retrospective at end of sprint


### STAND-UP

This is an **a-synchronous** process through Slack channel `#standups`

Answer the following questions:

1. Yesterday I worked on ...\[, unfortunately I wasn't able to X, Y or Z\ as planned]
1. Today I'll work on ...\[, and I think X, Y or Z may need some help. I'll reach out to ...\]
1. Things blocking me are \[..., ...\]

### GROOMING

This is a **synchronous** video session.

The goal is to have our top of the backlog prioritized. Issues at the top MUST NOT have questions
at the start of the Sprint.

- Max. 45 minutes
- Each issue a max of 10 minutes - https://e.ggtimer.com/10minutes
- Process
    - Start at top of backlog
    - Issues that do not have questions, ask: "Any new concerns?"
    - Issues that have questions, ask: "Who is doing what to make this clear?". Record
    decisions and actions as comment on the issue.

### RETROSPECTIVE

This is a **synchronous** video session with a time-cap of 30 minutes

- Discuss last retrospective's resolution and whether it's a change we want to keep.
- Each team member specifies his/her most important negative and most important positive.
- After each team member, we vote for the most important negative
- Only the negative with highest vote is discussed. Agree on a resolution for next sprint.


### ISSUES THAT MAY CONTAIN SENSITIVE INFORMATION

Local Motion is running on an 'internal AWS cluster'. Any issues/tasks related to creating or maintaining
the internal AWS Kubernetes cluster will live in two places.

1. The real issue may contain sensitive information and is hosted on the internal JIRA (or otherwise) 
1. A placeholder task on ZenHub board: 
    - A short description of the task without revealing sensitive information
    - The JIRA issue number (without exposing internal URLs)
    
    