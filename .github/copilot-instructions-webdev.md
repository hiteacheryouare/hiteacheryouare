Perfect — so you want a webdev-specific universal Copilot config, extending your global rules but tailored for JavaScript / TypeScript, frameworks, UI, and modern front-end workflow — basically your “one config to rule them all” for all web projects.

This version integrates your personal JavaScript style guide (arrow functions, camelCase, semicolons, no explicit declarations, etc.) while keeping your pragmatic + humorous tone and framework-agnostic flexibility (Astro, React, Svelte, Vue, vanilla, etc.).

Here’s the final version:

⸻

🦒 GitHub Copilot Instructions — Universal Web Development Edition

🌐 Project Context

You are working on web projects that value clarity, pragmatism, and simplicity over dogma.
We prefer things that are explicit, maintainable, and human-readable.
No over-engineering. No “industry-standard” fluff unless it genuinely helps.

We build websites and web apps that just work, look clean, and are fun to maintain.
Giraffes and hedgehogs approve. 🦒🦔

⸻

🧠 Core Philosophy
	1.	Clarity > cleverness.
	2.	Functionality > purity.
	3.	Consistency > convention.
	4.	Simplicity scales.
	5.	Code should have personality.

When in conflict, simplicity wins. Always.

⸻

🗂️ Project Structure (Recommended)

/src
  /components   # UI elements, pages, and layouts
  /utils        # Helpers, transformations, constants
  /assets       # Images, fonts, media
  /styles       # Global or shared .scss/.css

	•	Shallow folder depth — 2 or 3 levels max.
	•	Components and utilities go in their proper homes.
	•	Keep each file under ~200 lines if possible.
	•	Split large logic naturally; don’t invent abstractions for the sake of it.

⸻

💻 JavaScript / TypeScript Style Guide

Formatting
	•	Indentation: Tabs (no spaces).
	•	Line endings: CRLF.
	•	Quotes: Single 'like this'.
	•	Semicolons: Always.
	•	Line length: Use common sense — readable, not cramped.

Naming Conventions

Everything in camelCase:
	•	Variables → userData
	•	Functions → processLogin
	•	Constants → maxItems
	•	Files → userCard.jsx, authHelpers.ts
	•	Components → PascalCase for React/Svelte/Vue components

Function Declarations
	•	Always use arrow functions or anonymous exports.
	•	Never use function keyword for new code.
	•	Never name default exports.
	•	Keep functions short and self-contained.

Examples:

// ✅ Correct
const processData = (data) => {
	// logic
	return result;
};

export default () => {
	return <div>Example</div>;
};

// ❌ Wrong
function processData(data) { ... } // Never
export default function MyComponent() { ... } // Never

Variable Rules
	•	Use const by default.
	•	Use let when reassigning.
	•	Never use var unless forced by ancient code or specific scope quirks.
	•	No implicit globals — everything must be declared.

Data & Logic
	•	Put all constants, arrays, mock data, or repeated logic in /src/utils.
	•	Keep render or template files focused on structure, not computation.
	•	Avoid magic numbers or unexplained constants — name everything meaningfully.

⸻

⚛️ Component Philosophy

Applies to React, Svelte, Vue, Astro, or other component-based frameworks:
	•	Each component = one purpose.
	•	Break up large files (>200 lines) into smaller pieces.
	•	Move heavy logic to /utils and import.
	•	Keep markup readable — no nested ternaries or logic bombs.
	•	Avoid prop drilling where possible — use context or helpers instead.
	•	No “God components” that handle everything.

Example:

// ✅ GOOD
import { data } from '../utils/data';
import { formatData } from '../utils/formatData';

export default () => {
	return (
		<div>
			{formatData(data).map((item) => (
				<p key={item.id}>{item.text}</p>
			))}
		</div>
	);
};


⸻

💄 Styling Rules
	1.	Bootstrap for structure.
	•	Use it for modals, cards, navbars, layout grids, etc.
	2.	Tailwind for utilities.
	•	Use it for spacing, color, typography, and responsiveness.
	3.	NEVER raw CSS except for global overrides.
	4.	Use .scss files (not .sass).
	5.	Always support dark mode using Tailwind’s dark: utilities.
	6.	Avoid third-party UI kits (Material-UI, Chakra, Shadcn, etc.).

Example:

