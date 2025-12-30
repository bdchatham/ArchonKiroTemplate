# Requirements Document: Archon Documentation Foundation Refinement

## Introduction

This specification defines requirements for refining the Archon documentation foundation to ensure optimal documentation generation and management for automated agents and system stakeholders. The goal is to align the steering file (`.kiro/steering/archon-docs.md`) and contract file (`CLAUDE.md`) with the archon-docs power's full capabilities while optimizing for RAG retrieval and stakeholder needs.

## Glossary

- **Archon_System**: The RAG (Retrieval-Augmented Generation) system that ingests documentation from `.kiro/docs/` to build mental models for sourcing code and architectural information
- **RAG_Agent**: An automated agent that retrieves and uses documentation from the Archon system
- **Documentation_Contract**: The `CLAUDE.md` file at repository root that defines authoritative documentation standards
- **Steering_File**: The `.kiro/steering/archon-docs.md` file that provides always-active guidance to Kiro
- **Retrieval_Chunk**: A section of documentation optimized for retrieval, typically 400-800 tokens with clear headings
- **Provenance**: Source references linking documentation to actual code and infrastructure files
- **Stakeholder**: Any person or system that consumes documentation (engineers, operators, RAG agents)
- **Core_Documentation_Files**: The 6 stable files (overview.md, architecture.md, operations.md, api.md, data-models.md, faq.md)

## Requirements

### Requirement 1: Documentation Stability Principle

**User Story:** As a RAG agent, I want documentation to maintain a stable structure, so that I can reliably retrieve information across repository updates.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL explicitly state that only 6 Core_Documentation_Files exist
2. THE Documentation_Contract SHALL prohibit creating additional documentation files for new features
3. THE Documentation_Contract SHALL specify that new features must be added as sections within existing Core_Documentation_Files
4. THE Steering_File SHALL enforce the 6-file limit during all documentation updates
5. WHEN a new feature is added, THE Steering_File SHALL guide placement into the appropriate existing file

### Requirement 2: Stakeholder-Focused Documentation

**User Story:** As a documentation maintainer, I want clear guidance on who uses the documentation and how, so that I can optimize content for all stakeholders.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL explicitly identify all Stakeholder types (engineers, operators, RAG agents)
2. THE Documentation_Contract SHALL describe how each Stakeholder type uses the documentation
3. THE Documentation_Contract SHALL include optimization guidance for RAG retrieval patterns
4. THE Documentation_Contract SHALL specify quality criteria for stakeholder-focused content
5. THE Steering_File SHALL remind Kiro to consider all Stakeholders when updating documentation

### Requirement 3: Retrieval Optimization Strategy

**User Story:** As a RAG agent, I want documentation structured for optimal retrieval, so that I can quickly find relevant information.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL explain that headings serve as retrieval keys
2. THE Documentation_Contract SHALL require descriptive, specific headings (not generic like "Details")
3. THE Documentation_Contract SHALL mandate consistent terminology across all Core_Documentation_Files
4. THE Documentation_Contract SHALL specify that related information must be grouped in single sections
5. THE Steering_File SHALL enforce heading quality and terminology consistency during updates

### Requirement 4: Documentation Refactoring Guidance

**User Story:** As a developer, I want clear guidance on when and how to refactor documentation, so that sections remain optimally sized for retrieval.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL specify the maximum section size (~1000 tokens)
2. THE Documentation_Contract SHALL provide refactoring triggers (when sections exceed limits)
3. THE Documentation_Contract SHALL include refactoring patterns (split into subsections, move to different file)
4. THE Steering_File SHALL detect oversized sections and prompt refactoring
5. THE Steering_File SHALL guide the refactoring process with specific steps

### Requirement 5: Documentation Audit Workflow

**User Story:** As a developer, I want a systematic audit process, so that I can ensure documentation accuracy and completeness.

#### Acceptance Criteria

1. THE Steering_File SHALL include a documentation audit workflow
2. THE audit workflow SHALL require understanding the system before making changes
3. THE audit workflow SHALL mandate identifying gaps, stale content, and oversized sections
4. THE audit workflow SHALL require proposing a plan before implementing changes
5. THE Steering_File SHALL enforce incremental, focused updates rather than large rewrites

### Requirement 6: Cross-File Consistency

**User Story:** As a RAG agent, I want consistent information across all documentation files, so that I don't receive conflicting information.

#### Acceptance Criteria

1. THE Steering_File SHALL require checking all affected Core_Documentation_Files when making updates
2. THE Steering_File SHALL mandate consistent terminology across all files
3. THE Steering_File SHALL require updating related sections in multiple files for feature changes
4. THE Steering_File SHALL provide a checklist of which files typically need updates for common changes
5. WHEN updating one file, THE Steering_File SHALL prompt checking related content in other files

