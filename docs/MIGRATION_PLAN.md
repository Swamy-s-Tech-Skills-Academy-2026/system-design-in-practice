# Content Migration Plan

**Date**: December 13, 2025  
**Source**: System Design Course Curriculum (45 sections)  
**Target**: System Design in Practice Repository

---

## Migration Strategy

This document outlines how to adapt and organize the course content into our repository structure. We will **not copy verbatim** but rather:

1. **Extract key concepts** and organize them logically
2. **Create our own content** inspired by the topics
3. **Maintain consistency** with our repository structure
4. **Add our own insights** and examples

---

## Content Mapping

### Section 1-3: Foundations & Interview Prep
**Target Location**: New sections in `src/`

- **Section 1**: Introduction → `src/introduction/`
- **Section 2**: System Design Interviews → `src/interview-prep/`
- **Section 3**: Preliminary Concepts → `src/foundations/`

### Section 4: Non-Functional Characteristics
**Target Location**: `src/principles/` (already exists)

- Availability → `src/principles/availability.md`
- Reliability → `src/principles/reliability.md`
- Scalability → `src/principles/scalability.md`
- Maintainability → `src/principles/maintainability.md` (new)
- Fault Tolerance → `src/principles/fault-tolerance.md` (new)

### Section 5: Back-of-the-Envelope Calculations
**Target Location**: `src/foundations/back-of-envelope.md` (new)

### Section 6-25: Building Blocks
**Target Location**: `src/building-blocks/` (expand existing)

**New files to create:**
- `dns.md` - Domain Name System
- `key-value-store.md` - Key-Value Store design
- `cdn.md` - Content Delivery Network
- `sequencer.md` - Unique ID generation
- `monitoring.md` - Distributed Monitoring
- `distributed-cache.md` - Distributed Cache (expand caching.md)
- `pub-sub.md` - Pub-Sub system
- `blob-store.md` - Blob/Object Storage (expand object-storage.md)
- `distributed-logging.md` - Distributed Logging
- `task-scheduler.md` - Distributed Task Scheduler
- `sharded-counters.md` - Sharded Counters

**Existing files to expand:**
- `load-balancers.md` - Already exists
- `databases.md` - Already exists
- `message-queues.md` - Already exists
- `search.md` - Already exists
- `object-storage.md` - Expand with blob store content

### Section 26-41: Case Studies
**Target Location**: `src/case-studies/` (expand significantly)

**New case studies to create:**
- `youtube/` - Video streaming platform
- `quora/` - Q&A platform
- `google-maps/` - Mapping and navigation
- `yelp/` - Proximity service
- `uber/` - Ride-sharing platform
- `twitter/` - Social media platform
- `newsfeed/` - Newsfeed system
- `instagram/` - Photo sharing platform
- `web-crawler/` - Web crawler design
- `whatsapp/` - Messaging platform
- `typeahead/` - Autocomplete system
- `google-docs/` - Collaborative editing
- `deployment/` - Code deployment system
- `payment/` - Payment system
- `chatgpt/` - LLM-based system

**Existing:**
- `url-shortener/` - Already exists

### Section 42: Spectacular Failures
**Target Location**: `src/failures/` (new directory)

- Real-world outage case studies
- Failure analysis and lessons learned

### Section 43-45: Additional Resources
**Target Location**: `src/references/` and `src/interview-prep/`

---

## Implementation Phases

### Phase 1: Foundation (Week 1-2)
- [ ] Create `src/introduction/` with course overview
- [ ] Create `src/interview-prep/` with interview strategies
- [ ] Create `src/foundations/` with preliminary concepts
- [ ] Expand `src/principles/` with maintainability and fault tolerance

### Phase 2: Building Blocks (Week 3-6)
- [ ] Expand existing building blocks files
- [ ] Create new building blocks (DNS, CDN, Sequencer, etc.)
- [ ] Add detailed design patterns for each

### Phase 3: Case Studies (Week 7-12)
- [ ] Start with URL Shortener (already scaffolded)
- [ ] Add high-priority case studies (YouTube, Twitter, Uber)
- [ ] Add remaining case studies incrementally

### Phase 4: Advanced Topics (Week 13-14)
- [ ] Add failures section
- [ ] Complete references
- [ ] Add diagrams and visualizations

---

## Content Creation Guidelines

1. **Original Content**: Write in our own words, don't copy-paste
2. **Structure**: Follow existing file structure (requirements, HLD, LLD, scalability, trade-offs)
3. **Examples**: Use our own examples and scenarios
4. **Diagrams**: Create original diagrams using Mermaid/PlantUML
5. **References**: Cite sources appropriately
6. **Practical Focus**: Emphasize real-world applications and trade-offs

---

## Notes

- This is a **migration plan**, not a verbatim copy
- Content will be adapted to our repository's style and structure
- We'll add our own insights, examples, and perspectives
- Focus on interview preparation and practical application

