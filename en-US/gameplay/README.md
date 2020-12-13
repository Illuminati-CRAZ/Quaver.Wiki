---
name: Gameplay
---

# Quaver Gameplay

This section explains the different parts of gameplay within Quaver. It gives a synopsis of how the game is played, its scoring, rating, and grading systems, and much more!

## Game Mode: Keys

<center>
![](/docs/images/gameplay.jpg)
</center>

Quaver is built to support multiple game modes, but the main focus of the game is the Keys game mode. The concept of this game mode has been used in a variety of different rhythm games such as Beatmania, Dance Dance Revolution, and osu!.

The concept of the game mode is simple - notes fall down from the screen (or up depending on scroll direction), and the objective is to press the correct key at the correct time.

Quaver has both 4 Keys (4K) and 7 Keys (7K) which are treated as two game modes and have separate leaderboards for them.

The game also has the potential to be skinned and played with upwards scrolling - which ultimately makes the game able to look and feel like a majority of different rhythm games. It has support for colored arrow skins (DDR), or bar skins (Beatmania-styled).

### Scoring Systems

This section explains the different types of scoring and grading systems Quaver has.

#### Grading

This section outlines the accuracy percentage that is needed to achieve each grade.

| Grade | Accuracy                                                   |
| ----- | ---------------------------------------------------------- |
| X     | 100% (Only achievable by getting all Marvelous judgements) |
| SS    | 99%                                                        |
| S     | 95%                                                        |
| A     | 90%                                                        |
| B     | 80%                                                        |
| C     | 70%                                                        |
| D     | <70%                                                       |
| F     | Failed                                                     |

#### Accuracy

Accuracy is a weighted average of received judgements out of the sum of judgements throughout a play.

You receive one judgement per regular note and two judgements for a long note (press and release).
Okays are weighted less than misses to discourage mashing.

| Judgement | Weighting |
| --------- | --------- |
| Marvelous | 100%      |
| Perfect   | 98.25%    |
| Great     | 65%       |
| Good      | 25%       |
| Okay      | -100%     |
| Miss      | -50%      |

#### Performance Rating

Your performance rating is an assessment of your performance throughout a given play in correlation to the map's difficulty rating. It is the same metric that is used to measure scores in global rankings.

The formula is relatively simple with it being:

`PerformanceRating = DifficultyRating * Math.Pow(Accuracy / 0.98, 6);`

#### Overall Rating

Your overall rating is a weighted sum of all your plays in the Keys (4K or 7K) game mode. 4K and 7K are separate and have two different leaderboards.

Only your top score will account for the full amount of score rating, and it will decrease will each lower score.

The weighted sum calculation is similar to Performance Points, used in the rhythm game osu!.

`OverallRating = PerformanceRating[1] * 0.95^0 + PerformanceRating[2] * 0.95^1 + PerformanceRating[3] * 0.95^2 + ...`

#### Score

Score is another measurement of your performance throughout a play in Quaver. It is mainly a measurement of how frequently you are able to combo in correlation to the judgements received. It isn't used in any metric for global rankings and is purely in the game as a form of "XP." Score is capped at 1 million points.

#### Judgement Timing Windows

This section explains the judgement windows that are used within Quaver. It details the time in milliseconds needed to press a key for a note in order to receive it. Currently there is one standard judgement timing window in Quaver, however this may change in the future.

Long note release windows are 50% larger than the standard judgement windows.
Not releasing a long note results in a Good.

| Judgement | Window |
| --------- | ------ |
| Marvelous | ±18ms  |
| Perfect   | ±43ms  |
| Great     | ±76ms  |
| Good      | ±106ms |
| Okay      | ±127ms |
| Miss      | ±164ms |

#### Combo

Combo is when you successfully hit objects without missing.

* Not pressing an object within its judgement timing windows will result in a Miss, resetting your combo.
* Pressing an object too early (128-164ms) will result in a Miss, resetting your combo.
* Not releasing a long note will result in a Good, which does not reset your combo.

### Skins

You can completely customize the game to your liking. [See the Skins/Keys section of the wiki](/docs/Skins/Keys).
