# Website-Redesign-Project

GitHub Project (Projects v2) setup guide for the university assignment scenario.

## 1) `gh issue create` commands for the 9 core sub-tasks

> Replace `OWNER` and `REPO` before running.

```bash
gh issue create --repo OWNER/REPO --title "Requirements: Conduct stakeholder interviews" --body "Interview key stakeholders to gather business goals, branding expectations, user needs, and constraints for the redesign." --label "phase:requirements"
gh issue create --repo OWNER/REPO --title "Requirements: Develop requirements document" --body "Document functional and non-functional requirements, success metrics, and scope boundaries based on interview findings." --label "phase:requirements"
gh issue create --repo OWNER/REPO --title "Requirements: Host review meeting for sign-off" --body "Run a requirements review meeting with stakeholders, capture feedback, and obtain formal sign-off." --label "phase:requirements"

gh issue create --repo OWNER/REPO --title "Design: Create wireframes and prototypes" --body "Create low/high-fidelity wireframes and interactive prototypes covering key user journeys and navigation flows." --label "phase:design"
gh issue create --repo OWNER/REPO --title "Design: Develop mock-ups and collect feedback" --body "Produce visual mock-ups aligned with updated branding and iterate using structured stakeholder feedback." --label "phase:design"
gh issue create --repo OWNER/REPO --title "Design: Hold design approval session" --body "Present final design direction, confirm accessibility/UX considerations, and secure design approval." --label "phase:design"

gh issue create --repo OWNER/REPO --title "Development: Set up dev environment and tools" --body "Set up repository workflows, local environments, branching conventions, and required tooling for the team." --label "phase:development"
gh issue create --repo OWNER/REPO --title "Development: Implement front-end" --body "Build responsive UI components and navigation experience based on approved designs and branding updates." --label "phase:development"
gh issue create --repo OWNER/REPO --title "Development: Build back-end shopping cart and payments" --body "Implement server-side commerce features including cart state, checkout flow, and payment gateway integration." --label "phase:development"
```

### Optional batch script version

```bash
#!/usr/bin/env bash
set -euo pipefail

REPO="OWNER/REPO"

gh issue create --repo "$REPO" --title "Requirements: Conduct stakeholder interviews" --body "Interview key stakeholders to gather business goals, branding expectations, user needs, and constraints for the redesign." --label "phase:requirements"
gh issue create --repo "$REPO" --title "Requirements: Develop requirements document" --body "Document functional and non-functional requirements, success metrics, and scope boundaries based on interview findings." --label "phase:requirements"
gh issue create --repo "$REPO" --title "Requirements: Host review meeting for sign-off" --body "Run a requirements review meeting with stakeholders, capture feedback, and obtain formal sign-off." --label "phase:requirements"

gh issue create --repo "$REPO" --title "Design: Create wireframes and prototypes" --body "Create low/high-fidelity wireframes and interactive prototypes covering key user journeys and navigation flows." --label "phase:design"
gh issue create --repo "$REPO" --title "Design: Develop mock-ups and collect feedback" --body "Produce visual mock-ups aligned with updated branding and iterate using structured stakeholder feedback." --label "phase:design"
gh issue create --repo "$REPO" --title "Design: Hold design approval session" --body "Present final design direction, confirm accessibility/UX considerations, and secure design approval." --label "phase:design"

gh issue create --repo "$REPO" --title "Development: Set up dev environment and tools" --body "Set up repository workflows, local environments, branching conventions, and required tooling for the team." --label "phase:development"
gh issue create --repo "$REPO" --title "Development: Implement front-end" --body "Build responsive UI components and navigation experience based on approved designs and branding updates." --label "phase:development"
gh issue create --repo "$REPO" --title "Development: Build back-end shopping cart and payments" --body "Implement server-side commerce features including cart state, checkout flow, and payment gateway integration." --label "phase:development"
```

## 2) Suggested GitHub Project custom fields (Projects v2)

- **Status** (single select): `Backlog`, `Ready`, `In Progress`, `Blocked`, `In Review`, `Done`
- **Priority** (single select): `P1 - Critical`, `P2 - High`, `P3 - Medium`, `P4 - Low`
- **Phase** (single select): `Requirements`, `Design`, `Development`, `Testing`, `Launch`
- **Role Owner** (single select): `Project Manager`, `Web Designer`, `Front-End Developer`, `Back-End Developer`, `QA Tester`, `Marketing Lead`
- **Effort** (number): story points or estimated days
- **Target Iteration** (iteration): 2-week iterations across the 6-month timeline
- **Target Milestone** (single select): `M1 Requirements Finalised`, `M2 Design Approved`, `M4 Development Complete`, `M5 Testing Complete`, `M6 Site Launch`

## 3) Example dependency to represent

Since Projects v2 has no native dependency arrows, use **linked issues + a note field**:

- Make **"Development: Implement front-end"** depend on **"Design: Hold design approval session"**.
- In the front-end issue body, add: `Blocked by #<design-approval-issue-number>`.
- Optionally add a `Blocked By` text field in Project to store the issue reference.

## 4) Representing the 5 milestones

Create GitHub Milestones (repo-level) with due dates, then assign issues:

1. **Requirements finalised** — due end of Month 1
2. **Design approved** — due end of Month 2
3. **Development complete** — due end of Month 4
4. **Testing complete** — due end of Month 5
5. **Site launch** — due end of Month 6

Use milestones for deadline tracking and Projects v2 for day-to-day status/priority/ownership.
