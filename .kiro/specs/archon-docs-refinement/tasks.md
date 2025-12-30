# Implementation Plan: Archon Documentation Foundation Refinement

## Overview

This implementation plan refines the Archon documentation foundation by enhancing `CLAUDE.md` and `.kiro/steering/archon-docs.md` to align with the archon-docs power's full capabilities. The tasks are organized to build incrementally, starting with CLAUDE.md (the contract), then archon-docs.md (the enforcement), and finally validation.

## Tasks

- [x] 1. Enhance CLAUDE.md with Documentation Stability and Maintenance Philosophy
  - Add "Documentation Stability Principle" section after "Documentation Location"
  - Add "Documentation Maintenance Philosophy" section after "Required Documentation Files"
  - Explicitly state the 6-file limit and prohibition on new files
  - Specify where new features should be documented
  - Emphasize incremental updates over large rewrites
  - _Requirements: 1.1, 1.2, 1.3, 8.1, 8.2, 8.3, 8.4_

- [x] 2. Add Stakeholders and Retrieval Optimization to CLAUDE.md
  - Add "Stakeholders and Usage" section after "Documentation Maintenance Philosophy"
  - Identify three stakeholder types: engineers, operators, RAG agents
  - Describe how each stakeholder uses the documentation
  - Add "Retrieval Optimization Strategy" subsection under "Documentation Standards"
  - Explain headings as retrieval keys
  - Require descriptive, specific headings
  - Mandate consistent terminology across files
  - _Requirements: 2.1, 2.2, 2.3, 2.4, 3.1, 3.2, 3.3, 3.4_

- [x] 3. Add Documentation Refactoring and Quality Validation to CLAUDE.md
  - Add "Documentation Refactoring" subsection under "Documentation Standards"
  - Specify maximum section size (~1000 tokens)
  - Provide refactoring triggers and patterns
  - Add "Quality Validation Checklist" section before "Security"
  - Include checklist items for grounding, structure, consistency, completeness
  - _Requirements: 4.1, 4.2, 4.3, 9.1, 9.2, 9.3, 9.4, 9.5_

- [x] 4. Add Code Quality Standards to CLAUDE.md
  - Add "Code Quality Standards" section after "Quality Validation Checklist"
  - Add "Naming Conventions" subsection (expressive names)
  - Add "Method Sizing" subsection (10-30 lines, preferably <20)
  - Add "Commenting Guidelines" subsection (infrequent, purposeful)
  - Add "Clean Code Principles" subsection (pragmatic approach)
  - Prohibit breadcrumb comments explicitly
  - Encourage helper methods for clarity
  - Allow comments for remote services and complex components
  - _Requirements: 13.1, 13.2, 13.3, 13.4, 13.5, 13.6, 13.7_

- [x] 5. Add Examples and Anti-Patterns to CLAUDE.md
  - Add "Examples and Anti-Patterns" section before "Security"
  - Include well-structured section example
  - Include poorly-structured section anti-pattern
  - Show good vs. bad heading examples
  - Demonstrate proper provenance formatting
  - Provide examples covering all 6 core files
  - _Requirements: 12.1, 12.2, 12.3, 12.4, 12.5_

- [x] 6. Strengthen Contract Authority in CLAUDE.md
  - Update "Contract Authority" section
  - Explicitly state CLAUDE.md has final authority
  - Reference archon-docs.md as the enforcement mechanism
  - Clarify precedence rules for conflicts
  - _Requirements: 11.1, 11.3_

- [x] 7. Checkpoint - Review CLAUDE.md enhancements
  - Verify all new sections are present and complete
  - Verify examples are clear and helpful
  - Verify code quality standards are comprehensive
  - Ensure all requirements 1-13 are addressed in CLAUDE.md
  - Ask the user if questions arise

- [x] 8. Add Documentation Audit Workflow to archon-docs.md
  - Add "Documentation Audit Workflow" section after "Documentation Contract (CLAUDE.md)"
  - Include Step 1: Understand the system (scan code, infra, docs)
  - Include Step 2: Audit documentation (identify gaps, stale content, oversized sections)
  - Include Step 3: Plan before rewriting (propose bullet list of changes)
  - Include Step 4: Implement incrementally (small, focused updates)
  - _Requirements: 5.1, 5.2, 5.3, 5.4, 5.5_

