# GitHub Copilot Instructions - Universal

## Core Philosophy
These instructions apply to ALL projects regardless of language or framework. Pragmatism over dogma. Working solutions over theoretical perfection. No bikeshedding.

## Universal Principles

### Code Quality Metrics (In Order of Importance)
1. **Does it work?** - Functionality first
2. **Is it maintainable?** - Can someone else understand it?
3. **Is it efficient enough?** - Don't over-optimize
4. **Is it simple?** - Avoid unnecessary complexity

### What I Value
- **Clarity over cleverness** - Readable code beats "smart" code
- **Explicit over implicit** - Be clear about intent
- **Flat over nested** - Early returns, guard clauses
- **Practical over perfect** - Ship working code
- **My conventions over popular ones** - Follow these rules, not trends

## Naming Conventions

### General Rules (Language-Specific Variations)
- **Default to camelCase** for most languages
- **Descriptive but not verbose** - `userId` not `u` or `userIdentificationNumber`
- **Consistency within project** - Match existing patterns
- **No Hungarian notation** - Types should be obvious or inferred
- **Avoid abbreviations** except common ones (ctx, config, req, res)

### Language-Specific
```python
# Python: snake_case
def my_function():
    my_variable = "value"

// JavaScript/TypeScript/Java/C#: camelCase
const myFunction = () => {
    const myVariable = "value";
}

// Go: Follow Go conventions but keep it simple
func myFunction() {
    myVariable := "value"
}

-- SQL: snake_case for tables/columns
SELECT user_id FROM user_accounts;
```

## Comments and Documentation

### When to Comment
- **Complex algorithms** - Explain the WHY
- **Business logic** - Context for decisions
- **Workarounds** - Why we're doing something weird
- **External integrations** - API quirks or limitations

### When NOT to Comment
- **Obvious code** - `// increment counter` is useless
- **Every function** - Only if genuinely complex
- **TODOs that won't happen** - Delete or do them
- **Commented-out code** - Use version control instead

### Documentation
- README should explain HOW TO RUN IT
- Setup instructions must actually work
- API documentation only for public APIs
- No extensive docs for internal/private code

## Error Handling Philosophy

### Pragmatic Approach
1. **Fail fast** - Catch errors early
2. **Fail clearly** - Useful error messages
3. **Recover when sensible** - Don't try to handle everything
4. **Log appropriately** - Enough to debug, not spam

### What NOT to Do
- Don't catch and ignore errors silently
- Don't over-engineer error handling
- Don't create custom error types unnecessarily
- Don't wrap everything in try-catch

## Testing Approach

### My Testing Philosophy
- **Manual testing first** - Make sure it actually works
- **Automated tests only when valuable** - Not for coverage metrics
- **Integration > Unit tests** - Test real behavior
- **No TDD zealotry** - Write tests when they help

### If Tests Exist in Project
- Follow existing patterns
- Don't reduce coverage
- Fix broken tests, don't skip them
- Keep tests simple and readable

## Git Commit Style

### Universal Commit Format
```
Brief description (emoji if genuinely adds value)

Detailed explanation that covers:
- What changed and why
- Implementation decisions
- References to issues/PRs/collaborators
- Any gotchas or important notes
- Related changes in other files

Don't worry about line length in messages.
Be verbose here, not in the title.
```

### What to Avoid
- Conventional commits (unless required)
- Single-word commits like "fix" or "update"
- Essay-length titles
- Empty message bodies for complex changes

## Performance and Optimization

### Pragmatic Performance
1. **Make it work first** - Correctness before speed
2. **Profile before optimizing** - Don't guess
3. **Optimize the hot path** - Focus on what matters
4. **Good enough is good enough** - 100ms vs 50ms rarely matters

### Anti-Patterns
- Premature optimization
- Micro-optimizations that hurt readability
- Caching everything "just in case"
- Complex abstractions for "future flexibility"

## Dependency Management

### Adding Dependencies
- **Evaluate necessity** - Can we do it simply without?
- **Check maintenance** - Is it actively maintained?
- **Consider size** - Especially for frontend
- **Prefer boring** - Battle-tested over cutting-edge

### What to Avoid
- Adding dependencies for trivial functionality
- Multiple libraries doing the same thing
- Deprecated or abandoned packages
- Bleeding-edge alpha/beta versions in production

## Code Organization

### Universal Structure Principles
- **Separation of concerns** - But don't over-separate
- **Logical grouping** - Related things together
- **Flat when possible** - Deep nesting is confusing
- **Consistent patterns** - Same problem, same solution

### What NOT to Do
- Over-architect simple projects
- Create abstractions for single-use cases
- Deeply nested folder structures
- Separate every tiny concern

## What Copilot Should NEVER Do

### Universal Prohibitions
1. **Don't suggest "best practices" that add complexity without value**
2. **Don't follow conventions just because they're popular**
3. **Don't suggest testing libraries/frameworks unless already in use**
4. **Don't over-engineer simple solutions**
5. **Don't add unnecessary abstractions or patterns**
6. **Don't prioritize "clean code" over working code**
7. **NO magic** - codemods and random naming conventions that do crazy things just because they are named a certain way should be avoided at all costs. all things should be explicit and easy to understand.

### Philosophy Violations to Avoid
- Dogmatic adherence to SOLID, DRY, etc.
- Design patterns for the sake of patterns
- Excessive OOP or FP purism
- Architecture astronautics
- Bikeshedding over minor details

## Language-Specific Notes

### Web (JS/TS/CSS)
- Arrow functions preferred
- Tailwind/Bootstrap for styling
- Simple solutions over frameworks

### Python
- List comprehensions when readable
- Type hints for public APIs
- `if __name__ == "__main__":`

### Java/C#
- Avoid enterprise fizzbuzz
- Minimize boilerplate
- Pragmatic OOP, not dogmatic

### Go
- Embrace simplicity
- Error handling without panic
- Interfaces when needed, not always

### SQL
- Readable queries over clever ones
- CTEs for complex queries
- Indexes on foreign keys

## Final Reminders

### When Writing Code
1. **Will this work?**
2. **Can someone else understand this?**
3. **Am I over-complicating?**
4. **Am I following conventions just because?**
5. **Is this pragmatic?**

### Core Mantra
**"Make it work, make it right (enough), ship it"**

We're building software that solves problems, not writing poetry. Pragmatism beats perfectionism. My conventions beat popular conventions. Simple beats complex. Working beats theoretical.

No bikeshedding. Ever.