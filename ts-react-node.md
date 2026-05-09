# Interview prep study plan

> **How to use this:** For every topic, do all the reading first, then attempt every exercise yourself before asking for help. The exercises are fully solvable from the linked material. You don't know something until you can write it cold with the tab closed.

---

## Phase 1 — Weeks 1–2: React, JavaScript & TypeScript

---

### Week 1 — React & JavaScript

---

#### Monday

**useEffect — deps array & cleanup**

- [ ] Read: Synchronizing with effects → [react.dev](https://react.dev/learn/synchronizing-with-effects)
- [ ] Read: useEffect reference → [react.dev](https://react.dev/reference/react/useEffect)
- [ ] Read: AbortController → [MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)
- [ ] Read: Cancelling a fetch → [javascript.info](https://javascript.info/fetch-abort)
- [ ] Exercise: Write a component that fetches data on mount and cancels the request on unmount using `AbortController`
- [ ] Exercise: Write 3 `useEffect` examples from scratch — one with no deps, one with deps, one with cleanup
- [ ] Exercise: Explain to yourself out loud — what happens if you forget the cleanup function?

**Closures & scope**

- [ ] Read: Variable scope, closures → [javascript.info](https://javascript.info/closure)
- [ ] Exercise: Write a closure-based counter that increments, decrements, and resets — without using a class
- [ ] Exercise: Write a `makeMultiplier(x)` function that returns a function which multiplies any number by `x`

**Debounce — write from scratch**

- [ ] Read: Debounce explanation & task → [javascript.info](https://javascript.info/task/debounce)
- [ ] Read: setTimeout reference → [MDN](https://developer.mozilla.org/en-US/docs/Web/API/setTimeout)
- [ ] Exercise: Write `debounce(fn, delay)` from scratch — no looking once you start
- [ ] Exercise: Close the tab and write it again from memory. Repeat until you can do it in under 2 minutes

**Evening exercise**

- [ ] Build a debounced search input that fetches from the a public API of your choice, typed in TypeScript, with loading & error states

---

#### Tuesday

**useCallback & useMemo**

- [ ] Read: useCallback → [react.dev](https://react.dev/reference/react/useCallback)
- [ ] Read: useMemo → [react.dev](https://react.dev/reference/react/useMemo)
- [ ] Read: Referential equality in JS → [javascript.info](https://javascript.info/object-copy)
- [ ] Exercise: Build a parent/child pair where the child re-renders unnecessarily, then fix it with `useCallback`
- [ ] Exercise: Write a component where an expensive calculation only reruns when its inputs change, using `useMemo`
- [ ] Exercise: Explain to yourself — what is referential equality and why does it matter for these hooks?

**Event loop & microtask queue**

- [ ] Read: Event loop → [javascript.info](https://javascript.info/event-loop)
- [ ] Read: Microtasks → [javascript.info](https://javascript.info/microtask-queue)
- [ ] Play with the visualiser → [jsv9000.app](https://www.jsv9000.app/)
- [ ] Exercise: Without looking, write the console output order for a snippet mixing `setTimeout`, `Promise.then`, and synchronous code
- [ ] Exercise: Verify your answer using the visualiser, then try a harder snippet

**Promises & async/await**

- [ ] Read: Promises → [javascript.info](https://javascript.info/promise-basics)
- [ ] Read: Async/await → [javascript.info](https://javascript.info/async-await)
- [ ] Read: Promise.all and combinators → [javascript.info](https://javascript.info/promise-api)
- [ ] Exercise: Write a promise chain, then rewrite it as async/await — make sure the behaviour is identical
- [ ] Exercise: Write a function that runs 3 fetches in parallel using `Promise.all`
- [ ] Exercise: Write a function that runs the same 3 fetches sequentially using async/await

**Evening exercise**

- [ ] Build a `useFetch<T>` custom hook with loading / error / data state, fully typed in TypeScript

---

#### Wednesday

**Controlled vs uncontrolled inputs**

- [ ] Read: Controlled vs uncontrolled components → [react.dev](https://react.dev/learn/sharing-state-between-components#controlled-and-uncontrolled-components)
- [ ] Read: Reacting to input with state → [react.dev](https://react.dev/learn/reacting-to-input-with-state)
- [ ] Exercise: Build a controlled text input that shows a live character count
- [ ] Exercise: Build an uncontrolled form using `useRef` that reads the value only on submit
- [ ] Exercise: Explain to yourself — when would you reach for each approach?

**`this` binding — arrow vs regular functions**

- [ ] Read: Object methods and `this` → [javascript.info](https://javascript.info/object-methods)
- [ ] Read: Arrow functions and `this` → [javascript.info](https://javascript.info/arrow-functions)
- [ ] Exercise: Write an object with a method that uses `this` — call it in 3 different ways and predict the value of `this` each time
- [ ] Exercise: Write the same method as an arrow function and explain why the behaviour changes

**`var` / `let` / `const`, hoisting & the temporal dead zone**

- [ ] Read: var and hoisting → [javascript.info](https://javascript.info/var)
- [ ] Read: let, const and the temporal dead zone → [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#temporal_dead_zone_tdz)
- [ ] Read: Variables → [javascript.info](https://javascript.info/variables)
- [ ] Exercise: Write examples that demonstrate `var` hoisting — predict the output before running
- [ ] Exercise: Write an example that triggers a temporal dead zone error with `let`, then explain why it happens
- [ ] Exercise: Explain to yourself — what is the temporal dead zone, and why doesn't `var` have one?

**Evening exercise**

- [ ] Timed: build a fetch + display + cancel-on-unmount component. 45 min, no googling for the first 30

---

#### Thursday

**React.memo**

- [ ] Read: memo reference, skipping re-renders with memo → [react.dev](https://react.dev/reference/react/memo)
- [ ] Exercise: Build a parent/child where the child is wrapped in `React.memo` and only re-renders when its props actually change
- [ ] Exercise: Deliberately break it by passing a new object literal as a prop on every render — observe the re-render, then fix it with `useMemo`

**Context API — performance pitfalls**

- [ ] Read: Passing data deeply with context → [react.dev](https://react.dev/learn/passing-data-deeply-with-context)
- [ ] Read: Scaling up with context and reducer → [react.dev](https://react.dev/learn/scaling-up-with-reducer-and-context)
- [ ] Exercise: Build a context that holds a counter value — put a log in a consumer component and observe how often it re-renders as the value changes
- [ ] Exercise: Split the context into a value context and a dispatch context to prevent unnecessary re-renders

**Error boundaries**

- [ ] Read: Catching errors with error boundaries → [react.dev](https://react.dev/reference/react/Component#catching-rendering-errors-with-an-error-boundary)
- [ ] Exercise: Write an error boundary class component from scratch — it should catch errors and render a fallback UI
- [ ] Exercise: Wrap a component that intentionally throws and verify the fallback renders instead of crashing the page

**Array methods — map, filter, reduce**

- [ ] Read: Array methods → [javascript.info](https://javascript.info/array-methods)
- [ ] Exercise: Reimplement `map`, `filter`, and `reduce` from scratch using a plain `for` loop
- [ ] Exercise: Given an array of objects with a `category` property, group them by category using only `reduce`

**Theory Q&A**

- [ ] Ask Claude to quiz you on all React + JS topics covered Mon–Thu — aim for 15+ questions

---

#### Friday

**Reconciliation & virtual DOM**

- [ ] Read: Preserving and resetting state → [react.dev](https://react.dev/learn/preserving-and-resetting-state)
- [ ] Read: Rendering and committing → [react.dev](https://react.dev/learn/render-and-commit)
- [ ] Exercise: Write an example where swapping the `key` prop on a component fully resets its state — explain why
- [ ] Exercise: Explain to yourself — what triggers a re-render? What does React actually compare in the diff?

**Throttle**

- [ ] Read: Throttle task → [javascript.info](https://javascript.info/task/throttle)
- [ ] Read: setTimeout and setInterval → [javascript.info](https://javascript.info/settimeout-setinterval)
- [ ] Exercise: Write `throttle(fn, limit)` from scratch
- [ ] Exercise: Explain to yourself — what is the difference between debounce and throttle? Give a real-world use case for each

**Memoization with closures**

- [ ] Read: Closures → [javascript.info](https://javascript.info/closure)
- [ ] Read: Memoization → [javascript.info](https://www.freecodecamp.org/news/understanding-memoize-in-javascript-51d07d19430e/)
- [ ] Exercise: Write a `memoize(fn)` function that caches results using a closure — it should return the cached result if the same arguments are passed again

**Custom hooks**

- [ ] Read: Reusing logic with custom hooks → [react.dev](https://react.dev/learn/reusing-logic-with-custom-hooks)
- [ ] Exercise: Write a `useDebounce(value, delay)` hook that returns the debounced value
- [ ] Exercise: Write a `useLocalStorage<T>(key, initialValue)` hook that syncs state with localStorage

**Evening exercise**

- [ ] Full mini-project: debounced search from a public API of your choice, fully typed in TS, loading & error states, cancel stale requests with `AbortController`

---

#### Saturday

**Mock session**

- [ ] Timed 45 min: reproduce the debounced search task completely cold — no help, no googling
- [ ] Review: write down every moment you hesitated. Those are Monday's warmup topics

---

### Week 2 — TypeScript deep dive

---

#### Monday

**Generics — writing & reading**

- [ ] Read: TypeScript generics tutorial → [totaltypescript.com](https://www.totaltypescript.com/typescript-generics-in-three-easy-patterns)
- [ ] Read: Generics handbook → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/generics.html)
- [ ] Exercise: Write a generic `identity<T>(arg: T): T` function
- [ ] Exercise: Write a generic `getProperty<T, K extends keyof T>(obj: T, key: K): T[K]` function from scratch
- [ ] Exercise: Write a generic typed `useFetch<T>` hook that returns `{ data: T | null, loading: boolean, error: string | null }`

**Utility types — `Partial`, `Required`, `Pick`, `Omit`, `ReturnType`, `Awaited`**

- [ ] Read: Utility types handbook → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/utility-types.html)
- [ ] Exercise: For each utility type, write a usage example from scratch without looking at the docs
- [ ] Exercise: Reimplement `Partial<T>` and `Pick<T, K>` yourself using mapped types — verify they behave the same

**Practice**

- [ ] Complete typescript-exercises levels 1–8 → [typescript-exercises.github.io](https://typescript-exercises.github.io/)

---

#### Tuesday

**Type narrowing — `typeof`, `instanceof`, `in`, type predicates**

- [ ] Read: Narrowing → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/narrowing.html)
- [ ] Exercise: Write a function that accepts `string | number | null` and handles each case with correct narrowing
- [ ] Exercise: Write a user-defined type guard using `is` that checks whether an unknown value is a specific object shape
- [ ] Exercise: Write a function that uses the `in` operator to distinguish between two different object types

**Discriminated unions**

- [ ] Read: Discriminated unions → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#discriminated-unions)
- [ ] Exercise: Model a `Result<T>` type as a discriminated union: `{ ok: true; data: T } | { ok: false; error: string }`
- [ ] Exercise: Write a function that handles both branches — make sure TypeScript errors if you forget a branch

**`unknown` vs `any` vs `never`**

- [ ] Read: unknown and any → [mariusschulz.com](https://mariusschulz.com/blog/the-unknown-type-in-typescript)
- [ ] Read: The never type → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#the-never-type)
- [ ] Exercise: Write a function that accepts `unknown`, narrows it to a string safely, and returns its length
- [ ] Exercise: Add a `never` exhaustiveness check to your `Result<T>` handler from above
- [ ] Exercise: Explain to yourself — why is `any` dangerous? When is `unknown` the right choice?

**Evening exercise**

- [ ] Timed: type a full fetch response pipeline from scratch — raw API response → typed domain model → typed component props, using generics and your `Result<T>` type

---

#### Wednesday

**Interfaces vs type aliases**

- [ ] Read: Type vs interface → [totaltypescript.com](https://www.totaltypescript.com/type-vs-interface-which-should-you-use)
- [ ] Read: Object types → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/objects.html)
- [ ] Exercise: Write an example of interface declaration merging — add a property to an existing interface in a second block
- [ ] Exercise: Try to do the same with a type alias — observe the error and explain why it happens
- [ ] Exercise: Explain to yourself — when would you prefer an interface? When a type alias?

**Mapped types**

- [ ] Read: Mapped types → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/mapped-types.html)
- [ ] Exercise: Reimplement `Readonly<T>` from scratch using a mapped type
- [ ] Exercise: Reimplement `Record<K extends string, V>` from scratch
- [ ] Exercise: Write a mapped type that makes all properties of an object optional and `null`able

**Conditional types**

- [ ] Read: Conditional types → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/conditional-types.html)
- [ ] Exercise: Write a conditional type `IsArray<T>` that resolves to `true` if `T` is an array, `false` otherwise
- [ ] Exercise: Write a type `Unwrap<T>` that extracts `T` from `Promise<T>` — verify it works nested

**Practice**

- [ ] Complete typescript-exercises levels 9–18 → [typescript-exercises.github.io](https://typescript-exercises.github.io/)

---

#### Thursday

**`keyof` & `typeof`**

- [ ] Read: keyof type operator → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/keyof-types.html)
- [ ] Read: typeof type operator → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/typeof-types.html)
- [ ] Exercise: Write a function `getProperty<T, K extends keyof T>(obj: T, key: K): T[K]` — this should be type-safe with no `any`
- [ ] Exercise: Use `typeof` to derive a type from a config object at runtime — use that type to type a function parameter

**Declaration merging**

- [ ] Read: Declaration merging → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/declaration-merging.html)
- [ ] Exercise: Merge two interface declarations to add a method to an existing interface
- [ ] Exercise: Explain to yourself — why does TS allow interface merging but not type alias merging?

**Typing fetch correctly**

- [ ] Read: Generics → [typescriptlang.org](https://www.typescriptlang.org/docs/handbook/2/generics.html)
- [ ] Read: fetch API → [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
- [ ] Exercise: Write a typed `fetchJson<T>(url: string, signal?: AbortSignal): Promise<Result<T>>` wrapper using your `Result<T>` type from Tuesday — no `any` anywhere

**Theory Q&A**

- [ ] Ask Claude to quiz you on TypeScript + React combined — aim for 20 questions

---

#### Friday

**Review & consolidation**

- [ ] Revisit the 3 TS topics that felt shakiest this week — rewrite examples from scratch without looking
- [ ] Revisit any React topics from week 1 that still feel uncertain

**Evening exercise**

- [ ] Build a fully typed custom hook library: `useFetch<T>`, `useDebounce<T>`, `useLocalStorage<T>` — no `any`, proper generics, handles edge cases

---

#### Saturday

**Mock session**

- [ ] Ask Claude for a 20-question React + TS theory interview — timed, no notes
- [ ] Write down 3 things still uncertain — these open week 3

---

## Phase 2 — Weeks 3–4: Node.js, Express, REST & Auth

---

### Week 3 — Node.js & Express

---

#### Monday

**Event loop — call stack, callback queue, microtask queue**

- [ ] Read: Event loop timers and nexttick → [nodejs.org](https://nodejs.org/learn/asynchronous-work/event-loop-timers-and-nexttick)
- [ ] Read: process.nextTick → [nodejs.org](https://nodejs.org/learn/asynchronous-work/understanding-processnexttick)
- [ ] Read: setImmediate → [nodejs.org](https://nodejs.org/learn/asynchronous-work/understanding-setimmediate)
- [ ] Read: Event loop explained → [javascript.info](https://javascript.info/event-loop)
- [ ] Exercise: Without looking, write the console output order for a snippet mixing `setTimeout(0)`, `Promise.then`, `process.nextTick`, and synchronous code
- [ ] Exercise: Verify your answer by running it, then try a more complex combination
- [ ] Exercise: Explain to yourself — when would you actually reach for `process.nextTick`?

**CommonJS vs ESM**

- [ ] Read: ESM in Node → [nodejs.org](https://nodejs.org/api/esm.html)
- [ ] Read: Modules comparison → [nodejs.org](https://nodejs.org/api/module.html#commonjs-namespaces)
- [ ] Exercise: Write the same module (exports a function and a constant) in both CommonJS and ESM formats
- [ ] Exercise: Explain to yourself — why can't you `require()` an ESM module? What is top-level await and why does it only work in ESM?

**Evening exercise**

- [ ] Build a small Express server from scratch with typed routes, body parsing, query params, and route params

---

#### Tuesday

**Middleware — what it is, `next()`, execution order**

- [ ] Read: Using middleware → [expressjs.com](https://expressjs.com/en/guide/using-middleware.html)
- [ ] Read: Writing middleware → [expressjs.com](https://expressjs.com/en/guide/writing-middleware.html)
- [ ] Exercise: Write 3 middleware functions from scratch: a request logger, a simple auth check that blocks unauthenticated requests, and a request timer that logs how long each request takes
- [ ] Exercise: Deliberately register middleware in the wrong order and observe how it breaks — then fix it
- [ ] Exercise: Explain to yourself — what happens if you never call `next()` in a middleware?

**Router-level vs app-level middleware**

- [ ] Read: Router-level middleware → [expressjs.com](https://expressjs.com/en/guide/using-middleware.html#middleware.router)
- [ ] Exercise: Refactor your server to use `express.Router()` for a `/api/notes` route group
- [ ] Exercise: Apply your auth middleware only to that router, not to the whole app — verify public routes still work

**Route params, query params, body parsing**

- [ ] Read: Routing guide → [expressjs.com](https://expressjs.com/en/guide/routing.html)
- [ ] Exercise: Write routes that use all three: `/users/:id` (route param), `?page=2&limit=10` (query params), and a POST with a JSON body
- [ ] Exercise: Type all three in TypeScript using Express's generic request types

**Error handling middleware**

- [ ] Read: Error handling → [expressjs.com](https://expressjs.com/en/guide/error-handling.html)
- [ ] Exercise: Write an error handling middleware with the 4-argument signature `(err, req, res, next)`
- [ ] Exercise: Throw an error from an async route handler — verify it reaches your error middleware (hint: you need to catch it and call `next(err)`)

**Evening exercise**

- [ ] Add CORS, helmet, and rate limiting to your server → [expressjs.com](https://expressjs.com/en/advanced/best-practice-security.html)

---

#### Wednesday

**REST API design — status codes**

- [ ] Read: HTTP status codes → [MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
- [ ] Exercise: Without looking, write the correct status code for: success, created, no content, bad request, unauthorised, forbidden, not found, conflict, internal server error
- [ ] Exercise: Explain to yourself — what is the difference between 401 and 403?

**Resource naming, idempotency & versioning**

- [ ] Read: Resource naming → [restfulapi.net](https://restfulapi.net/resource-naming/)
- [ ] Read: Idempotency → [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent)
- [ ] Read: API versioning → [restfulapi.net](https://restfulapi.net/versioning/)
- [ ] Exercise: Design the URL structure for a REST API that manages blog posts and their comments — name every endpoint
- [ ] Exercise: Write down which HTTP methods are idempotent and explain why `POST` is not

**Pagination & error response structure**

- [ ] Read: Cursor-based pagination → [sitepoint.com](https://www.sitepoint.com/paginating-real-time-data-cursor-based-pagination/)
- [ ] Read: JSON:API error structure → [jsonapi.org](https://jsonapi.org/format/#errors)
- [ ] Exercise: Design a consistent JSON error response shape and implement it in your Express error middleware
- [ ] Exercise: Add cursor-based pagination to a GET route that returns a list of items

**Evening exercise**

- [ ] Build a full CRUD REST API (e.g. a notes app) with correct status codes, typed request/response bodies, consistent error responses, and pagination on the list endpoint

---

#### Thursday

**JWT structure — header, payload, signature**

- [ ] Read: JWT introduction → [jwt.io](https://jwt.io/introduction)
- [ ] Read: JWT handbook → [auth0.com](https://auth0.com/resources/ebooks/jwt-handbook)
- [ ] Exercise: Take a real JWT string and decode the header and payload by hand using base64 — do not use a library
- [ ] Exercise: Explain to yourself — where is the signature verified? What stops someone from changing the payload and reusing the token?

**JWT vs sessions — tradeoffs**

- [ ] Read: Sessions vs tokens → [auth0.com](https://auth0.com/blog/stateless-auth-for-stateful-minds/)
- [ ] Exercise: Write a pros/cons list for JWT and sessions from memory
- [ ] Exercise: Explain to yourself — why are JWTs stateless? Why does that make them hard to invalidate before expiry?

**Password hashing — bcrypt & salts**

- [ ] Read: Understanding bcrypt → [auth0.com](https://auth0.com/blog/hashing-in-action-understanding-bcrypt/)
- [ ] Exercise: Write a register function that hashes a password with bcrypt before saving
- [ ] Exercise: Write a login function that compares a plaintext password to a stored hash
- [ ] Exercise: Explain to yourself — why is bcrypt intentionally slow? What is a salt and what does it prevent?

**HTTP-only cookies**

- [ ] Read: Cookies and security → [MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies#security)
- [ ] Read: SameSite cookies → [web.dev](https://web.dev/articles/samesite-cookies-explained)
- [ ] Exercise: Explain to yourself — why can't JavaScript read an HTTP-only cookie? Why does that matter for XSS protection?
- [ ] Exercise: Explain — why does HTTP-only alone not protect against CSRF, and what does `SameSite=Strict` add?

**Evening exercise**

- [ ] Add JWT auth to your CRUD API: register, login, and a protected route that rejects requests without a valid token

---

#### Friday

**Streams & backpressure**

- [ ] Read: Backpressuring in streams → [nodejs.org](https://nodejs.org/learn/modules/backpressuring-in-streams)
- [ ] Read: Stream API → [nodejs.org](https://nodejs.org/api/stream.html)
- [ ] Exercise: Write a script that reads a large file as a stream and pipes it to a writable stream
- [ ] Exercise: Explain to yourself — what is backpressure? What goes wrong if you ignore it?

**Error handling in async Node code**

- [ ] Read: Error propagation and handling → [nodejs.org](https://nodejs.org/api/errors.html#error-propagation-and-interception)
- [ ] Read: Error handling in Express → [expressjs.com](https://expressjs.com/en/guide/error-handling.html)
- [ ] Exercise: Write an Express route with an async handler that properly catches errors and passes them to `next(err)` — no unhandled promise rejections
- [ ] Exercise: Add a global handler for `uncaughtException` and `unhandledRejection` — explain to yourself why these are last resorts, not normal error handling

**Clustering & worker threads**

- [ ] Read: Cluster API → [nodejs.org](https://nodejs.org/api/cluster.html)
- [ ] Read: Worker threads → [nodejs.org](https://nodejs.org/api/worker_threads.html)
- [ ] Exercise: Explain to yourself — what problem does clustering solve? When would you use worker threads instead of clustering?

**Theory Q&A**

- [ ] Ask Claude to quiz you on Node + Express + REST + Auth — aim for 20 questions

---

#### Saturday

**Mock session**

- [ ] Timed 45 min: build an Express API from scratch — typed routes, auth middleware, CRUD, consistent error handling
- [ ] Review: identify gaps, flag for week 4 warmup

---

### Week 4 — Security, testing & Git

---

#### Monday

**XSS — what it is & prevention**

- [ ] Read: XSS attack → [MDN](https://developer.mozilla.org/en-US/docs/Web/Security/Attacks/XSS)
- [ ] Read: XSS prevention cheat sheet → [cheatsheetseries.owasp.org](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
- [ ] Exercise: Explain to yourself — what is the difference between stored, reflected, and DOM-based XSS?
- [ ] Exercise: Write 3 concrete prevention measures from memory

**CSRF — what it is & prevention**

- [ ] Read: CSRF attack → [MDN](https://developer.mozilla.org/en-US/docs/Web/Security/Attacks/CSRF)
- [ ] Read: CSRF prevention cheat sheet → [cheatsheetseries.owasp.org](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)
- [ ] Exercise: Explain to yourself — why does CSRF work? Walk through a real attack scenario step by step
- [ ] Exercise: Explain — why does HTTP-only not prevent CSRF? What does a CSRF token actually do?

**OAuth 2.0 — authorization code flow**

- [ ] Read: Authorization code grant → [oauth.net](https://oauth.net/2/grant-types/authorization-code/)
- [ ] Read: OAuth 2.0 simplified → [aaronparecki.com](https://aaronparecki.com/oauth-2-simplified/)
- [ ] Exercise: Draw the full authorization code flow from memory — browser → auth server → your server → access token
- [ ] Exercise: Explain to yourself — what is the difference between an access token and a refresh token? Why does the short expiry of access tokens matter?

**Evening exercise**

- [ ] Security audit your CRUD API from week 3: add input validation, sanitisation, rate limiting on auth routes, and helmet headers

---

#### Tuesday

**Vitest — `describe`, `it`, `expect`, setup & teardown**

- [ ] Read: Getting started → [vitest.dev](https://vitest.dev/guide/)
- [ ] Read: API reference → [vitest.dev](https://vitest.dev/api/)
- [ ] Exercise: Write tests for your `debounce` function from week 1 — cover the happy path, edge cases, and verify the timer resets on repeated calls
- [ ] Exercise: Write a test file that uses `beforeEach` to reset shared state and `afterEach` to clean up — explain to yourself why test isolation matters

**`vi.mock` — mocking modules**

- [ ] Read: Mocking → [vitest.dev](https://vitest.dev/guide/mocking)
- [ ] Exercise: Mock a module that makes HTTP requests and write tests that assert your code handles both a successful response and a network failure
- [ ] Exercise: Explain to yourself — why do you mock the module at the top level rather than the fetch call inside it?

**`vi.spyOn` — spying on functions**

- [ ] Read: vi.spyOn → [vitest.dev](https://vitest.dev/api/vi#vi-spyon)
- [ ] Exercise: Use `vi.spyOn` to assert that a function was called with specific arguments
- [ ] Exercise: Restore the spy after the test — explain why failing to restore it can break other tests

**Testing async code**

- [ ] Read: Testing async operations → [vitest.dev](https://vitest.dev/guide/learn/async)
- [ ] Exercise: Write a test for an async function that rejects — assert the specific error is thrown
- [ ] Exercise: Write a test for a function that uses `setTimeout` — use `vi.useFakeTimers()` to control time

**Evening exercise**

- [ ] Write unit tests for your CRUD API's route handlers and your custom React hooks from week 2

---

#### Wednesday

**Testing strategy — what to test and what to mock**

- [ ] Read: Testing trophy → [kentcdodds.com](https://kentcdodds.com/blog/the-testing-trophy-and-testing-classifications)
- [ ] Read: What is a mock → [kentcdodds.com](https://kentcdodds.com/blog/but-really-what-is-a-javascript-mock)
- [ ] Read: Write tests → [kentcdodds.com](https://kentcdodds.com/blog/write-tests)
- [ ] Exercise: Explain to yourself — what does "test behaviour, not implementation" mean? Give a concrete example of each
- [ ] Exercise: Explain — what does code coverage tell you, and what does it not tell you?

**Testing React components with Testing Library**

- [ ] Read: React Testing Library intro → [testing-library.com](https://testing-library.com/docs/react-testing-library/intro/)
- [ ] Read: Queries reference → [testing-library.com](https://testing-library.com/docs/queries/about)
- [ ] Read: user-event → [testing-library.com](https://testing-library.com/docs/user-event/intro)
- [ ] Exercise: Write a test for your debounced search component — simulate typing in the input and assert the results render
- [ ] Exercise: Write tests for the loading state and the error state

**Evening exercise**

- [ ] Add React Testing Library tests to your API/debounced search component — cover the input interaction, loading state, error state, and results rendering

---

#### Thursday

**Git — rebase vs merge**

- [ ] Read: Merging vs rebasing → [atlassian.com](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
- [ ] Exercise: Create a feature branch, make 3 commits, then rebase it onto main — observe the linear history
- [ ] Exercise: Do the same with merge — observe the merge commit and explain the difference
- [ ] Exercise: Explain to yourself — when would a team prefer rebase? When merge?

**Interactive rebase — `git rebase -i`**

- [ ] Read: Rewriting history → [atlassian.com](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)
- [ ] Exercise: Make 4 messy commits on a branch, then squash them into 1 clean commit using `rebase -i`
- [ ] Exercise: In the same session, reorder two commits and reword one commit message

**`git stash`, `cherry-pick`, `bisect`**

- [ ] Read: git stash → [atlassian.com](https://www.atlassian.com/git/tutorials/saving-changes/git-stash)
- [ ] Read: git cherry-pick → [atlassian.com](https://www.atlassian.com/git/tutorials/cherry-pick)
- [ ] Read: git bisect → [git-scm.com](https://git-scm.com/docs/git-bisect)
- [ ] Exercise: Use `git stash`, switch branches, apply the stash — then drop it
- [ ] Exercise: Cherry-pick a single commit from one branch onto another
- [ ] Exercise: Explain to yourself — what problem does `git bisect` solve? When would you use it?

**Branching strategies & commit messages**

- [ ] Read: Comparing workflows → [atlassian.com](https://www.atlassian.com/git/tutorials/comparing-workflows)
- [ ] Read: Conventional commits → [conventionalcommits.org](https://www.conventionalcommits.org/en/v1.0.0/)
- [ ] Exercise: Explain to yourself — what is trunk-based development? What is the key discipline it requires?
- [ ] Exercise: Write 5 commit messages in conventional commits format for realistic changes

**Theory Q&A**

- [ ] Ask Claude to quiz you on security + testing + Git — aim for 20 questions

---

#### Friday

**CI/CD basics**

- [ ] Read: GitHub Actions quickstart → [docs.github.com](https://docs.github.com/en/actions/quickstart)
- [ ] Read: Deployment strategies → [martinfowler.com](https://martinfowler.com/bliki/BlueGreenDeployment.html)
- [ ] Exercise: Write a basic GitHub Actions workflow file from scratch: lint → test → build
- [ ] Exercise: Explain to yourself — what is blue/green deployment? What is a feature flag and what problem does it solve?
- [ ] Exercise: Explain — how do you handle secrets in a pipeline? Why must you never commit them?

**Mock interview**

- [ ] Ask Claude for a full backend mock interview — theory + one live coding task, timed, no notes

---

#### Saturday

**Mock session**

- [ ] Ask Claude for 30 theory questions across all Phase 1 + Phase 2 topics — timed, no notes
- [ ] Score yourself honestly. List remaining weak spots

---

## Phase 3 — Week 5: Performance, CSS & algorithms

---

### Week 5

---

#### Monday

**Core Web Vitals — LCP, CLS, INP**

- [ ] Read: Web Vitals → [web.dev](https://web.dev/articles/vitals)
- [ ] Read: LCP → [web.dev](https://web.dev/articles/lcp)
- [ ] Read: CLS → [web.dev](https://web.dev/articles/cls)
- [ ] Read: INP → [web.dev](https://web.dev/articles/inp)
- [ ] Exercise: Explain to yourself — what does each metric measure? What are the most common causes of a bad score for each?
- [ ] Exercise: Run Lighthouse on a real project → [Chrome Docs](https://developer.chrome.com/docs/lighthouse/overview) — fix the top 3 issues it reports

**Lazy loading — `React.lazy` & `Suspense`**

- [ ] Read: lazy reference → [react.dev](https://react.dev/reference/react/lazy)
- [ ] Read: Suspense reference → [react.dev](https://react.dev/reference/react/Suspense)
- [ ] Exercise: Add lazy loading to a heavy component — wrap it in `Suspense` with a fallback
- [ ] Exercise: Open the network tab and verify the chunk only loads when the component is actually rendered

**Code splitting & dynamic imports**

- [ ] Read: Dynamic import → [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/import)
- [ ] Read: Code splitting → [javascript.info](https://javascript.info/modules-dynamic-imports)
- [ ] Exercise: Write a dynamic `import()` that loads a module only when a button is clicked — log the module to verify
- [ ] Exercise: Explain to yourself — what is the relationship between dynamic imports and code splitting?

**HTTP caching — Cache-Control, CDN**

- [ ] Read: HTTP cache → [web.dev](https://web.dev/articles/http-cache)
- [ ] Read: Cache-Control → [MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control)
- [ ] Exercise: Explain to yourself — what is the difference between `no-cache` and `no-store`?
- [ ] Exercise: Explain — what does `stale-while-revalidate` do? When would you use it?

**Bundle analysis**

- [ ] Read: bundlephobia → [bundlephobia.com](https://bundlephobia.com/)
- [ ] Exercise: Check the bundle size of 3 libraries you use regularly — find a lighter alternative for at least one

---

#### Tuesday

**Flexbox**

- [ ] Read: Complete guide to flexbox → [css-tricks.com](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [ ] Read: Flexbox → [MDN](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Flexbox)
- [ ] Exercise: Build from scratch without looking: a navbar with logo left and links right, a centered card, a footer pinned to the bottom
- [ ] Exercise: Explain to yourself — what is the difference between the main axis and cross axis? What does `flex: 1` actually expand to?

**CSS Grid**

- [ ] Read: Complete guide to grid → [css-tricks.com](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [ ] Read: Grid → [MDN](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Grids)
- [ ] Exercise: Build from scratch: a two-column layout with a fixed sidebar and flexible main area
- [ ] Exercise: Build a responsive card grid using `auto-fit` and `minmax` that reflows without media queries
- [ ] Exercise: Explain to yourself — when would you reach for Grid over Flexbox, and vice versa?

**Specificity, the cascade & CSS custom properties**

- [ ] Read: Specificity → [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
- [ ] Read: Cascade → [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)
- [ ] Read: CSS custom properties → [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- [ ] Exercise: Calculate the specificity score for 5 selectors without using a tool — then verify
- [ ] Exercise: Build a small UI that uses CSS variables for its colour scheme — switch the entire theme by changing 2–3 variables

**Responsive design & Tailwind**

- [ ] Read: Responsive web design basics → [web.dev](https://web.dev/articles/responsive-web-design-basics)
- [ ] Read: Reusing styles in Tailwind → [tailwindcss.com](https://tailwindcss.com/docs/reusing-styles)
- [ ] Exercise: Take one of your layouts from today and make it fully responsive, mobile-first, using media queries
- [ ] Exercise: Rebuild the same layout using Tailwind utility classes

---

#### Wednesday

**Big O — reading & estimating complexity**

- [ ] Read: Big O cheat sheet → [bigocheatsheet.com](https://www.bigocheatsheet.com/)
- [ ] Exercise: Estimate the time complexity of 5 functions you wrote earlier in this plan — write your reasoning
- [ ] Exercise: Explain to yourself — why does O(n²) become catastrophic at scale? At what n does it noticeably slow down?

**Hashmaps for O(n) lookups**

- [ ] Read: Map → [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
- [ ] Read: Objects as hashmaps → [javascript.info](https://javascript.info/map-set)
- [ ] Exercise: Solve "two sum" — brute force O(n²) first, then optimise to O(n) using a hashmap
- [ ] Exercise: Explain to yourself exactly why the hashmap solution is O(n)
- [ ] 2–3 Exercism exercises → [exercism.org](https://exercism.org/tracks/typescript)

**Two pointers & sliding window**

- [ ] Read: Two pointers pattern → [neetcode.io](https://neetcode.io/roadmap)
- [ ] Exercise: Solve "longest substring without repeating characters" using a sliding window
- [ ] Exercise: Solve "valid palindrome" using two pointers
- [ ] 2 LeetCode easy problems → [leetcode.com](https://leetcode.com/problemset/?difficulty=EASY)

---

#### Thursday

**Basic recursion & tree traversal**

- [ ] Read: Recursion and stack → [javascript.info](https://javascript.info/recursion)
- [ ] Exercise: Write a recursive function to flatten a deeply nested array — no built-in `flat()`
- [ ] Exercise: Write a recursive function to sum all numeric values in a nested object of arbitrary depth
- [ ] Exercise: Explain to yourself — what is the base case? What happens if you forget it?

**Sorting fundamentals**

- [ ] Read: Array sort → [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
- [ ] Read: Sort comparator → [javascript.info](https://javascript.info/array-methods#sort-fn)
- [ ] Exercise: Write a custom comparator that sorts an array of objects by multiple fields (e.g. by category, then alphabetically by name)
- [ ] Exercise: Explain to yourself — what does a comparator returning a negative number mean? What is the complexity of `.sort()` in V8?

**Array & string manipulation practice**

- [ ] 3–4 Exercism exercises → [exercism.org](https://exercism.org/tracks/typescript)
- [ ] 2 Codewars katas → [codewars.com](https://www.codewars.com/kata/search/typescript)

---

#### Friday

**Review & consolidation**

- [ ] Revisit the 2 performance topics that felt shakiest
- [ ] Revisit the 1 CSS topic that felt shakiest
- [ ] Revisit the algorithm pattern that felt hardest

**Theory Q&A**

- [ ] Ask Claude to quiz you on performance + CSS + algorithms — aim for 15 questions

---

#### Saturday

**Mock session**

- [ ] Full mock interview: theory across all 5 weeks + one live coding task — timed, no notes
- [ ] Review: note what still needs work going into week 6

---

## Phase 4 — Week 6: Mock interview week

---

### Week 6

---

#### Monday

- [ ] Morning: Revisit your 3 weakest topics from the entire plan — rewrite examples from scratch without looking
- [ ] Afternoon: Ask Claude for a full mock interview — theory + live coding, simulated pressure, no notes

---

#### Tuesday

- [ ] Morning: Drill any gaps exposed in Monday's mock
- [ ] Afternoon: Timed live coding — 3 different exercises back to back, 30 min each, no help

---

#### Wednesday

- [ ] Morning: Light review only — no new topics. Read through your own notes and examples
- [ ] Afternoon: Final full mock — treat it exactly like a real interview, talk through everything out loud

---

#### Thursday

- [ ] Light review max 1–2 hours. Rest matters more than cramming now
- [ ] Research the company — their stack, recent news, questions you want to ask them

---

#### Friday

- [ ] Interview day — you're ready

---

## Ongoing — after the plan

- [ ] Keep doing 2–3 Exercism problems per week regardless of outcome → [exercism.org](https://exercism.org/tracks/typescript)
- [ ] After each interview (pass or fail), write down every question you were asked — review the ones you fumbled
