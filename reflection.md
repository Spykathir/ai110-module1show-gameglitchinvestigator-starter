# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

I gave it 3 plays, it seems to consistantly give the incorrect hint (guess higher when its lower, aand lower when higher).  In one example the answer was a negative number.  The score in the developer log is different than the score given when I win the game AND the score is weird, like I lose an inconsistant amount of points for each guess, maybe it's based on how far off of the correct answer I was?  Something is also wrong with the attempt counter, I think im loseing an attempt but im not really sure how.  
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used Claude for this project.  Claude was super helpful and almost every suggestion was simple and effective.  One fix that Claude cought that I didnt was the range for the different diffucilties in the settings was accurite but the prompt under "make a guess" was always "guess a number between 1 and 100".  He also helped me solve the scoreing issue.  One thing he may have gotten wrong, he thinks the number range for hard should be bigger, I think it makes sence for it to be bigger but it also comes with fewer guesses, so I think it could go either way.  
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

Every bug that got fixed I tried to check with at least 3 games.  I didnt try to use the AI to test any of the corrections, I just did that manualy.  
---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

Everytime I acted on the app, the streamlit returned the full app, so it could pick a new number every time.  I guess just imagine that the streamlit randomly draws a new number everytime, except for thje session_state which is the same.  I used the line: 
if "secret" not in st.session_state:
    st.session_state.secret = random.randint(low, high)

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

I think asking the AI stright up, here's what I am going for, do you see anything that may work against me on that?? is a solid strat to get started.  Next time I may ask the AI to build me some test cases so I can check to see if it works every time, especiealy if there are some edge cases I didnt think of.  Now I know to think of AI generated code as something given to me by a student, so I need to check it every time and give clear and approachable prompts so I get exactly what I'm looking for.  