- [x] 9. Add Cross-File Consistency Requirements to archon-docs.md
  - Add "Cross-File Consistency" section after "RAG-Friendly Documentation Rules"
  - Require checking all affected files when making updates
  - Mandate consistent terminology across all files
  - Require updating related sections in multiple files
  - Provide cross-file checking prompts
  - _Requirements: 6.1, 6.2, 6.3, 6.4, 6.5_

- [x] 10. Add Common Update Patterns to archon-docs.md
  - Add "Common Update Patterns" section after "Cross-File Consistency"
  - Add "New Component Pattern" subsection
    - Specify updating architecture.md, operations.md, potentially api.md and data-models.md
  - Add "New Endpoint Pattern" subsection
    - Specify updating api.md, potentially architecture.md
  - Add "Schema Change Pattern" subsection
    - Specify updating data-models.md, potentially architecture.md
  - Add "Decision Tree" subsection with flowchart for determining which files need updates
  - _Requirements: 10.1, 10.2, 10.3, 10.4, 10.5_

- [x] 11. Add Documentation Refactoring and Code Quality to archon-docs.md
  - Add "Documentation Refactoring" section after "Common Update Patterns"
  - Include detection of oversized sections (>1000 tokens)
  - Include prompting for refactoring with specific steps
  - Add "Code Quality Enforcement" section after "Documentation Refactoring"
  - Include flagging breadcrumb comments for removal
  - Include suggesting refactoring for methods exceeding 30 lines
  - Include enforcing expressive naming
  - Include reminding about minimal commenting
  - _Requirements: 4.4, 4.5, 13.8, 13.9, 13.10_

- [x] 12. Enhance Existing Sections in archon-docs.md
  - Update "Repository Structure" section
    - Add enforcement language for 6-file limit
    - Add guidance for feature placement
  - Update "RAG-Friendly Documentation Rules" section
    - Add subsection 6: "Heading quality and terminology"
    - Enforce descriptive headings
    - Enforce terminology consistency
  - Update "Workflow Integration" section
    - Add cross-file consistency checks to "When making code changes"
    - Add stakeholder consideration reminders
  - _Requirements: 1.4, 1.5, 2.5, 3.5, 7.4, 7.5, 8.5_

- [x] 13. Strengthen Steering Deference to Contract
  - Update "Documentation Contract (CLAUDE.md)" section
  - Explicitly state deference to CLAUDE.md in case of conflicts
  - Reference CLAUDE.md as the authoritative source
  - Instruct reading CLAUDE.md first when conflicts arise
  - _Requirements: 11.2, 11.4, 11.5_

- [x] 14. Checkpoint - Review archon-docs.md enhancements
  - Verify all new sections are present and complete
  - Verify audit workflow is clear and actionable
  - Verify common update patterns are comprehensive
  - Verify code quality enforcement is included
  - Ensure all requirements 1-13 are addressed in archon-docs.md
  - Ask the user if questions arise

- [x] 15. Validate cross-references between files
  - Verify CLAUDE.md references archon-docs.md correctly
  - Verify archon-docs.md references CLAUDE.md correctly
  - Verify deference hierarchy is clear
  - Verify no conflicting guidance exists
  - _Requirements: 11.1, 11.2, 11.3, 11.4, 11.5_

- [x] 16. Final validation and testing
  - Perform manual validation of CLAUDE.md completeness
  - Perform manual validation of archon-docs.md enforcement
  - Verify stakeholder coverage is complete
  - Verify example quality is high
  - Test end-to-end documentation update workflow
  - Verify all 13 requirements are fully implemented

## Notes

- Each task builds on previous tasks to ensure incremental progress
- Checkpoints ensure validation at key milestones
- All tasks reference specific requirements for traceability
- Focus is on enhancing existing files rather than creating new ones
- Implementation follows the design document structure closely
