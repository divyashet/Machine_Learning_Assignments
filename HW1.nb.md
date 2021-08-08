






<div class="container-fluid main-container">















<div class="fluid-row" id="header">

<div class="btn-group pull-right">
<button type="button" class="btn btn-default btn-xs dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false"><span>Code</span> <span class="caret"></span></button>
<ul class="dropdown-menu" style="min-width: 50px;">
<li><a id="rmd-show-all-code" href="">Show All Code</a></li>
<li><a id="rmd-hide-all-code" href="">Hide All Code</a></li>
<li role="separator" class="divider"></li>
<li><a id="rmd-download-source" href="">Download Rmd</a></li>
</ul>
</div>



<h1 class="title toc-ignore">Exploring Data Analysis with R</h1>

</div>



<div id="problem-1exploring-vegas-hotel-dataset" class="section level2">
<h2>Problem 1–Exploring Vegas Hotel Dataset</h2>
<div id="explore-the-overall-structure-of-the-dataset-using-str." class="section level3">
<h3>1.Explore the overall structure of the dataset using str().</h3>



<pre class="r"><code class="hljs">directory &lt;- getwd()
lasvegas &lt;- read.csv(<span class="hljs-string">"vegashotels.csv"</span>, sep = <span class="hljs-string">';'</span>)
str(lasvegas)</code></pre>


<pre><code class="hljs">'data.frame':   504 obs. of  20 variables:
 $ User.country     : Factor w/ 48 levels "Australia","Belgium",..: 48 48 48 46 4 4 46 48 18 4 ...
 $ Nr..reviews      : int  11 119 36 14 5 31 45 2 24 12 ...
 $ Nr..hotel.reviews: int  4 21 9 7 5 8 12 1 3 7 ...
 $ Helpful.votes    : int  13 75 25 14 2 27 46 4 8 11 ...
 $ Score            : int  5 3 5 4 4 3 4 4 4 3 ...
 $ Period.of.stay   : Factor w/ 4 levels "Dec-Feb","Jun-Aug",..: 1 1 3 3 3 3 3 3 3 3 ...
 $ Traveler.type    : Factor w/ 5 levels "Business","Couples",..: 4 1 3 4 5 2 2 3 4 3 ...
 $ Pool             : Factor w/ 2 levels "NO","YES": 1 1 1 1 1 1 1 1 1 1 ...
 $ Gym              : Factor w/ 2 levels "NO","YES": 2 2 2 2 2 2 2 2 2 2 ...
 $ Tennis.court     : Factor w/ 2 levels "NO","YES": 1 1 1 1 1 1 1 1 1 1 ...
 $ Spa              : Factor w/ 2 levels "NO","YES": 1 1 1 1 1 1 1 1 1 1 ...
 $ Casino           : Factor w/ 2 levels "NO","YES": 2 2 2 2 2 2 2 2 2 2 ...
 $ Free.internet    : Factor w/ 2 levels "NO","YES": 2 2 2 2 2 2 2 2 2 2 ...
 $ Hotel.name       : Factor w/ 21 levels "Bellagio Las Vegas",..: 3 3 3 3 3 3 3 3 3 3 ...
 $ Hotel.stars      : Factor w/ 5 levels "3","3,5","4",..: 1 1 1 1 1 1 1 1 1 1 ...
 $ Nr..rooms        : int  3773 3773 3773 3773 3773 3773 3773 3773 3773 3773 ...
 $ User.continent   : Factor w/ 6 levels "Africa","Asia",..: 4 4 4 3 4 4 3 4 2 4 ...
 $ Member.years     : int  9 3 2 6 7 2 4 0 3 5 ...
 $ Review.month     : Factor w/ 12 levels "April","August",..: 5 5 4 4 8 8 1 1 9 9 ...
 $ Review.weekday   : Factor w/ 7 levels "Friday","Monday",..: 5 1 3 1 6 6 1 6 3 6 ...</code></pre>



</div>
<div id="use-summary-to-get-a-summary-statistics-of-each-variable.-does-any-of-the-variables-have-missing-values" class="section level3">
<h3>Use summary to get a summary statistics of each variable. Does any of the variables have missing values?</h3>



<pre class="r"><code class="hljs">summary(lasvegas)</code></pre>


<pre><code class="hljs">    User.country  Nr..reviews     Nr..hotel.reviews Helpful.votes   
 USA      :217   Min.   :  1.00   Min.   :  0.00    Min.   :  0.00  
 UK       : 72   1st Qu.: 12.00   1st Qu.:  5.00    1st Qu.:  8.00  
 Canada   : 65   Median : 23.50   Median :  9.00    Median : 16.00  
 Australia: 36   Mean   : 48.13   Mean   : 16.02    Mean   : 31.75  
 Ireland  : 13   3rd Qu.: 54.25   3rd Qu.: 18.00    3rd Qu.: 35.00  
 India    : 11   Max.   :775.00   Max.   :263.00    Max.   :365.00  
 (Other)  : 90                                                      
     Score       Period.of.stay  Traveler.type  Pool      Gym     
 Min.   :1.000   Dec-Feb:124    Business: 74   NO : 24   NO : 24  
 1st Qu.:4.000   Jun-Aug:126    Couples :214   YES:480   YES:480  
 Median :4.000   Mar-May:128    Families:110                      
 Mean   :4.123   Sep-Nov:126    Friends : 82                      
 3rd Qu.:5.000                  Solo    : 24                      
 Max.   :5.000                                                    
                                                                  
 Tennis.court  Spa      Casino    Free.internet
 NO :384      NO :120   NO : 48   NO : 24      
 YES:120      YES:384   YES:456   YES:480      
                                               
                                               
                                               
                                               
                                               
                                  Hotel.name  Hotel.stars   Nr..rooms   
 Bellagio Las Vegas                    : 24   3  : 96     Min.   : 188  
 Caesars Palace                        : 24   3,5: 72     1st Qu.: 826  
 Circus Circus Hotel &amp; Casino Las Vegas: 24   4  :120     Median :2700  
 Encore at wynn Las Vegas              : 24   4,5: 24     Mean   :2196  
 Excalibur Hotel &amp; Casino              : 24   5  :192     3rd Qu.:3025  
 Hilton Grand Vacations at the Flamingo: 24               Max.   :4027  
 (Other)                               :360                             
       User.continent  Member.years          Review.month   Review.weekday
 Africa       :  7    Min.   :-1806.0000   April   : 42   Friday   :65    
 Asia         : 36    1st Qu.:    2.0000   August  : 42   Monday   :74    
 Europe       :118    Median :    4.0000   December: 42   Saturday :61    
 North America:295    Mean   :    0.7679   February: 42   Sunday   :77    
 Oceania      : 41    3rd Qu.:    6.0000   January : 42   Thursday :62    
 South America:  7    Max.   :   13.0000   July    : 42   Tuesday  :80    
                                           (Other) :252   Wednesday:85    </code></pre>



</div>
<div id="draw-a-histogram-of-the-score-variable.-describe-what-you-see-in-the-histogram." class="section level3">
<h3>Draw a histogram of the score variable. Describe what you see in the histogram.</h3>



<pre class="r"><code class="hljs">lasvegas &lt;- read.csv(<span class="hljs-string">"vegashotels.csv"</span>, sep = <span class="hljs-string">';'</span>)
score &lt;- table(lasvegas$Score)
hist(score)</code></pre>


<p><img src="data:image/png;base64,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"></p>



<p>The Histogram is plotted by Score on the x-axis v/s Frequency on the y-axis.We can see no scores in between a00 and 150.The histogram is also skewed to the right and is said to be positively skewed.</p>
</div>
</div>
<div id="find-the-mode-of-score" class="section level2">
<h2>Find the mode of “Score”</h2>



<pre class="r"><code class="hljs"><span class="hljs-comment"># Create the function.</span>
getmode &lt;- <span class="hljs-keyword">function</span>(m) {
   uniqv &lt;- unique(m)
   uniqv[which.max(tabulate(match(m, uniqv)))]
}
<span class="hljs-comment"># Create the vector with numbers.</span>
m &lt;- lasvegas$Score
<span class="hljs-comment"># Calculate the mode using the user function.</span>
ModeofScore &lt;- getmode(m)
print(ModeofScore)</code></pre>


<pre><code class="hljs">[1] 5</code></pre>



</div>
<div id="use-the-quantile-function-to-get-the-quantiles-for-score.-what-is-the-median-of-score" class="section level2">
<h2>Use the “quantile” function to get the quantiles for score. What is the median of score?</h2>



