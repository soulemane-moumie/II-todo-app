# Copilot Instructions

## Project conventions

- This project uses Next.js App Router, React, strict TypeScript, Zustand, Tailwind CSS, and Bun. Follow the existing patterns and avoid introducing dependencies without a clear need.
- Keep route and UI code in `app/`. Reuse the separation between components, todo types (`app/lib/types/`), pure todo logic (`app/lib/logic/`), and Zustand state (`app/lib/store/`).
- Keep todo transformations immutable and in the logic layer where practical; keep components focused on rendering and user interaction. Use the existing `Todo` type and store/provider rather than duplicating their state or definitions.
- Follow the existing TypeScript and JSX formatting, import aliases (`@/`), and Tailwind utility-class conventions.
- Preserve accessible, usable interactions when changing the UI, including clear labels and appropriate native controls.

## Build and tests

- Run commands from this project directory.
- Run `bun test` for the logic and store tests; add or update tests under `tests/` for behavior changes.
- Run `bun run lint` and `bun run build` for relevant changes. Use `bun run dev` to start the development server when needed.
- Do not claim a check passed unless you ran it; report checks that could not be run.

## Code review

- Review the complete diff in context and report only actionable defects introduced by the change. Do not treat style preferences or speculative concerns as findings.
- Prioritize incorrect todo behavior or state updates, regressions in rendering or hydration, type/build/test failures, accessibility problems, and security or data-handling risks.
- Check relevant edge cases such as blank or whitespace-only todo text, toggling or deleting the correct item, immutable updates, empty lists, and client/server component boundaries.
- For each finding, include a concise explanation of the impact and the exact changed file and line. Rank findings by severity; omit a finding when its impact or relevance cannot be substantiated.
- Mention important test coverage gaps or verification limits separately from defects. Do not modify code as part of a review unless asked to implement fixes.
