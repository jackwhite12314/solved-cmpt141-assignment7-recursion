Download Link: https://assignmentchef.com/product/solved-cmpt141-assignment7-recursion
<br>
<strong>Question 1</strong>

<strong>Purpose: </strong>To practice recursion with a simple example.

<strong>Degree of Difficulty: </strong>Easy.

The evil Team Rocket has invented an incredible new space-ship! The ship works as follows:

<ul>

 <li>If the distance to the destination is greater than 1 meter, the ship will “fold space” and “jump” to a position exactly half way to the destination. It takes exactly <strong>one minute </strong>to perform this process.</li>

 <li>Any distance of <strong>1 mete</strong>r or less will take exactly <strong>one minute</strong>, using normal impulse rockets.</li>

</ul>

For example, if the ship has to travel 10 meters, it will jump 5 meters after the first minute, 2.5 meters the second minute, 1.25 meters the 3rd minute, and 0.625 meters the fourth minute. Finally, the remaining 0.625 meters takes one more minute. Thus the total time to travel 10 meters is 5 minutes. (That seems very slow, and it is for small distances; the true value of this method only reveals itself for large distances.)

Write a recursive function called spaceTime() that calculates the time needed for Team Rocket’s new ship to travel a given distance (in meters). The distance to travel must be a parameter to the function, and the function itself must not do any console input.

Test your function out on all of the following examples:

<ul>

 <li>Distance from Team Rocket’s base to the nearest Poke-Stop : 37 meters.</li>

 <li>Distance for a round-trip around the entire planet earth: 40075000 meters.</li>

 <li>Average distance between our earth and our sun: 1.49e11 meters (about 150 million km).</li>

 <li>Approximate distance between the sun and the closest star: 4.0e16 meters (about 4 light-years). Size of the observable universe: 8.8e26 meters (about 93 Giga-light-years)</li>

</ul>

<h1>Sample Run</h1>

Here is an example execution of the required program.

<table width="652">

 <tbody>

  <tr>

   <td width="652">Team Rocket’s drive requires:–                      7 minutes to travel 37 meters to the nearest Poke-Stop–                      27 minutes to travel 40075000.0 meters for a round-trip around the earth–                      39 minutes to travel 149000000000.0 meters from our earth to our sun–                      57 minutes to travel 4e+16 meters from our sun to the nearest star – 91 minutes to travel 8.8e+26 meters across the observable universeWOW, IS TEAM ROCKET EVER BLASTING OFF AGAIN!!</td>

  </tr>

 </tbody>

</table>




Your console output doesn’t have to look exactly like the above. Copy/paste your output for all of the  examples above into a document called a7q1_output.txt for submission.

<strong>Question 2 </strong>

<strong>Purpose: </strong>To practice recursion on a problem that can be split into parts

<strong>Degree of Difficulty: </strong>Moderate

Aspiring pokemon trainer Ash Ketchum has caught a lot of pokemon. To keep them healthy, he regularly feeds them vitamins. However, the vitamins are bigger than what a pokemon can swallow in one bite, and so when Ash’s pokemon team is given a vitamin, they will break it apart into smaller pieces.

Sometimes, though, the vitamin is SO big, that the pokemon have to break it apart more than once! Here is how the process works:

<ul>

 <li>If the vitamin’s weight is less than or equal to 0.1 grams, it is small enough to eat, and doesn’t need to be broken. Thus, there is 1 edible piece for 1 pokemon.</li>

 <li>Otherwise, the pokemon will team up to smash the vitamin into pieces of equal weight. The number of new pieces seems to be random (the pokemon can be a bit excitable), either 2, 3, or 4, but the weight of each new piece is the same (one-half, one-third or one-quarter of the previous piece). The pokemon will then break each of these pieces again until they are small enough to swallow.</li>

</ul>

