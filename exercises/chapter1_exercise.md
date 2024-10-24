### Exercise 1.1: Self-Play  
Suppose, instead of playing against a random opponent, the reinforcement learning algorithm described above played against itself, with both sides learning. What do you think would happen in this case? Would it learn a different policy for selecting moves?  

_My Solution_
- I think it'll learn to beat itself, with both the evolutionary method and the value function method
- Although with the value function method, I think it'll take more time for the algorithm to learn 
  - examples: at the beginning, all the moves have a probability of 0.5, all moves are random basically. Player A may make a dumb move, which results in player B will not learn as much as playing with an opponent who knows how to win from the beginning

_Key_

### Exercise 1.2: Symmetries  
Many tic-tac-toe positions appear different but are really the same because of symmetries. How might we amend the learning process described above to take advantage of this? In what ways would this change improve the learning process? Now think again. Suppose the opponent did not take advantage of symmetries. In that case, should we? Is it true, then, that symmetrically equivalent positions should necessarily have the same value?  

_My Solution_

_Key_


### Exercise 1.3: Greedy Play  
Suppose the reinforcement learning player was greedy, that is, it always played the move that brought it to the position that it rated the best. Might it learn to play better, or worse, than a nongreedy player? What problems might occur?  

_My Solution_

_Key_


### Exercise 1.4: Learning from Exploration  
Suppose learning updates occurred after all moves, including exploratory moves. If the step-size parameter is appropriately reduced over time (but not the tendency to explore), then the state values would converge to a different set of probabilities. What (conceptually) are the two sets of probabilities computed when we do, and when we do not, learn from exploratory moves? Assuming that we do continue to make exploratory moves, which set of probabilities might be better to learn? Which would result in more wins?

_My Solution_

_Key_


### Exercise 1.5: Other Improvements  
Can you think of other ways to improve the reinforcement learning player? Can you think of any better way to solve the tic-tac-toe problem as posed?

_My Solution_

_Key_

### Exercise 4: Joining two Gaussian variables  
Let $X$ and $Y$ are two Gaussian continuous random variables over $ \mathbb{R}$, i.e., $ X \sim N (\mu_1, \sigma_1^2)$, $Y \sim N (\mu_2, \sigma_2^2)$, let $ Z = X + Y$. Which of the following are true statements, explain:

1. $Z$ also has normal distributions
2. $E[Z] = \mu_1 + \mu_2$. Can you derive $Var(Z)$?

### Exercise 5  
Let $x \in \mathbb{R}^{N \times 1}$, compute the derivative of $\frac{df}{dx}$ with  
a) $f = x^Tx$  
b) $f = xx^T$

### Linkie 
- [Latex cheatsheet](https://wch.github.io/latexsheet/latexsheet.pdf) 





 
