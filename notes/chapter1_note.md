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


### An example: Tic Tac Toe 
