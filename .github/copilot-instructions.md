# GitHub Copilot Instructions for System Design in Practice

**Version**: 2.0  
**Last Updated**: December 13, 2025  
**Repository**: `system-design-in-practice`

---

## 🎯 Repository Purpose

**System Design in Practice** is a comprehensive guide to system design, focusing on real-world architectural decisions, trade-offs, and scalability patterns.

### What This Repository Provides

- **System Design Principles**: Availability, reliability, scalability, consistency, fault tolerance, maintainability, security
- **Building Blocks**: DNS, load balancers, databases, caching, messaging, search, and more
- **Architectural Patterns**: Caching, rate limiting, circuit breaker, CQRS, event-driven
- **Case Studies**: End-to-end system designs (URL Shortener, YouTube, Twitter, Uber, WhatsApp, etc.)
- **Failure Analysis**: Real-world outage case studies and lessons learned
- **Interview Preparation**: Strategies, do's and don'ts, mock interviews

### Target Audience

- Software Engineers preparing for system design interviews
- Senior engineers transitioning to architect roles
- Engineers designing scalable systems in production
- Technical leads and architects

### Business Value

- Interview-ready preparation materials
- Practical system design knowledge
- Real-world case studies and patterns
- Scalable architecture guidance

---

## 📁 Repository Structure

```text
system-design-in-practice/
├── .github/
│   ├── workflows/                         # CI/CD workflows
│   ├── ISSUE_TEMPLATE/                    # Issue templates
│   ├── copilot-instructions.md            # THIS FILE
│   └── prompts/                           # Reusable prompt templates
├── docs/                                  # Documentation
│   ├── ROADMAP.md                         # Learning path and roadmap
│   └── WORKSPACE_REVIEW.md                # Workspace review report
├── src/                                   # Educational content
│   ├── CONTENT_INDEX.md                   # Complete content index
│   ├── 01_introduction/                   # Getting started
│   │   ├── 01_modern-system-design.md
│   │   ├── 02_why-learn-system-design.md
│   │   ├── 03_course-structure.md
│   │   └── README.md
│   ├── 02_interview-prep/                 # Interview preparation
│   │   ├── 01_getting-ready.md
│   │   ├── 02_dos-and-donts.md
│   │   ├── 03_preparation-timeline.md
│   │   ├── 04_mock-interviews.md
│   │   ├── 05_ai-evaluation.md
│   │   └── README.md
│   ├── 03_foundations/                    # Foundational concepts
│   │   ├── 01_abstractions.md
│   │   ├── 02_network-abstractions.md
│   │   ├── 03_consistency-models.md
│   │   ├── 04_failure-models.md
│   │   ├── 05_back-of-envelope.md
│   │   ├── 06_c4-diagrams.md
│   │   └── README.md
│   ├── 04_principles/                     # System design principles
│   │   ├── 01_availability.md
│   │   ├── 02_reliability.md
│   │   ├── 03_scalability.md
│   │   ├── 04_consistency.md
│   │   ├── 05_fault-tolerance.md
│   │   ├── 06_maintainability.md
│   │   └── 07_security.md
│   ├── 05_building-blocks/                # Core building blocks
│   │   ├── 01_dns.md
│   │   ├── 02_load-balancers.md
│   │   ├── 03_databases.md
│   │   ├── 04_key-value-store.md
│   │   ├── 05_cdn.md
│   │   ├── 06_sequencer.md
│   │   ├── 07_monitoring.md
│   │   ├── 08_distributed-cache.md
│   │   ├── 09_message-queues.md
│   │   ├── 10_pub-sub.md
│   │   ├── 11_object-storage.md
│   │   ├── 12_search.md
│   │   ├── 13_distributed-logging.md
│   │   ├── 14_task-scheduler.md
│   │   └── 15_sharded-counters.md
│   ├── 06_patterns/                       # Architectural patterns
│   │   ├── 01_caching.md
│   │   ├── 02_rate-limiting.md
│   │   ├── 03_circuit-breaker.md
│   │   ├── 04_cqrs.md
│   │   └── 05_event-driven.md
│   ├── 07_case-studies/                   # End-to-end case studies
│   │   ├── url-shortener/
│   │   │   ├── requirements.md
│   │   │   ├── high-level-design.md
│   │   │   ├── low-level-design.md
│   │   │   ├── scalability.md
│   │   │   ├── trade-offs.md
│   │   │   └── diagrams/                  # Case study specific diagrams
│   │   ├── youtube/
│   │   ├── twitter/
│   │   ├── instagram/
│   │   ├── uber/
│   │   ├── whatsapp/
│   │   ├── google-maps/
│   │   ├── yelp/
│   │   ├── quora/
│   │   ├── newsfeed/
│   │   ├── web-crawler/
│   │   ├── livestreaming/
│   │   ├── videoconferencing/
│   │   ├── typeahead/
│   │   ├── google-docs/
│   │   ├── deployment/
│   │   ├── payment/
│   │   ├── chatgpt/
│   │   └── README.md
│   ├── 08_failures/                       # Real-world failure analysis
│   │   ├── 01_introduction.md
│   │   ├── 02_facebook-outage.md
│   │   ├── 03_aws-kinesis-outage.md
│   │   ├── 04_aws-outage.md
│   │   ├── 05_lessons-learned.md
│   │   └── README.md
│   └── references/                        # Learning resources
│       ├── books.md
│       ├── papers.md
│       └── tools.md
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
└── lychee.toml                            # Link checker configuration
```