<pre class="r"><code class="hljs">q &lt;- quantile(lasvegas$Score)
print(q)</code></pre>


<pre><code class="hljs">  0%  25%  50%  75% 100% 
   1    4    4    5    5 </code></pre>


<pre class="r"><code class="hljs">p &lt;-median(lasvegas$Score)
print(p)</code></pre>


<pre><code class="hljs">[1] 4</code></pre>



</div>
<div id="use-the-ifelse-function-you-can-get-help-on-the-syntax-of-this-function-in-r-by-typing-ifelse-to-create-a-factor-variable-sentiment-which-takes-the-value-positive-if-score-is-4-or-5-and-negative-otherwise.-you-can-use-the-method-factor-to-create-a-factor-from-a-character-vector." class="section level2">
<h2>Use the ifelse function (You can get help on the syntax of this function in R by typing ?ifelse) to create a factor variable “sentiment” which takes the value “positive” if score is 4 or 5 and “negative” otherwise. You can use the method “factor” to create a factor from a character vector.</h2>



<pre class="r"><code class="hljs">lasvegas &lt;- read.csv(<span class="hljs-string">"vegashotels.csv"</span>, sep = <span class="hljs-string">';'</span>)
ses&lt;- ifelse((lasvegas$Score == <span class="hljs-number">4</span>) | (lasvegas$Score == <span class="hljs-number">5</span>),<span class="hljs-string">"Positive"</span>,<span class="hljs-string">"Negative"</span>)
ses.f &lt;- factor(ses, levels = c(<span class="hljs-string">"Positive"</span>,<span class="hljs-string">"Negative"</span>))
is.factor(ses.f)</code></pre>


<pre><code class="hljs">[1] TRUE</code></pre>


<pre class="r"><code class="hljs">lasvegas$Sentiment&lt;-ses.f
lasvegas$Sentiment</code></pre>


<pre><code class="hljs">  [1] Positive Negative Positive Positive Positive Negative Positive
  [8] Positive Positive Negative Negative Negative Negative Negative
 [15] Negative Positive Negative Positive Negative Negative Positive
 [22] Negative Positive Negative Positive Positive Positive Negative
 [29] Positive Positive Positive Negative Negative Negative Positive
 [36] Negative Positive Positive Positive Negative Negative Negative
 [43] Negative Positive Positive Positive Positive Negative Negative
 [50] Positive Negative Positive Negative Positive Positive Negative
 [57] Positive Positive Positive Positive Positive Negative Negative
 [64] Negative Negative Positive Negative Negative Positive Negative
 [71] Negative Positive Negative Positive Positive Positive Positive
 [78] Positive Positive Negative Negative Positive Negative Positive
 [85] Positive Positive Positive Positive Negative Positive Positive
 [92] Negative Positive Positive Positive Positive Positive Positive
 [99] Negative Negative Positive Positive Positive Positive Positive
[106] Negative Positive Positive Positive Positive Positive Positive
[113] Negative Positive Positive Negative Positive Positive Positive
[120] Positive Positive Positive Positive Positive Positive Negative
[127] Positive Positive Negative Positive Positive Negative Positive
[134] Negative Positive Positive Positive Positive Positive Positive
[141] Positive Negative Positive Positive Positive Positive Positive
[148] Positive Positive Positive Positive Positive Positive Negative
[155] Negative Positive Negative Positive Positive Positive Positive
[162] Positive Positive Positive Positive Positive Negative Positive
[169] Negative Positive Positive Positive Positive Positive Positive
[176] Positive Positive Positive Positive Negative Positive Positive
[183] Positive Positive Negative Positive Positive Positive Positive
[190] Negative Positive Positive Positive Positive Positive Positive
[197] Positive Positive Positive Positive Negative Positive Positive
[204] Positive Positive Positive Positive Positive Negative Positive
[211] Positive Positive Positive Positive Positive Positive Positive
[218] Positive Positive Positive Positive Negative Positive Positive
[225] Positive Positive Positive Positive Positive Positive Positive
[232] Positive Positive Negative Positive Positive Negative Positive
[239] Positive Positive Negative Positive Positive Positive Negative
[246] Positive Positive Negative Positive Positive Positive Positive
[253] Positive Negative Positive Positive Positive Positive Negative
[260] Positive Negative Positive Positive Positive Negative Positive
[267] Positive Positive Positive Positive Negative Positive Positive
[274] Positive Positive Positive Positive Positive Positive Positive
[281] Positive Positive Positive Positive Positive Positive Positive
[288] Positive Positive Negative Positive Positive Positive Positive
[295] Positive Positive Positive Negative Positive Positive Positive
[302] Positive Positive Positive Positive Positive Negative Positive
[309] Negative Positive Positive Positive Positive Positive Positive
[316] Positive Positive Positive Positive Positive Positive Positive
[323] Positive Positive Positive Positive Positive Positive Positive
[330] Positive Negative Positive Positive Positive Positive Positive
[337] Positive Positive Negative Positive Positive Positive Positive
[344] Positive Negative Negative Positive Negative Positive Positive
[351] Negative Positive Positive Positive Negative Positive Positive
[358] Negative Positive Positive Negative Positive Negative Negative
[365] Positive Positive Negative Negative Negative Negative Positive
[372] Positive Negative Positive Positive Positive Positive Positive
[379] Positive Positive Positive Positive Positive Positive Positive
[386] Positive Positive Positive Positive Positive Positive Positive
[393] Positive Positive Positive Positive Positive Positive Negative
[400] Positive Positive Positive Negative Positive Negative Positive
[407] Positive Positive Positive Positive Positive Positive Negative
[414] Positive Positive Positive Positive Positive Positive Positive
[421] Positive Positive Positive Positive Positive Positive Positive
[428] Positive Positive Positive Positive Positive Positive Positive
[435] Positive Positive Positive Negative Positive Negative Negative
[442] Positive Positive Positive Positive Positive Positive Positive
[449] Positive Positive Positive Positive Positive Positive Positive
[456] Negative Positive Positive Negative Positive Negative Positive
[463] Positive Negative Positive Negative Positive Negative Positive
[470] Positive Positive Positive Positive Positive Negative Positive
[477] Positive Positive Positive Positive Positive Negative Positive
[484] Negative Positive Positive Positive Positive Negative Positive
[491] Positive Negative Positive Positive Negative Positive Positive
[498] Negative Positive Positive Positive Positive Negative Positive
Levels: Positive Negative</code></pre>



</div>
<div id="take-a-summary-of-sentiment-to-make-sure-that-the-frequencies-of-positive-and-negative-categories-are-consistent-with-the-frequency-of-the-values-in-score-e.g.-the-frequency-for-the-positive-sentiment-should-be-equal-to-the-combined-frequency-of-4-and-5-for-the-score" class="section level2">
<h2>Take a summary of “sentiment” to make sure that the frequencies of “positive” and “negative” categories are consistent with the frequency of the values in Score (e.g., the frequency for the “positive” sentiment should be equal to the combined frequency of 4 and 5 for the Score)</h2>



<pre class="r"><code class="hljs">lasvegas &lt;- read.csv(<span class="hljs-string">"vegashotels.csv"</span>, sep = <span class="hljs-string">';'</span>)
ses&lt;- ifelse((lasvegas$Score == <span class="hljs-number">4</span>) | (lasvegas$Score == <span class="hljs-number">5</span>),<span class="hljs-string">"Positive"</span>,<span class="hljs-string">"Negative"</span>)
ses.f &lt;- factor(ses, levels = c(<span class="hljs-string">"Positive"</span>,<span class="hljs-string">"Negative"</span>))
is.factor(ses.f)</code></pre>


<pre><code class="hljs">[1] TRUE</code></pre>


<pre class="r"><code class="hljs">lasvegas$Sentiment&lt;-ses.f
summary(lasvegas$Sentiment)</code></pre>


<pre><code class="hljs">Positive Negative 
     391      113 </code></pre>


<pre class="r"><code class="hljs">summary(lasvegas$Score == <span class="hljs-number">4</span> |lasvegas$Score == <span class="hljs-number">5</span>)</code></pre>


<pre><code class="hljs">   Mode   FALSE    TRUE 
logical     113     391 </code></pre>



