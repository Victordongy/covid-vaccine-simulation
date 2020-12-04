# covid-vaccine-simulation
A simulation project for Covid vaccine distribution  

## Model Details 

### Model Input : 
- death rate = 0 for now
- n citizens in total
- v vaccines in total
- r := effective rate of a vaccine, eg. 95%
- Potential population spreading covid at the end of day 0 (beginning of day 1) = k
- Risk of getting infected:  factors - age, 5% working in hospitals occupation, lifestyle, area

### Procedure : 
- Day 0:
  - the $k(2-4k \cdot 14)$ cases in total (accumulated sum from past 2 weeks, moving window),  changes everyday
  - $P(i \,getting \,vaccine) = (v/7) / (n-k),  P( i \,getting \,virus) = , P(\text{i spreading out}) =$ 
- Day 1 : $(k : \text{starting number of people getting covid})$
$n-k$ people are requesting vaccination, but only $v/7$ people getting vaccination and $vr/7$ are sure to be virus-free.
  - $u$ (getting newly infected in day 1) : $u = 1.17 * k$  (infection rate)
  - Recover : $re = 0.1 * k$  
  - Update $k = k_{0}$(infected people on day 0) + $u$ (newly infected on day 1) - $re$

- Day 2:
    - $N-k-u-(v*r/7)$ (people requesting vaccination)
    - $N-k-u$(infected in day 1)-$v/7$(vaccinated in day 1) people not getting vaccinated
    - distribute $v/7$ to $N-k-u-v*r/7$  people 
    - More complex : model to predict the risk of people 
