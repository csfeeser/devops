## Docker Image Warmup!

<img src="https://learnwithmemes.files.wordpress.com/2022/04/water_leak.jpg?w=500" alt="Water Leak Meme" width="400">

### OBJECTIVES:
- Review [35. 💻 Running Flask Servers in a Docker Container](https://live.alta3.com/content/tlg-devops/labs/content/devops/flask-in-docker.html)
- Get the Flask app below running inside a Docker container (again, use the lab above to help you!)
    - Build an image that runs the python script below.
    - Create a container using that image. Name it whatever you want, expose it on whatever local port you like.
    - Test that the app is working by using `curl`! Remember to add `/rock` or `/paper` or `/scissors` to the end!
 
```python
#!/usr/bin/python3
"""
To use, try:
    curl localhost:5000/paper
    curl localhost:5000/rock
    curl localhost:5000/scissors
"""

import random
from flask import Flask
app = Flask(__name__)

choices = ["paper", "rock", "scissors"]

# if user sends HTTP GET to /paper
@app.route("/paper")
def paper():
    user_choice = "paper"
    computer_choice = random.choice(choices)
    result = determine_winner(user_choice, computer_choice)
    return f"Computer chose: {computer_choice}\n{result}"

# if user sends HTTP GET to /rock
@app.route("/rock")
def rock():
    user_choice = "rock"
    computer_choice = random.choice(choices)
    result = determine_winner(user_choice, computer_choice)
    return f"Computer chose: {computer_choice}\n{result}"

# if user sends HTTP GET to /scissors
@app.route("/scissors")
def scissors():
    user_choice = "scissors"
    computer_choice = random.choice(choices)
    result = determine_winner(user_choice, computer_choice)
    return f"Computer chose: {computer_choice}\n{result}"

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (
        (user_choice == "paper" and computer_choice == "rock") or
        (user_choice == "rock" and computer_choice == "scissors") or
        (user_choice == "scissors" and computer_choice == "paper")
    ):
        return "You win!"
    else:
        return "Computer wins!"

# bind to all IP addresses port 5000
if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000, debug=True)
```
