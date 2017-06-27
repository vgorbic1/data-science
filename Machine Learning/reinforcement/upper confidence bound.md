## Upper Confidence Bound (UCB)
UCB may help in solving the Multi-Armed Bandit Problem:
- We have *d* arms. For example, arms are ads that we display to users
each time they download a web page.
- Each time a user connects to the page, that makes a round.
- At each round *n* we choose one ad to display to the user.
- At each round *n* ad *i* gives reward *r<sub>i</sub>(n) E {0,1}: r<sub>i</sub>(n) = 1* if the user
clicked on the ad *i*, and 0 if the user didn't.
- Our goal is to maximize the total reward we get over many rounds.
