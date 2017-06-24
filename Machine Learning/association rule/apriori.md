## Apriori
People who bought ... also bought ...

Find percentage of people who pick one product (calculate support):

![ap](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/ap.jpg)

Find cofnidence, which is the percentage of people who pick one and another product together:

![ap2](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/ap2.jpg)

Find lift, which is confidence devided by support:

![ap3](https://github.com/vgorbic1/data-science/blob/master/Machine%20Learning/images/ap3.jpg)

1. Set a minimum support and confidence
2. Take all the subsets i transactions having higher support than minimum support
3. Take all the rules of these subsets having higher confidence than minimum confidence
4. Sort the rules by decreasing lift
