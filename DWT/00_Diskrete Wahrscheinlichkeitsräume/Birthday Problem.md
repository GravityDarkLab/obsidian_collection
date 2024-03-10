[[Bedingte Wahrscheinlichkeiten]].


- What is the probability that at least two people in a group of n people share the same birthday?

To solve this problem, we can start by calculating the probability that **==no two people share the same birthday==**, and then **==subtract that probability from 1==** to get the probability that at least two people do share the same birthday.

The probability that the first person has a unique birthday is 1. The probability that the second person has a unique birthday is (364/365), since there are 364 remaining days in the year that are not the first person's birthday. The probability that the third person has a unique birthday is (363/365), and so on, until the nth person, whose probability of having a unique birthday is ((365-n+1)/365).

To find the probability that no two people share the same birthday, we can multiply these probabilities together: 
![[Pasted image 20230429124229.png]]

To find the probability that at least two people share the same birthday, we can subtract this probability from 1:
$$1 - \frac{365!}{365^n * (365-n)!}$$

