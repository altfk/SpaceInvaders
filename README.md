# This game has been developed by Nawal Gurung
# I adapted the game for a Geocaching Mystery
# e-Mail: altf11@gmx.de

###### Shortended version of the original Readme ########
# **JavaScript Game**

**Technologies used**
* JavaScript (ES6)
* jQuery
* HTML5 + HTML5 Audio
* CSS + GitHub

**My Game** - Space Invaders
You can find a hosted version here : https://nawalgurung.com/GA-Project-1/

# **Game overview**
Space Invaders is a classic arcade game from the 80s. The player can only move right and left and aims to shoot an invading alien armada, before it reaches the planet's surface using a mounted gun turret.
The aliens also move from left to right, and also down each time the reach the side of the screen. The aliens also periodically drop bombs towards the player.
Once the player has destroyed a wave of aliens, the game starts again. The aim is to achieve the highest score possible before either being destroyed by the aliens, or allowing them to reach the planet's surface.

The main idea of this project was to create a game using basic grid layout so the spaceship is able to move left and right. This was created by a list of  (20 x 20) 'div's in the HTML. Each divs within the grid is an individual element. These divs are nestled within a container. The spaceship, aliens, laser and explosions were created by applying classes to the elements within the grid. When these elements are moved, their class is also removed from the div of their current position and applied to the new div which becomes their new current position.
I created the aliens in an array and displayed them on the grid by adding class aliens to the divs. Their movement patterns are created by moving the index of the aliens array with a for each loop and then passing the aliens indexes on the the div index to display.
To move the player's lasers and alien's bombs I created a function with a set interval to move the index of player's laser upwards and alien bomb class downwards every few milliseconds. Within this function, I incorporated collision detection condition, so that when the players laser hits the alien it initiates the explosive sprite sheet class and removes the alien.

# **Challenges**
There were several timings and aliens direction bugs that I had to deal with. For example, if the last alien died at left edge of the screen would mean that the global variable for next wave of aliens is still left instead of right (default value). As the aliens wave are generated at div index 0 this led to error as the new wave of alines indexes would go - 1, -2, -3 when it should go right 0, 1, 2. I fixed this error by generating the aliens from the centre of the grid on all cases which meant that the new wave of alien could go right or left and when they reach the edge of the grid the aliens would move down a row.

# **Wins**
In this project, I had to work with arrays and various array methods to build the main logic of the game. Timings events were also crucial part of this project as a lot of features depended on it and I managed to used it to create some of the main features that showed movement in the game including explosive sprite sheet animation.
I was particularly pleased with my function that made use of localStorage to keep a record of score board. This gave more meaning to the game as user would try to be on the score board of top 5.
