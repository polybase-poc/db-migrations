# AI Code Review Bot: Carson

## Butler Bot Profile

**Name:** Carson
**Team:** data-platform
**Persona:** Precise, data-integrity focused, cautious with changes. Focus: Schema design (normalization, indexes), migration safety, backwards compatibility, query performance

## What the Bot Reviews

The Carson bot automatically reviews all pull requests using Claude API (Sonnet 4.5).

### Review Focus

Based on the database stack, the bot checks for:

Precise, data-integrity focused, cautious with changes. Focus: Schema design (normalization, indexes), migration safety, backwards compatibility, query performance

### When Reviews Run

- ✅ PR opened, updated, or reopened
- ✅ PR is not in draft mode
- ✅ PR has fewer than 500 lines changed
- ❌ Skipped for draft PRs
- ❌ Skipped for very large PRs (>500 lines)

## How to Interact with Bot Comments

1. **Address issues**: Fix code based on feedback and push updates
2. **Explain decisions**: Reply to bot comment with rationale
3. **Request re-review**: Bot automatically re-reviews on new commits
4. **Mark resolved**: Once addressed, mark conversation as resolved

## Large PR Reviews

For PRs >500 lines, the bot won't automatically review (cost control).

To get AI review on large PRs:
- Break into smaller PRs if possible
- Use local Claude Code: `/doc-check` or spawn review agent
- Request manual review from team members

## Cost Considerations

- Cost per review: ~$0.014
- Monthly budget: $20-50
- Supports 1,400-3,500 reviews/month across all repos

If you notice the bot not reviewing, check:
1. Is PR >500 lines?
2. Is PR in draft mode?
3. Is CLAUDE_API_KEY configured in repository secrets?

## Manual Review Alternative

```bash
# Local review with Claude Code
claude-code review --pr <number>

# Or spawn review agent
claude-code agent doc-analyzer --pr <number>
```
