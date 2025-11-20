# Contributing to Openwater Commons

Thank you for your interest in contributing to Openwater! We're building open-source medical devices to democratize healthcare innovation and bring advanced medical imaging to 3.5 billion underserved people.

---

## 🚧 Current Status

**We're in the middle of a major transition (November 2025):**

1. **License Migration:** Moving from AGPL-3.0 to Apache 2.0 (Week 3-4)
2. **Repository Restructure:** Organizing 137+ repos into clear product lines
3. **Community Infrastructure:** Setting up forums, chat, governance
4. **Documentation:** Building comprehensive docs at docs.openwater.health

**Full contribution guidelines will be available in December 2025.** For now, this document provides essential information for early contributors.

---

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Community](#community)
- [Recognition](#recognition)

---

## Code of Conduct

This project adheres to the Contributor Covenant [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to community@openwater.health (in setup).

---

## How Can I Contribute?

### 🐛 Reporting Bugs

**Before submitting a bug report:**
- Check existing issues to avoid duplicates
- Collect system information (OS, Python version, etc.)
- Create a minimal reproduction case

**Submit bugs via GitHub Issues** with:
- Clear, descriptive title
- Steps to reproduce
- Expected vs. actual behavior
- System environment details
- Screenshots if applicable

### 💡 Suggesting Features

**Before suggesting features:**
- Check if it's already proposed or in development
- Consider if it aligns with project goals
- Think about implementation complexity

**Submit feature requests via GitHub Issues** with:
- Problem statement (what pain point does this solve?)
- Proposed solution
- Alternative approaches considered
- Use cases and impact

### 📝 Improving Documentation

Documentation contributions are highly valued!

**Types of documentation:**
- API documentation and code comments
- Getting started guides and tutorials
- Architecture and design documents
- User guides and examples
- Translation to other languages

**Submit documentation improvements via Pull Requests.**

### 💻 Contributing Code

**Areas where we need help:**
- Core platform features (OpenLIFU, OpenMOTION)
- Hardware designs and firmware
- Cloud services and infrastructure
- Testing and quality assurance
- Integration with medical imaging platforms (3D Slicer, OHIF)

---

## Getting Started

### Prerequisites

**For Python Development:**
```bash
# Python 3.8+ required
python --version

# Clone the repository
git clone https://github.com/OpenwaterHealth/[repo-name].git
cd [repo-name]

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
pip install -r requirements-dev.txt  # Development dependencies
```

**For Hardware/Firmware:**
- See individual repository READMEs for specific toolchains
- Hardware designs typically use KiCad or similar tools
- Firmware often requires ARM toolchains

### Development Environment Setup

**Recommended Tools:**
- **IDE:** VSCode, PyCharm, or similar
- **Version Control:** Git (command line or GUI)
- **Documentation:** Markdown editor with preview
- **Testing:** pytest for Python projects

**Configuration:**
- Set up pre-commit hooks (coming soon)
- Configure linting and formatting tools
- Review repository-specific setup guides

---

## Development Workflow

### 1. Find or Create an Issue

**Browse existing issues:**
- Look for `good first issue` labels (coming soon)
- Check `help wanted` issues
- Review the roadmap for upcoming features

**Create new issues:**
- Describe the problem or feature clearly
- Get feedback before starting major work
- Discuss technical approach with maintainers

### 2. Fork and Branch
```bash
# Fork the repository on GitHub
# Then clone your fork
git clone https://github.com/YOUR-USERNAME/[repo-name].git
cd [repo-name]

# Add upstream remote
git remote add upstream https://github.com/OpenwaterHealth/[repo-name].git

# Create a feature branch
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### 3. Make Your Changes

**Follow these guidelines:**
- Write clear, self-documenting code
- Add comments for complex logic
- Follow existing code style
- Write or update tests
- Update documentation

**Commit message format:**
```
type: short description (50 chars or less)

Longer explanation if needed (wrap at 72 characters).

Fixes #123
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

### 4. Test Your Changes
```bash
# Run tests
pytest

# Run linting
flake8 .
black --check .

# Run type checking (if applicable)
mypy .
```

### 5. Submit a Pull Request
```bash
# Push to your fork
git push origin feature/your-feature-name

# Open a Pull Request on GitHub
```

**PR Guidelines:**
- Reference related issues
- Describe what changed and why
- Include screenshots for UI changes
- Ensure all checks pass
- Respond to review feedback promptly

### 6. Code Review Process

**What to expect:**
- Maintainers will review within 3-5 business days
- Constructive feedback for improvements
- Possible requests for changes
- Approval and merge when ready

**After merge:**
- Your contribution is recognized
- You're added to CONTRIBUTORS.md
- Feature appears in next release notes

---

## Style Guides

### Python Code Style

**Follow PEP 8 with these specifics:**
- Line length: 100 characters (not 79)
- Use Black for formatting
- Use type hints for function signatures
- Docstrings: Google style

**Example:**
```python
def process_ultrasound_data(
    data: np.ndarray,
    sampling_rate: float,
    filter_params: Optional[Dict[str, Any]] = None
) -> np.ndarray:
    """Process raw ultrasound data with optional filtering.
    
    Args:
        data: Raw ultrasound data array
        sampling_rate: Sampling rate in Hz
        filter_params: Optional filtering parameters
        
    Returns:
        Processed data array
        
    Raises:
        ValueError: If sampling_rate is invalid
    """
    ...
```

### Documentation Style

**Markdown guidelines:**
- Use ATX-style headers (`#`, `##`, not underlines)
- One sentence per line for easier diffing
- Include code examples with language tags
- Link to related documents

**Code comments:**
- Explain *why*, not *what*
- Update comments when code changes
- Use TODO/FIXME/NOTE appropriately

### Git Commit Messages

**Good commit messages:**
```
feat: add LIFU pulse sequence validation

Implements validation for pulse sequences to ensure safety parameters
are within FDA guidelines before transmission.

- Validates frequency ranges
- Checks intensity limits
- Verifies timing constraints

Fixes #456
```

**Bad commit messages:**
```
fixed stuff
update
asdfasdf
```

---

## Community

### Communication Channels

**Primary:**
- **GitHub Issues** - Bug reports, feature requests
- **GitHub Discussions** - Q&A, ideas, general discussion (launching soon)
- **Pull Requests** - Code review and technical discussion

**Coming Soon:**
- **Discord/Slack** - Real-time chat
- **Forum** - Long-form discussions (discourse.openwater.health)
- **Mailing List** - Announcements and important updates

### Community Calls

**Monthly community calls** (starting Q1 2026):
- Technical updates and roadmap
- Contributor spotlights
- Q&A with maintainers
- Open discussion

**TSC Meetings** (starting December 2025):
- Monthly, public, recorded
- Technical decisions and governance
- Meeting notes published in this repo

### Getting Help

**If you're stuck:**
1. Check existing documentation and issues
2. Search GitHub Discussions (when available)
3. Ask in community chat (when available)
4. Open an issue with your question

**Please be patient** - we're a growing community and may take a few days to respond.

---

## Contributor License Agreement (CLA)

**⚠️ CLA Coming in December 2025**

To contribute code, you'll need to sign our Contributor License Agreement. This:
- Grants Openwater permission to use your contributions
- Confirms you have rights to contribute the code
- Allows dual-licensing if needed for certain partnerships
- Protects both you and the project

**The CLA will be:**
- Simple and straightforward (based on Apache CLA)
- Signed electronically via GitHub
- One-time process (applies to all contributions)
- Required before your first PR can be merged

---

## Recognition

### Contributors Are Valued

**We recognize contributors through:**
- **CONTRIBUTORS.md** - Permanent record in the repository
- **Release Notes** - Called out in version announcements
- **Monthly Newsletter** - Contributor spotlights
- **Community Calls** - Showcasing significant contributions
- **Swag** - Openwater t-shirts and stickers (coming soon)
- **Certification** - Recognition through developer program (planned)

### Contribution Levels

**As you contribute more, you can progress:**

1. **Contributor** - Anyone who submits a PR
2. **Regular Contributor** - 5+ merged PRs, 3+ months active
3. **Core Contributor** - 25+ merged PRs, 6+ months active, significant features
4. **Committer** - Core contributor + TSC nomination, merge rights
5. **TSC Member** - Elected by community or appointed

Each level brings additional privileges and responsibilities.

---

## License

By contributing to Openwater Commons, you agree that your contributions will be licensed under the **Apache License 2.0**.

**Current license transition:**
- Moving from AGPL-3.0 to Apache 2.0 (Week 3-4)
- All new contributions will be Apache 2.0
- Existing code being relicensed with contributor consent
- [Read full rationale →](LICENSE-TRANSITION.md)

---

## Questions?

**This is a living document.** As our community grows and processes mature, this guide will evolve.

**For questions about contributing:**
- Open an issue in this repository
- Tag it with `question` label
- We'll respond within a few days

**For urgent matters:**
- Contact community@openwater.health (in setup)
- Reach out to project leadership directly

---

## Additional Resources

- **[Code of Conduct](CODE_OF_CONDUCT.md)** - Community standards
- **[Governance](GOVERNANCE.md)** - Decision-making and TSC
- **[License Transition](LICENSE-TRANSITION.md)** - Why Apache 2.0
- **[Architecture Docs](docs/architecture.md)** - Technical overview (coming soon)
- **[API Reference](docs/api-reference.md)** - Developer documentation (coming soon)

---

**Thank you for contributing to Openwater Commons!**

Together, we're building the infrastructure for a new healthcare economy that serves everyone, not just the wealthy few.

---

**Last Updated:** November 20, 2025  
**Next Review:** December 2025  
**Status:** Living Document - Will expand as community grows
