# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
  The first time I ran the game it looked functional — it showed 
  a number input field, a Submit Guess button, and a difficulty 
  selector. However, after playing a couple of rounds I started 
  noticing the bugs described below.

- List at least two concrete bugs you noticed at the start  
  - Bug 1: The hints were backwards. When I guessed higher 
    than the secret number, it said "Go Higher" instead of 
    "Go Lower".
  - Bug 2: The score was inconsistent. The debug info showed 
    score: 5 during the game but the final score displayed was 45.
  - Bug 3: The game allowed one extra guess after winning. 
    The input field stayed active after the correct answer, 
    letting me submit 52 even though I had already won.

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
  I started using Claude but then pivoted to Copilot to go as instructed in the guide. So, I used Copilot to help identify and fix the bugs in  
  this project.
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
  Copilot correctly fixed the check_guess 
  function by reversing the hint logic. When I described that 
  hints were backwards, it identified the exact lines and 
  swapped "Too High" and "Too Low" correctly. I verified it 
  by running the game and testing with numbers above and below 
  the secret.

- Give one example of an AI suggestion that was incorrect or misleading (including  what the AI suggested and how you verified the result).
  Copilot's first attempt at fixing the score was still inconsistent — the debug info and final score showed different values. I had to run the game 
  again to verify it wasn't fully fixed and prompt Copilot 
  again more specifically.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
    I verified each fix by running the game manually after each 
    change and checking the Developer Debug Info panel.
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
    I ran pytest after Copilot generated a new test for check_guess. 
    The test verified that guess=75 against secret=50 returns "Too High". 
    All 4 tests passed, confirming the hint logic was correctly fixed.

- Did AI help you design or understand any tests? How?
    Yes, I asked Copilot to generate a pytest case targeting the 
    hint bug I fixed. It created the test function and also fixed 
    existing tests that were checking the wrong part of the returned 
    tuple. This helped me understand that check_guess returns 
    (outcome, message) and tests should check result[0].
---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
    I think everytime the user interacted with the app, the entire script was run from top to bottom so it might have generated a new random secret number each time. 
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
    It's like an app with Alzheimers, everytime you click a button the app forgets everything and starts over. Streamlite without session state which is like a small memory that survives those reruns and is able to remember things between clicks. 
- What change did you make that finally gave the game a stable secret number?
    The fix was storing the secret number in Streamlit's session_state so it only gets generated once at the start of a new game, not on every rerun.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects? - This could be a testing habit, a prompting strategy, or a way you used Git.
    Independent chats when asking to fix things, so the AI has a clearer memory. Not mixing bugs on the same chat. Be specific on stating the problem and the action I need it to do. And, definitely running automated tests!!!

- What is one thing you would do differently next time you work with AI on a coding task?
    I would open a new chat for each specific bug instead of mixing problems in one conversation. I noticed Copilot gave better answers when the prompt was focused on one issue.    

- In one or two sentences, describe how this project changed the way you think about AI generated code.
    AI-generated code always needs human review — it can look correct but still have subtle bugs. We need to verify the suggestions rather than accepting them blindly.
