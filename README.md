# Octop subpath auth-recovery browser evidence

Base: TencentCloud/Octop `6ae53c2119d40b032c602d26e1aed7625b733bff` (`develop`).
Candidate: `fix/subpath-auth-recovery`.

Actual Vite/React application, Chromium 1228 via the repository-locked Python Playwright. `VITE_BASE_PATH=/tools/octop/`.

Only API responses are fixtures. Setup status reports setup complete; the login POST returns `503 {"setup_required": true}`. All credentials shown are synthetic. No real accounts, identity provider, model request, or backend state is used.

A real username/password form fill and slider drag precede the login click. Before the fix, the request recovery navigates to `/setup`, outside the application base; Vite displays its base-URL warning. After the fix, the bootstrap-route guard keeps `/tools/octop/login` mounted and displays the existing setup-required error. This deliberately preserves the existing root-deployment bootstrap guard behavior.

The JSON files record observed paths, API requests and page errors. Both runs have no JavaScript page errors. Screenshots are unmodified browser captures. This is browser integration evidence with synthetic API responses, not a live reverse-proxy or OAuth deployment test.