</div>
<div id="use-chisquare-test-to-determine-if-sentiment-is-associated-with-any-of-the-variables-pool-gymfree.internet-period.of.stay-traverler.type-andhotel.stars-assume-the-significance-level-alpha0.01.-which-of-these-variables-are-associated-with-sentiment" class="section level2">
<h2>Use chisquare test to determine if sentiment is associated with any of the variables: “Pool”, “Gym”,“Free.Internet”, “Period.of.Stay”, “traverler.type”“, and”hotel.stars" (Assume the significance level alpha=0.01). Which of these variables are associated with sentiment?</h2>



<pre class="r"><code class="hljs">lasvegas &lt;- read.csv(<span class="hljs-string">"vegashotels.csv"</span>, sep = <span class="hljs-string">';'</span>)
ses&lt;- ifelse((lasvegas$Score == <span class="hljs-number">4</span>) | (lasvegas$Score == <span class="hljs-number">5</span>),<span class="hljs-string">"Positive"</span>,<span class="hljs-string">"Negative"</span>)
ses.f &lt;- factor(ses, levels = c(<span class="hljs-string">"Positive"</span>,<span class="hljs-string">"Negative"</span>))
is.factor(ses.f)</code></pre>


<pre><code class="hljs">[1] TRUE</code></pre>


<pre class="r"><code class="hljs">ses.f</code></pre>


<pre><code class="hljs">  [1] Positive Negative Positive Positive Positive Negative Positive
  [8] Positive Positive Negative Negative Negative Negative Negative
 [15] Negative Positive Negative Positive Negative Negative Positive
 [22] Negative Positive Negative Positive Positive Positive Negative
 [29] Positive Positive Positive Negative Negative Negative Positive
 [36] Negative Positive Positive Positive Negative Negative Negative
 [43] Negative Positive Positive Positive Positive Negative Negative
 [50] Positive Negative Positive Negative Positive Positive Negative
 [57] Positive Positive Positive Positive Positive Negative Negative
 [64] Negative Negative Positive Negative Negative Positive Negative
 [71] Negative Positive Negative Positive Positive Positive Positive
 [78] Positive Positive Negative Negative Positive Negative Positive
 [85] Positive Positive Positive Positive Negative Positive Positive
 [92] Negative Positive Positive Positive Positive Positive Positive
 [99] Negative Negative Positive Positive Positive Positive Positive
[106] Negative Positive Positive Positive Positive Positive Positive
[113] Negative Positive Positive Negative Positive Positive Positive
[120] Positive Positive Positive Positive Positive Positive Negative
[127] Positive Positive Negative Positive Positive Negative Positive
[134] Negative Positive Positive Positive Positive Positive Positive
[141] Positive Negative Positive Positive Positive Positive Positive
[148] Positive Positive Positive Positive Positive Positive Negative
[155] Negative Positive Negative Positive Positive Positive Positive
[162] Positive Positive Positive Positive Positive Negative Positive
[169] Negative Positive Positive Positive Positive Positive Positive
[176] Positive Positive Positive Positive Negative Positive Positive
[183] Positive Positive Negative Positive Positive Positive Positive
[190] Negative Positive Positive Positive Positive Positive Positive
[197] Positive Positive Positive Positive Negative Positive Positive
[204] Positive Positive Positive Positive Positive Negative Positive
[211] Positive Positive Positive Positive Positive Positive Positive
[218] Positive Positive Positive Positive Negative Positive Positive
[225] Positive Positive Positive Positive Positive Positive Positive
[232] Positive Positive Negative Positive Positive Negative Positive
[239] Positive Positive Negative Positive Positive Positive Negative
[246] Positive Positive Negative Positive Positive Positive Positive
[253] Positive Negative Positive Positive Positive Positive Negative
[260] Positive Negative Positive Positive Positive Negative Positive
[267] Positive Positive Positive Positive Negative Positive Positive
[274] Positive Positive Positive Positive Positive Positive Positive
[281] Positive Positive Positive Positive Positive Positive Positive
[288] Positive Positive Negative Positive Positive Positive Positive
[295] Positive Positive Positive Negative Positive Positive Positive
[302] Positive Positive Positive Positive Positive Negative Positive
[309] Negative Positive Positive Positive Positive Positive Positive
[316] Positive Positive Positive Positive Positive Positive Positive
[323] Positive Positive Positive Positive Positive Positive Positive
[330] Positive Negative Positive Positive Positive Positive Positive
[337] Positive Positive Negative Positive Positive Positive Positive
[344] Positive Negative Negative Positive Negative Positive Positive
[351] Negative Positive Positive Positive Negative Positive Positive
[358] Negative Positive Positive Negative Positive Negative Negative
[365] Positive Positive Negative Negative Negative Negative Positive
[372] Positive Negative Positive Positive Positive Positive Positive
[379] Positive Positive Positive Positive Positive Positive Positive
[386] Positive Positive Positive Positive Positive Positive Positive
[393] Positive Positive Positive Positive Positive Positive Negative
[400] Positive Positive Positive Negative Positive Negative Positive
[407] Positive Positive Positive Positive Positive Positive Negative
[414] Positive Positive Positive Positive Positive Positive Positive
[421] Positive Positive Positive Positive Positive Positive Positive
[428] Positive Positive Positive Positive Positive Positive Positive
[435] Positive Positive Positive Negative Positive Negative Negative
[442] Positive Positive Positive Positive Positive Positive Positive
[449] Positive Positive Positive Positive Positive Positive Positive
[456] Negative Positive Positive Negative Positive Negative Positive
[463] Positive Negative Positive Negative Positive Negative Positive
[470] Positive Positive Positive Positive Positive Negative Positive
[477] Positive Positive Positive Positive Positive Negative Positive
[484] Negative Positive Positive Positive Positive Negative Positive
[491] Positive Negative Positive Positive Negative Positive Positive
[498] Negative Positive Positive Positive Positive Negative Positive
Levels: Positive Negative</code></pre>


<pre class="r"><code class="hljs">lasvegas$Sentiment&lt;-ses.f
<span class="hljs-comment"># Load the library.</span>
<span class="hljs-keyword">library</span>(<span class="hljs-string">"MASS"</span>)
<span class="hljs-comment"># Perform the Chi-Square test.</span>
chisq &lt;- chisq.test(lasvegas$Sentiment,lasvegas$Gym)</code></pre>



<p>Sentiment can be associated with <span class="math inline">\(Gym ,\)</span>Pool,$Free.Internet as the chi-square test evaluates whether there is a significant association between the categories of the two variables.The chisq.test() functions only works when the length of the two varaiables is same.</p>
</div>
<div id="exploring-california-housing-dataset" class="section level1">
<h1>Exploring California Housing Dataset</h1>
<div id="explore-the-structure-of-dataset-using-str-function.-how-many-numerical-and-categorical-attributes-are-there-in-the-dataset." class="section level2">
<h2>Explore the structure of dataset using str function. How many numerical and categorical attributes are there in the dataset.</h2>



<pre class="r"><code class="hljs">directory &lt;- getwd()
housing &lt;- read.csv(<span class="hljs-string">"housing.csv"</span>, sep = <span class="hljs-string">','</span>)
str(housing)</code></pre>


<pre><code class="hljs">'data.frame':   20640 obs. of  10 variables:
 $ longitude         : num  -122 -122 -122 -122 -122 ...
 $ latitude          : num  37.9 37.9 37.9 37.9 37.9 ...
 $ housing_median_age: num  41 21 52 52 52 52 52 52 42 52 ...
 $ total_rooms       : num  880 7099 1467 1274 1627 ...
 $ total_bedrooms    : num  129 1106 190 235 280 ...
 $ population        : num  322 2401 496 558 565 ...
 $ households        : num  126 1138 177 219 259 ...
 $ median_income     : num  8.33 8.3 7.26 5.64 3.85 ...
 $ median_house_value: num  452600 358500 352100 341300 342200 ...
 $ ocean_proximity   : Factor w/ 5 levels "&lt;1H OCEAN","INLAND",..: 4 4 4 4 4 4 4 4 4 4 ...</code></pre>



</div>
<div id="take-a-summary-statistics-of-the-dataset.-does-any-of-the-variables-have-missing-values" class="section level2">
<h2>Take a summary statistics of the dataset. Does any of the variables have missing values?</h2>



<pre class="r"><code class="hljs"><span class="hljs-comment">##To  find the Summary of the Dataset</span>
summary(housing)</code></pre>


