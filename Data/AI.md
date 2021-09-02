### AI
While moving through the house, the player will have to contend with various computer-controlled AI players. A director will be responsible for the following: 
 * Adding AI elements to the game.
 * Figuring out how much HP the AI elements have.
 * Calculating the current menace. How much the player is under.
 * Backing off menace when required.
 * Increasing menace when required

Pressure at any time in the game.  When the player is under a higher amount of "pressure", they will have less ability to steal loot; however, when the "pressure" is reduced, the player will have more scope and space to complete the game's actions.

#### AI Type: Ghosts
The first level adversary of the game that the player will face is the ghost. These phantasms represent the stock enemy of the player.
 * Ears. In this world, ghosts have ears. When a player is searching for items, this will make noise
 * Sight Cone. They will have limited vision in front of them.

Ghost Attributes:
 * Hitpoints: How many hit points a ghost has before it dies
 * Aggression: How aggressive the ghost is.

#### AI Type: Cops
Will activity hunt the player and arrest them to end the game. When one cop spots the player, he will alert the others via radio. These cops may start activity hunting the player depending on their aggressiveness and menace.

#### AI Type: Residents
Will walk in their house from room to room. Not activity looking for the player. Will call the police if they see the player.  This will then cause the police to spawn in the current map and start hunting the player.

#### Jobs
Jobs will happen with a tree. More advanced jobs will be added to the tree when game events happen so enemies will do new things to the player.
 * Patrolling. While in this mode, enemies will move around across their nav meshes with no patterns. 
 * Attacking: Enemy has its sensors activated and is currently trying to attack the player.
 * Swarming: Ghosts will look to group up against the player. This node will only be added when there is a low level of menace.

#### Menance
A menace value will be calculated at all times to tell the AI director how to build up the AI and what enemies to inject and what hitpoints and aggression the enemies have. Factors that will affect the "menace score" are:
 * Current enemy count on the map
 * Current Player Health
 * Player Powerups
During the game, the menace factor will modulate up and down. This modulation will be handled by a leaky bucket algorithm. The higher the player scores, the more the bucket will fill. The more full the bucket, the harder it will be to complete game goals. Menace floor value will increase as game time progresses, meaning that the game will get harder and harder the more further the player can proceed.