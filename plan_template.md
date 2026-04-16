# CSS Icon Class Replacement — Executor Agent Task

## Objective
Replace icon CSS classes in the codebase using the provided icon inventory and mapping. Create a dedicated feature branch first, then perform a one-time replacement only within the approved root folders.

## Inputs
- `all-old-icons.txt`
  - Contains all known old icon CSS classes, one per line.
- `mapping.yaml`
  - Contains the mapping from old icon classes to new icon classes.
  - Each key is an old icon CSS class and each value is the corresponding new icon CSS class.
- `ROOT_FOLDERS`
  - Only search and modify files inside these folders:
    - MYIVYPROJECT/
    - ...
- `EXCLUDED_FOLDERS`
  - Do not search or modify files inside these folders:
    - target/
    - src_generated/
    - ANYOTHERFOLDER

## Execution Steps

### 1. Create a feature branch
Create a dedicated branch for this work before making any changes.

### 2. Search for old icon classes
Find all exact matches of the old icon classes listed in `all-old-icons.txt` within files under `ROOT_FOLDERS`.

Include relevant file types such as:
- source files
- templates
- styles
- markup
- generated files
- configuration files

Do not search or modify anything under `EXCLUDED_FOLDERS`.

### 3. Collect and group matches
Group all matches by file and record every occurrence of each old icon class.

### 4. Resolve replacements
For each found old icon class:
- check whether a replacement exists in `mapping.yaml`
- if a mapping exists, record the old → new replacement pair
- if no mapping exists, record that no replacement is available

### 5. Replace mapped icon classes
Replace each old icon class with its mapped new icon class where a mapping exists.

Preserve:
- surrounding formatting
- whitespace
- other class names in the same string or attribute

Do not alter unrelated or similar strings.

### 6. Report findings
Provide a report covering all found old icon classes, including:
- file location
- old icon class
- whether a mapping was found
- whether a replacement was applied
- whether no mapping exists

### 7. Verify the result
Re-scan the workspace to confirm:
- all mapped old icon classes have been removed
- the new icon classes appear in the expected locations
- no files under `EXCLUDED_FOLDERS` were changed

## Acceptance Criteria
- All old icon classes with a mapping are replaced.
- Any old icon classes without a mapping are reported but left unchanged.
- No files under `EXCLUDED_FOLDERS` are modified.
- The final report clearly lists all matches and actions taken.
