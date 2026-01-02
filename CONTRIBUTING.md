# Contributing to Career Optimization Resources

**Version:** 1.0  
**Last Updated:** January 2, 2026
**Status:** Production Ready

Thank you for your interest in contributing to this repository! This document provides guidelines for making updates and maintaining quality.

---

## 📋 Table of Contents

- [Getting Started](#getting-started)
- [Repository Structure](#repository-structure)
- [Style Guide](#style-guide)
- [How to Contribute](#how-to-contribute)
- [Quality Standards](#quality-standards)
- [Commit Guidelines](#commit-guidelines)
- [Documentation Updates](#documentation-updates)
- [Testing Changes](#testing-changes)
- [Review Process](#review-process)

---

## Getting Started

### Prerequisites

- Git installed
- Markdown editor (VS Code, Typora, or any text editor)
- Basic understanding of markdown syntax
- Familiarity with the repository structure

### Clone the Repository

```bash
git clone <repository-url>
cd <repository-name>
```

### Set Up Pre-Commit Hooks

Pre-commit hooks are already installed in `.git/hooks/pre-commit` and will run automatically.

**Test the hook:**
```bash
.git/hooks/pre-commit
```

---

## Repository Structure

```
/workspace/
├── Braintrust-Profile/          Platform-specific content
├── Career-Planning/             Strategic planning documents
├── Certifications/              Certification roadmaps
├── Contractor-Hiring-SOW/       Hiring documentation (9 files)
├── Contractor-Hiring-Support/   Hiring support materials
├── Financial-Planning/          Financial tracking templates
├── Income-Opportunities/        Research and opportunity guides
├── Platform-Profiles/           Content for 15 platforms
├── Platform-Research/           Contractor research
├── Platform-Setup-Guides/       Setup instructions
├── Resume/                      Resume files (MD + PDF)
├── Templates/                   Reusable templates
├── Tracking-Tools/              Progress tracking dashboards
├── .github/workflows/           GitHub Actions (CI/CD)
├── .git/hooks/                  Pre-commit hooks
└── *.md                         Root-level documentation
```

**Key Files:**
- `README.md` - Repository overview and entry point
- `PROJECT_SUMMARY_AND_INDEX.md` - Master index of all documents
- `CHANGELOG.md` - Version history and changes
- `CONTRIBUTING.md` - This file

---

## Style Guide

### Markdown Formatting

**Headers:**
```markdown
# H1 - Document Title (one per file)
## H2 - Major Section
### H3 - Subsection
#### H4 - Minor Point
```

**File Naming:**
- Use `Title_Case_With_Underscores.md` for files
- Use `Title-Case-With-Hyphens/` for folders
- Be descriptive: `Freelance_Financial_Tracker.md` not `tracker.md`

**Document Structure:**
Every markdown file should have:

```markdown
# Document Title

**Version:** 1.0  
**Last Updated:** January 2, 2026
**Status:** Production Ready

**Purpose:** Brief description of document purpose  
**Use For:** When/how to use this document  
**Related Documents:** Links to related files

---

## Section 1

Content here...

---

**Related Documents:**
- [Link to related doc](path/to/doc.md)

**Questions?** Contact information or reference
```

**Formatting Standards:**

✅ **DO:**
- Use **bold** for emphasis on key terms
- Use `code blocks` for file names, commands, code
- Use > blockquotes for important callouts
- Use tables for comparison data
- Use ✅ ⚠️ ❌ emojis sparingly for status indicators
- Include examples where helpful
- Add "Last Updated" date at top of file

❌ **DON'T:**
- Use ALL CAPS for headers (use sentence case)
- Overuse emojis (max 2-3 per section)
- Use overly technical jargon without explanation
- Leave placeholder text like `[Your name]` uncommented
- Create files without H1 headers

**Links:**
- Use relative links: `[Link Text](../folder/file.md)`
- External links: `[Link Text](https://example.com)`
- Don't use absolute paths: ❌ `/workspace/file.md`

**Code Blocks:**
````markdown
```bash
# Example command
git commit -m "Your message"
```
````

**Tables:**
```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data     | Data     | Data     |
```

**Lists:**
```markdown
- Unordered list item
- Another item
  - Nested item (2 spaces)

1. Ordered list item
2. Another item
   a. Sub-item (3 spaces)
```

---

## How to Contribute

### 1. Create a New Branch

```bash
# Create and switch to new branch
git checkout -b feature/your-feature-name

# Or for bug fixes
git checkout -b fix/your-fix-name
```

**Branch Naming:**
- `feature/` - New content or templates
- `fix/` - Bug fixes or corrections
- `docs/` - Documentation improvements
- `refactor/` - Reorganization or restructuring

### 2. Make Your Changes

- Edit files using markdown editor
- Follow the style guide above
- Test markdown rendering (preview in VS Code or GitHub)
- Add examples where helpful

### 3. Update CHANGELOG.md

Add your changes to `CHANGELOG.md` under the `[Unreleased]` section:

```markdown
## [Unreleased]

### Added
- New document: `Templates/Your_New_Template.md`
- Added section to `README.md` about XYZ

### Changed
- Updated `CHANGELOG.md` format
- Improved `Financial_Tracker.md` examples

### Fixed
- Corrected typo in `Resume.md`
- Fixed broken link in `README.md`
```

### 4. Stage and Commit

```bash
# Stage your changes
git add .

# Commit (pre-commit hook will run automatically)
git commit -m "Add new template for XYZ"

# If pre-commit hook updates dates, review and commit again if needed
git add .
git commit -m "Add new template for XYZ (with updated dates)"
```

### 5. Push and Create Pull Request

```bash
# Push to remote
git push origin feature/your-feature-name

# Create pull request on GitHub
# Or use: gh pr create --title "Your PR Title" --body "Description"
```

---

## Quality Standards

### Checklist for New Documents

Before submitting a new document, ensure:

- [ ] File has proper H1 header
- [ ] Version number, Last Updated date, Status included
- [ ] Purpose statement at top
- [ ] Related documents linked at bottom
- [ ] Examples provided where appropriate
- [ ] No placeholder text left uncommented (e.g., `[Your name]`)
- [ ] Consistent formatting (follow style guide)
- [ ] Spell-checked and proofread
- [ ] Links tested (internal and external)
- [ ] Added to `PROJECT_SUMMARY_AND_INDEX.md`
- [ ] Added to `CHANGELOG.md`

### Checklist for Updates to Existing Documents

- [ ] "Last Updated" date updated (auto-updated by pre-commit hook)
- [ ] Version number updated if major changes
- [ ] Changes documented in `CHANGELOG.md`
- [ ] Existing formatting style maintained
- [ ] Cross-references updated if file moved/renamed
- [ ] No broken links introduced

---

## Commit Guidelines

### Commit Message Format

```
<type>: <subject>

<body (optional)>

<footer (optional)>
```

**Types:**
- `feat:` - New feature or document
- `fix:` - Bug fix or correction
- `docs:` - Documentation changes
- `style:` - Formatting changes (no content change)
- `refactor:` - Reorganization or restructuring
- `chore:` - Maintenance tasks (updating dates, etc.)

**Examples:**

```
feat: Add financial projection template

Added comprehensive financial projection template with 3 scenarios
(conservative, realistic, optimistic). Includes Excel formulas and
examples.

Closes #42
```

```
fix: Correct broken links in README

Updated 3 broken links in README.md that were pointing to old file locations
after recent folder restructuring.
```

```
docs: Improve LinkedIn optimization guide

- Added visual guidelines for headshot and banner
- Included step-by-step Canva instructions
- Added 5 banner content examples
```

### Commit Best Practices

✅ **DO:**
- Write clear, descriptive commit messages
- Make atomic commits (one logical change per commit)
- Reference issues/PRs if applicable (#123)
- Keep commits focused

❌ **DON'T:**
- Write vague messages ("update files", "fix stuff")
- Commit work-in-progress without noting it
- Mix unrelated changes in one commit
- Commit sensitive information (hook will block)

---

## Documentation Updates

### Adding a New Template

1. Create file in `/Templates/` folder
2. Follow template structure:
   ```markdown
   # Template Name
   
   **Version:** 1.0  
   **Last Updated:** January 2, 2026
   **Status:** Production Ready
   
   **Purpose:** What this template is for
   **Use For:** When to use it
   
   ## Template Content...
   ```

3. Add version number and metadata
4. Include fill-in-the-blank sections
5. Provide examples
6. Add to `PROJECT_SUMMARY_AND_INDEX.md`
7. Update `CHANGELOG.md`

### Adding a New Guide

1. Create file in appropriate folder
2. Follow documentation structure (see Style Guide)
3. Include table of contents if >500 lines
4. Cross-reference related documents
5. Add actionable checklist or next steps
6. Add to navigation (`README.md`, `PROJECT_SUMMARY_AND_INDEX.md`)
7. Update `CHANGELOG.md`

### Updating Existing Documents

1. Open file and make changes
2. Update "Last Updated" date (or let pre-commit hook do it)
3. If major changes, increment version number
4. Document changes in `CHANGELOG.md`
5. Test all links
6. Commit with descriptive message

---

## Testing Changes

### Manual Testing

Before committing:

1. **Preview Markdown Rendering**
   - Use VS Code markdown preview (Ctrl+Shift+V)
   - Or push to GitHub and view rendered version
   - Check tables, lists, code blocks render correctly

2. **Test Internal Links**
   ```bash
   # Use markdown-link-check (if installed)
   markdown-link-check your-file.md
   ```

3. **Spell Check**
   - Use VS Code spell checker extension
   - Or run through Grammarly
   - Or use built-in spell check

4. **Validate Markdown**
   ```bash
   # Use markdownlint (if installed)
   markdownlint your-file.md
   ```

### Automated Testing (GitHub Actions)

When you push to GitHub, automated checks run:

- **Markdown Linting** (`.github/workflows/markdown-lint.yml`)
  - Checks formatting consistency
  - Validates markdown syntax
  - Fails if formatting issues found

- **Link Checking** (`.github/workflows/link-check.yml`)
  - Tests all internal and external links
  - Runs on push and weekly schedule
  - Creates issue if broken links found

**View Results:**
- Go to GitHub Actions tab
- Check workflow run status
- Fix any errors before merging

---

## Review Process

### Self-Review Checklist

Before requesting review:

- [ ] Changes tested locally
- [ ] Markdown renders correctly
- [ ] No broken links
- [ ] Spell-checked
- [ ] Style guide followed
- [ ] `CHANGELOG.md` updated
- [ ] Commit message is clear
- [ ] No sensitive information included

### Pull Request Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] New document/template
- [ ] Update to existing document
- [ ] Bug fix (typo, broken link, etc.)
- [ ] Refactoring (reorganization)
- [ ] Documentation improvement

## Checklist
- [ ] Follows style guide
- [ ] CHANGELOG.md updated
- [ ] No broken links
- [ ] Tested markdown rendering
- [ ] Self-reviewed changes

## Related Issues
Closes #[issue number]

## Screenshots (if applicable)
[Add screenshots of rendered markdown if visual changes]
```

### Review Criteria

Reviewers will check:

1. **Content Quality**
   - Accurate information
   - Clear writing
   - Helpful examples
   - Actionable advice

2. **Formatting**
   - Follows style guide
   - Consistent with existing docs
   - Proper markdown syntax
   - Tables/lists formatted correctly

3. **Completeness**
   - All sections present
   - No placeholder text left
   - Links working
   - CHANGELOG updated

4. **Value**
   - Adds value to repository
   - Doesn't duplicate existing content
   - Useful for target audience

---

## Questions?

**For questions about:**
- **Style Guide:** Review this document and existing files
- **Technical Issues:** Check `.git/hooks/README.md` for hook troubleshooting
- **GitHub Actions:** Review workflow files in `.github/workflows/`
- **General Questions:** Create an issue on GitHub

---

## Thank You! 🎉

Your contributions help make this repository better for everyone. Every improvement, no matter how small, is appreciated!

**Happy Contributing!** 💪

---

**Related Documents:**
- [README.md](README.md) - Repository overview
- [CHANGELOG.md](CHANGELOG.md) - Version history
- [PROJECT_SUMMARY_AND_INDEX.md](PROJECT_SUMMARY_AND_INDEX.md) - Master index
- [.git/hooks/README.md](.git/hooks/README.md) - Pre-commit hook documentation

---

**Version:** 1.0  
**Last Updated:** January 2, 2026
**Maintained By:** Repository Owner  
**License:** [Specify license if applicable]
