# Database_league
A database system and web app for a fantasy soccer application. No longer live hosted at the moment and no more updates in future.

<h2>Er Diagram</h2>
<img src="Diagrams/ER Diagram.png"><br />
<h2>Relational Database Diagram</h2>
<img src="Diagrams/relational.png"><br />
<h2>Sample Queries:</h2>
<b>Returns the number of players on teams with players shooting above 20% by alphabetical order<br> Query:</b><br>
SELECT players.team, COUNT(players.team) as 'Players Above 20%' FROM players WHERE players.goals/players.shots>.18 GROUP BY players.team ORDER BY players.team ASC

<b>Returns fantasy teams where over 30 points have been scored and their current player is under the age of 29. Sorted by age youngest to oldest.<br> Query:<br></b>
SELECT ut.team_name, players.name, ut.points, players.age from user_teams as ut INNER JOIN players on ut.roster = players.playerID WHERE ut.points>30 and players.age<29 ORDER BY players.age ASC

<b>Returns the name of the player on the users team This is used to let users know what the players name is that is on their roster.<br>Query:<br></b>
SELECT players.name FROM players INNER JOIN user_teams ON players.playerID=user_teams.roster WHERE user_teams.accountID = ?
