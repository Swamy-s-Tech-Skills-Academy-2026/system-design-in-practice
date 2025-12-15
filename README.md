# System Design in Practice

This repository is a practical guide to system design, focusing on real-world architectural decisions, trade-offs, and scalability patterns.

## What This Repository Covers

- Core system design principles
- Common architectural patterns
- Building blocks of distributed systems
- End-to-end system design case studies
- Diagrams (C4, sequence, flow)
- Trade-offs and failure scenarios

## Who This Is For

- Software Engineers preparing for system design interviews
- Senior engineers transitioning to architect roles
- Engineers designing scalable systems in production

## Philosophy

Design is about **trade-offs**, not perfect solutions.

---

## Repository Structure

> **📋 Single Source of Truth**: The complete and up-to-date repository structure is maintained in [`docs/RepositoryStructure.md`](docs/RepositoryStructure.md). This file should be referenced for the authoritative structure.

For the complete repository structure with all file names and details, see: **[docs/RepositoryStructure.md](docs/RepositoryStructure.md)**

**Quick Overview**:
```text
system-design-in-practice/
│
├── README.md
├── docs/
│   ├── ROADMAP.md
│   ├── RepositoryStructure.md             # Single source of truth for structure
│   └── review-reports/
├── src/
│   ├── CONTENT_INDEX.md          # Complete content index
│   │
│   ├── 01_introduction/          # Getting started
│   │   ├── modern-system-design.md
│   │   ├── why-learn-system-design.md
│   │   └── course-structure.md
│   │
│   ├── 02_interview-prep/        # Interview preparation
│   │   ├── getting-ready.md
│   │   ├── dos-and-donts.md
│   │   ├── preparation-timeline.md
│   │   ├── mock-interviews.md
│   │   └── ai-evaluation.md
│   │
│   ├── 03_foundations/           # Foundational concepts
│   │   ├── abstractions.md
│   │   ├── network-abstractions.md
│   │   ├── consistency-models.md
│   │   ├── failure-models.md
│   │   └── back-of-envelope.md
│   │
│   ├── 04_principles/            # System design principles
│   │   ├── scalability.md
│   │   ├── reliability.md
│   │   ├── availability.md
│   │   ├── consistency.md
│   │   ├── security.md
│   │   ├── maintainability.md
│   │   └── fault-tolerance.md
│   │
│   ├── 05_building-blocks/       # Core building blocks
│   │   ├── dns.md
│   │   ├── load-balancers.md
│   │   ├── databases.md
│   │   ├── key-value-store.md
│   │   ├── cdn.md
│   │   ├── sequencer.md
│   │   ├── monitoring.md
│   │   ├── distributed-cache.md
│   │   ├── message-queues.md
│   │   ├── pub-sub.md
│   │   ├── object-storage.md
│   │   ├── search.md
│   │   ├── distributed-logging.md
│   │   ├── task-scheduler.md
│   │   └── sharded-counters.md
│   │
│   ├── 07_case-studies/          # End-to-end case studies
│   │   ├── url-shortener/
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
│   │   └── chatgpt/
│   │
│   ├── 06_patterns/              # Architectural patterns
│   │   ├── caching.md
│   │   ├── rate-limiting.md
│   │   ├── circuit-breaker.md
│   │   ├── cqrs.md
│   │   └── event-driven.md
│   │
│   ├── 08_failures/              # Real-world failure analysis
│   │   ├── introduction.md
│   │   ├── facebook-outage.md
│   │   ├── aws-kinesis-outage.md
│   │   ├── aws-outage.md
│   │   └── lessons-learned.md
│   │
│   └── references/               # Learning resources
│       ├── books.md
│       ├── papers.md
│       └── tools.md
│
├── docs/
│   └── ROADMAP.md                 # Learning path and roadmap
│
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
└── LICENSE
```

This structure is **interview-ready, blog-ready, and extensible**.

---

## Getting Started

1. Review the [ROADMAP.md](docs/ROADMAP.md) to understand the learning path
2. Check [src/CONTENT_INDEX.md](src/CONTENT_INDEX.md) for a complete topic index
3. Start with **src/01_introduction/** for an overview
4. Review **src/02_interview-prep/** if preparing for interviews
5. Study **src/03_foundations/** for fundamental concepts
6. Explore **src/04_principles/** for system design principles
7. Learn **src/05_building-blocks/** to understand core components
8. Study **src/07_case-studies/** for end-to-end system designs
9. Review **src/08_failures/** to learn from real-world incidents

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Attribution & Learning Sources

This repository represents a learning journey in system design. The content has been created through study and synthesis of knowledge from:

- **Books**: Various system design and distributed systems textbooks and reference materials
- **Video Courses**: Online courses and educational video content on system design
- **Web Resources**: Articles, documentation, and technical blogs from the software engineering community
- **Real-World Case Studies**: Analysis of publicly available system architectures and design patterns

**Note**: All content in this repository is original and transformative. While inspired by various learning sources, the explanations, examples, diagrams, and case studies are created from first principles to provide a unique learning experience.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
