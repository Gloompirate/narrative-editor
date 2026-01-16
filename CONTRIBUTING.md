# Contributing to Narrative Editor

Thank you for your interest in contributing! This document provides guidelines for contributing to the project.

## How to Contribute

### Reporting Bugs
1. Check if the bug has already been reported in [Issues](https://github.com/YOUR_USERNAME/narrative-editor/issues)
2. Create a new issue with:
   - Clear title
   - Steps to reproduce
   - Expected vs actual behavior
   - Browser and version
   - Sample JSON if applicable

### Suggesting Features
1. Check [existing feature requests](https://github.com/YOUR_USERNAME/narrative-editor/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement)
2. Create a new issue with:
   - Clear use case
   - Expected behavior
   - Mockups/examples if applicable

### Code Contributions

#### Getting Started
1. Fork the repository
2. Clone your fork: `git clone https://github.com/YOUR_USERNAME/narrative-editor.git`
3. Create a branch: `git checkout -b feature/amazing-feature`

#### Development Guidelines
- **Single File**: Keep everything in `narrative-editor.html`
- **Backward Compatibility**: Ensure existing JSON files still work
- **No Build Process**: Everything must work with just HTML/JS/CSS
- **Browser Support**: Test in Chrome, Firefox, Edge, Safari
- **Comments**: Add clear comments for complex logic
- **Testing**: Test with provided test files

#### Making Changes
1. Edit `narrative-editor.html`
2. Test thoroughly:
   - Load existing JSON files
   - Create new content
   - Test all view modes
   - Run validation
   - Test bulk operations
3. Document your changes
4. Commit: `git commit -m 'Add amazing feature'`
5. Push: `git push origin feature/amazing-feature`
6. Create Pull Request

#### Pull Request Guidelines
- Clear title describing the change
- Description of what changed and why
- Reference any related issues
- Include screenshots for UI changes
- Confirm browser testing was done

## Code Style

### JavaScript
- Use modern ES6+ syntax
- Prefer `const` over `let`
- Use arrow functions for callbacks
- Keep functions focused and small
- Add JSDoc comments for complex functions

### React
- Use functional components
- Use hooks (useState, useEffect, etc.)
- Keep components modular
- Avoid inline styles for repetitive styling
- Use meaningful variable names

### HTML/CSS
- Use semantic HTML
- Keep CSS organized by section
- Use CSS variables for colors/spacing
- Maintain consistent indentation (4 spaces)

## Testing

### Manual Testing Checklist
- [ ] Load sample JSON
- [ ] Create new content in each view
- [ ] Edit existing content
- [ ] Delete content
- [ ] Run validation
- [ ] Test search functionality
- [ ] Test bulk operations
- [ ] Test preview mode
- [ ] Test flag debugger
- [ ] Export JSON
- [ ] Test in multiple browsers

### Test Files
Use the provided test files:
- `test-validation-issues.json` - Contains intentional errors
- Test with your own complex narratives

## Documentation

When adding features:
- Update README.md if user-facing
- Update FEATURE-SUMMARY.md for comprehensive changes
- Add inline comments for complex code
- Update this CONTRIBUTING.md if process changes

## Questions?

- Open a [Discussion](https://github.com/YOUR_USERNAME/narrative-editor/discussions)
- Check existing [Issues](https://github.com/YOUR_USERNAME/narrative-editor/issues)
- Review [FEATURE-SUMMARY.md](FEATURE-SUMMARY.md) for detailed documentation

## Code of Conduct

- Be respectful and constructive
- Focus on the issue, not the person
- Accept constructive criticism
- Help create a welcoming environment

Thank you for contributing! 🎉
