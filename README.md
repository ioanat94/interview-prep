# Interview Prep

A 6-week fullstack interview prep plan + an AI prompt to generate your own for any stack.

## What's in this repo

### `ts-react-node.md` — The study plan

A detailed, day-by-day 6-week prep plan built around a TypeScript/React/Node.js stack. Every topic includes curated reading links (free resources only) followed by hands-on exercises that are fully solvable from the linked material.

**Topics covered:**

- **Week 1:** React (hooks, reconciliation, performance) & JavaScript fundamentals (closures, the event loop, promises, debounce/throttle)
- **Week 2:** TypeScript deep dive (generics, utility types, narrowing, discriminated unions, mapped & conditional types)
- **Week 3:** Node.js & Express (middleware, routing, REST API design, JWT auth, bcrypt, HTTP-only cookies)
- **Week 4:** Security (XSS, CSRF, OAuth 2.0), testing (Vitest, React Testing Library, mocking), and Git (rebase, cherry-pick, bisect, branching strategies)
- **Week 5:** Web performance (Core Web Vitals, lazy loading, code splitting, HTTP caching), CSS (Flexbox, Grid, specificity, Tailwind), and algorithms (Big O, hashmaps, two pointers, recursion)
- **Week 6:** Mock interview week: full theory + live coding sessions, timed and without notes

### `prompt-example.md` — Generate your own plan

A prompt template you can paste into any AI assistant to generate a structured study plan tailored to your own stack, timeline, and goals.

Replace the bracketed placeholders with your details:

```
I want to prepare for a technical interview. My stack is [e.g. Python/Django/PostgreSQL].
I have [X weeks / full time / evenings only] available to study.
My goals are: [e.g. be prepared for both frontend and backend, theoretical questions and live coding]
```

The more specific you are, the better the output. The prompt instructs the model to follow the same structure as the plan in this repo: phased weeks, reading before exercises, checkbox format, free resources only, and Saturday mock sessions.

## How to use the study plan

1. Open `ts-react-node.md` and start at Week 1, Day 1.
2. Do all the reading for a topic before attempting the exercises.
3. Check off items as you go, both reading and exercises.
4. For theory Q&A days, paste the relevant section into an AI assistant and ask it to quiz you.
5. On Saturdays, do the mock session timed and without notes. Write down every moment you hesitated.