<pre><code class="hljs">   longitude         latitude     housing_median_age  total_rooms   
 Min.   :-124.3   Min.   :32.54   Min.   : 1.00      Min.   :    2  
 1st Qu.:-121.8   1st Qu.:33.93   1st Qu.:18.00      1st Qu.: 1448  
 Median :-118.5   Median :34.26   Median :29.00      Median : 2127  
 Mean   :-119.6   Mean   :35.63   Mean   :28.64      Mean   : 2636  
 3rd Qu.:-118.0   3rd Qu.:37.71   3rd Qu.:37.00      3rd Qu.: 3148  
 Max.   :-114.3   Max.   :41.95   Max.   :52.00      Max.   :39320  
                                                                    
 total_bedrooms     population      households     median_income    
 Min.   :   1.0   Min.   :    3   Min.   :   1.0   Min.   : 0.4999  
 1st Qu.: 296.0   1st Qu.:  787   1st Qu.: 280.0   1st Qu.: 2.5634  
 Median : 435.0   Median : 1166   Median : 409.0   Median : 3.5348  
 Mean   : 537.9   Mean   : 1425   Mean   : 499.5   Mean   : 3.8707  
 3rd Qu.: 647.0   3rd Qu.: 1725   3rd Qu.: 605.0   3rd Qu.: 4.7432  
 Max.   :6445.0   Max.   :35682   Max.   :6082.0   Max.   :15.0001  
 NA's   :207                                                        
 median_house_value   ocean_proximity
 Min.   : 14999     &lt;1H OCEAN :9136  
 1st Qu.:119600     INLAND    :6551  
 Median :179700     ISLAND    :   5  
 Mean   :206856     NEAR BAY  :2290  
 3rd Qu.:264725     NEAR OCEAN:2658  
 Max.   :500001                      
                                     </code></pre>


<pre class="r"><code class="hljs"><span class="hljs-comment">## To find the missing values in the dataset</span>
which(is.na(housing$total_bedrooms))</code></pre>


<pre><code class="hljs">  [1]   291   342   539   564   697   739  1098  1351  1457  1494  1607
 [12]  2029  2116  2302  2324  2335  2352  2413  2421  2579  2609  2648
 [23]  2827  3025  3329  3355  3377  3483  3486  3530  3722  3779  3913
 [34]  3922  3959  4044  4047  4187  4280  4310  4392  4448  4497  4592
 [45]  4601  4630  4668  4692  4739  4744  4745  4768  4853  5060  5217
 [56]  5223  5237  5655  5666  5679  5724  5752  5991  6053  6069  6221
 [67]  6242  6254  6299  6422  6542  6591  6815  6836  6963  7098  7114
 [78]  7169  7192  7229  7317  7331  7548  7655  7669  7764  7807  8338
 [89]  8384  8531  8916  9150  9572  9621  9623  9815  9846  9878  9943
[100]  9971 10034 10217 10237 10386 10390 10429 10496 10762 10886 10916
[111] 11097 11312 11352 11442 11450 11513 11742 12102 12415 12571 12810
[122] 13016 13070 13312 13333 13337 13598 13657 13707 13926 13933 13934
[133] 14016 14153 14174 14308 14332 14387 14463 14522 14642 14931 14971
[144] 14987 15031 15061 15119 15138 15398 15480 15608 15664 15891 15976
[155] 16026 16039 16105 16106 16331 16758 16880 16881 16886 17042 17199
[166] 17203 17640 17826 17841 17924 17929 17974 18178 18247 18262 18333
[177] 18347 18467 18787 18874 18915 19061 19072 19123 19151 19253 19333
[188] 19392 19403 19486 19560 19608 19639 19767 19819 19834 19891 19933
[199] 19960 20047 20070 20126 20268 20269 20373 20461 20485</code></pre>



</div>
<div id="remove-the-rows-with-missing-values.-you-can-use-either-complete.cases-function-or-na.omit-function-for-this-purpose.-run-complete.cases-and-na.omit-in-r-to-get-help-on-these-functions-and-to-see-some-examples." class="section level2">
<h2>Remove the rows with missing values. You can use either “complete.cases” function or “na.omit” function for this purpose. Run ?complete.cases and ?na.omit in R to get help on these functions and to see some examples.</h2>



<pre class="r"><code class="hljs">na.omit(housing$total_bedrooms)</code></pre>


<pre><code class="hljs">   [1]  129 1106  190  235  280  213  489  687  665  707  434  752  474
  [14]  191  626  283  347  293  455  298  184  367  541  337  437  123
  [27]  244  421  492  160  447  481  409  366  574  282  432  390  330
  [40]  715  419  311  202  202  311  420  322  312  195  375  453  456
  [53]  853  456  235  243  288  335  341   43  211   29  190  237  182
  [66]  209  354  244  109  644  152  297  204    4  161  462  562  243
  [79]  374  176  289   56   97  164  184  143  451  348   42   78  392
  [92]   87   31  347  623 2477 1331  107 1270 1085 1414 1603  242  701
 [105] 1914  225  482  460  751  855  289 1098 1196  559  428  287 1750
 [118] 1105  399  454  406   54  411  574  365 1048  473  597  674  346
 [131]  490  210  460  788  184  223  271  264  181  534   38  333  436
 [144]  605  535  212  335  465  464  541  339  536  486  229  402  292
 [157]  313  238  365  550  168  510  502  835 1065  792  469  864  492
 [170]  526  188  391  606  647  228  373  398  588  289  420  749  184
 [183]  414  480  299 1344  395  264  431  395  180  376   43  129  237
 [196]  779  128  301  206  146  215  530  472  258  825  396  217  574
 [209]  145  199  314  690  190  575  450  711  376  307  557  409  500
 [222]  447  499  293  711  354  263  259  341  195  256  405  271  451
 [235]  761  459  195  452  533  528  508  300  224  244  710  460  248
 [248]  114  473  514  463  314  173  153  498  375  328  254  597  415
 [261]  443  399  403  502  414  180  428  445  415  397   31  205  193
 [274]  332   95  233  387  243  217  262  195  336  317 2048  260  746
 [287]  440  322  177  128  194  397  349  342  533  367  413  358  397
 [300]  261  175  452  236  257  408  282  547  471  362  391  259  510
 [313]  393  207  238  132  736  370  565  189  297  212  154  253  147
 [326]  291  215  293  119  874  445  134  193  371  126  226  183  391
 [339]   76  218  261  263  233  214  307  320  271  248  390  514  624
 [352]  211  343  307  574  286  365  231  491  261  111  105  200   54
 [365]   93  666  161  256  399  178  454  131  275  277  294  140  281
 [378]  287  300  181  147  223  239  238  263  422  522  349  402 1212
 [391]  293  283  291  930  698  261  175  380  332  421  274  279  273
 [404]  240  270  373  328  250  328  169  408  329  473  366  293  335
 [417]  195  494  531  457  460  417  410  648  391  592  491  200  215
 [430]  424  490  442  395  146   97  118  127  119  376  749  188  132
 [443]  548  536  198  416  696  446  930  439  682  255  604  837  141
 [456]  465  460  236  371  998 1108  368  698  195  353  300  755  324
 [469]  404  367  460  607  450  668  472  435  417  691  550  305  186
 [482]  372  583 1744  832  744  604  517  191  318  444  225  474  663
 [495]  768  920  400  300  426   83  307  145  198  484  419  813 2408
 [508]  379  310  335  366  381  396  246  312  203  517  403  516  323
 [521]  177  235  179  386  566  220  320  157  217  239  280  264  263
 [534]  535  869  368  309  363 1073  763  306  350  388  377  481  559
 [547]  458  315  371  168  444  479  284 1110  542  185  516  471  246
 [560]  289  753  581  525  436 1249  365 2885 1379  648 1554 1270  365
 [573] 2045  467  570  302  480  477  531  368  350  387  366  824  622
 [586]  625  282  336 1073  269  295  657  447  272  310  790  736  758
 [599] 1107  618  499 1309  324  274  202  685  817  557  201  403  316
 [612]  416  223  129  819  470  408  289  206  313  147  200  533  554
 [625]   69  659  284  398  245  814  242  132  601  587  372  251 1047
 [638]  320  394  390  268  394  383  207  153  132  253  451  339  298
 [651] 1526  866 1007  557  710  178  244  292 1054  769  228  391  317
 [664]  221  287  252  219  208  303  365  348  391  407  278  273  447
 [677]  443  308  535  613  716  500  269  278  284  787  617  508  635
 [690]  461  306  789  651  310  560   25  194  590  236  936  357 1326
 [703] 1279  426 1207  370  682  168  305  353  110  538  463  348  342
 [716]  503  481  413  897  428  484  253  394  389  401  445  399  340
 [729]  518  533  398  249  347  534  318  681  703  247  811  655  500
 [742]  313  259  318  816  671  739  409  251  419  348  610 1168  372
 [755]  790 1439  393  436  191  142  464  722  192  200  115  643  225
 [768]  316  652  494  311  327   76   27 2031  458  167  808  280  849
 [781]  102  242  284  435  245  199  307  212 1253  440  171  127  133
 [794] 1516  723  860  304  450  286  252  172  352  547  173  118  324
 [807]  236  271  259  216  179  364  518  376  465 1374  356  346  293
 [820]  108  274  221  309  443  711  345  522  280  295  302  638  497
 [833]  474  832  276  365  551  418  251  240  544  686  338  302 1273
 [846]  383  333  889  295  760  717   94  678  783  597 1031  478  717
 [859] 2993 2708 1064 1407 1376 1818  311 2861  857  312  964 1492  778
 [872]  532  274  485 1005 1294  993 1823  344 1247 1375 2098  748 1540
 [885]  192  526  342  645  382 1207  475  529  652  496  420  387  566
 [898]  703  371  715  507  415  744  495 1249  406  371  303  939  623
 [911]  511  948  764 1125  741  973 3864  577 1588  676  322  744 1373
 [924]  532  532  369  731  835  922   97 1068  343  672  478  264  856
 [937]  437  712  673 1390 1576  716  668  637  459  845 1027 1050  209
 [950]  424  555 1137  223  582  308  254  547  423 1207  270  239  624
 [963]  301  471  288  273 1294  680  116  134  464  184  833  800  294
 [976]  741  701  664  242 2074   40   23 1344 1510  554  306   74  352
 [989] 1049 2220   81  943  639  351  711  372  498  588 1082  736
 [ reached getOption("max.print") -- omitted 19433 entries ]