<div className="card">
	<div className="card-body p-4 dark:bg-gray-800">
		<h2 className="text-2xl font-bold dark:text-white">Title</h2>
	</div>
</div>


⸻

🧰 Libraries and Dependencies
	•	Use libraries intentionally, not reflexively.
	•	Native APIs > third-party packages where possible.
	•	Avoid “magic” libraries that hide complexity behind config.
	•	Every dependency should earn its place.

Avoid adding:
	•	UI frameworks beyond Bootstrap/Tailwind.
	•	Overcomplicated state management (use context/hooks/local state first).
	•	Unnecessary testing frameworks.

⸻

🧪 Testing & Debugging
	•	Manual testing is fine.
	•	Quick browser checks or console logs > heavy testing libraries.
	•	Use small, isolated debug utilities when needed.
	•	Don’t write tests for trivial functions — test meaningful behavior.

When something breaks:
	1.	Git revert to last working commit.
	2.	Simplify the approach.
	3.	Don’t over-engineer the fix.

⸻

⚙️ Error Handling
	•	Fail visibly, not silently.
	•	Log meaningful messages.
	•	Avoid complex “catch everything” frameworks.
	•	Keep error logic clear and direct.

Example:

try {
	await fetchData();
} catch (err) {
	console.error('Failed to fetch data:', err);
}


⸻

🗣️ Git Commit Style

Title
	•	Short and human.
	•	Funny or emoji welcome.
	•	No shouting or robotic phrasing.

Example:

🦔 Fixed mobile navbar not closing

Body
	•	Long, detailed, narrative-style explanation.
	•	Include why decisions were made, not just what changed.
	•	Mention related issues, PRs, or bots.
	•	List changed files if significant.

Example:

🦒 Fixed dropdown flicker on Safari

Turns out Safari was re-rendering the entire nav on state change.
Switched the toggle handler to use a ref-based approach instead of state.
Also added dark mode classes for dropdown text.

Files changed:
- /src/components/Navbar.jsx
- /src/utils/navHelpers.ts

Relates to PR #42, Issue #38


---
## 📦 Dependency & Environment Management

**Local-First, Project-Scoped Everything**
- Every project should have its own isolated dependency environment
- No global installations unless absolutely unavoidable
- Dependencies should live in the project directory where you can see and delete them
- Reproducibility > convenience

**Preferred Patterns:**
- ✅ npm with local node_modules
- ✅ uv for Python (project-scoped virtual environments)
- ✅ Local package installation that you can `rm -rf` when things break

**Rejected Patterns:**
- ❌ CDN imports (looking at you, `<script src="https://cdn..."`)
- ❌ URL-based package imports (Deno's import maps)
- ❌ Globally-scoped package managers (pip's default behavior)
- ❌ Forced remote coupling (Go's GitHub requirement)

**Why:**
- If your internet dies, your project should still work
- If a CDN goes down, your site shouldn't break
- If you delete a project folder, all traces should vanish with it
- Dependencies should be *tangible things you can inspect*, not abstract remote references

**Golden Rule:**
If I can't `cd` into it, `ls` it, and `rm -rf` it, I don't trust it.

⸻

🧭 Copilot Guidance

Copilot should:
	•	Write clear, simple, modern JS/TS.
	•	Use arrow functions, camelCase, and semicolons.
	•	Follow Bootstrap + Tailwind styling only.
	•	Suggest small, explicit functions instead of big abstractions.
	•	Prefer readability over brevity.
	•	Assume manual testing, not Jest or Cypress.

Copilot should NEVER:
	1.	Suggest function declarations (function foo() {}).
	2.	Use var.
	3.	Suggest UI frameworks other than Bootstrap/Tailwind.
	4.	Introduce unnecessary dependencies.
	5.	Use fancy build setups, decorators, or magic patterns.

⸻

🧭 When in Doubt
	1.	Use arrow functions.
	2.	Keep it simple.
	3.	Keep it modular.
	4.	Keep it readable.
	5.	Use Bootstrap for structure, Tailwind for detail.
	6.	Remember: 🦒 Giraffes and 🦔 hedgehogs are cool.

⸻

Would you like me to create a short “drop-in” version (like a 30-line copilot.config.md snippet you can paste at the top of any repo)? That version is great for embedding directly in project roots without the full doc.