---

## 🔧 Development Guidelines

### When Working with System Design Content

1. **Follow Zero-Copy Policy**: All content must be transformative, not reformative
2. **Use Numbering**: Files must use `01_`, `02_`, etc. (never `00_`)
3. **Keep Modular**: Recommended ≤150 lines per file (split, don't trim)
4. **Create Original Diagrams**: Use Mermaid-first with ASCII fallback
5. **Case Study Structure**: Follow standard structure (requirements, HLD, LLD, scalability, trade-offs)

### When Creating Educational Content

#### File Naming
- ✅ Use zero-padded numeric prefixes: `01_`, `02_`, etc.
- ❌ **NEVER** use `00_` prefix - **NO EXCEPTIONS**
- ✅ Use hyphens for multi-word names: `01_modern-system-design.md`

#### Content Structure
- ✅ Recommended ≤150 lines per file
- ✅ Split into multiple parts if content exceeds 150 lines
- ✅ Never trim or condense content
- ✅ Each part should be self-contained

#### YAML Frontmatter (Recommended for content files)
```yaml
---
learning_level: "Beginner" | "Intermediate" | "Advanced"
prerequisites: ["required knowledge", "prior concepts"]
estimated_time: "25 minutes"
learning_objectives:
  - "Specific, measurable outcome 1"
  - "Specific, measurable outcome 2"
related_topics:
  prerequisites: []
  builds_upon: []
  enables: []
  cross_refs: []
---
```

### When Creating Case Studies

#### Standard Structure
Each case study should include:
- `requirements.md` - Functional and non-functional requirements
- `high-level-design.md` - System architecture and component interactions
- `low-level-design.md` - Detailed design of components
- `scalability.md` - Scaling strategies and considerations
- `trade-offs.md` - Design decisions and their trade-offs
- `diagrams/` - Case study specific diagrams
  - `context-diagram.md` - C4 Level 1: System context
  - `container-diagram.md` - C4 Level 2: Container architecture
  - `component-diagram.md` - C4 Level 3: Component details
  - `sequence-diagrams/` - Interaction flows and sequences

### Security Best Practices

- ❌ **NEVER** commit API keys or secrets
- ✅ **ALWAYS** use environment variables or secure configuration
- ✅ **ALWAYS** add sensitive files to `.gitignore`

---

## 📋 Code Quality Standards

### Markdown Files

- Use proper heading hierarchy (H1 → H2 → H3)
- Include code fence language specifications
- Follow markdownlint rules
- Use UTF-8 encoding
- Line length ~120 chars (tables/URLs may exceed)

### Diagrams

- **Mermaid-first**: Primary visualization method
- **ASCII fallback**: Include ASCII fallback for compatibility
- **Never embed copyrighted figures**: Create original diagrams
- **Co-locate with content**: Diagrams in case study `diagrams/` folders

---

## 🚀 Content Creation Workflow

### Transformative Workflow

1. **Source Intake**: Skim for intent and big ideas; don't copy notes verbatim
2. **Concept Map**: Create fresh outline with different sectioning
3. **Teach Differently**: Use new analogies, scenarios, datasets, use-cases
4. **Produce Original Artifacts**: Explanations, Mermaid diagrams, minimal examples
5. **Cross-Link**: Add references across sections
6. **Similarity Audit**: Ensure no sentences/structures resemble source
7. **Optional References**: Add "References/Inspired by" links (no copied phrasing)

### Quality Gate Questions

Before publishing any content:
1. ✅ Is this explanation clearer than the source material?
2. ✅ Does this fit naturally in the learning progression?
3. ✅ Would a learner understand this without the original source?
4. ✅ Are the examples relevant and practical?
5. ✅ Does this content add educational value beyond the reference?
6. ✅ Is this content within 150 lines for effective delivery?

---

## 📝 Local Quality Checks

Before committing changes:

### Markdown Linting
```bash
npx markdownlint-cli2 "**/*.md"
```

### Link Checking (Lychee via Docker)
```bash
docker run --rm -v "${PWD}:/input:ro" lycheeverse/lychee --config /input/lychee.toml "/input/**/*.md"
```

### Pre-Commit Checklist

- [ ] Run markdownlint and fix any issues
- [ ] Run Lychee link checker (if Docker available)
- [ ] Verify all file references point to existing files
- [ ] Check that code fences have language specifications
- [ ] Ensure proper blank lines around headings and lists
- [ ] Verify file naming (no `00_` prefixes)
- [ ] Check numbering consistency

---

## 🔗 Quick Links

- [Learning Path](docs/ROADMAP.md)
- [Content Index](src/CONTENT_INDEX.md)
- [System Design Principles](src/04_principles/)
- [Building Blocks](src/05_building-blocks/)
- [Case Studies](src/07_case-studies/)
- [Contributing](CONTRIBUTING.md)

---

## 📞 Support

- **Issues**: Use GitHub Issues for bug reports and feature requests
- **Discussions**: Use GitHub Discussions for questions and ideas
- **Contributing**: See [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines

---

## 🔄 Update Verification Protocol

**After ANY structural change, IMMEDIATELY update**:

1. ✅ `.github/copilot-instructions.md` - Repository Structure section (THIS FILE)
2. ✅ `README.md` - Repository Structure section
3. ✅ `.cursor/rules/02_repository-structure.mdc` - Repository structure
4. ✅ Relevant documentation files

**Self-Check Question**: "Did I update the instruction files?" - If no, STOP and do it NOW.
