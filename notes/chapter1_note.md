# CHAPTER 1. INTRODUCTION 

### What is RL?

- RL is a computational approach to learning from interactions (much like human)
- RL can either be a class of problems, a class of solutions, or the field that studies both

- there are 2 distinct features of RL
1. trial and error 
2. delayed reward (maximizing a reward signal)

- a key feature of RL is that it explicitly considers the whole problem of a goal-directed agent interacting with an uncertain environment
- correct choice requires taking into account indirect, delayed consequences of actions, and thus may require foresight or planning

### Elements of RL 

- RL uses the formal framework of Markov decision processes to define the interaction between a learning agent and its environment in terms of states, actions, and rewards

1. **policy**: a mapping from perceived states of the environment to actions to be taken when in those states
2. **reward system**: the goal of the a RL problem (a number for the agent to optimize)
3. **value function**: the total amount of reward an agent can expect to accumulate over the future
  - what's good in the long run
  - it's much harder to determine than rewards 
4. **model of the environment** (optional): something that mimics the behavior of the environment → allows inferences to be made about how the environment will behave
  - used for planning
  - there are 2 methods
    - **model free** (explicitly trial-and-error)
    - **model based methods** (uses models and planning)

- RL relies heavy on the concept of **state**
  - as input to the policy ad value function
  - as both input to and output from the model
- **evolutionary methods**: policies that obtain the most reward, and random variations of them, are carried over to the next generation of policies, and the process repeats


### An example: Tic Tac Toe (3x3)

- the agent:
- consider draws and losses to be equally bad (since in 3x3 Tic Tac Toe, you can never lose with perfect play)
- the opponent is an imperfect player
- *how might we construct a player that will find the imperfections in its opponent’s play and learn to maximize its chances of winning*

- the approaches to this problem

#### Minimax 
- is not correct because it assumes a particular way of playing by the opponent
- example: a minimax player would never reach a game state from which it could lose, even if in fact it always won from that state because of incorrect play by the opponent

#### Dynamic Programming 
- solve the problem by _computing_ an optimal solution for any opponent, but require as input a complete **specification of that opponent**
  - including the probabilities with which the opponent makes each move in each board state - not available a priori
  - such information can be estimated from experience - playing many games against the opponent → learn a model of the opponent’s behavior (up to some level of confidence) → apply dynamic programming to compute and optimal solution

#### Evolutionary method 
- solve the problem by searching the space of possible policies (a rule that tells the player what move to make for every state of the game) for one with a high probability of winning
  - the probability for each policy is estimated by playing many games
  - the frequency of wins is used to direct the next policy selection
  - each policy change is made only after many games, and only the final outcome of each game is used (what happens during the games is ignored)

#### The Approach of making use of a Value function 

**1. Set up a table of numbers (one for each possible state of the game)**  
  - each number will be the latest estimate of the probability of our winning from that state → the state’s **value**
  - the whole number is the learned **value function**

**2. we set the initial values of all the states to 0.5**

**3. we the play many games againts the opponent**
  - to select the moves we examine the states that would result from each of our possible and look up their current values in the table
  - most of the time we move **greedily**
  - occasionally, we select randomly from among the other moves instead → **exploratory moves**

 **4. while playing we update the states' values using the formula** $V(S_t) \leftarrow V(S_t) + \alpha[V(S_{t+1} - V(S_t))]$
   - $\alpha$ is a small positive fraction call **step-size parameter**, which influences the rate of learning
   - if the step-size parameter is reduced properly over time, then this method converges, for any fixed opponent, to the true probabilities of winning from each state given optimal play by our player
   - if the step-size parameter is not reduced all the way to zero over time, then this player also plays well against opponents that slowly change their way of playing
