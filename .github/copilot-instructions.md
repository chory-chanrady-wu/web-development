<!--
Guidance for AI coding assistants working in this repository.
Keep this file concise and focused on codebase-specific patterns and examples.
--> 

# Copilot instructions — Quality Shop static website

Purpose: give AI coding agents just-the-facts they need to be productive editing this small static site.

Key facts
- Project type: simple static website (HTML + inline CSS). No build system, package manager, or server-side code present.
- Primary files in root: `login.html`, `footer.html`. Treat other .html files in the root as single-file pages.

What to change
- Small visual changes, content updates, and accessibility improvements are allowed in-place.
- Avoid introducing new build tooling, frameworks, or dependencies unless explicitly requested.

Patterns and conventions
- Pages are standalone HTML documents. Keep edits self-contained (update only the target .html and inline <style> when making CSS tweaks).
- Reuse class names found in `footer.html` (for example: `.footer`, `.footer-logo`, `.all-item`, `.footer-item`, `.contact`) when adding similarly structured footer-like components on other pages.
- Minimal JS: none exists in the repo. If adding JS, keep it small and inline or add a new `.js` file in the root and reference it from the page. Note: ask the user before adding new scripts that change behavior.

Accessibility and assets
- Prefer semantic HTML (for example: use <footer> as in `footer.html`, use <form> and proper labels for `login.html` when implementing login fields).
- When adding images, prefer relative assets if the user supplies them; otherwise external CDN links are acceptable (the footer currently uses external icon URLs).

Examples to follow
- Update footer styles by editing `footer.html` inline <style>. Example class names: `.footer`, `.footer-logo`, `.all-item`, `.footer-item`, `.contact`.
- Implement login content inside `login.html`; add a `<form>` with `method="post"` and accessible `<label>`s. Keep form action blank or use a placeholder comment and ask the user where to submit.

Testing and verification
- Manual verification: open the changed .html files in a browser. There is no automated test harness.
- When adding JS or CSS, minimize scope to avoid breaking other pages (changes are global only if applied to shared files).

When in doubt
- Ask the user before: adding build tools, creating backend endpoints, introducing frameworks, or moving files into new directories.

Contact points
- Refer explicitly to `login.html` and `footer.html` for concrete examples and class names.

End of file
