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
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
