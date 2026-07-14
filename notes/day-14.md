# Day 14 Notes

## What I learned today
- The N+1 API problem. GitHub has no "all commits by user" endpoint, so I 
  make one request per repo. This is the exact problem GraphQL was built 
  to solve.
- Error handling depends on context. fetch_all_commits uses continue on 
  failures instead of returning None, because one empty repo (409 error) 
  shouldn't stop the rest from being collected.
- Found a hidden O(n²) in my language counter. Checking membership in a 
  list scans element by element, checking a dict is basically instant 
  (hash lookup, same idea as SQL indexes). Refactored to O(n).
- dict.get(key, 0) collapses the if/else membership check when counting 
  into one line.
- Commit timestamps arrive in UTC. Converted to GST with 
  timezone(timedelta(hours=4)) so late-night stats reflect Dubai time.
- statistics.mode() on lists instead of manual frequency dicts. Nice to 
  use the built-in version of something I wrote from scratch on Day 12.
- My persona logic silently depends on the language dict arriving sorted. 
  It works, but only because calculate_language_breakdown sorts before 
  returning. These implicit contracts between functions are worth noticing.
- The rich library: Panels, Tables, color markup, staged reveals.
- READMEs: Known Limitations covers flaws in what the product does, 
  Roadmap covers what it doesn't claim to do yet. Don't mix them.

## What I built today
- fetch_all_commits(): flat timestamp list across all repos, handles 409s 
  and author filtering
- calculate_language_breakdown(): sorted percentage dict with zero-division 
  guard
- analyze_commit_times(): total commits, peak hour and day, late-night 
  stats, all in local time
- determine_persona(): 6 personas, ordered if/elif, most specific first, 
  default fallback last
- display_wrapped(): 4 rich cards with staged reveal
- Full README with limitations and 3-phase roadmap
- SHIPPED Commit Wrapped Phase 1. My results: 31 commits, Thursday peak, 
  8 PM coder, "The Ghost Committer"

## One thing that confused me
- My efficiency claim was wrong in an interesting way. I thought merging 
  two loops into one was the optimization. It wasn't, O(2n) = O(n), 
  constants drop. The real fix was replacing list membership checks with 
  dict lookups, which killed a hidden quadratic. First time applying Big O 
  to my own code and the bottleneck wasn't where I assumed.

## What I'll do tomorrow
- LinkedIn post announcing Commit Wrapped Phase 1
- 30-Days-Of-Python Day 13 (list comprehensions) + HTML foundations
- Update PROGRESS.md: Phase 1 complete, Phase 2 (Next.js web version) next