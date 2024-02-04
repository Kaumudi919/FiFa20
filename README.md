### FiFa20

FIFA 20 Football is arguably the most popular sport in the world and FIFA is the most popular football (soccer) simulation game by Electronic Arts (EA Sports).<br>
##### Problem Statement:
Explore football skills from given FIFA 20 data and cluster football players based on their skills.<br>

#####Attribute Information : 
The attributes used in the project are:
●	Name: Name of the player. 
●	Age: Age of the player.
●	Height: Height of the player in inches (transformed to centimeters in preprocessing).
●	Overall: General performance quality and value of the player representing the key positional skills and international reputation rated between 1-99. Overall attribute is used only in preprocessing and discussion stages because using it in modelling could lead to domination by this feature. The aim of the project is not basically sort and categorize the players using their overall talent and international reputation, but to cluster them based on using their whole skillset.
●	Potential: Maximum Overall rating expected to be reached by a player in the top of his career rated between 1-99.
●	PreferredFoot: Right or Left. Label encoder is applied as 0 for left and 1 for right.
●	WeakFoot: Represents how well a player uses his weak foot (e.g. left for righties) rated between 1 to 5.
●	WorkRate: Degree of the effort the player puts in terms of attack and defense rated as low, medium and high. This feature is divided into two new features as AttackWorkRate and DefenseWorkRate. Besides, label encoder is applied as 0 for low, 0.5 for medium and 1 for high.
●	Position: Position of the players on the pitch which determines their roles and responsibilities in the team. Forward positions in the football and FIFA 19 can be grouped as striker (ST: Center striker, RS: right striker, LS: left striker), forward (CF: center forward, RF: right forward, LF: left forward) and winger (RW: right winger, LW: left winger). The word, forward, is used both as a general term and a special position. Strikers are positioned in front of forwards and wingers and very closed to the opposing goal. Their main responsibilities are attacking and scoring goals, that’s why their ball control, shooting and finishing skills are expected to be well. Center forwards are positioned right behind the strikers. They are expected to receive balls from the others and score assists to the others or goals. In addition to the skills expected from strikers, they have to be good at passing. Right forwards and left forwards are positioned at the right and left of the center forwards with the same expectations. Wingers are positioned near the touchlines to create chances for strikers and forwards from the right and left side of the field by breakthrough and crosses and to score goals. They are expected to be good at dribbling, acceleration, passing and crossing. Positions are used only in preprocessing and discussion stages. 
●	ST: Positional skill. Player’s general ability when playing in ST position rated between 1-99.
●	RS: Positional skill. Player’s general ability when playing in in RS position rated between 1-99.
●	LS: Positional skill. Player’s general ability when playing in in LS position rated between 1-99.
●	CF: Positional skill. Player’s general ability when playing in in CF position rated between 1-99.
●	RF: Positional skill. Player’s general ability when playing in in RF position rated between 1-99.
●	LF: Positional skill. Player’s general ability when playing in in LF position rated between 1-99.
●	RW: Positional skill. Player’s general ability when playing in in RW position rated between 1-99.
●	LW: Positional skill. Player’s general ability when playing in in LW position rated between 1-99.
●	Crossing: Crossing skill of the player rated between 1-99. Cross is a long-range pass from wings to center.
●	Finishing: Finishing skill of the player rated between 1-99. Finishing in football refers to finish an attack by scoring a goal.
●	HeadingAccuracy: Player’s accuracy to pass or shoot by using his head rated between 1-99.
●	ShortPassing: Player’s accuracy for short passes rated between 1-99.
●	LongPassing: Player’s accuracy for long passes rated between 1-99.
●	Dribbling: Dribbling skill of the player rated between 1-99. Dribbling is carrying the ball without losing while moving in one particular direction.
●	SprintSpeed: Speed rate of the player rated between 1-99.
●	Acceleration: Shows how fast a player can reach his maximum sprint speed rated between 1-99.
●	FKAccuracy: Player’s accuracy to score free kick goals rated between 1-99.
●	BallControl: Player’s ability to control the ball rated between 1-99.
●	Balance: Player’s ability to remain steady while running, carrying and controlling the ball rated between 1-99.
●	ShotPower: Player’s strength level of shooting the ball rated between 1-99.
●	Jumping: Player’s jumping skill rated between 1-99.
●	Penalties: Player’s accuracy to score goals from penalty rated between 1-99.
●	Strength: Physical strength of the player rated between 1-99.
●	Agility: Gracefulness and quickness of the player while controlling the ball rated between 1-99.
●	Reactions: Acting speed of the player to what happens in his environment rated between 1-99.
●	Aggression: Aggression level of the player while pushing, pulling and tackling rated between 1-99.
●	Positioning: Player’s ability to place himself in the right position to receive the ball or score goals rated between 1-99.
●	Vision: Player’s mental awareness about the other players in the team for passing rated between 1-99.
●	Volleys: Player’s ability to perform volleys rated between 1-99.
●	LongShots: Player’s accuracy of shoots from long distances rated between 1-99.
●	Stamina: Player’s ability to sustain his stamina level during the match rated between 1-99. Players with lower stamina get tired fast.
●	Composure: Player’s ability to control his calmness and frustration during the match rated between 1-99.
●	Curve: Player’s ability to curve the ball while passing or shooting rated between 1-99.
●	Interceptions: Player’s ability to intercept the ball while opposite team’s players are passing rated between 1-99. It is a defensive skill.
●	StandingTackle: Player’s ability to perform tackle (take the ball from the opposite player) while standing rated between 1-99. It is a defensive skill.
●	SlidingTackle: Player’s ability to perform tackle by sliding rated between 1-99. It is a defensive skill.
●	Marking: Player’s ability to apply strategies to prevent opposing team from taking the ball rated between 1-99. It is a defensive skill.  