attr(,"na.action")
  [1]   291   342   539   564   697   739  1098  1351  1457  1494  1607
 [12]  2029  2116  2302  2324  2335  2352  2413  2421  2579  2609  2648
 [23]  2827  3025  3329  3355  3377  3483  3486  3530  3722  3779  3913
 [34]  3922  3959  4044  4047  4187  4280  4310  4392  4448  4497  4592
 [45]  4601  4630  4668  4692  4739  4744  4745  4768  4853  5060  5217
 [56]  5223  5237  5655  5666  5679  5724  5752  5991  6053  6069  6221
 [67]  6242  6254  6299  6422  6542  6591  6815  6836  6963  7098  7114
 [78]  7169  7192  7229  7317  7331  7548  7655  7669  7764  7807  8338
 [89]  8384  8531  8916  9150  9572  9621  9623  9815  9846  9878  9943
[100]  9971 10034 10217 10237 10386 10390 10429 10496 10762 10886 10916
[111] 11097 11312 11352 11442 11450 11513 11742 12102 12415 12571 12810
[122] 13016 13070 13312 13333 13337 13598 13657 13707 13926 13933 13934
[133] 14016 14153 14174 14308 14332 14387 14463 14522 14642 14931 14971
[144] 14987 15031 15061 15119 15138 15398 15480 15608 15664 15891 15976
[155] 16026 16039 16105 16106 16331 16758 16880 16881 16886 17042 17199
[166] 17203 17640 17826 17841 17924 17929 17974 18178 18247 18262 18333
[177] 18347 18467 18787 18874 18915 19061 19072 19123 19151 19253 19333
[188] 19392 19403 19486 19560 19608 19639 19767 19819 19834 19891 19933
[199] 19960 20047 20070 20126 20268 20269 20373 20461 20485
attr(,"class")
[1] "omit"</code></pre>



</div>
<div id="draw-a-histogram-and-boxplot-of-the-median_house_value.-what-can-you-say-about-the-shape-of-median_house_value-is-the-median_house_value-sample-positively-skewed-symmetric-or-negatively-skewed" class="section level2">
<h2>Draw a histogram and boxplot of the median_house_value. What can you say about the shape of median_house_value? Is the median_house_value sample positively skewed, symmetric, or negatively skewed?</h2>



<pre class="r"><code class="hljs">housing &lt;- read.csv(<span class="hljs-string">"housing.csv"</span>, sep = <span class="hljs-string">','</span>)
median_house_value &lt;- housing$median_house_value
hist(median_house_value)</code></pre>


<p><img src="data:image/png;base64,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"></p>


<pre class="r"><code class="hljs">boxplot(housing$median_house_value, main=<span class="hljs-string">"Boxplot of median_house_value"</span>)</code></pre>


<p><img src="data:image/png;base64,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"></p>



<p>The histogram of median_House_Value is positively skewed.</p>
</div>
<div id="use-q-q-plot-to-examine-if-the-distribution-of-median_house_value-is-approximately-normal" class="section level2">
<h2>Use Q-Q plot to examine if the distribution of median_house_value is approximately normal?</h2>



<pre class="r"><code class="hljs">qqnorm(housing$median_house_value)</code></pre>


<p><img src="data:image/png;base64,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"></p>



</div>
<div id="use-iqr-method-to-find-outliers-of-the-median_house_value-attribute.-how-many-outliers-does-this-attribute-have" class="section level2">
<h2>Use IQR method to find outliers of the median_house_value attribute. How many outliers does this attribute have?</h2>



<pre class="r"><code class="hljs">IQR &lt;- IQR(housing$median_house_value)
IQR</code></pre>


<pre><code class="hljs">[1] 145125</code></pre>



</div>
<div id="use-pairs-and-cor-functions-to-get-a-scatter-plot-and-correlation-matrix-of-numerical-attributes-in-the-dataset.-does-any-of-the-numerical-attributes-have-a-linear-correlation-with-median_house_value" class="section level2">
<h2>Use “pairs” and “cor” functions to get a scatter plot and correlation matrix of numerical attributes in the dataset. Does any of the numerical attributes have a linear correlation with median_house_value?</h2>



<pre class="r"><code class="hljs">numeric_attributes = housing[,c(<span class="hljs-string">"median_income"</span>,<span class="hljs-string">"median_house_value"</span>)]
pairs(numeric_attributes)</code></pre>


<p><img src="data:image/png;base64,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"></p>


<pre class="r"><code class="hljs">cor(numeric_attributes)</code></pre>


<pre><code class="hljs">                   median_income median_house_value
median_income          1.0000000          0.6880752
median_house_value     0.6880752          1.0000000</code></pre>



<p>The median income is correlated with median_house_value in the housing dataset.</p>
</div>
<div id="is-there-a-significant-difference-between-the-mean-of-median_house_value-across-different-levels-of-ocean_proximity-use-side-by-side-box-plot-and-anova-with-significance-level-alpha0.01-to-answer-this-question.-interpret-the-side-by-side-box-plot-do-you-see-any-difference-between-the-mean-of-the-median_house_value-for-different-ocean_proximity-levels" class="section level2">
<h2>Is there a significant difference between the mean of median_house_value across different levels of ocean_proximity ? Use side by side box plot and ANOVA (with significance level alpha=0.01) to answer this question. Interpret the side by side box plot, do you see any difference between the mean of the median_house_value for different ocean_proximity levels?</h2>



<pre class="r"><code class="hljs">plot(housing$median_house_value ~ housing$ocean_proximity, col=<span class="hljs-string">"blue"</span>)</code></pre>


<p><img src="data:image/png;base64,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"></p>



<p>Yes, there are differences between the mean of different ocean proximity levels.The mean of the Island is highest amongst all and the mean of inland is the lowest.</p>
</div>
<div id="use-ifelse-function-to-create-a-new-factor-variable-is_inland-which-takes-the-value-yes-if-the-ocean_proximity-is-inland-and-no-otherwise." class="section level2">
<h2>Use ifelse function to create a new factor variable “Is_Inland” which takes the value “Yes” if the ocean_proximity is “Inland” and No" otherwise.</h2>



<pre class="r"><code class="hljs">housing &lt;- read.csv(<span class="hljs-string">"housing.csv"</span>, sep = <span class="hljs-string">','</span>)
Is_Inland &lt;- ifelse((housing$ocean_proximity == <span class="hljs-string">"INLAND"</span>),<span class="hljs-string">"Yes"</span>,<span class="hljs-string">"No"</span>)
Is_Inland.f &lt;- factor(Is_Inland, levels = c(<span class="hljs-string">"Yes"</span>,<span class="hljs-string">"No"</span>))
is.factor(Is_Inland.f)</code></pre>


