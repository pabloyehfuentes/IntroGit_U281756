# IntroGit_U281756
Introduction to Git - exercise

Lab2 Written Report:

1. Team Contributions

U281756's functions
- ask_yes_no
- collide_ball_walls
- collide_ball_paddle
- reset_ball
- compute_ai_direction

U282038's functions
- read_int_in_range()
- get_config()
- change_colors()
- read_color()

Both team members also worked on testing the program and making sure that all the functions worked correctly together.

2. Overview of your design

- main()
Configuration (comes before the Game loop) : configuration returns five values that can be adjusted by the user, paddle_h, paddle_speed, speed_ball_x, speed_ball_y, ball_radius. In the get_config() it get ask_yes_no to prompt the user if they want to change the values that have been preassigned. Then read_int_in_range() finds if the input value is valid, which must be an integer in a predefined range. Here we already see values traveling without global variables, read_int_in_range() uses parameters which show the maximum and minimum value that is accepted. This is similar to change_colors() which returns a tuple of (backg_col, foreg_col) it also uses ask_yes_no() and read_int_in_range() to make sure the input is between 0 - 255, for green, red and blue.

- Game Loop
   the variables for the game (paddle positions, ball position and velocity, and scores) are stored locally in the main(). Since each function receives values as parameters and returns new ones. For example, collide_ball_walls() receives positional values of the ball and dimensions of the screen, and then returns a new position and velocity of the ball when it hits a wall. This idea works with get_config() values, the value is returned once and then it is passed as parameters to any function that needs it.

3. Key implementation decisions
   
One important decision was to divide the program into smaller functions, so each function has a specific task. This makes the code easier to understand and test.
We also decided not to use global variables. Instead, we used parameters to pass information between functions and return values to get the results. This helps keep the code more organised.
Another decision was to separate the configuration from the game loop. This allows the user to change the game settings before starting to play.
Finally, we used separate functions for tasks such as checking user inputs, changing colours and detecting collisions. This made it easier to work on different parts of the program and find errors.

4. Problems and solutions
   
One of the main difficulties we encountered was the behaviour of the AI paddle.
Initially, the machine did not react quickly enough to reach the ball, which made it relatively easy for the player to win.
We tried increasing the AI paddle's speed, but this did not completely solve the problem. The paddle sometimes moved too much or remained still when it should have adjusted its position to follow the ball.
We realised that increasing the speed alone was not enough to improve its behaviour. The AI also needed to make better decisions about the ball's position and movement.
Although we tried different adjustments, we did not manage to solve this problem completely. Therefore, the AI paddle's behaviour remained one of the limitations of our final implementation.

5. Testing
By testing functions individually in Google Colab, we could check each function and see if it worked properly. We also tried different inputs to check that the functions returned the correct values.
On the other hand, for functions that needed the Pygame library, we tested them by running the program multiple times after each function had been completed and checking that everything worked properly.
We also checked that the different functions worked correctly together in the final game and that the changes did not affect other parts of the program.

7. Optional features
We added an extra option that allows the user to choose whether they want to play against the machine.
This question appears in main(), after the user has configured the game dimensions and colours.
This feature gives the user more control over the game and provides another way to play.

8. Use of AI Tools
AI tools were used to help fix bugs or errors that appeared when running the program. They were also useful for understanding some parts of the code and finding possible solutions to programming problems.
We also used AI to better understand the requirements of some functions, as some instructions were not completely clear. This helped us understand what each function was expected to do before implementing it. Overall, AI tools were used as a support tool during the development of the project, helping us understand the code, solve problems and improve our programming skills.
