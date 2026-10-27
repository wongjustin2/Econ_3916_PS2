# Problem Set 2 -- Did the Onboarding Redesign Work?

## Objective
I checked whether the PM's claim that satisfaction rose from 3.6 to 4.3 after the onboarding redesign holds up when only some users answer the survey.

## Methodology
- I simulated 50,000 users per period with a true mean satisfaction of 3.30 before the redesign and 3.40 after it.
- I added a response mechanism where the chance of answering depends on satisfaction itself and matched the PM's observed means of 3.60 and 4.30.
- I bootstrapped the mean and the median by hand and with scipy.stats.bootstrap and compared percentile and BCa intervals.
- I ran a coverage simulation over 1,000 repeated surveys and reported each coverage with its Monte Carlo SE.
- I ran a two-sample t-test with Cohen's d and a power analysis and simulated whether a larger sample makes the estimate better.
- I asked an AI to write inverse-probability weighting code and revised my prompt once to give it my variable names.

## Key Findings
- The apparent improvement of 0.704 points comes mostly from who answered because the true improvement is only 0.096 points.
- The response rate fell from 27.5% to 15.2% so the survey that produced the better number heard from fewer people.
- The intervals from the real survey contained the true mean 0.0% of the time and the intervals from a random survey contained it about 95% of the time.
- A larger sample makes the estimate more precise but the estimate stays about 0.61 points above the true improvement.
- Inverse-probability weighting on engagement and support tickets only moved the post-redesign mean from 4.304 to 4.143 against a true mean of 3.386.
- Post-redesign satisfaction among the users who answered is 4.30 (95% CI 4.29 to 4.32) and the fix is to survey a random sample of users and follow up until almost all of them answer.