For example, suppose the initial vitamin weighed 0.6 grams. The pokemon break it once, and we randomly determine that the vitamin breaks into 2 parts (each part weighs 0.3 grams). The pokemon break the first 0.3 gram piece, which breaks into 3 pieces. Since these pieces will each weigh 0.1 grams, they are now edible, so we have 3 edible pieces so far. The pokemon will then break the second 0.3 gram piece; this time, it breaks into 2 parts, each of which weighs 0.15 grams, which are still too large to eat. The pokemon break each of these parts again; the first breaks into 3 parts, each weighing 0.05 grams, so we have 3 more pieces. The second breaks into 4 parts, each weighing 0.0375 grams, so that’s another 4 pieces. There are no longer any pieces larger than 0.1 grams, so the total number of edible pieces is 3 + 3 + 4 = 10 pieces. So in this case, 10 different pokemon are able to get their vitamin dosage from a single, original 0.6 gram vitamin.

Tracing through the problem like in the paragraph above is exhausting! But if you bring yourself to trust in the power of recursion, solving this problem is not hard at all.

For this question, your task is to write a recursive program that will calculate how many edible vitamin pieces are made whenever a pokemon team is given a vitamin that weighs W grams.

<h1>Program Design</h1>

<ul>

 <li>Write a recursive function that simulates the breaking of a single vitamin. The weight of the vitamin (as a float) should be a parameter to your function. The function should return an integer, indicating the number of edible pieces produced from breaking the vitamin.</li>

</ul>

To write this function, you will need to use random numbers for when the vitamin is broken into parts. If you first import random as rand, then the expression rand.randint(a,b) will give you a random number in the range from <em>a </em>to <em>b </em>(including <em>a </em>and <em>b</em>). <strong>For this question, you ARE allowed to use a loop in your recursive function if you like; however, recursion should still do the “real work”</strong>. For instance, you might want to use a loop to iterate over the number of vitamin pieces created from a single smash.

<ul>

 <li>In the ’main’ part of your program, write a few lines of code that asks the user for the size of a vitamin, and uses a loop that will <strong>call your piece-counting recursive function 1000 times</strong>. Use the results of those 1000 simulations to report the average number of edible pieces produced from a vitamin.</li>

</ul>

An example of your program running might look like this:

How big is the vitamin, in grams? 1.0

<table>

 <tbody>

  <tr>

   <td> </td>

  </tr>

 </tbody>

</table>

On average, a pokemon team can get 18.774 bite-sized pieces from a 1 gram vitamin!

Note that because of the randomness involved you might never get this exact result with an input of 1.0 grams but it should be pretty close.

Run your program using vitamins of weight 5, 10 and 100 grams. Copy/paste your output for all of the examples above into a document called a7q2_output.txt for submission.

<strong>Question 3:</strong>

<strong>Purpose: </strong>To practice recursion on a classic problem

<strong>Degree of Difficulty: </strong>Tricky.

<strong>Nim </strong>is a 2-player game where the players take turns picking up sticks from a pile. On their turn, a player can pick up either 1, 2, or 3 sticks. The player who picks up the last stick loses.

Your job is to write a <strong>recursive function </strong>that determines, for a given number of sticks, the winner of the game assuming that both players play optimally. Your function should take <strong>exactly 2 </strong>parameters: an integer indicating the current number of sticks, and a boolean indicating which player is currently to move. It should return the boolean value True if player 1 (the player that took the very first turn) will win and False otherwise.

For example, if there are 4 sticks left and player 1 is to move, then player 1 can win by taking 3 sticks. This will leave only 1 stick left, which player 2 will have to pick up, thus losing the game.

This might sound a little difficult, especially the assumption that players will play optimally, but with the power of recursion, this is not a complicated problem. Your general approach should be to use recursion to simply <strong>try all possible moves </strong>(i.e. make 1 recursive call for each amount of sticks that can be removed) in each position.

Your function should be <strong>no longer than 12 lines of code </strong>(not counting comments) and possibly less (ours is 9). If you find your solution is getting any longer than that, you are overthinking it!

<h1>Sample Run</h1>

The output for your program might look something like this:

<table>

 <tbody>

  <tr>

   <td> </td>

  </tr>

 </tbody>

</table>

Enter the number of sticks for nim: 9

<table>

 <tbody>

  <tr>

   <td> </td>

  </tr>

 </tbody>

</table>

Will player1 win? False

<h1>Extra Notes</h1>

Nim is a well-known problem, and it is of course possible to come up with a mathematical rule that will tell you which player will win. You won’t get any marks for doing this though, as the point of the assignment is to practice using recursion.


