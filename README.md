### The House Always Wins: Simulating the Martingale Roulette Strategy

Can a gambler beat roulette by doubling their bet after every loss? This project uses Monte Carlo simulation to test the Martingale strategy, and finds that it loses money on average.

#### Question

Is the Martingale strategy in roulette profitable under real-world restrictions?

#### Method
Python simulation of a single casino visit on an American roulette wheel (18 red, 18 black, 2 green pockets, so each bet wins with probability 18/38)
Each visit ends when the player reaches a target winnings amount, goes bankrupt, or hits a limit on the number of spins
Apply a casino maximum wager and prevent bets larger than the player's remaining budget
Simulate 10,000 visits to estimate expected profit, relying on the Law of Large Numbers
Repeat the simulation across six starting budgets ($100 to $350), simulating 10,000 visits for each, to test whether a bigger bankroll helps

Default parameters: $200 starting budget, $300 exit, 200 spin maximum, $100 maximum wager.

#### Findings
**The strategy is not profitable.** Average profit was about –$36.65 per visit under the default parameters. 
**A bigger budget makes things worse.** Average profit became more negative as the starting budget increased, because each bankruptcy became more expensive.
**The house always wins.** Every $1 bet has an expected value of about –5.3 cents because of the two green pockets.
**Visits look good until they don't.** Individual visits often climb steadily, but a single bad luck streak wipes out the budget. In five sample visits, three ended in bankruptcy, two of them within 25 spins.

#### Files
roulette_martingale.ipynb: blog post for the assignment

#### Tools
Python, NumPy, pandas, Matplotlib

#### Disclaimer
Completed as a blog post assignment for DS 2026: Computational Probability at the University of Virginia.