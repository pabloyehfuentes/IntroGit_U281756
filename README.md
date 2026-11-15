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


2. Overview of your design
main()
   Configuration (comes before the Game loop)
      configuration returns five values that can be adjusted by the user, paddle_h, paddle_speed, speed_ball_x, speed_ball_y, ball_radius. In the get_config() it get ask_yes_no to prompt the user if they want to change the values that have been preassigned. Then read_int_in_range() finds if the input value is valid, which must be an integer in a predefined range. Here we already see values traveling without global variables, read_int_in_range() uses parameters which show the maximum and minimum value that is accepted. This is similar to change_colors() which returns a tuple of (backg_col, foreg_col) it also uses ask_yes_no() and read_int_in_range() to make sure the input is between 0 - 255, for green, red and blue.

   Game Loop
      the variables for the game (paddle positions, ball position and velocity, and scores) are stored locally in the main(). Since each function receives values as parameters and returns new ones. For example, collide_ball_walls() receives positional values of the ball and dimensions of the screen, and then returns a new position and velocity of the ball when it hits a wall.
      this idea works with get_config() values, the value is returned once and then it is passed as parameters to any function that needs it.

3. Key implementation decisions
One important decision was not to use global variables. Instead, we used parameters to pass information between functions and return values to get the results. This makes the code easier to understand and test.
We also decided to separate the configuration from the game loop. This allows the user to change the game settings before starting to play.
Another decision was to divide the program into smaller functions, so each function has a specific task. This makes the code easier to test and helps us find errors.
Finally, we added the option to play against the machine, allowing the user to choose how they want to play. 


5. Problems and solutions

When writing the code for the machine, it would not respond quickly to reach the ball making it very easy for the player to win. I could not find a solution for this, I tried to make the AI paddle faster but even then it made mistakes, such as moving excessively or staying still when it should have rearranged itself to meet the ball. 

5. Testing
   By testing functions individually in Google Colab, we can test each function and see that it works properly. On the other hand for functions that needed the pygame library, by running the program multiple times after each function had been completed and checking that it worked properly was enough testing. 

7. Optional features
- Added a user input asking if the user would like to play against the machine or not in the main loop, right after the configuration of the colors and dimensions.

8. Use of AI Tools
AI tools were used to help fix bugs or errors that appeared when running the program. They were also useful for understanding some parts of the code and finding possible solutions to programming problems. It also helped us understand why certain errors appeared and how we could correct them.
Overall, AI tools were used as a support tool during the development of the project.
