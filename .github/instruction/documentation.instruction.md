---
description: Documentation best practices and patterns
applyTo: '**/*'
---
# Documentation Rules

## Documentation Best Practices

- **Clarity Over Brevity:** Better to be clear than concise
- **Maintain Context:** Document the "why" more than the "what"
- **Update Proactively:** Update docs when code changes
- **Assume Fresh Eyes:** Write for someone unfamiliar with the code
- **Use Examples:** Show, don't just tell with code examples
- **Stay Current:** Remove outdated comments and documentation
- **Be Specific:** Avoid vague terms like "handles things" or "processes data"
- **Document Assumptions:** State implicit assumptions explicitly
- **Link Related Docs:** Reference related files, functions, or external resources
- **Test Documentation:** Verify that examples and instructions actually work
- **Use JSDoc:** Document all public functions, types, and classes with JSDoc
- **README Files:** Every app and package should have a README
- **Type Comments:** Add inline comments to complex types for clarity

---

## README Structure

Every app and package should have a README:

### README Template

```markdown
# App/Package Name

Brief one-sentence description.

## Overview

1-2 paragraphs explaining the purpose.



## Related Documentation

- [Related Doc 1](./path/to/doc)
- [Related Doc 2](./path/to/doc)
```
