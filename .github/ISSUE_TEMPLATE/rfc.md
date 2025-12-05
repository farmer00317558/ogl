---
name: RFC (Request for Comments)
about: Propose a major change to the OpenGen Link Protocol
title: '[RFC] '
labels: 'rfc, proposal'
assignees: ''
---

## Summary

Brief one-paragraph summary of the proposal.

---

## Motivation

Why is this change needed? What problem does it solve?

- What use case does this address?
- Who will benefit from this change?
- What happens if we don't implement this?

---

## Proposed Solution

### New Parameters

List any new parameters being proposed:

| Parameter | Type | Required | Description | Example |
|-----------|------|----------|-------------|---------|
| `param_name` | string | Yes/No | What it does | `example_value` |

### Changes to Existing Parameters

If modifying existing parameters, describe the changes:

- **Parameter name**: What's changing and why

### Specification Changes

Provide the exact specification text to be added or modified.

```markdown
### `param_name`

- **Type**: `string`
- **Required**: No
- **Description**: Detailed description...
- **Example**: `param_name=value`
```

---

## Examples

Show concrete usage examples:

### Source (Prompt Library)

```html
<a href="https://tool.com/?ogl_ver=1.0&prompt=example&new_param=value">
  Generate
</a>
```

### Target (Generation Tool)

```javascript
const params = new URLSearchParams(window.location.search);
const newParam = params.get('new_param');
// ... implementation
```

---

## Backwards Compatibility

- [ ] This change is fully backwards compatible
- [ ] This change affects existing implementations in the following ways: ___

**Impact Assessment:**

How will existing implementations be affected?

---

## Alternatives Considered

What other approaches did you consider?

1. **Alternative 1**: Description, pros/cons
2. **Alternative 2**: Description, pros/cons

Why was the proposed solution chosen over alternatives?

---

## Open Questions

List any unresolved questions or areas needing discussion:

- Question 1?
- Question 2?

---

## Implementation Plan

- [ ] Update specification document
- [ ] Add examples to documentation
- [ ] Update SDK (if applicable)
- [ ] Update CHANGELOG.md

---

## Stakeholders

Tag any relevant community members or projects:

- @username1
- @username2

---

## Additional Context

Any other information, screenshots, diagrams, or references.
