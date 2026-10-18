# Repository guidance

- This static presentation site is independent of the Weatherpins Django application.
- Keep the Russian page (`/`) and English page (`/en/`) synchronized in structure and visual treatment.
- Keep dependencies minimal. Prefer HTML, CSS, and small amounts of vanilla JavaScript only when needed.
- Do not add or claim features that have not been confirmed in the application.
- Do not access or change production infrastructure, including Netlify, DNS, or the Django production application, without permission.
- Make changes on a separate Git branch; do not merge to `main` unless asked.
- Do not run the Django development server. Do not open or occupy ports 8000 or 8001.
- Check local links and assets, both language pages, responsive behavior with available tools, and `git diff --check` after changes.
- In completion notes, list changed files and checks performed.