<pre><code class="hljs">[1] TRUE</code></pre>


<pre class="r"><code class="hljs">housing$Is_Inland &lt;- Is_Inland.f
housing$Is_Inland</code></pre>


<pre><code class="hljs">   [1] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
  [18] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
  [35] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
  [52] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
  [69] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
  [86] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [103] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [120] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [137] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [154] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [171] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [188] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [205] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [222] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [239] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [256] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [273] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [290] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [307] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [324] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [341] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [358] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [375] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [392] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [409] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [426] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [443] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [460] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [477] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [494] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [511] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [528] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [545] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [562] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [579] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [596] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [613] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [630] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [647] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [664] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [681] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [698] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [715] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [732] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [749] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [766] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [783] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [800] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [817] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [834] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [851] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [868] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [885] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [902] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [919] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [936] No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No  No 
 [953] No  No  Yes No  No  Yes No  No  No  No  No  No  No  Yes No  Yes Yes
 [970] Yes Yes No  No  Yes Yes Yes Yes Yes No  Yes Yes Yes Yes Yes Yes Yes
 [987] Yes Yes Yes No  Yes Yes Yes Yes Yes Yes Yes Yes Yes Yes
 [ reached getOption("max.print") -- omitted 19640 entries ]
Levels: Yes No</code></pre>



</div>
<div id="use-side-by-side-box-plot-to-visualize-the-relationship-between-is_inland-and-median_house_value.-is-there-a-significant-difference-between-the-means-of-median_house_value-for-inland-and-not-inland-houses-use-t-test-to-test-your-hypothesis-for-significance-level-alpha0.01" class="section level2">
<h2>Use side by side box plot to visualize the relationship between “Is_Inland” and “median_house_value”. Is there a significant difference between the means of median_house_value for Inland and not Inland houses? Use t-test to test your hypothesis for significance level alpha=0.01)</h2>



<pre class="r"><code class="hljs">x = rnorm(housing$median_house_value)
y = rnorm(housing$Is_Inland)
t.test(x,y)</code></pre>


<pre><code class="hljs">
    Welch Two Sample t-test

data:  x and y
t = 0.25011, df = 41278, p-value = 0.8025
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -0.01676581  0.02167056
sample estimates:
    mean of x     mean of y 
-0.0001481047 -0.0026004786 </code></pre>




</div>
</div>

