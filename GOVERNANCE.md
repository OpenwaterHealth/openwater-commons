# Openwater Commons Governance

**Status:** 🚧 Draft - Under Community Review  
**Version:** 0.1  
**Last Updated:** November 20, 2025

---

## Overview

Openwater Commons uses a **Technical Steering Committee (TSC)** governance model inspired by the Linux Foundation, Cloud Native Computing Foundation (CNCF), and Apache Software Foundation.

This model balances:
- **Open collaboration** - Community can contribute freely
- **Quality assurance** - Structured review and approval
- **Strategic alignment** - Coordination with Openwater's mission
- **Decentralized decision-making** - Community voice in major decisions

---

## Principles

### 1. Open and Transparent
- All TSC meetings are public and recorded
- Meeting notes published in this repository
- Major decisions documented with rationale
- RFC process for significant changes

### 2. Merit-Based
- Influence earned through contributions
- Technical expertise valued over affiliation
- Clear progression path for contributors
- Community can elect TSC members

### 3. Credibly Neutral
- Platform serves ecosystem, not single entity
- Fair processes for all participants
- Protection against capture by any stakeholder
- Balance between openness and sustainability

### 4. Pragmatic
- Decisions made efficiently
- Consensus preferred, but voting when needed
- Veto rights on critical business matters
- Focus on impact and execution

---

## Technical Steering Committee (TSC)

### Composition

**9 voting members total:**

**Openwater Representatives (3 seats):**
- CEO or delegate
- Chief Technology Officer or Technical Lead
- Director of Open-Source Business Strategy

**Academic/Research Representatives (3 seats):**
- Mayo Clinic representative
- Stanford University representative
- Johns Hopkins representative (or rotating slot)

**Community-Elected Representatives (3 seats):**
- Elected by Regular Contributors once we reach 50+ contributors
- 12-month terms with staggered elections
- Must be Core Contributors to be eligible

### Current TSC Members

**Openwater Representatives:**
1. Aaron (CEO)
2. David (Technical Lead)
3. Dan Blizinski (Director of Open-Source)

**Academic Representatives:**
1. Mayo Clinic - TBD (partnership in development)
2. Stanford - TBD (pending confirmation)
3. Johns Hopkins - TBD (in discussion)

**Community Representatives:**
1. **Position 1** - Requires 50+ contributors milestone
2. **Position 2** - Requires 50+ contributors milestone
3. **Position 3** - Requires 50+ contributors milestone

### TSC Responsibilities

The TSC is responsible for:

**Technical Direction:**
- Overall technical vision and roadmap
- Architecture and design decisions
- Technology stack and dependency choices
- Breaking changes and versioning

**Quality & Standards:**
- Code quality standards and review processes
- Testing and CI/CD requirements
- Documentation standards
- Security policies and practices

**Community & Process:**
- Contribution guidelines and processes
- Committer nominations and approvals
- Code of Conduct enforcement
- Community program oversight

**Licensing & IP:**
- Licensing decisions (with board approval)
- Contributor License Agreement (CLA)
- Patent and trademark policies
- Third-party dependency licensing

**Releases:**
- Release planning and scheduling
- Version numbering and compatibility
- Release criteria and quality gates
- Deprecation policies

### TSC Meetings

**Schedule:**
- Monthly standing meetings
- Special meetings as needed
- Minimum 5 members for quorum

**Process:**
- Agenda published 48 hours in advance
- Public attendance allowed (observer mode)
- Meeting notes published within 1 week
- Recorded and archived (audio/video)

**Location:**
- Video conference (link in meeting notes)
- Rotating times for global accessibility

---

## Decision-Making Process

### Consensus-First Approach

**The TSC seeks consensus on all decisions:**
1. Issue or RFC is proposed
2. Community discussion period (usually 2 weeks)
3. TSC discusses in meeting
4. Attempt to reach consensus
5. If consensus achieved → decision made
6. If consensus not possible → move to voting

### Voting

**When voting is needed:**
- **Simple majority:** 5 of 9 votes required
- **Abstentions:** Count toward quorum but not toward majority
- **Proxy voting:** Allowed with advance notice

**Voting process:**
- Posted in TSC meeting notes
- 48-hour voting window after meeting
- Results published publicly

### Veto Rights

**Openwater reserves veto rights on decisions affecting:**
1. **Intellectual Property & Licensing**
   - License changes (e.g., moving away from Apache 2.0)
   - Patent policies
   - Trademark usage

2. **FDA Regulatory Strategy**
   - Approaches to FDA clearance
   - Safety and quality systems
   - Clinical trial designs

