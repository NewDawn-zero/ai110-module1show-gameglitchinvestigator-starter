# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

The game ran but had several bugs. 

Bug 1: Wrong hint direction - I guessed 22, the secret was 26, 
but it said "Go LOWER!" instead of "Go HIGHER!"

Bug 2: Attempts did not count down correctly when submitting a guess.

Bug 3: Difficulty range was wrong - Easy mode showed "Range: 1 to 20" 
in settings but the game prompt said "Guess between 1 and 100."
---

## 2. How did you use AI as a teammate?

I used Copilot to assist me throughout this project.

Correct suggestion: The AI correctly identified that the hints 
were reversed in check_guess - guessing too high was showing 
"Go HIGHER" instead of "Go LOWER". I verified this by playing 
the game and confirming the hints now match the correct direction.

Incorrect/misleading suggestion: The AI initially gave me test 
code using `result = check_guess()` which failed because 
check_guess returns two values. I had to change it to 
`result, message = check_guess()` to fix it.

---

## 3. Debugging and testing your fixes

I decided a bug was fixed by both playing the game manually 
and running pytest to confirm the behavior.

I ran pytest on tests/test_game_logic.py which had 3 tests 
checking that check_guess returns the correct outcome for a 
win, too high, and too low guess. All 3 tests passed.

Copilot helped me write the tests but gave me incorrect code 
at first. I had to fix the unpacking of the return value 
from check_guess before the tests would pass.

---

## 4. What did you learn about Streamlit and state?

Streamlit reruns the entire script from top to bottom every 
time you interact with the page, like clicking a button or 
typing in a box. Session state is how you save information 
between those reruns and without it, things like your score 
and attempts would reset to zero every single time you clicked 
anything.

---

## 5. Looking ahead: your developer habits

One habit I want to reuse is writing pytest tests to verify 
fixes instead of just manually testing. It makes it easier 
to confirm nothing broke.

Next time I work with AI on a coding task I would read through 
the suggestions more carefully before applying them instead of 
just trusting them.

This project showed me that AI generated code can look correct 
but still have bugs. You still need to understand what the code 
is doing and test it yourself.
