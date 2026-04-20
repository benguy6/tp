# Vansh Puri (benguy6) - Project Portfolio Page

**Project: UniTasker**

UniTasker is a desktop application used to keep track of tasks and courses.

## Summary of Contributions

**New Features**

- Added a comprehensive in-app help system
  - Justification: Users can view command formats and feature-specific guidance without leaving the application
  - Highlight: Implemented `CommandHelp` and `HelpCommand`, expanded the supported help topics, aligned help text with real command formats, and strengthened help-related validation and test coverage
- Added command usability improvements
  - Justification: Small command-quality improvements reduce friction for users during daily use
  - Highlight: Added command aliases and improved the help flow by supporting clearer command discovery and stricter handling of invalid help inputs
- Added the Course Tracker data model and persistence layer
  - Justification: Students need their course and assessment data to be represented cleanly in memory and saved reliably across sessions
  - Highlight: Implemented the `Assessment`, `Course`, `CourseList`, `CourseStorage`, and `CourseException` classes, including weighted grade calculation, assessment storage, and file-based save/load support

**Code Contributed**: [RepoSense Link](https://nus-cs2113-ay2526-s2.github.io/tp-dashboard/?search=benguy6&sort=groupTitle&sortWithin=title&timeframe=commit&mergegroup=&groupSelect=groupByRepos&breakdown=true&checkedFileTypes=docs~functional-code~test-code~other&since=2026-02-20T00%3A00%3A00&filteredFileName=&tabOpen=true&tabType=authorship&tabAuthor=benguy6&tabRepo=AY2526S2-CS2113-T14-3%2Ftp%5Bmaster%5D&authorshipIsMergeGroup=false&authorshipFileTypes=docs~functional-code~test-code~other&authorshipIsBinaryFileTypeChecked=false&authorshipIsIgnoredFilesChecked=false)

General contributions:
- Implemented the Course Tracker data-layer classes: `Assessment`, `Course`, `CourseList`, and `CourseStorage`
- Implemented `CourseException` for course-specific error handling
- Implemented `CommandHelp` and `HelpCommand` for the in-app help feature
- Added command aliases and improved command usability around help and command discovery
- Improved help robustness by aligning help text with actual command formats and adding stricter help validation
- Updated the course class diagram in `CourseClassDiagram.puml`

**Test Coverage Contributions**
- Added JUnit tests for `Assessment`, `Course`, and `CourseStorage`
- Added tests for the help system, including topic routing and parser-to-command behaviour

**Contributions to Team-Based Tasks**
- Owned the Course Tracker data layer while coordinating with the command-flow implementation done by my teammate
- Worked on keeping command help text, user documentation, and implemented command formats consistent across the project
- Supported final cleanup by improving validation and testing around the help feature

**Developer Guide Contributions**
- Added Course Tracker architecture and design overview, focusing on the model and storage structure
- Added the course class diagram and sequence diagram content
- Documented the design considerations for course persistence and grade calculation
- Detailed weighted score calculation algorithm with formula: (scoreObtained / maxScore) * weightage, with concrete examples showing Finals (40%, 85/100) contributes 34 points
- Documented file persistence format and sentinel value (-1.0) for ungraded assessments, enabling robust multi-course storage
- Explained validation layer architecture: CourseManager validates inputs, Assessment validates during recordScore(), two-tier defensive approach
- Justified design constants: MAX_WEIGHTAGE=100% (prevents impossible grading), MAX_ALLOWED_SCORE=10,000 (flexible scoring), NOT_GRADED=-1.0 (explicit ungraded state)
- Documented robustness features: graceful handling of missing/corrupted files, atomic file overwrites for crash resilience, defensive directory creation, malformed line skipping

**User Guide Contributions**
- Documented the Course Tracker commands in the User Guide with comprehensive examples
- Documented the help feature and command summary content, including all 8 command aliases (a, d, l, m, u, p, s, f)
- Updated documentation to reflect aliases and corrected command formats where needed
- Added Course Tracker examples section explaining weighted grade calculation: Finals (40%, 85/100) + Midterm (20%, 20/25) + Lab (15%, ungraded) = 83% current grade based only on graded work
- Documented weightage constraints with rejected configuration example: Finals (40%) + Midterm (60%) + Lab (15%) exceeds 100% limit
- Documented scoring constraints: max score range 0-10,000, scores must be non-negative and not exceed assessment maximum
- Explained course completion status checking and distinction between interim current grade vs. final grade when fully graded

**Review/Mentoring Contributions**
- Reviewed PRs and provided feedback
- Helped teammates with code quality and documentation alignment

**Contributions Beyond the Project Team**
- No major external contributions to report beyond the project repository at this stage