##### The remaining feature is the abbrevation of football position score:
* LS:Long snapper or left striker.
* ST:Striker
* RS:Right striker
* LW:Left sided wingers.
* LF:Left forward
* CF:Center forward
* RF:Right forward
* RW:The RW is usually on the right end of the attacking trident, with the Striker and Left Winger, which mainly contributes to the team in terms of goals and assists.
* LAM:Left attacking midfield
* CAM:Center attacking midfield
* RAM:Right attacking midfield
* LM:Left midfield
* LCM:Left center midfield
* CM:Center Midfield
* RCM:Right center midfield
* RM:Right midfield
* LWB:Left Wing Back
* LDM:Left defensive midfield
* CDM:Center defensive midfield
* Right defensive midfield
* RWB:Right wing back
* LB:Left back
* LCB:Left center back
* CB:Center back
* RCB:Right center back

##### Data Preprocessing:

•	Checking basic informations of the dataset.
•	Checking for the null values, there are some features which are player_tags, loaned_from nation_position, nation_jersy_number, gk_diving, gk_handling, gk_kicking, gk_reflexes, gk_speed, gk_positioning and player_traits has more than 50% missing null values so in this case we are dropped it. Some unique features also dropped like that sofifa_id, team_jersey_number, player_url, short_name, long_name and dob.
•	Remaining less than 50% missing values removed by imputing method. For imputing method checked distribution of data. 
•	Data split into numerical, categorical and numerical data which has object datatype.

1.Handling numerical data :
•	For numerical data distribution is not normally distributed.so data imputed by median value.
•	Numerical columns are more so check for correleation of data and remove highly correleated data.
•	Check outliers of numerical data and data also not normally distributed so handling outliers use IQR method.
2. Handling numerical data which has object datatype:
•	Numerical data which has object datatype for player positions are ls, st, rs,  lw, lf, cf, rf, rw, lam, cam, ram, lm, lcm, cm, rcm, rm, lwb, ldm, cdm, rdm, rwb, lb, lcb, cb, rcb and rb.
•	There is some NAN values replace those by 0 using fillna() function. And change datatype of these data into int.
•	Checking correleation of that data and remove highly correleated data.
•	Handling outliers of data using IQR method.
3.Handling categorical data:
•	In the categorical data using one hot encoding data converted into numerical data.

•	Concatenate all these data.
•	Apply scaling technique on data which is minmax scaling.
•	Now, data is ready to passed to machine learning algorithm.

