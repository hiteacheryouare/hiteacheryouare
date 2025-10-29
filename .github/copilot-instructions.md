Perfect — so you want a universal copilot-instructions.md that codifies your personal engineering philosophy across all projects, regardless of language or framework.

I’ll base it on your original Astro-specific file but abstract it to a language-agnostic, framework-neutral guide — keeping your humor, personality, and pragmatic discipline intact.

Here’s the complete, ready-to-use version:

⸻

🦒 GitHub Copilot Instructions (Universal)

Project Context

You are assisting in projects that value pragmatic solutions over dogmatic conventions.
We prioritize clarity, maintainability, and sanity over “best practices” for their own sake.

No bikeshedding.
No unnecessary abstraction.
Giraffes and hedgehogs are welcome. 🦒🦔

⸻

🔧 Core Philosophy
	1.	Working code beats perfect code.
	2.	Readability is everything.
	3.	Explicit > implicit.
	4.	Simplicity scales; cleverness breaks.
	5.	Personality belongs in code.

If mainstream conventions conflict with these principles, ignore them.

⸻

🗂️ Project Structure
	•	Keep folder structures logical and minimal.
	•	Separate core logic, utilities, and presentation (whatever those mean for the language).
	•	Avoid deep nesting. Two or three levels is enough.
	•	Use clear, human-readable filenames in camelCase.
	•	myFunction.js, dataHelpers.py, userRoutes.go

When a file grows over ~200 lines or a function feels “dense,” split it up. Don’t force abstractions—split naturally.

⸻

🧠 Code Style Rules (Language-Agnostic)

General Formatting
	•	Indentation: Tabs (never spaces).
	•	Line endings: CRLF.
	•	Quotes: Single quotes 'like this' if the language allows.
	•	Semicolons: Always, if the language uses them.
	•	Line length: No strict max; use judgment.

Naming

Everything in camelCase:
	•	Variables → userData
	•	Functions → fetchUserData
	•	Constants → apiUrl
	•	Files → userRoutes.js
	•	No screaming snake case. Ever.

⸻

🧩 Function & Class Conventions
	•	Prefer arrow functions or lambdas when possible.
	•	Avoid traditional function or overly verbose class syntax unless the language requires it.
	•	Keep functions short, clear, and purpose-driven.
	•	Name functions descriptively — no cryptic abbreviations.
	•	Default exports or public entry points should be anonymous unless naming improves clarity.

Golden Rule:

If someone can’t tell what your function does by reading it once, rewrite it.

⸻

💬 Comments
	•	Only comment complex or non-obvious logic.
	•	No “what this line does” fluff.
	•	No JSDoc-style boilerplate unless it adds real value.
	•	Explain why, not what.
	•	Humor and personality are encouraged when genuine.

Example:

// Yes, I know this loop looks cursed. It’s faster and I hate it too.


⸻

💄 Styling (Cross-Language)
	•	Use a utility-first mindset.
	•	Never hardcode colors, spacing, or typography if your stack supports tokens or utility classes.
	•	Avoid raw CSS or inline styles unless you have to.
	•	Use preprocessor or system-level styling (scss, design tokens, etc.) only when necessary.
	•	Always include dark mode or theme variants if applicable.

⸻

🧰 Dependencies
	•	Keep external libraries to a minimum.
	•	Don’t add dependencies to solve trivial problems.
	•	Avoid trendy, overabstracted tools that obscure intent.
	•	Native solutions > third-party when possible.

Rule of thumb:

Every new dependency must earn its keep.

⸻

🧪 Testing & Debugging
	•	Manual testing is fine.
	•	Automated testing is great if it’s lightweight and adds real value.
	•	Prefer small, focused scripts or quick REPL tests over bloated test suites.
	•	Don’t mock the world just to test a function.

When something breaks:
	1.	Revert to last working version.
	2.	Try a simpler approach.
	3.	Don’t over-engineer the fix.

⸻

⚙️ Error Handling
	•	Handle errors visibly, not silently.
	•	Fail fast, log meaningfully, move on.
	•	No layers of abstract error frameworks unless required.
	•	Keep recovery logic simple and human-readable.

⸻

🗣️ Commit Style

Title
	•	Short, clear, maybe funny.
	•	Emoji allowed and encouraged if it adds personality. 🦒🦔

Example:

🦔 Fix weird navbar thing again

Body
	•	Write as if telling the story of what changed.
	•	Explain why decisions were made.
	•	Include related issues, PRs, or files changed.
	•	It’s okay to overexplain. Future-you will thank you.

Example:

🦒 Adjusted login redirect

Found that the redirect logic was running before the session token initialized. 
Moved the check to after the auth middleware executes. 
Also noticed the “remember me” checkbox wasn’t persisting across sessions—fixed that too.

Files changed:
- /src/routes/login.js
- /src/utils/authHelpers.js

Related: PR #24, Issue #19


⸻

🧭 Copilot Guidance

Copilot should:
	•	Prioritize clarity and simplicity over cleverness.
	•	Suggest modular, readable code with clear variable names.
	•	Avoid introducing unnecessary abstractions or dependencies.
	•	Use arrow functions, camelCase, and consistent formatting.
	•	Keep code visually neat and easy to reason about.

Copilot should NEVER:
	1.	Suggest testing libraries by default.
	2.	Add UI frameworks or dependencies without context.
	3.	Write cryptic, magic-heavy code.
	4.	Follow mainstream style guides just because they’re “standard.”
	5.	Overabstract — clarity beats cleverness.

⸻

🧭 When in Doubt
	1.	Keep it explicit.
	2.	Keep it simple.
	3.	Keep it small.
	4.	Keep it readable.
	5.	And remember: Giraffes and hedgehogs are cool. 🦒🦔

⸻

Would you like me to make a “compact” version next (like one you could paste as a header block comment inside any project’s main file, summarizing your style in <50 lines)?
That’s often useful for when you don’t want a full Markdown doc but want your rules baked into a repo’s DNA.