3. **Core Business Model**
   - Revenue model changes
   - Pricing structures
   - Commercial partnerships

4. **Security & Safety**
   - Critical security vulnerabilities
   - Safety-critical features
   - Incident response

**Veto process:**
- Must be exercised within 7 days of decision
- Must include written rationale
- Can be overridden by unanimous TSC vote (9 of 9)

---

## Request for Comments (RFC) Process

### When RFC is Required

**Major technical decisions need RFC:**
- Architectural changes affecting multiple projects
- Breaking API changes
- New product lines or major features
- Significant dependency updates
- Changes to development processes
- Security or safety-critical changes

**No RFC needed for:**
- Bug fixes
- Minor features in existing components
- Documentation improvements
- Routine maintenance

### RFC Workflow

**Step 1: Draft RFC**
- Create RFC document in `openwater-governance/rfcs/` repo
- Use template: `rfcs/RFC-TEMPLATE.md`
- Assign RFC number (next available)

**Step 2: Community Comment Period**
- Minimum 2 weeks for major changes
- Posted to GitHub Discussions
- Announced in community channels
- Open to all feedback

**Step 3: TSC Review**
- TSC discusses in monthly meeting
- May request revisions
- Seeks consensus or calls vote

**Step 4: Decision**
- **Accepted:** Move forward with implementation
- **Rejected:** Document reasons, archive RFC
- **Deferred:** Not ready yet, revisit later

**Step 5: Implementation**
- Assigned to working group or contributor
- Tracked as GitHub project
- Progress reported in TSC meetings

### RFC Template

See: `docs/rfc-template.md` (coming soon)

---

## Contribution Levels & Progression

### Level 1: Contributor

**Requirements:**
- Submit at least 1 merged pull request

**Rights:**
- Listed in CONTRIBUTORS.md
- Invited to community calls
- Can propose RFCs

### Level 2: Regular Contributor

**Requirements:**
- 5+ merged pull requests
- Active for 3+ months
- Constructive community participation

**Rights:**
- GitHub "triage" role (can label issues)
- Vote in contributor surveys
- Invited to contributor-only discussions

### Level 3: Core Contributor

**Requirements:**
- 25+ merged pull requests
- Active for 6+ months
- Significant feature development or major bug fixes
- Positive community reputation

**Rights:**
- GitHub "write" role (can merge own PRs after review)
- Can review others' PRs
- Eligible for committer nomination

### Level 4: Committer

**Requirements:**
- Core Contributor status
- Nomination by TSC member
- TSC approval (simple majority vote)
- Demonstrated technical leadership

