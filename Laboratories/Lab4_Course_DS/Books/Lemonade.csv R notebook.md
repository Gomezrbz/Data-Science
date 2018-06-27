

```R
library("AzureML")
ws <- workspace()
dat <- download.datasets(ws, "Lemonade.csv")
```


```R
head(dat)
```


<table>
<thead><tr><th>Date</th><th>Day</th><th>Temperature</th><th>Rainfall</th><th>Flyers</th><th>Price</th><th>Sales</th></tr></thead>
<tbody>
	<tr><td>01/01/2017</td><td>Sunday    </td><td>27.0      </td><td>2.00      </td><td>15        </td><td>0.3       </td><td>10        </td></tr>
	<tr><td>02/01/2017</td><td>Monday    </td><td>28.9      </td><td>1.33      </td><td>15        </td><td>0.3       </td><td>13        </td></tr>
	<tr><td>03/01/2017</td><td>Tuesday   </td><td>34.5      </td><td>1.33      </td><td>27        </td><td>0.3       </td><td>15        </td></tr>
	<tr><td>04/01/2017</td><td>Wednesday </td><td>44.1      </td><td>1.05      </td><td>28        </td><td>0.3       </td><td>17        </td></tr>
	<tr><td>05/01/2017</td><td>Thursday  </td><td>42.4      </td><td>1.00      </td><td>33        </td><td>0.3       </td><td>18        </td></tr>
	<tr><td>06/01/2017</td><td>Friday    </td><td>25.3      </td><td>1.54      </td><td>23        </td><td>0.3       </td><td>11        </td></tr>
</tbody>
</table>




```R
# Print statistics for Temperature and Sales
summary(dat[c('Temperature', 'Sales')])
print('Standard Deviations:')
apply(dat[c('Temperature', 'Sales')],2,sd)

# Print correlation for temperature vs Sales
print('Correlation:')
cor(dat[c('Temperature', 'Sales')])

# Plot Temperature vs Sales
plot(dat$Temperature, dat$Sales, xlab="Temperature", ylab="Sales") 
```


      Temperature         Sales      
     Min.   : 15.10   Min.   : 7.00  
     1st Qu.: 49.70   1st Qu.:20.00  
     Median : 61.10   Median :25.00  
     Mean   : 60.73   Mean   :25.32  
     3rd Qu.: 71.30   3rd Qu.:30.00  
     Max.   :102.90   Max.   :43.00  


    [1] "Standard Deviations:"



<dl class="dl-horizontal">
	<dt>Temperature</dt>
		<dd>16.1962656753799</dd>
	<dt>Sales</dt>
		<dd>6.89358916523938</dd>
</dl>



    [1] "Correlation:"



<table>
<thead><tr><th></th><th>Temperature</th><th>Sales</th></tr></thead>
<tbody>
	<tr><th>Temperature</th><td>1.0000000</td><td>0.9898321</td></tr>
	<tr><th>Sales</th><td>0.9898321</td><td>1.0000000</td></tr>
</tbody>
</table>




![png](output_2_5.png)

