# ironman
This repository contains code that analyzes the [Ironman](https://www.ironman.com/) triathlon finisher data publicly available on sites such as Ironman's site, [Athlinks](https://www.athlinks.com/search/events?category=events&filters=%7B%22dateRangeFilter%22%3A%7B%22enabled%22%3Afalse%2C%22value%22%3A%7B%22from%22%3A%22%22%2C%22to%22%3A%22%22%7D%7D%2C%22locationFilter%22%3A%7B%22enabled%22%3Afalse%2C%22value%22%3A%7B%22location%22%3A%22%22%2C%22range%22%3A50%7D%7D%2C%22typeFilter%22%3A%7B%22ironmanAndUp%22%3Atrue%2C%22triathlon%22%3Atrue%7D%7D&term=ironman), and several others.

## About Ironman

The Ironman group is the largest multisport event organizer in the world notably hosting triathlon races of the same name. An "Ironman" contains three events performed sequentially with time between events counting towards overall time:
1. 2.4 mile swim
2. 112 mile bike
3. 26.2 mile run

Nearly 1 million people have finished an Ironman-branded full-distance race globally since the first race in Hawaii in February of 1978. The Ironman group offers races of other distances such as the 70.3 or "Half Iron" distance and single sport events such as the Rock-N-Roll Marathon.

## Empirical strategy

Ironman events have several sharp "cutoffs" that generate quasi-random variation in outcomes at the cutoff. 

1. World Championship qualification slots: there are finite slots allocated to each age group for the World Championships, which are allocated by finishing position. Because slots are allocated by position and not time, a person can finish mere seconds after a competitor and not qualify for the world championships.
2. Age group age ranges: those born on January 1st are only a day older than those born on December 31st but may have to race in one age group higher
3. Water temperature: wetsuits are not permitted in races with sufficiently warm water, and hence the cutoff generates exogenous variation in wetsuit legality

These cutoffs allow identification of Local Average Treatment Effects (LATEs), local to those affected by the cutoffs. For example, the estimated effect of wetsuits on swim time would be local to those who attend races on the margin of having a wetsuit-legal swim.
