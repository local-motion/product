## LOCAL MOTION WAY OF WORKING

### TOOLS

1. Register at ZenHub and install the Chrome plugin -- https://www.zenhub.com/


### SCHEDULE

- 2 week sprints starting on Wednesday
- 1x grooming session per week
- Stand-ups are done asynchronously through Slack


### STAND-UP

Answer the following questions:

1. Yesterday I worked on ...\[, unfortunately I wasn't able to X, Y or Z\ as planned]
1. Today I'll work on ...\[, and I think X, Y or Z may need some help. I'll reach out to ...\]
1. Things blocking me are \[..., ...\]

### GROOMING

The goal is to have our top of the backlog prioritized. Issues at the top MUST NOT have questions
at the start of the Sprint.

- Max. 45 minutes
- Each issue a max of 10 minutes - https://e.ggtimer.com/10minutes
- Process
    - Start at top of backlog
    - Issues that do not have questions, ask: "Any new concerns?"
    - Issues that have questions, ask: "Who is doing what to make this clear?". Record
    decisions and actions as comment on the issue.


### SENSITIVE ISSUES

Local Motion is running on an 'internal AWS cluster'. Any issues/tasks related to creating or maintaining
the internal AWS Kubernetes cluster will live in two places.

1. The real issue may contain sensitive information and is hosted on the internal JIRA (or otherwise) 
1. A placeholder task on ZenHub board: 
    - A short description of the task without revealing sensitive information
    - The JIRA issue number (without exposing internal URLs)
    
    