### Requirement 7: Provenance and Grounding

**User Story:** As an engineer, I want documentation linked to actual code, so that I can verify accuracy and find implementation details.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL require "Source" subsections for all significant content
2. THE Documentation_Contract SHALL mandate specific file references (not vague descriptions)
3. THE Documentation_Contract SHALL prohibit documenting behavior without code evidence
4. THE Steering_File SHALL enforce provenance during all documentation updates
5. WHEN code is added or modified, THE Steering_File SHALL require updating Source references

### Requirement 8: Documentation Maintenance Philosophy

**User Story:** As a documentation maintainer, I want a clear philosophy for maintaining documentation, so that I make consistent decisions.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL include a "Documentation Maintenance Philosophy" section
2. THE philosophy SHALL prioritize updating existing sections over creating new files
3. THE philosophy SHALL emphasize incremental updates over large rewrites
4. THE philosophy SHALL mandate removing stale content rather than adding alongside it
5. THE Steering_File SHALL reinforce the philosophy during all documentation tasks

### Requirement 9: Quality Validation Criteria

**User Story:** As a developer, I want clear quality criteria, so that I can validate documentation before committing.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL include a validation checklist
2. THE checklist SHALL cover grounding (all statements have code references)
3. THE checklist SHALL cover structure (sections are 400-800 tokens, headings are descriptive)
4. THE checklist SHALL cover consistency (terminology matches across files)
5. THE checklist SHALL cover completeness (all Core_Documentation_Files are updated for changes)

### Requirement 10: Common Update Patterns

**User Story:** As a developer, I want examples of common update patterns, so that I can quickly apply the right approach.

#### Acceptance Criteria

1. THE Steering_File SHALL include common update patterns (new component, new endpoint, schema change)
2. WHEN adding a new component, THE pattern SHALL specify updating architecture.md, operations.md, and potentially api.md and data-models.md
3. WHEN adding a new endpoint, THE pattern SHALL specify updating api.md and potentially architecture.md
4. WHEN changing a schema, THE pattern SHALL specify updating data-models.md and potentially architecture.md
5. THE Steering_File SHALL provide a decision tree for determining which files need updates

### Requirement 11: Contract Authority and Precedence

**User Story:** As Kiro, I want clear precedence rules, so that I know which guidance to follow when conflicts arise.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL explicitly state it has final authority
2. THE Steering_File SHALL explicitly defer to Documentation_Contract in case of conflicts
3. THE Documentation_Contract SHALL reference the Steering_File as the enforcement mechanism
4. THE Steering_File SHALL reference the Documentation_Contract as the authoritative source
5. WHEN conflicts arise, THE Steering_File SHALL instruct reading Documentation_Contract first

### Requirement 12: Examples and Anti-Patterns

**User Story:** As a developer, I want concrete examples, so that I can understand what good documentation looks like.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL include examples of well-structured sections
2. THE Documentation_Contract SHALL include examples of poor structure (anti-patterns)
3. THE Documentation_Contract SHALL show good vs. bad heading examples
4. THE Documentation_Contract SHALL demonstrate proper provenance formatting
5. THE examples SHALL cover all Core_Documentation_Files

### Requirement 13: Code Quality Standards

**User Story:** As a developer, I want clear code quality standards, so that the codebase remains clean, maintainable, and self-documenting.

#### Acceptance Criteria

1. THE Documentation_Contract SHALL prohibit breadcrumb comments (e.g., "changed from x to y", "doing x because y failed")
2. THE Documentation_Contract SHALL require expressive method and variable names that convey intent
3. THE Documentation_Contract SHALL recommend methods be 10-30 lines long, preferably under 20 lines
4. THE Documentation_Contract SHALL encourage helper methods to improve clarity and reduce method length
5. THE Documentation_Contract SHALL specify that comments should be infrequent and only used when behavior cannot be inferred from code
6. THE Documentation_Contract SHALL allow comments for remote service behaviors or complex foundational components
7. THE Documentation_Contract SHALL reference Clean Code principles while emphasizing pragmatism over dogmatism
8. THE Steering_File SHALL enforce these code quality standards during all code changes
9. WHEN reviewing code, THE Steering_File SHALL flag breadcrumb comments for removal
10. WHEN methods exceed 30 lines, THE Steering_File SHALL suggest refactoring into helper methods

**Source**
- `.kiro/steering/archon-docs.md` (current version)
- `CLAUDE.md` (current version)
- archon-docs power documentation
- Clean Code principles (Robert C. Martin)
