# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

The first time I ran it, it seemed fine when I typed the correct answer, but worked weird in the newgamee button and the hints displayed.
A few concrete bugs I found:

1. The hints were opposite of what they should be. It said go higher, when it should've actually said go lower. For example, when the secret number was 87 and I entered 32, it told me to lower, when it should have told me to go higher.
2. The newgame button: the secret score changed, but it did not seem to reset my score/history.
3. The difficulty toggle on the left: The range for "Normal" was more than the range for "Hard"

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used Copilot this time.
Correct suggestions: The lines in app.py that were causing the issues. For most of them, it was able to find it, but could not give me clear directions for the reset issue. It also refactored well, keeping the UI component parts in app.py and moving the inner logic to the separate file.
Incorrect/Misleading suggestions: When it refactored the program, it didn't correct the range issue correctly. It had kept the same error as before, where normal is 0-100. I highlighted that line, and then it helped to fix it.

I learned a little bit more about creating pytests from how it decided to go about it as well. When I wasn't sure about why it made a change, I asked it to explain.

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---Answer
I decided the bug was fixed when I tested it 5-10 times on streamlit. I manually ran the test on the website to check if the range-difficulty issue was fixed, if the range showed the correct values. I also checked it with the pytest, to check if the range for normal was indeed 0-50 and hard is 0-100. It asserts that both of those are true.

I don't have a lot of experience with creating my own pytests, so I learned about how to create one(and that we needed to have it in a separate file/folder) and it is less complicated than I thought it was, so that was really nice.

I asked it to explain conftest.py, and it explained that it allowed me to run tests from a seperate folder. I'm not sure right now if this is the common choice to make among programmers, but I will look this up online or do some research and learn more about making pytests.

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

For me it did not change every single time, but only seemed to change sometimes. When the number of attempts were even, the secret variable was converted to a string, and on odd attempts, it was left as it is. I think when it was converted to a string, the comparisons might have changed.

Streamlit reruns are when the entire script is run again when you click a button or interact with something on the screen. Session state keeps your values safe, so that the program remembers it as long as you are using your session. Otherwise, each time we rerun, the previous values are forgotten.

To finally get a stable number, the connection to #even number of attempts had to be removed, which made the number be kept as a numeric value for each guess, making the comparisons accurate.

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.

  Answer: I want to start writing simple pytests. As well adding more information in my git commit messages.

- What is one thing you would do differently next time you work with AI on a coding task?

  By the end of the session, I was promting better than I was at the beginning. I think I will start by giving more context, so that it can find the action point way quicker. I will also ask it to make only a few edits at a time, so I can carefully check the changes it's asking to make before allowing.

- In one or two sentences, describe how this project changed the way you think about AI generated code.

  I used to be a little wary of starting using AI generated code, because I didn't want to forget fundamentals. But now, I'm learning that if you are in control, and you intentionally use AI to help you after you have looked at the situation/output first for yourself, it can really help a lot. It also teach a lot of things, like creating tests or separating UI-game logic.
