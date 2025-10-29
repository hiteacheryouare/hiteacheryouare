# GitHub Copilot Instructions - Web Development Projects

## Project Context
These instructions apply to all JavaScript, TypeScript, and web development projects. We value pragmatic solutions over dogmatic conventions. No bikeshedding allowed.

## Language Rules

### JavaScript/TypeScript Guidelines
- TypeScript for complex logic and type-critical code
- JavaScript for simple, straightforward implementations
- JSX for simple React components without props
- TSX for complex React components with props/state

### File Structure (Adapt to framework)
```
/src or /app
  /components   # UI components
  /utils        # Helper functions and shared logic
  /lib          # External integrations
  /styles       # Global styles only
```

## Code Style Requirements

### Formatting Standards
- **Indentation**: TABS (not spaces)
- **Line endings**: Windows (CRLF) 
- **Quotes**: Single quotes only `'like this'`
- **Semicolons**: ALWAYS use semicolons;
- **Trailing commas**: Yes in multi-line objects/arrays
- **Equality**: Use `===` except when type coercion is explicitly needed

### Naming Conventions
- **Everything**: camelCase
  - Variables: `myVariable`
  - Functions: `myFunction`  
  - Constants: `myConstant` (NOT UPPER_SNAKE_CASE)
  - Files: `myComponent.jsx` or `helperFunction.ts`
  - CSS classes: Use framework conventions (Tailwind utilities)

### Function Declarations - CRITICAL RULE
```javascript
// ✅ CORRECT - Named anonymous arrow functions
const myFunction = () => {
	// function body
};

// ✅ CORRECT - Anonymous default export
export default () => {
	// component/function body
};

// ✅ CORRECT - Async arrow function
const fetchData = async () => {
	// async logic
};

// ❌ WRONG - Never use explicit function declaration
function myFunction() { } // NEVER DO THIS

// ❌ WRONG - Never name default exports  
export default function MyComponent() { } // NEVER DO THIS

// ⚠️ EXCEPTION - Only use var for single-use, no-hoisting-issue variables
var tempThing = 'used once'; // Rarely acceptable
```

## Framework-Agnostic Component Rules
- Maximum 200 lines per component/module
- Separate data from logic from presentation
- Helper functions go in separate utility files
- Mock data and constants in dedicated files
- Keep side effects minimal and isolated

## Styling Philosophy

### Preferred Styling Approach (in order)
1. **Bootstrap COMPONENTS** - For structural UI elements (modals, cards, etc.)
2. **Tailwind CSS** - For utility classes and custom styling
3. **CSS Modules or SCSS** - Only when framework requires it
4. **Never raw CSS** - Exception: Global resets or critical overrides

### What NOT to Use
- NO shadcn/ui
- NO headlessui  
- NO Material-UI, Ant Design, Chakra UI
- NO CSS-in-JS unless project already uses it
- NO styled-components unless project already uses it

### Dark Mode
Always include dark mode considerations using:
- Tailwind's `dark:` prefix
- CSS variables for theming
- System preference detection

## What Copilot Should NEVER Suggest

### Absolute Prohibitions
1. **NO testing libraries by default** - Only if project already has tests
2. **NO external UI libraries** beyond Bootstrap/Tailwind unless already in project
3. **NO explicit function declarations** - Always arrow functions
4. **NO unnecessary abstractions** - Keep it simple
5. **NO `var` keyword** except for truly single-use cases
6. **NO following conventions just because they're "best practices"**

### Anti-Patterns to Avoid
- Over-engineering simple solutions
- Premature optimization
- Excessive commenting on obvious code
- Deep nesting (flatten with early returns)
- Callback hell (use async/await)
- Global state unless absolutely necessary

## Comments Philosophy
- Only comment truly complex/unclear code
- No JSDoc unless project requires it
- No TODO comments that will never get done
- Comments should explain WHY, not WHAT

## Git Commit Style

### Commit Title
- Terse, general description
- Emoji if genuinely funny/relevant 
- No conventional commit format unless required

### Commit Message Body  
- Extremely detailed and verbose
- Reference everything relevant:
  - Contributors, bots, PRs, issues
  - Files changed and why
  - Related commits and context
  - Implementation decisions

## Async and Data Handling
- Prefer `async/await` over `.then()` chains
- Simple fetch over axios unless needed
- Handle errors pragmatically, not dogmatically
- No complex state management unless truly necessary

## Build and Deploy
- Keep build configs simple
- No over-optimization of bundle size
- Deploy via GitHub Actions when possible
- Environment variables for configuration

## Core Philosophy
- **Pragmatism > Dogma**: Solutions that work over "perfect" code
- **Simplicity > Complexity**: Avoid over-engineering
- **My conventions > Popular conventions**: These rules override "best practices"
- **No bikeshedding**: Spend time on real problems, not style debates
- **Working code > Clean code**: Make it work first, refactor if needed

## Framework-Specific Notes

### React/Next.js
- Functional components only
- Hooks over HOCs
- Server components where beneficial
- App router over pages router (Next.js 13+)

### Vue
- Composition API over Options API
- Script setup syntax preferred
- Single-file components

### Svelte/SvelteKit  
- Use built-in stores sparingly
- Leverage compiler optimizations
- Server-side rendering by default

### Node.js/Express
- Arrow functions for routes
- Middleware for cross-cutting concerns  
- Simple error handling, not elaborate

## Remember
When suggesting code:
1. Arrow functions ALWAYS
2. Bootstrap components + Tailwind utilities for styling
3. Keep modules under 200 lines
4. Avoid mainstream conventions that conflict with these rules
5. Pragmatic and working > theoretically perfect