# How to Write Tech Docs

<details>

<summary>Written with 💖 by Rakesh Asapanna</summary>

- Professional Experience: [asra.dev](https://asra.dev/)
- GitHub: [@rozeappletree](https://github.com/rozeappletree)
- LinkedIn: [in/asapanna-rakesh](https://www.linkedin.com/in/asapanna-rakesh/)

</details>
<br/>

## Introduction: Establishing Documentation as an Engineering Discipline

https://github.com/user-attachments/assets/28f7d3de-f973-4ff5-a14c-f8155a8c0da7

Great documentation is an often-overlooked yet critical component for the success and large-scale adoption of any software project. It is not an afterthought or the final, rushed step in a release plan, but an integral feature of the software itself—often the very first feature a user interacts with. When documentation is clear, accurate, and helpful, it builds trust, accelerates onboarding, and empowers users. When it is missing or inaccurate, it becomes a primary source of friction, frustration, and disengagement.
This guide reveals the repeatable, end-to-end process for creating and managing high-value technical documentation, framing it as a core engineering discipline. Just as developers refine their code through a "developer loop" of writing, testing, and iterating, technical writers and documentarians follow an analogous "writer loop." This process requires understanding the user's problem, creating a plan to solve it, using established patterns, and writing content that provides a clear solution.
By treating documentation with the same rigor and process-oriented mindset as software development, teams can transform it from a liability into a powerful asset. This guide will walk you through the four major phases of that professional lifecycle:
1. **Foundation and Planning:** Understanding your users and architecting a content plan to meet their needs.
2. **Content Creation and Authoring:** Drafting text and integrating essential code samples and visuals.
3. **Quality Assurance and Release:** Refining content through a structured editing and review process before publishing.
4. **Lifecycle Management:** Gathering feedback, measuring quality, and maintaining the documentation's integrity over time.

<img width="1250" height="480" alt="image" src="https://github.com/user-attachments/assets/dc343d25-5db1-4b1b-8d27-063680d5acbb" />


## Principle Elements / Steps Involved in Doc Workflow

Principle 11 steps detailing the documentation workflow:

1. **Understanding your audience:** This involves breaking the "curse of knowledge" by performing user research to identify users' goals, who they are, and their needs, often condensing findings into personas, user stories, and friction logs.
2. **Planning your documentation:** This step involves translating the empathy gained from user research into action by determining which content types—such as READMEs, conceptual documentation, or procedural documentation—best address user needs, culminating in a comprehensive documentation plan.
3. **Drafting documentation:** Focuses on confronting the blank page by defining the document's goal and title, creating an outline, and filling in content using paragraphs, lists, and callouts while striving for simplicity and clarity.
4. **Editing documentation:** This is the analytical act of reviewing text to ensure it meets user needs, focusing on technical accuracy, completeness, structure, clarity, and brevity, often through a collaborative peer review process.
5. **Integrating code samples:** Recognizing that code is critical to developers, this step covers providing code samples that are explained, concise, clear, usable, and trustworthy, often exploring tooling options like testing or autogenerating samples.
6. **Adding visual content:** Addresses using visuals, such as screenshots and diagrams (boxes and arrows, flowcharts, swimlanes), to convey information quickly and effectively, while ensuring accessibility and maintaining minimal clutter.
7. **Publishing documentation:** Involves building a content release process, aligning the publishing timeline with code releases, deciding how to deliver content to meet users where they are, and announcing the documentation's availability.
8. **Gathering and integrating feedback:** Details establishing scalable feedback channels—like monitoring support issues or creating user surveys—and establishing a triage process to convert user feedback into prioritized, actionable tasks.
9. **Measuring documentation quality:** Focuses on defining "quality" by assessing functional quality (does it fulfill its purpose?) and structural quality (is it well-written?) and using a strategy of clustered metrics (like TTHW or unique visitors) to evaluate success.
10. **Organizing documentation:** Involves establishing the information architecture—using combinations of sequences, hierarchies, and webs—to help readers build a mental map of the content, often utilizing navigation cues and landing pages.
11. **Maintaining and deprecating documentation:** Covers planning for ongoing maintenance, assigning document owners, automating toil (e.g., freshness checks and linters), and correctly deprecating or deleting content that is no longer useful or accurate

  
---

# 1. Understanding Audience

```mermaid
graph TD
    Root["I. Understanding Your Audience"]
    
    Root --> Curse["The Curse of Knowledge"]
    Root --> Sketch["Initial User Sketch"]
    Root --> Validate["Validate User Understanding (Research)"]
    Root --> Condense["Condensing Research Findings"]
    Root --> Friction["Creating a Friction Log (record user experience)"]
    
    Curse --> CurseA["Humans assume shared knowledge"]
    Curse --> CurseB["Break the curse with empathy"]
    
    Sketch --> SketchA["Define user goals (Engineering & Business)"]
    Sketch --> SketchB["Identify who users are"]
    Sketch --> SketchC["Outline user needs (questions docs must answer)"]
    
    SketchB --> UserA["Role (Developer, SRE, PM)"]
    SketchB --> UserB["Experience/Situation"]
    SketchB --> UserC["Characteristics (Skill, Language, OS)"]
    
    Validate --> ValidA["Existing Data Sources"]
    Validate --> ValidB["Collecting New Data"]
    
    ValidA --> ExistA["Support tickets (group by theme)"]
    ValidA --> ExistB["Developer relations/UX/Marketing teams"]
    
    ValidB --> NewA["Direct interviews (open questions)"]
    ValidB --> NewB["Developer surveys (quick & painless, targeted questions)"]
    
    Condense --> CondA["User Personas (semi-fictional character)"]
    Condense --> CondB["User Stories (As a [user], I want [activity] so I can [goal])"]
    Condense --> CondC["User Journey Maps (timeline of user path/feelings)"]
```

Understanding your audience is the first and most essential step in the documentation creation process. This step focuses on establishing empathy for users, which is required to write effective documentation.

The core objective of this initial phase is to overcome the _"curse of knowledge,"_ a cognitive bias where writers assume others possess the same knowledge they do. This curse can lead to using jargon or omitting crucial information.

Here are the key components of this phase, designed to break the curse of knowledge and set users on the path to success:

- **Creating an Initial Sketch of Your Users:** To write effectively, writers must first understand who their users are and what they want to achieve.
- **Define User Goals:** Research is guided by understanding what users want to accomplish by reading the documentation. Documentation must align with both the engineering goal (what the user wants) and the business goal (what the organization wants).
- **Understand User Identity:** Users can be defined by their role (e.g., developers, product managers), level of experience (e.g., junior developers), or the situation they are in (e.g., using documentation at 4 a.m. after a pager alert). Because not every user's needs can be met, writers must prioritize the users most important for the product or business.
- **Outline User Needs:** This involves listing the specific questions documentation must answer, ranging from general (e.g., "How do I get started?") to product-specific (e.g., "How do I authenticate against your API?"). During research, the distinction between user wants (e.g., a sports car) and user needs (e.g., a bus ticket) must be identified.
Validating User Understanding (User Research)
The initial sketch of users, goals, and needs must be validated through user research.
- **Existing Data Sources:** Support tickets are considered a "gold mine" for understanding user needs, as they reveal what frustrated users require most. Other organizational teams like developer relations, product support, UX, and marketing can also provide valuable insights. Support issues should be grouped by themes, such as topic, process, or user type, to identify patterns.
- **Collecting New Data:** If existing data is insufficient, new data can be collected through direct interviews and developer surveys.
  - **Direct Interviews:** These are used to "dig a little deeper" into pressing issues, emphasizing quality over quantity of participants. Interviews should use specific, open questions (questions that elicit stories and detailed explanations) rather than closed, yes-or-no questions.
  - **Developer Surveys:** These provide actionable and immediate insights from a large group but must be quick, painless, and focused on targeted, closed questions.
Condensing and Applying Findings
Research results must be condensed into tangible records for use in subsequent writing stages.
- **User Personas:** These are semi-fictional characters representing the ideal reader, compiling essential characteristics like developer skill, languages, environment, and role. Personas help the writer focus on the users who need the most help, such as junior developers.
- **User Stories:** These are short summaries of what a user is trying to achieve, following the format: "As a [type of user], I want [activity] so that I can [goal]".
- **User Journey Maps:** These are diagrams illustrating the path a user takes through a product to accomplish a task, highlighting points of happiness or areas for improvement.
- **Friction Log:** A journal where the developer uses the software as a newcomer would, recording the difference between expected and actual behavior at each sequential step. Noticing "friction" (frustration, anger) helps identify opportunities to improve documentation or the product itself.
