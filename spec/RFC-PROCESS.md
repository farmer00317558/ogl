# RFC (Request for Comments) Process

This document describes the process for proposing and implementing major changes to the OpenGen Link Protocol.

---

## What is an RFC?

An RFC (Request for Comments) is a design document that proposes significant changes to the OGL specification. The RFC process ensures that:

- Changes are well-thought-out and documented
- The community has input on important decisions
- Breaking changes are carefully considered
- The specification remains coherent and maintainable

---

## When Do You Need an RFC?

### RFC Required

You **MUST** submit an RFC for:

- Adding new **required** parameters
- Changing the behavior of existing parameters
- Removing or deprecating parameters
- Adding support for new modalities (video, audio, 3D, etc.)
- Breaking backwards compatibility
- Major changes to the URL structure or encoding

### RFC Not Required

You can submit a regular PR for:

- Typo fixes and grammar improvements
- Clarifying existing documentation
- Adding examples
- Adding new **optional** parameters that don't affect existing behavior
- Minor specification clarifications

**If unsure**, open a GitHub Issue with the `question` label to ask.

---

## RFC Lifecycle

```
[Draft] → [Discussion] → [Consensus] → [Implementation] → [Accepted]
                ↓
            [Rejected]
```

### 1. Draft Phase

**Goal**: Articulate the problem and proposed solution.

1. **Copy the RFC template** from `.github/ISSUE_TEMPLATE/rfc.md`
2. **Open a GitHub Issue** titled `[RFC] Your Proposal Name`
3. **Fill out all sections** thoroughly:
   - Summary
   - Motivation
   - Proposed Solution
   - Examples
   - Backwards Compatibility
   - Alternatives Considered

### 2. Discussion Phase

**Goal**: Gather community feedback and refine the proposal.

- **Duration**: Minimum 1 week, longer for complex proposals
- **Activities**:
  - Community members comment and ask questions
  - Author addresses feedback and concerns
  - Author updates the RFC based on discussion
  - Tag relevant stakeholders (platform maintainers, SDK authors)

**Healthy Discussion Includes**:
- Questions about edge cases
- Suggestions for alternative approaches
- Concerns about backwards compatibility
- Real-world use case validation

### 3. Consensus Phase

**Goal**: Determine if the RFC should be accepted.

**Acceptance Criteria**:
- ✅ At least **2 approvals** from community members (not including author)
- ✅ No unresolved **major objections**
- ✅ All questions answered
- ✅ Minimum discussion period has passed

**Major Objections** include:
- Backwards compatibility concerns
- Security or privacy issues
- Conflicts with existing parameters
- Fundamental design flaws

Minor disagreements on implementation details do not block consensus.

### 4. Implementation Phase

**Goal**: Update the specification and documentation.

Once consensus is reached:

1. **Create a Pull Request** with:
   - Updated specification document (`spec/vX.X.X.md`)
   - Updated `CHANGELOG.md`
   - Added examples (if applicable)
   - Updated README (if applicable)

2. **Reference the RFC Issue** in the PR description

3. **Wait for review** and address any final feedback

### 5. Accepted or Rejected

- **Accepted**: PR is merged, RFC issue is closed with `accepted` label
- **Rejected**: RFC issue is closed with `rejected` label and explanation

---

## RFC Template Sections

### Summary

A one-paragraph overview. Should be understandable without reading the rest.

### Motivation

**Answer these questions**:
- What problem are we solving?
- Why is this important?
- What happens if we don't do this?

### Proposed Solution

**Include**:
- Exact specification text
- New parameter definitions (name, type, required/optional, description)
- Changes to existing parameters
- Examples

### Examples

**Show**:
- How a Source would generate the URL
- How a Target would parse and use the parameters
- Edge cases and error handling

### Backwards Compatibility

**Address**:
- Does this break existing implementations?
- How can implementations migrate?
- Can old and new versions coexist?

### Alternatives Considered

**Explain**:
- What other solutions were considered?
- Why was this approach chosen?
- What are the trade-offs?

---

## Decision Making

### Who Decides?

- The OGL community collectively makes decisions
- Maintainers facilitate the process but don't have veto power
- All voices are heard, but not all suggestions will be incorporated

### Resolving Disagreements

If consensus cannot be reached:

1. **Extend discussion period** - Allow more time for deliberation
2. **Seek compromise** - Can the proposal be modified to address concerns?
3. **Table the RFC** - Mark as `postponed`, may be revisited later
4. **Withdraw** - Author may withdraw the proposal

---

## Tips for Writing RFCs

### Do

- ✅ Start with a clear problem statement
- ✅ Provide concrete examples
- ✅ Consider edge cases
- ✅ Acknowledge trade-offs
- ✅ Be open to feedback
- ✅ Update the RFC as discussion evolves

### Don't

- ❌ Propose solutions without explaining the problem
- ❌ Ignore backwards compatibility
- ❌ Dismiss alternative approaches without explanation
- ❌ Assume your use case is universal
- ❌ Rush to implementation before consensus

---

## Example RFCs

### Good RFC Example

**Title**: `[RFC] Add support for ControlNet parameters`

**Summary**: "Proposes adding optional `controlnet`, `controlnet_model`, and `controlnet_weight` parameters to support ControlNet-based image generation workflows."

**Why it's good**:
- Clear, specific proposal
- Explains the motivation (many tools support ControlNet)
- Provides concrete examples
- Backwards compatible (optional parameters)

### Bad RFC Example

**Title**: `[RFC] Make things better`

**Summary**: "We should add more parameters."

**Why it's bad**:
- Vague and non-specific
- No clear problem statement
- No concrete proposal
- No examples

---

## FAQ

### How long does the RFC process take?

- **Minimum**: 1 week for discussion
- **Typical**: 2-4 weeks for major changes
- **Complex proposals**: May take longer

### Can I implement while the RFC is in discussion?

You can create a proof-of-concept implementation, but don't submit it as a PR until consensus is reached.

### What if my RFC is rejected?

- Rejection is not personal - it means the proposal isn't the right fit **right now**
- You can revise and resubmit
- You can implement it as a custom extension in your own project

### Can I modify an RFC after posting?

Yes! Edit the original issue to incorporate feedback. Mark major changes clearly.

---

## Version History

- **v1.0** (2025-12-05): Initial RFC process definition

---

## Questions?

Open an issue with the `question` label or ask in the discussions.

---

<p align="center">
  <strong>Thank you for helping make OGL better!</strong>
</p>
