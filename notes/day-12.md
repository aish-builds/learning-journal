# Day 12 Notes

## What I learned today
- 30-Days-Of-Python Day 11: Functions in depth — *args for arbitrary positional 
  arguments, **kwargs for arbitrary named arguments, default parameters
- `isinstance()` — checking if a value belongs to a specific type or set of types
- `dict.fromkeys(list, 0)` — initialising a dictionary from a list with a default value
- `.sort()` vs `sorted()` — .sort() modifies in place and returns None, sorted() 
  returns a new list without touching the original
- Statistical functions from scratch — mean, median, mode, range, variance, std
- Abdul Bari 1.10.2: Comparison of Functions — using limits to formally compare 
  growth rates, L'Hôpital's rule for indeterminate forms
- Abdul Bari 1.11: Best, Worst and Average Case Analysis — these describe the 
  input, not the notation. Big O can be applied to any case, not just worst case.

## What I built today
- 5 function exercises from 30-Days-Of-Python Day 11:
  - add_all_nums with *args and type validation
  - solve_quadratic_eqn using discriminant and math.sqrt
  - Statistical suite: mean, median, mode, range, variance, std
  - show_args using **kwargs
  - is_prime with √n optimisation (skipping even numbers after checking 2)

## One thing that confused me
- Both versions of is_prime have the same Big O complexity of O(√n) even though 
  Version 2 does half the actual work by skipping even numbers. This is the 
  limitation of Big O, it drops constants, so O(√n/2) and O(√n) are treated 
  identically. The constant factor matters in practice (especially as n is scaled) but 
  Big O notation can't capture it. Good reminder that theoretical complexity and 
  real-world performance aren't always the same thing.

## What I'll do tomorrow
- 30-Days-Of-Python Day 12: Modules
- HTML and CSS foundations — freeCodeCamp
- Build first static webpage
- SQL: GROUP BY and JOIN on W3Schools