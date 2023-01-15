# App Description #
A quiz app created with GUI in python using tkinter. The app opens the starting frame prompting you to start the quiz. After pressing the button, you are taken on a login page. You can choose to create an account or login with an existing one. The sign up page requires you to fill all fields.

After starting the Quiz, you have to choose your test's difficulty level. The 5 questions are randomly generated from TriviaDB's API, so they are most likely to be different at every run.

After choosing the difficulty, you have 25 seconds to answer the questions. If the time is up and you do not click submit, your answer will not be registered.

After taking the quiz you have a diagram pie that represents your results. You can choose to re-attempt the quiz (with different questions) or, if you want a different one, you have to sign out, sign in and choose your difficulty.

# Implementation #

The main features of this app are : 
* TkInter GUI
* SQLite login page
* TriviaDB API
* timer on questions

I began by creating the FrontEnd, the start page, sign up page and login page using TkInter's Documentation. In quiz.db are stored the accounts and the application connects to this database using SQLite syntax (functions addUserToDataBase and gotoLogin).

Then, I created the menu prompting you to choose the difficulty and start the actual quiz based on that. Every difficulty has its special functions getting the questions from TriviaDB's API. Based on the button pressed, each function starts. Using the requests module, I get the questions from https://opentdb.com/api_config.php. Then, start the quiz, display the questions, get the answers and display the countdown on the TkInter frame. 

After each question is displayed and I get the responses, I build a diagram pie using matplotlib and display it. I have also implemented the Re-attempt and Sign Out buttons by destroying the current frame and calling back the functions from the beginning.

# How to Run #
In order to start the application make sure that both quiz.py and quiz-icon.png are in the same file. Otherwise, it is going to trigger a TkInter Exception. Run the following command in bash:

```bash
$ python quiz.py
```
# Documentation #
* https://docs.python.org/3/library/tk.html
* https://compucademy.net/user-login-with-python-and-sqlite/
* https://www.udemy.com/course/100-days-of-code/
* https://www.w3schools.com/python/matplotlib_pie_charts.asp
* https://datatofish.com/matplotlib-charts-tkinter-gui/
* https://www.geeksforgeeks.org/how-to-embed-matplotlib-charts-in-tkinter-gui/
