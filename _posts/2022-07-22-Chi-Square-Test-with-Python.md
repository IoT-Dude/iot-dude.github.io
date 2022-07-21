# Chi Square Test with Python

Simple explanation of Chi Square feature test with basic python code

Three swedish hockey teams

The chi square test is used to test the models created for categorical variables. That is, it is another classical hypothesis test that we encounter a lot in statistics. This test is a statistical version of facts vs expectations. We have a theory, an expectation about an event and we have also observed some sample, now we want to test them.


## We can apply the chi square test in two ways:

1. Goodness of Fit Test: We have one categorical variable. We want to examine how well our sample reflects the entire population.
2. Test of Independence: We have two categorical variable. We want to check if there is a relationship between these two.


## The formula
![chi_square_20220613.png](attachment:583c5f10-6b7b-4507-9618-826c80902127.png)

The value of chi square is the sum of squares of the difference between observed values minus expected values divided by expectation. c is degree of freedom.


## Goodness of Fit

Let’s say we ask 100 people in sweden with the promise of buying a beer and asked them which team they are supporting. According to the somwe sort of research, we already knew that the rate of people supporting Brynäs 45 percent.  Frölunda was 35 percent and Björklöven was 20. This is our expectation. On the other hand, when we look at the samples, our observation is as follows respectively: 54, 38 and 8.


<h2>Data Table</h2>

<table>
  <tr>
    <th>Team</th>
    <th>Expectation</th>
    <th> Observation</th>
  </tr>
  <tr>
    <td>Brynäs</td>
    <td>45</td>
    <td>54</td>
  </tr>
  <tr>
    <td>Frölunda</td>
    <td>35</td>
    <td>38</td>
  </tr>
  <tr>
    <td>Björklöven</td>
    <td>20</td>
    <td>8</td>
  </tr>
  </table>

Our null hypotheses is that Observation is right. Alternate hypotheses is that they were wrong. We choose level of significance 5% as usual. 
Our degree of freedom is 2, since if we know the amount of supporters of 2 clubs we can get the 3rd one too. And also c = k-1 = 3–1 = 2.


![chi_square_20220613.png](attachment:55cecaf0-6c52-4699-b11b-0173ee3f7b9a.png)

One can also write it: ((54-45)² / 45) + ((38-35)² / 35) + ((8-20)² / 20) = 


```python
chiSquareValue = ((54-45)*(54-45)/45) + ((38-35)*(38-35)/35) + ((8-20)*(8-20)/20)
print(chiSquareValue)
```

    9.257142857142856


Our chi square value for degree of two is 9.26 and for 0.05 confidence level, our critical value is 5.991. Chi square table link here. 
https://people.richland.edu/james/lecture/m170/tbl-chi.html

If our value is greater than critical value, we can reject null hypotheses, and yes, in this case we reject the null and accept the alternate.

Test of Independence

Actually same thing but there is one more variable. So, let’s add one more to our example above. We noticed that our 100 ishockeyfriends in the pub which we where asking were consuming 2 types of beer; Pilsner and Lager. We wonder if there is a relation between the hockey team and the choice of beer type. We collect the sample again.
Beer


<h2>Data Table</h2>

<table>
  <tr>
    <th>Team</th>
    <th>Pilsner</th>
    <th>Lager</th>
      <th>Totalt</th>
  </tr>
  <tr>
    <td>Brynäs</td>
    <td>34</td>
    <td>20</td>
    <td>54</td>
  </tr>
  <tr>
    <td>Frölunda</td>
    <td>5</td>
    <td>33</td>
    <td>38</td>
  </tr>
  <tr>
    <td>Björklöven</td>
    <td>4</td>
    <td>4</td>
    <td>8</td>
  </tr>
    
  <tr>
    <td>Totalt</td>
    <td>43</td>
    <td>57</td>
    <td>100</td>
  </tr>
</table>

To calculate expected values, we will use joint probability which is: P(Joint) = Marginal Prob * Marginal Prob. 
<br>
For example we can calculate the expected value of Brynäs fans who love to drink Pilsner beer as follow:
<br>
E = (54 * 43) / 100 = 23.2. So let’s calculate all the expected values:


<h2>Data Table</h2>

<table>
  <tr>
    <th>Team</th>
    <th>Pilsner</th>
    <th>Lager</th>
      <th>Totalt</th>
  </tr>
  <tr>
    <td>Brynäs</td>
    <td>23.2/td>
    <td>30.8</td>
    <td>54</td>
  </tr>
  <tr>
    <td>Frölunda</td>
    <td>16.3</td>
    <td>21.7</td>
    <td>38</td>
  </tr>
  <tr>
    <td>Björklöven</td>
    <td>3.4</td>
    <td>4.6</td>
    <td>8</td>
  </tr>
    
  <tr>
    <td>Totalt</td>
    <td>43</td>
    <td>57</td>
    <td>100</td>
  </tr>
</table>

So our null hypotheses is that supported team is independent of beer preference. 
<br>Alternate hypotheses is that supported team is NOT independent of beer preference. 
<br>
Our degree of freedom is df = (r-1)(c-1) = (3–1)(2–1) = 2. 
<br>
<br>
And we use the same equation again to calculate chi square value:

((34-23.2)² / 23.2) + ((5-16.3)² / 16.3) + ((4-3.4)² / 3.4) + ((20-30.8)² / 30.8) = 


```python
chiSquareValue = ((34-23.2)*(34-23.2)/23.2) + ((5-16.3)*(5-16.3)/16.3) + ((4-3.4)*(4-3.4)/3.4) + ((20-30.8)*(20-30.8)/30.8)
print(chiSquareValue)
```

    16.754223878139058


Calculated value 16.75 is again greater than critical value, therefore we reject null hypotheses and accept alternate. We can say that both variables dependent.






v1.2
