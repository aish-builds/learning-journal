# Day 11 Notes

## What I learned today
- Properties of Asymptotic Notations: transitivity, reflexivity, symmetry and 
  transpose symmetry across Big O, Omega and Theta
- Comparison of Functions: using logarithms to formally compare growth rates 
  of two functions
- More practice on OOP inheritance concepts
- Method overriding: child redefines a parent method to change behaviour 
  while keeping the same name
- Git commands: practiced status, diff, git add ., git commit -m “initial commit”, 
  clone, checkout -b, branch -d in terminal
- Completed GitHub Skills: Introduction to GitHub lab (branching and committing 
  on a branch)
- Completed GitHub Skills: Review pull requests lab (how PRs work, how to review and 
  merge changes, how teams collaborate on the same codebase)

## What I built today
- No project today. Focused on Git fundamentals and practice

## One thing that confused me
- Why n! uses Ω(1) as a lower bound when Ω(2^n) or Ω(n) is clearly tighter 
  and more accurate. Ω(1) is used as a proof of concept to show the 
  minimum requirement for a valid bound and not something you'd use in practice. 
  But the more important insight is why Theta doesn't exist for n! at all. Since O and Ω don't converge to the same function, n! can't be sandwiched by a single f(n).

## What I'll do tomorrow
- Algorithms: Best, worst and average case analysis
- First Neetcode problems: Contains Duplicate, Valid Anagram, Two Sum
- .gitignore setup in learning-journal