<div id="rmd-source-code">LS0tDQp0aXRsZTogIkV4cGxvcmluZyBEYXRhIEFuYWx5c2lzIHdpdGggUiINCm91dHB1dDogaHRtbF9ub3RlYm9vaw0KLS0tDQoNCg0KIyNQcm9ibGVtIDEtLUV4cGxvcmluZyBWZWdhcyBIb3RlbCBEYXRhc2V0DQoNCiMjIzEuRXhwbG9yZSB0aGUgb3ZlcmFsbCBzdHJ1Y3R1cmUgb2YgdGhlIGRhdGFzZXQgdXNpbmcgc3RyKCkuDQoNCg0KYGBge3J9DQpkaXJlY3RvcnkgPC0gZ2V0d2QoKQ0KDQpsYXN2ZWdhcyA8LSByZWFkLmNzdigidmVnYXNob3RlbHMuY3N2Iiwgc2VwID0gJzsnKQ0KDQpzdHIobGFzdmVnYXMpDQoNCmBgYA0KDQojIyNVc2Ugc3VtbWFyeSB0byBnZXQgYSBzdW1tYXJ5IHN0YXRpc3RpY3Mgb2YgZWFjaCB2YXJpYWJsZS4gRG9lcyBhbnkgb2YgdGhlIHZhcmlhYmxlcyBoYXZlIG1pc3NpbmcgdmFsdWVzPw0KDQpgYGB7cn0NCg0Kc3VtbWFyeShsYXN2ZWdhcykNCg0KYGBgDQojIyNEcmF3IGEgaGlzdG9ncmFtIG9mIHRoZSBzY29yZSB2YXJpYWJsZS4gRGVzY3JpYmUgd2hhdCB5b3Ugc2VlIGluIHRoZSBoaXN0b2dyYW0uDQoNCmBgYHtyfQ0KDQpsYXN2ZWdhcyA8LSByZWFkLmNzdigidmVnYXNob3RlbHMuY3N2Iiwgc2VwID0gJzsnKQ0KDQpzY29yZSA8LSB0YWJsZShsYXN2ZWdhcyRTY29yZSkNCg0KaGlzdChzY29yZSkNCg0KDQpgYGANClRoZSBIaXN0b2dyYW0gaXMgcGxvdHRlZCBieSBTY29yZSBvbiB0aGUgeC1heGlzIHYvcyBGcmVxdWVuY3kgb24gdGhlIHktYXhpcy5XZSBjYW4gc2VlIG5vIHNjb3JlcyBpbiBiZXR3ZWVuIGEwMCBhbmQgMTUwLlRoZSBoaXN0b2dyYW0gaXMgYWxzbyBza2V3ZWQgdG8gdGhlIHJpZ2h0IGFuZCBpcyBzYWlkIHRvIGJlIHBvc2l0aXZlbHkgc2tld2VkLg0KDQoNCiMjIEZpbmQgdGhlIG1vZGUgb2YgIlNjb3JlIg0KDQpgYGB7cn0NCg0KIyBDcmVhdGUgdGhlIGZ1bmN0aW9uLg0KZ2V0bW9kZSA8LSBmdW5jdGlvbihtKSB7DQogICB1bmlxdiA8LSB1bmlxdWUobSkNCiAgIHVuaXF2W3doaWNoLm1heCh0YWJ1bGF0ZShtYXRjaChtLCB1bmlxdikpKV0NCn0NCg0KIyBDcmVhdGUgdGhlIHZlY3RvciB3aXRoIG51bWJlcnMuDQptIDwtIGxhc3ZlZ2FzJFNjb3JlDQoNCiMgQ2FsY3VsYXRlIHRoZSBtb2RlIHVzaW5nIHRoZSB1c2VyIGZ1bmN0aW9uLg0KTW9kZW9mU2NvcmUgPC0gZ2V0bW9kZShtKQ0KcHJpbnQoTW9kZW9mU2NvcmUpDQpgYGANCg0KIyMgVXNlIHRoZSAicXVhbnRpbGUiIGZ1bmN0aW9uIHRvIGdldCB0aGUgcXVhbnRpbGVzIGZvciBzY29yZS4gV2hhdCBpcyB0aGUgbWVkaWFuIG9mIHNjb3JlPw0KYGBge3J9DQoNCnEgPC0gcXVhbnRpbGUobGFzdmVnYXMkU2NvcmUpDQpwcmludChxKQ0KDQpwIDwtbWVkaWFuKGxhc3ZlZ2FzJFNjb3JlKQ0KcHJpbnQocCkNCg0KYGBgDQoNCiMjVXNlIHRoZSBpZmVsc2UgZnVuY3Rpb24gKFlvdSBjYW4gZ2V0IGhlbHAgb24gdGhlIHN5bnRheCBvZiB0aGlzIGZ1bmN0aW9uIGluIFIgYnkgdHlwaW5nID9pZmVsc2UpIHRvIGNyZWF0ZSBhIGZhY3RvciB2YXJpYWJsZSAic2VudGltZW50IiB3aGljaCB0YWtlcyB0aGUgdmFsdWUgInBvc2l0aXZlIiBpZiBzY29yZSBpcyA0IG9yIDUgYW5kICJuZWdhdGl2ZSIgb3RoZXJ3aXNlLiBZb3UgY2FuIHVzZSB0aGUgbWV0aG9kICJmYWN0b3IiIHRvIGNyZWF0ZSBhIGZhY3RvciBmcm9tIGEgY2hhcmFjdGVyIHZlY3Rvci4NCg0KYGBge3J9DQoNCg0KDQpsYXN2ZWdhcyA8LSByZWFkLmNzdigidmVnYXNob3RlbHMuY3N2Iiwgc2VwID0gJzsnKQ0KDQpzZXM8LSBpZmVsc2UoKGxhc3ZlZ2FzJFNjb3JlID09IDQpIHwgKGxhc3ZlZ2FzJFNjb3JlID09IDUpLCJQb3NpdGl2ZSIsIk5lZ2F0aXZlIikNCg0Kc2VzLmYgPC0gZmFjdG9yKHNlcywgbGV2ZWxzID0gYygiUG9zaXRpdmUiLCJOZWdhdGl2ZSIpKQ0KDQppcy5mYWN0b3Ioc2VzLmYpDQoNCmxhc3ZlZ2FzJFNlbnRpbWVudDwtc2VzLmYNCg0KbGFzdmVnYXMkU2VudGltZW50DQoNCg0KYGBgDQoNCiMjVGFrZSBhIHN1bW1hcnkgb2YgInNlbnRpbWVudCIgdG8gbWFrZSBzdXJlIHRoYXQgdGhlIGZyZXF1ZW5jaWVzIG9mICJwb3NpdGl2ZSIgYW5kICJuZWdhdGl2ZSIgY2F0ZWdvcmllcyBhcmUgY29uc2lzdGVudCB3aXRoIHRoZSBmcmVxdWVuY3kgb2YgdGhlIHZhbHVlcyBpbiBTY29yZSAoZS5nLiwgdGhlIGZyZXF1ZW5jeSBmb3IgdGhlICJwb3NpdGl2ZSIgc2VudGltZW50IHNob3VsZCBiZSBlcXVhbCB0byB0aGUgY29tYmluZWQgZnJlcXVlbmN5IG9mIDQgYW5kIDUgZm9yIHRoZSBTY29yZSkNCg0KYGBge3J9DQoNCmxhc3ZlZ2FzIDwtIHJlYWQuY3N2KCJ2ZWdhc2hvdGVscy5jc3YiLCBzZXAgPSAnOycpDQoNCnNlczwtIGlmZWxzZSgobGFzdmVnYXMkU2NvcmUgPT0gNCkgfCAobGFzdmVnYXMkU2NvcmUgPT0gNSksIlBvc2l0aXZlIiwiTmVnYXRpdmUiKQ0KDQpzZXMuZiA8LSBmYWN0b3Ioc2VzLCBsZXZlbHMgPSBjKCJQb3NpdGl2ZSIsIk5lZ2F0aXZlIikpDQoNCmlzLmZhY3RvcihzZXMuZikNCg0KbGFzdmVnYXMkU2VudGltZW50PC1zZXMuZg0KDQpzdW1tYXJ5KGxhc3ZlZ2FzJFNlbnRpbWVudCkNCg0KDQpzdW1tYXJ5KGxhc3ZlZ2FzJFNjb3JlID09IDQgfGxhc3ZlZ2FzJFNjb3JlID09IDUpDQoNCmBgYA0KDQojIyBVc2UgY2hpc3F1YXJlIHRlc3QgdG8gZGV0ZXJtaW5lIGlmIHNlbnRpbWVudCBpcyBhc3NvY2lhdGVkIHdpdGggYW55IG9mIHRoZSB2YXJpYWJsZXM6ICJQb29sIiwgIkd5bSIsIkZyZWUuSW50ZXJuZXQiLCAiUGVyaW9kLm9mLlN0YXkiLCAidHJhdmVybGVyLnR5cGUiIiwgYW5kICJob3RlbC5zdGFycyIgKEFzc3VtZSB0aGUgc2lnbmlmaWNhbmNlIGxldmVsIGFscGhhPTAuMDEpLiBXaGljaCBvZiB0aGVzZSB2YXJpYWJsZXMgYXJlIGFzc29jaWF0ZWQgd2l0aCBzZW50aW1lbnQ/DQoNCmBgYHtyfQ0KDQpsYXN2ZWdhcyA8LSByZWFkLmNzdigidmVnYXNob3RlbHMuY3N2Iiwgc2VwID0gJzsnKQ0KDQpzZXM8LSBpZmVsc2UoKGxhc3ZlZ2FzJFNjb3JlID09IDQpIHwgKGxhc3ZlZ2FzJFNjb3JlID09IDUpLCJQb3NpdGl2ZSIsIk5lZ2F0aXZlIikNCg0Kc2VzLmYgPC0gZmFjdG9yKHNlcywgbGV2ZWxzID0gYygiUG9zaXRpdmUiLCJOZWdhdGl2ZSIpKQ0KDQppcy5mYWN0b3Ioc2VzLmYpDQoNCnNlcy5mDQoNCmxhc3ZlZ2FzJFNlbnRpbWVudDwtc2VzLmYNCg0KIyBMb2FkIHRoZSBsaWJyYXJ5Lg0KbGlicmFyeSgiTUFTUyIpDQoNCiMgUGVyZm9ybSB0aGUgQ2hpLVNxdWFyZSB0ZXN0Lg0KY2hpc3EgPC0gY2hpc3EudGVzdChsYXN2ZWdhcyRTZW50aW1lbnQsbGFzdmVnYXMkR3ltKQ0KDQoNCg0KYGBgDQogU2VudGltZW50IGNhbiBiZSBhc3NvY2lhdGVkIHdpdGggJEd5bSAsJFBvb2wsJEZyZWUuSW50ZXJuZXQgYXMgdGhlIGNoaS1zcXVhcmUgdGVzdCBldmFsdWF0ZXMgd2hldGhlciB0aGVyZSBpcyBhIHNpZ25pZmljYW50IGFzc29jaWF0aW9uIGJldHdlZW4gdGhlIGNhdGVnb3JpZXMgb2YgdGhlIHR3byB2YXJpYWJsZXMuVGhlIGNoaXNxLnRlc3QoKSBmdW5jdGlvbnMgb25seSB3b3JrcyB3aGVuIHRoZSBsZW5ndGggb2YgdGhlIHR3byB2YXJhaWFibGVzIGlzIHNhbWUuDQoNCiNFeHBsb3JpbmcgQ2FsaWZvcm5pYSBIb3VzaW5nIERhdGFzZXQNCg0KIyMgRXhwbG9yZSB0aGUgc3RydWN0dXJlIG9mIGRhdGFzZXQgdXNpbmcgc3RyIGZ1bmN0aW9uLiBIb3cgbWFueSBudW1lcmljYWwgYW5kIGNhdGVnb3JpY2FsIGF0dHJpYnV0ZXMgYXJlIHRoZXJlIGluIHRoZSBkYXRhc2V0Lg0KDQpgYGB7cn0NCg0KZGlyZWN0b3J5IDwtIGdldHdkKCkNCg0KaG91c2luZyA8LSByZWFkLmNzdigiaG91c2luZy5jc3YiLCBzZXAgPSAnLCcpDQoNCnN0cihob3VzaW5nKQ0KDQoNCmBgYA0KDQojI1Rha2UgYSBzdW1tYXJ5IHN0YXRpc3RpY3Mgb2YgdGhlIGRhdGFzZXQuIERvZXMgYW55IG9mIHRoZSB2YXJpYWJsZXMgaGF2ZSBtaXNzaW5nIHZhbHVlcz8NCg0KYGBge3J9DQojI1RvICBmaW5kIHRoZSBTdW1tYXJ5IG9mIHRoZSBEYXRhc2V0DQpzdW1tYXJ5KGhvdXNpbmcpDQoNCiMjIFRvIGZpbmQgdGhlIG1pc3NpbmcgdmFsdWVzIGluIHRoZSBkYXRhc2V0DQp3aGljaChpcy5uYShob3VzaW5nJHRvdGFsX2JlZHJvb21zKSkNCg0KDQpgYGANCg0KDQojI1JlbW92ZSB0aGUgcm93cyB3aXRoIG1pc3NpbmcgdmFsdWVzLiBZb3UgY2FuIHVzZSBlaXRoZXIgImNvbXBsZXRlLmNhc2VzIiBmdW5jdGlvbiBvciAibmEub21pdCIgZnVuY3Rpb24gZm9yIHRoaXMgcHVycG9zZS4gUnVuID9jb21wbGV0ZS5jYXNlcyBhbmQgP25hLm9taXQgaW4gUiB0byBnZXQgaGVscCBvbiB0aGVzZSBmdW5jdGlvbnMgYW5kIHRvIHNlZSBzb21lIGV4YW1wbGVzLg0KDQpgYGB7cn0NCg0KbmEub21pdChob3VzaW5nJHRvdGFsX2JlZHJvb21zKQ0KDQoNCmBgYA0KDQojI0RyYXcgYSBoaXN0b2dyYW0gYW5kIGJveHBsb3Qgb2YgdGhlIG1lZGlhbl9ob3VzZV92YWx1ZS4gV2hhdCBjYW4geW91IHNheSBhYm91dCB0aGUgc2hhcGUgb2YgbWVkaWFuX2hvdXNlX3ZhbHVlPyBJcyB0aGUgbWVkaWFuX2hvdXNlX3ZhbHVlIHNhbXBsZSBwb3NpdGl2ZWx5IHNrZXdlZCwgc3ltbWV0cmljLCBvciBuZWdhdGl2ZWx5IHNrZXdlZD8NCg0KYGBge3J9DQoNCmhvdXNpbmcgPC0gcmVhZC5jc3YoImhvdXNpbmcuY3N2Iiwgc2VwID0gJywnKQ0KDQptZWRpYW5faG91c2VfdmFsdWUgPC0gaG91c2luZyRtZWRpYW5faG91c2VfdmFsdWUNCg0KaGlzdChtZWRpYW5faG91c2VfdmFsdWUpDQoNCmJveHBsb3QoaG91c2luZyRtZWRpYW5faG91c2VfdmFsdWUsIG1haW49IkJveHBsb3Qgb2YgbWVkaWFuX2hvdXNlX3ZhbHVlIikNCg0KDQoNCg0KYGBgDQpUaGUgaGlzdG9ncmFtIG9mIG1lZGlhbl9Ib3VzZV9WYWx1ZSBpcyBwb3NpdGl2ZWx5IHNrZXdlZC4NCg0KDQojI1VzZSBRLVEgcGxvdCB0byBleGFtaW5lIGlmIHRoZSBkaXN0cmlidXRpb24gb2YgbWVkaWFuX2hvdXNlX3ZhbHVlIGlzIGFwcHJveGltYXRlbHkgbm9ybWFsPw0KDQpgYGB7cn0NCg0KcXFub3JtKGhvdXNpbmckbWVkaWFuX2hvdXNlX3ZhbHVlKQ0KDQoNCmBgYA0KDQojI1VzZSBJUVIgbWV0aG9kIHRvIGZpbmQgb3V0bGllcnMgb2YgdGhlIG1lZGlhbl9ob3VzZV92YWx1ZSBhdHRyaWJ1dGUuIEhvdyBtYW55IG91dGxpZXJzIGRvZXMgdGhpcyBhdHRyaWJ1dGUgaGF2ZT8NCg0KYGBge3J9DQpJUVIgPC0gSVFSKGhvdXNpbmckbWVkaWFuX2hvdXNlX3ZhbHVlKQ0KSVFSDQoNCg0KYGBgDQojI1VzZSAicGFpcnMiIGFuZCAiY29yIiBmdW5jdGlvbnMgdG8gZ2V0IGEgc2NhdHRlciBwbG90IGFuZCBjb3JyZWxhdGlvbiBtYXRyaXggb2YgbnVtZXJpY2FsIGF0dHJpYnV0ZXMgaW4gdGhlIGRhdGFzZXQuIERvZXMgYW55IG9mIHRoZSBudW1lcmljYWwgYXR0cmlidXRlcyBoYXZlIGEgbGluZWFyIGNvcnJlbGF0aW9uIHdpdGggbWVkaWFuX2hvdXNlX3ZhbHVlPw0KDQpgYGB7cn0NCg0KbnVtZXJpY19hdHRyaWJ1dGVzID0gaG91c2luZ1ssYygibWVkaWFuX2luY29tZSIsIm1lZGlhbl9ob3VzZV92YWx1ZSIpXQ0KDQpwYWlycyhudW1lcmljX2F0dHJpYnV0ZXMpDQoNCmNvcihudW1lcmljX2F0dHJpYnV0ZXMpDQoNCg0KYGBgDQoNClRoZSBtZWRpYW4gaW5jb21lIGlzIGNvcnJlbGF0ZWQgd2l0aCBtZWRpYW5faG91c2VfdmFsdWUgaW4gdGhlIGhvdXNpbmcgZGF0YXNldC4NCg0KIyNJcyB0aGVyZSBhIHNpZ25pZmljYW50IGRpZmZlcmVuY2UgYmV0d2VlbiB0aGUgbWVhbiBvZiBtZWRpYW5faG91c2VfdmFsdWUgYWNyb3NzIGRpZmZlcmVudCBsZXZlbHMgb2Ygb2NlYW5fcHJveGltaXR5ID8gVXNlIHNpZGUgYnkgc2lkZSBib3ggcGxvdCBhbmQgQU5PVkEgKHdpdGggc2lnbmlmaWNhbmNlIGxldmVsIGFscGhhPTAuMDEpIHRvIGFuc3dlciB0aGlzIHF1ZXN0aW9uLiBJbnRlcnByZXQgdGhlIHNpZGUgYnkgc2lkZSBib3ggcGxvdCwgZG8geW91IHNlZSBhbnkgZGlmZmVyZW5jZSBiZXR3ZWVuIHRoZSBtZWFuIG9mIHRoZSBtZWRpYW5faG91c2VfdmFsdWUgZm9yIGRpZmZlcmVudCBvY2Vhbl9wcm94aW1pdHkgbGV2ZWxzPw0KDQoNCmBgYHtyfQ0KDQoNCnBsb3QoaG91c2luZyRtZWRpYW5faG91c2VfdmFsdWUgfiBob3VzaW5nJG9jZWFuX3Byb3hpbWl0eSwgY29sPSJibHVlIikNCg0KDQpgYGANClllcywgdGhlcmUgYXJlIGRpZmZlcmVuY2VzIGJldHdlZW4gdGhlIG1lYW4gb2YgZGlmZmVyZW50IG9jZWFuIHByb3hpbWl0eSBsZXZlbHMuVGhlIG1lYW4gb2YgdGhlIElzbGFuZCBpcyBoaWdoZXN0IGFtb25nc3QgYWxsIGFuZCB0aGUgbWVhbiBvZiBpbmxhbmQgaXMgdGhlIGxvd2VzdC4NCg0KIyNVc2UgaWZlbHNlIGZ1bmN0aW9uIHRvIGNyZWF0ZSBhIG5ldyBmYWN0b3IgdmFyaWFibGUgIklzX0lubGFuZCIgd2hpY2ggdGFrZXMgdGhlIHZhbHVlICJZZXMiIGlmIHRoZSBvY2Vhbl9wcm94aW1pdHkgaXMgIklubGFuZCIgYW5kIE5vIiBvdGhlcndpc2UuDQoNCmBgYHtyfQ0KDQoNCmhvdXNpbmcgPC0gcmVhZC5jc3YoImhvdXNpbmcuY3N2Iiwgc2VwID0gJywnKQ0KDQpJc19JbmxhbmQgPC0gaWZlbHNlKChob3VzaW5nJG9jZWFuX3Byb3hpbWl0eSA9PSAiSU5MQU5EIiksIlllcyIsIk5vIikNCg0KSXNfSW5sYW5kLmYgPC0gZmFjdG9yKElzX0lubGFuZCwgbGV2ZWxzID0gYygiWWVzIiwiTm8iKSkNCg0KaXMuZmFjdG9yKElzX0lubGFuZC5mKQ0KDQpob3VzaW5nJElzX0lubGFuZCA8LSBJc19JbmxhbmQuZg0KDQpob3VzaW5nJElzX0lubGFuZA0KDQoNCmBgYA0KDQojI1VzZSBzaWRlIGJ5IHNpZGUgYm94IHBsb3QgdG8gdmlzdWFsaXplIHRoZSByZWxhdGlvbnNoaXAgYmV0d2VlbiAiSXNfSW5sYW5kIiBhbmQgIm1lZGlhbl9ob3VzZV92YWx1ZSIuIElzIHRoZXJlIGEgc2lnbmlmaWNhbnQgZGlmZmVyZW5jZSBiZXR3ZWVuIHRoZSBtZWFucyBvZiBtZWRpYW5faG91c2VfdmFsdWUgZm9yIElubGFuZCBhbmQgbm90IElubGFuZCBob3VzZXM/IFVzZSB0LXRlc3QgdG8gdGVzdCB5b3VyIGh5cG90aGVzaXMgZm9yIHNpZ25pZmljYW5jZSBsZXZlbCBhbHBoYT0wLjAxKQ0KDQpgYGB7cn0NCnggPSBybm9ybShob3VzaW5nJG1lZGlhbl9ob3VzZV92YWx1ZSkNCnkgPSBybm9ybShob3VzaW5nJElzX0lubGFuZCkNCnQudGVzdCh4LHkpDQoNCmBgYA0KDQoNCg==</div>



</div>