**Rights:**
- GitHub "maintain" role (can merge others' PRs)
- Can approve RFCs
- Expected to review PRs regularly
- Invited to committer meetings

**Responsibilities:**
- Review PRs within 3 business days
- Maintain code quality standards
- Mentor new contributors
- Represent project professionally

### Level 5: TSC Member

**Requirements:**
- **Community-elected seats:** Elected by Regular Contributors
- **Academic seats:** Appointed by partner institutions
- **Openwater seats:** Appointed by Openwater leadership

**Rights:**
- Full voting rights on all decisions
- Can propose RFCs directly
- Access to confidential information (security, business)
- Can nominate committers

**Responsibilities:**
- Attend monthly TSC meetings
- Review and vote on major decisions
- Represent constituent interests
- Maintain conflict-of-interest disclosures

---

## Elections

### Community TSC Seats

**Eligibility:**
- Must be Core Contributor or higher
- Active within last 6 months
- Nominated by 3+ Regular Contributors

**Voting:**
- All Regular Contributors can vote
- Ranked-choice voting (Condorcet method)
- 2-week nomination period
- 2-week voting period

**Terms:**
- 12-month terms
- Staggered (one seat up for election every 4 months)
- Can serve multiple consecutive terms
- Can be recalled by 2/3 vote of Regular Contributors

**First Election:**
- Triggered when we reach 50+ Regular Contributors
- All 3 community seats elected simultaneously
- Initial terms: 4 months, 8 months, 12 months (for staggering)

---

## Working Groups & Special Interest Groups (SIGs)

### Purpose

Working Groups focus on specific areas of the project:
- **Technical Working Groups:** OpenLIFU, OpenMOTION, Cloud Services
- **Special Interest Groups:** Documentation, Community, Security, Regulatory

### Formation

**Any contributor can propose a WG:**
1. Submit proposal to TSC
2. Include: charter, scope, initial members
3. TSC reviews and approves

**Requirements:**
- At least 3 active members
- Clear scope and deliverables
- Regular meeting schedule
- Public meeting notes

### Working Group Governance

**Each WG has:**
- **Lead(s):** Appointed by TSC or elected by WG members
- **Charter:** Defines scope and goals
- **Regular meetings:** At least monthly
- **Reporting:** Updates to TSC quarterly

**WG Decision-Making:**
- Consensus-first within WG
- Major decisions escalate to TSC
- WG can approve minor changes independently

---

## Conflict Resolution

### Types of Conflicts

1. **Technical Disagreements** - Different approaches to implementation
2. **Process Conflicts** - Disputes about procedures or governance
3. **Code of Conduct Violations** - Behavioral issues
4. **Licensing/IP Disputes** - Intellectual property concerns

### Resolution Process

**Step 1: Direct Discussion**
- Parties attempt to resolve directly
- Document positions and concerns

**Step 2: Mediation**
- Involve neutral TSC member or committer
- Facilitate discussion
- Seek compromise

**Step 3: TSC Review**
- Escalate to full TSC
- Present both sides
- TSC makes binding decision

**Step 4: Appeal**
- Can appeal TSC decision to Openwater leadership
- Only for decisions significantly impacting mission/business
- Leadership decision is final

---

## Amendments

### Process for Changing Governance

**This document can be amended by:**
1. **2/3 TSC vote** (6 of 9 members)
2. **OR Community petition** signed by 50+ Regular Contributors
3. **Plus approval** from Openwater CEO (for changes affecting IP, licensing, or business model)

**Amendment Process:**
1. Propose amendment via RFC
2. 4-week community comment period
3. TSC vote
4. If approved, 2-week implementation period

**Emergency Amendments:**
- Can be fast-tracked for security or legal issues
- Requires unanimous TSC vote (9 of 9)
- Rationale must be documented

---

## Openwater's Role

### As Platform Steward

**Openwater (the company) serves as:**
- Legal entity holding trademarks and certain IP
- FDA regulatory sponsor
- Employer of core team members
- Provider of infrastructure (servers, CI/CD, etc.)
- Coordinator of business partnerships

### Separation of Concerns

**TSC controls:**
- Technical direction and architecture
- Code contributions and quality
- Community processes and culture
- Day-to-day technical decisions

**Openwater controls:**
- Business strategy and partnerships
- FDA regulatory submissions
- Fundraising and financial management
- Trademark and brand management
- Employment decisions

### Balancing Interests

**Openwater commits to:**
- Respecting TSC technical authority
- Transparent communication of business needs
- Good-faith collaboration with community
- Long-term sustainability of open-source platform

**Community commits to:**
- Understanding Openwater's business needs
- Respect for veto rights on critical matters
- Collaboration on sustainable business model
- Recognition of Openwater's investment

---

## Transparency & Accountability

### Public Information

**Always public:**
- TSC meeting notes and recordings
- RFC documents and decisions
- Contributor statistics and metrics
- Roadmap and release plans
- Governance documents

**May be confidential:**
- Security vulnerabilities (until patched)
- Unreleased business partnerships
- Personal information about contributors
- Legal matters under privilege

### Reporting

**TSC publishes:**
- Monthly activity reports
- Quarterly community health metrics
- Annual governance review
- Contributor statistics

---

## Getting Involved

### For Contributors

- Start by reading [CONTRIBUTING.md](CONTRIBUTING.md)
- Join community discussions
- Submit PRs and participate in reviews
- Progress through contribution levels

### For Organizations

- Partner as academic institution (TSC seat)
- Sponsor community programs
- Contribute engineering resources
- Join as research partner

### For Users

- Provide feedback via issues
- Participate in user research
- Share success stories
- Help others in community channels

---

## Resources

- **TSC Meeting Notes:** `docs/community/meetings/`
- **RFCs:** `openwater-governance` repository (coming soon)
- **Election Results:** `docs/community/elections/`
- **Working Groups:** `docs/community/working-groups/`

---

## Questions About Governance?

- Open an issue in this repository
- Attend a TSC meeting (schedule in meeting notes)
- Email: governance@openwater.health (in setup)

---

**This is a living document.** It will evolve as our community grows and we learn what works.

**Inspired by successful open-source governance models:**
- Linux Foundation Technical Charter
- CNCF Governance
- Apache Software Foundation
- Kubernetes Community Governance

---

**Status:** Draft v0.1  
**Approved by:** [Pending TSC formation]  
**Next Review:** January 2026  
**Feedback:** Open an issue or PR to suggest changes
```
