# CSE Technical Onboarding

This repo contains instructions, guidance and details of an exercise intended to get new starters in CSE familiar with several aspects of how we work, the technology we use and how we approach a project engagement. It is closely aligned to the [CSE Engineering Fundamentals](https://microsoft.github.io/code-with-engineering-playbook/) which is a playbook that provides both specific technical advice and general high level guidance on what good looks like to CSE.

## 📝 Anticipated Outcomes and Activities

- Plan & execute work, in an agile fashion similar to a real CSE customer engagement.
- DevOps; infrastructure as code, CI/CD, release automation.
- Solution design, architecture choices
- Write some code!
- Learn to work with Azure and range of services, SDKs etc.

## 🔎 Outline

This exercise should be done as a team, ideally as a whole crew; with the dev lead, engineers and TPM all working together as they would on a real customer engagement. The length of time you spend should be agreed upfront but 2~4 weeks is a recommendation.

The following is intended as a high level guideline to provide some structure to the exercise, but kept deliberately open ended. There will be a lot of ambiguity and questions at the start, you should consult the [engineering fundamentals](https://microsoft.github.io/code-with-engineering-playbook/) then agree upfront as a group on your approach

- Create project in AzDo or GitHub to track work and hold code, docs, wiki etc.
- Decide on where and how you will collaborate, e.g. Teams
- Carry out a "mini" Architecture Design Session (ADS), the dev lead will likely run this with you, [based on one of the provided scenarios below](#customer-scenarios).
- Agree a programming language & toolchain to code in, it's potentially best if the whole team works on the same language. Suggestions are: Node.js/TypeScript, Go, C#, or Python.
- Build high level design, solutioning, architecture/service choices, and diagrams etc.
- Build backlog
  - Focus on spikes and investigations where there is ambiguity, include them in backlog/board
- Sprint in 1-week sprints in lightweight scrum fashion. Note. Strict adherence to a agile methodology like scrum is not the purpose of this exercise, however some structure & process is expected to replicate a real engagement.
  - Iterate with weekly cadence: sprint planning, backlog refinement and retro.
- Use a trunk based development & version control flow, using CI pipelines and PRs. The **main** branch should always be shippable and functional.

## 🏃‍♂️ Execution

### Architecture Design Session (ADS)

An ADS is normally run over 3 or 5 days with a customer and acts as kick off for the 'code-with' phase of an engagement.

- Begin mapping established business requirements, constraints and success criteria into technical requirements
- Define scope, customer requirements frequently exceed what is feasible in the timescales, and with the teams & technology available
- Understand major unknowns and areas that require deeper research
- Develop technical architecture
- Identify additional tech skills needed for the engagement

For this on-boarding exercise it should be done over a day, and essentially acts as the kick off for the exercise.

### Rough Schedule

This is a hypothetical timeline:

- WEEK 1: Start with the ADS and/or kick off session, agree approach & roles. Get pre-reqs in place such as access to Azure subscription(s), create project boards & code repo(s) etc
- WEEK 2: Start investigation spikes, create initial codebase, pick & deploy Azure services and next layer of logical or functional design
- WEEK 3: Sprint on agreed backlog items, build out API features, automated CI and CD, repeatably deployable environments
- WEEK 4: Wrap up, run demos, document findings

### Guiding Principles

- The object of the exercise is to learn.
- Ask questions, and take your time - there is no award for speed :)
- The scenario scope will likely cover much more than you can accomplish, this is normal (customer's often have a scope greater than we can hope to meet with a single crew) - along as priority & core focus is agreed upfront as a group.
- Senior developers and other subject matter experts should guide towards answers and outcomes, rather than "taking over" and giving complete solutions to problems.

## 🧙 Facilitation  

At least one member of the team, ideally the dev lead or TPM should have experience of working on or running several CSE projects, they should act as a facilitator & coordinator. The role of the facilitator is to:

- Act and in-part "role-play" as the customer in the initial ADS, answering questions and clarifying requirements where required. This helps set the direction for the team.
- The scenario will not cover every small detail of what is required. The facilitator should invent and encourage the team to be creative, e.g. "What should this API endpoint be named?",  especially if the team are stuck or paralyzed by ambiguity.
- Drive the overall shape of what the team agree to do, especially the initial backlog, and help team agree cadence and sprint structure

## 👷‍♂️ Customer Scenarios

Currently one scenario is provided, potentially more will be added later:
  
- [Iommi Corp - Modernized Customer Experience](scenarios/iommi-corp/readme.md)

## 🔧 Technical Pre Reqs & Dev Environments

As this exercise is designed for new hires and people new to CSE, there maybe many questions about developer tools, setup of laptops and local environments. A guide has been provided to assist with this. However nothing in this guide is mandatory

- [CSE Developer: local environmental and dev tooling guide](dev-guide.md)

## Contributing

Yes, please 🙂  
Contact [Ben Coleman](mailto:ben.coleman@microsoft.com) or raise an issue / PR.
