# Day 13 Notes

## What I learned today
- How APIs actually work end to end — endpoints, GET requests, status codes, 
  and JSON parsing with the requests library
- The universal API pattern: build URL → send request → check status code → 
  parse JSON → work with plain Python data
- Query parameters — ?author= filters commits to only mine (excludes fork 
  noise), ?per_page=100 overrides the default page size of 30
- Guard clauses — checking response.status_code != 200 and returning early 
  before trusting any data
- Personal access tokens — created one with minimal scope (public_repo), 
  raising my rate limit from 60 to 5,000 requests/hour
- The .env pattern for secrets — python-dotenv, .gitignore verification 
  before every push, never hardcoding credentials
- Modules in practice — splitting the project into fetchers.py and main.py, 
  each file imports its own dependencies, main.py orchestrates
- Inspecting unfamiliar API data before coding against it — print keys, 
  json.dumps with indent, or just visit the endpoint in a browser

## What I built today
- Started Commit Wrapped (Phase 1 CLI) — my flagship project
- fetch_user_profile() — profile data with 404 handling and the 
  `data["name"] or data["login"]` fallback idiom
- fetch_repos() — all public repos with language None → "Other"
- github.com/aish-builds/commit-wrapped

## One thing that confused me
- Hit a TypeError ("string indices must be integers") that made no sense 
  until I realized GitHub had returned an error dict instead of a repo list — 
  I'd burned through my 60 unauthenticated requests testing. Looping over a 
  dict iterates its keys (strings), which is why repo["name"] crashed. 
  Lesson: always check the status code before trusting the response shape.

## What I'll do tomorrow
- fetch_all_commits() — the hardest fetch (one request per repo, 409 errors 
  on empty repos)
- calculate_language_breakdown()
- Commit time analysis, personas, and rich display — ship Phase 1