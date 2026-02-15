# Contributing to Celstomp

Thank you for considering contributing! This guide walks you through the process.

## Ways to Contribute

### Code Contributions

- **Bug fixes** - Fix issues
- **Features** - Add new functionality
- **Refactoring** - Improve code quality
- **Performance** - Speed optimizations

### Non-Code Contributions

- **Documentation** - Improve docs
- **Tutorials** - Create guides
- **Bug reports** - Report issues
- **Feedback** - Share ideas

## Getting Started

### 1. Fork the Repository

1. Go to https://github.com/ginyoa/celstomp_v1
2. Click "Fork" button
3. Clone your fork:

```bash
git clone https://github.com/YOUR_USERNAME/celstomp_v1.git
cd celstomp_v1
```

### 2. Set Up Development Environment

```bash
# Install dependencies
npm install

# Start dev server
npm run dev
```

See [Building from Source](./building.md) for details.

### 3. Create a Branch

```bash
git checkout -b feature/my-feature-name
```

Branch naming:
- `feature/description` - New features
- `fix/description` - Bug fixes
- `docs/description` - Documentation
- `refactor/description` - Code refactoring

## Making Changes

### Development Workflow

1. **Make changes** in your branch
2. **Test thoroughly** in multiple browsers
3. **Check for console errors**
4. **Verify existing features** still work
5. **Update documentation** if needed

### Code Standards

Follow existing patterns:

- **2 spaces** for indentation
- **Semicolons** at end of statements
- **Single quotes** for strings
- **Meaningful names** for variables/functions
- **Comments** for complex logic

Example:

```javascript
// Good
function calculateDistance(x1, y1, x2, y2) {
  const dx = x2 - x1;
  const dy = y2 - y1;
  return Math.sqrt(dx * dx + dy * dy);
}

// Bad
function calc(a,b,c,d){return Math.sqrt((c-a)**2+(d-b)**2)}
```

### Testing Checklist

Before submitting:

- [ ] Works in Chrome
- [ ] Works in Firefox
- [ ] No console errors
- [ ] Keyboard shortcuts work
- [ ] Touch input works (if applicable)
- [ ] Save/load works
- [ ] Export works
- [ ] Undo/redo works

## Submitting Changes

### Commit Messages

Write clear, descriptive commits:

```
Add keyboard shortcut for frame navigation

- Press 'F' to jump to next keyframe
- Press 'Shift+F' for previous
- Works in all modes
- Added to help menu
```

Format:
- **Subject line:** Brief summary (50 chars max)
- **Blank line**
- **Body:** Detailed explanation (optional)

### Push to Your Fork

```bash
git add .
git commit -m "Your commit message"
git push origin feature/my-feature-name
```

### Create Pull Request

1. Go to your fork on GitHub
2. Click "Compare & pull request"
3. Fill out the PR template
4. Submit

### PR Template

```markdown
## Description
Brief description of what this PR does

## Changes Made
- List specific changes
- Be clear and concise

## Testing
- How you tested these changes
- Browser/OS combinations tested

## Screenshots (if applicable)
Add screenshots for UI changes

## Related Issues
Fixes #123 or References #456
```

## Code Review Process

### What to Expect

1. **Automated checks** run (if configured)
2. **Maintainer review** within a few days
3. **Feedback** may be requested
4. **Changes** might be needed
5. **Approval** and merge

### Responding to Feedback

- **Be open** to suggestions
- **Ask questions** if unclear
- **Make requested changes**
- **Update PR** with new commits

### After Merge

- Your contribution is now part of Celstomp!
- You'll be added to contributors list
- Changes will be in next release

## Reporting Bugs

### Before Reporting

1. **Check existing issues** - Avoid duplicates
2. **Update to latest version** - Bug might be fixed
3. **Try different browser** - Isolate the issue

### Bug Report Template

Use this format:

```markdown
## Bug Description
Clear description of what happens

## Steps to Reproduce
1. Go to '...'
2. Click on '...'
3. See error

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Environment
- OS: [e.g., Windows 11]
- Browser: [e.g., Chrome 120]
- Version: [e.g., commit hash]

## Screenshots
If applicable

## Console Errors
Paste any error messages
```

## Suggesting Features

### Feature Request Format

```markdown
## Feature Description
What you want to happen

## Problem Statement
What problem this solves

## Proposed Solution
How it should work

## Use Cases
When would this be useful

## Mockups
If applicable, show examples
```

## Documentation Contributions

### Improving Docs

Documentation lives in:
- `README.md` - Main project docs
- `CONTRIBUTING.md` - This file
- `SECURITY.md` - Security policy
- `CODE_OF_CONDUCT.md` - Community standards
- GitHub templates (`.github/`)

### Style Guide

- **Clear and concise** - Get to the point
- **Examples** - Show, don't just tell
- **Screenshots** - Visual aids help
- **Step-by-step** - Numbered lists for procedures

## Community Guidelines

### Code of Conduct

Follow our [Code of Conduct](../community/code-of-conduct.md):

- **Be respectful** - To all community members
- **Be constructive** - Criticize ideas, not people
- **Be inclusive** - Welcome newcomers
- **Be professional** - Keep it work-appropriate

### Communication

- **GitHub Issues** - Bug reports, features
- **Pull Requests** - Code discussions
- **Be patient** - Maintainers are volunteers
- **Be helpful** - Assist other contributors

## Development Tips

### Start Small

Good first contributions:
- Fix typos in documentation
- Add keyboard shortcuts
- Improve error messages
- Update comments
- Fix small UI issues

### Ask Questions

Not sure about something?

- Check existing issues
- Read the documentation
- Ask in pull request
- Open a discussion

### Learn the Codebase

Start here:
1. Read [Architecture](./architecture.md)
2. Explore [Project Structure](./project-structure.md)
3. Check [Code Organization](./code-organization.md)
4. Run the [Tutorial](../guides/tutorial.md)

## Recognition

### Contributors

All contributors are recognized in:
- README.md credits section
- Release notes
- Project history

### License

By contributing, you agree that your contributions will be licensed under the GPL v3 license.

## Getting Help

### Resources

- [Documentation](../introduction.md)
- [FAQ](../reference/faq.md)
- [Troubleshooting](../reference/troubleshooting.md)

### Contact

- Open an issue
- Comment on pull requests
- Check existing discussions

## Thank You!

Your contributions make Celstomp better for everyone. Whether it's code, documentation, bug reports, or feedback - every contribution matters.

Happy animating!

## See Also

- [Code of Conduct](../community/code-of-conduct.md) - Community standards
- [Security Policy](../community/security.md) - Reporting vulnerabilities
- [Building from Source](./building.md) - Development setup
