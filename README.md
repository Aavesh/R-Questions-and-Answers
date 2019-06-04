---


---

<p><strong>Q1 ) Consider following vector wheel:</strong></p>
<p>wheel &lt;- c(“DD”,“7”,“BBB”,“BB”,“B”,“c”,“0”)</p>
<p>For above vector make a data frame that contains every possible combination of three symbols from the wheel vector.</p>
<p>Ans) Using expand.grid() this can be achieved with single line of code.</p>
<p>combos&lt;- expand.grid(wheel,wheel,wheel,stringAsFactors=FALSE)</p>
<p>combos</p>
<p><strong>Q2) How sorting sort() is done in R? Is it similar to C language?</strong></p>
<p>Ans) To sort a dataframe in R, use the order( ) function. By default, sorting is <a href="http://ASCENDING.To">ASCENDING.To</a> sort in descending order we can pass decreasing=TRUE.</p>
<p>R performs lexicographic sorting as opposed to C language,which sort in ASCII order. This means that the sort order will depend upon the locale of the machine the codes run on. In other words ,the sort order may be different if the machine running R is configured to Danish then it will if the machine is configured to use English.</p>
<p><strong>Q3) Explain R Data Frame ?</strong></p>
<p>Ans 3) Data Frames are the two dimensional version of a list.You can think of a data frame as R’s equivalent to the Excel spreadsheet because it stores data in similar format</p>
<p>Following are the characteristics of a data frame.</p>
<ul>
<li>
<p>The column names should be non-empty.</p>
</li>
<li>
<p>The row names should be unique.</p>
</li>
<li>
<p>The data stored in a data frame can be of numeric, factor or character type.</p>
</li>
<li>
<p>Each column should contain same number of data items.</p>
</li>
</ul>
<p><strong>Q4) What are different data data structures in R? Explain them too?</strong></p>
<p>Ans) R has following Data structures</p>
<ol>
<li>
<p>Vector</p>
</li>
<li>
<p>Matrix</p>
</li>
<li>
<p>Array</p>
</li>
<li>
<p>List</p>
</li>
<li>
<p>Data frame</p>
</li>
</ol>
<p><strong>Q5) Imagine you counted the birds in your backyard on three different days and store the count in the matrix</strong></p>
<p>like this</p>
<p>counts&lt;- matrix(c(2,3,4,8,4,5,2,3,4),ncol=3)</p>
<p>colnames(counts)&lt;- c(“sparrows”,“crow”,“owl”)</p>
<p>counts</p>
<p><img src="https://lh3.googleusercontent.com/FfShcPue7oi1jbyCIGoiuZAYkxPNqa9YMj7W2z7-lxX7pJO4fa57DWyFl20DDvOYb6oKfIGxrWzWsiGnh2bVmfDQKtwcd7ffn60c32Fmtb7AYQ1oJ279JbP9HOM79Up8kITJ5auw" alt=""></p>
<p>Using one line code find maximum count per species on any given day.</p>
<p>Ans) The same can be achieved using apply().</p>
<p>apply(counts,2,max)</p>
<p><img src="https://lh3.googleusercontent.com/lo94S6Ldd10Z7GU7dbDJAxyel3V_1H43zZMCJI5U1BNX4IRy_JG9gezt_bD7ycJTAb8FatRmiNzgkbRJ8aA4splB8-YB5w6FwCrXjCsACDffN_yeEgIPmzfcHDFbjtmZhPfd5z7S" alt=""></p>
<p>The function syntax is below</p>
<p>: apply(variable, margin, function).</p>
<p>–variable is the variable you want to apply the function to.</p>
<p>–margin specifies if you want to apply by row (margin = 1), by column (margin = 2), or for each element (margin = 1:2). Margin can be even greater than 2, if we work with variables of dimension greater than two.</p>
<p>–function is the function you want to apply to the elements of your variable</p>
<p><strong>Q6) What are different ways of specifying the subset in R?</strong></p>
<p>Ans6) Subsetting is a very important component of data management and there are several ways that one can subset data in R.Consider a vector x:</p>
<p>x &lt;- c(2.1, 4.2, 3.3, 5.4,6.5)</p>
<p>Table below illustrates the five way of specifying the subset elements.</p>
<p><img src="https://lh5.googleusercontent.com/uV0zGmf3tqL-3b6aAJ0TtWakQJUbAKPfXbEAnuxgwgdHq7UnM8dAt1EJYJuHAbZ_RbqegVoEAUv6VhvHmEBRO1qe2N-aqsiDxl1G6BtyqCVDwCScHM-1jWznQUjc7k0xAvyZz2bM" alt=""></p>
<p><strong>Q7) Explain merge() function and how it is similar to database join ?</strong></p>
<p>Ans) Merge function is used to combine data frames. The merge function allows 4 ways of combining data,just like the database join.</p>
<ul>
<li>
<p>Natural join: To keep only rows that match from the data frames, specify the argument all=FALSE.</p>
</li>
<li>
<p>Full outer join:To keep all rows from both data frames, specify all=TRUE.</p>
</li>
<li>
<p>Left outer join:To include all the rows of your data frame x and only those from y that match, specify x=TRUE.</p>
</li>
<li>
<p>Right outer join:To include all the rows of your data frame y and only those from x that match, specify y=TRUE.</p>
</li>
</ul>
<p><strong>Q8) Consider a plain text file poker.csv with introductory text that is not part of the dataset . Below find the content of poker.csv as shaded.</strong></p>
<p>This is test data to give a example</p>
<p>We accidentally repeated the last row of data</p>
<p>“Card” , “suit” , “value”</p>
<p>“Ace” , “spades”,”14”</p>
<p>“King”,”spades”,”13”</p>
<p>“Queen”,”spades”,”12”</p>
<p>“Jack” ,”spades”,”10”</p>
<p>“Jack”,”spades”,””10”</p>
<p>Using read.table(),write a code in R that will read just the 5 lines(4 rows plus a header)</p>
<p>Ans) read.table(“poker.csv”, sep=",",header=TRUE,skip=3,nrows=5)</p>
<p><strong>Q9) Which of these are character strings 1, “1” , and “one”</strong></p>
<p>Ans ) a) 1 b) only “one”</p>
<p>c) only “1” d) “1” and “one” are character strings</p>
<p><strong>Q10)From where does indexing starts in R vectors ?</strong></p>
<p>Ans) The vector indices in R starts with 1. This is opposite to most the the programing language such as C where indices start at 0.</p>
<p><strong>Q11) Explain dim(x) function in R ? Give a example to support.</strong></p>
<p>Ans) The dim function of the R programming language returns the dimension (e.g. the number of columns and rows) of a matrix, array or dataframe.</p>
<p>Example:</p>
<p>x&lt;-c(2,3,4,5,6,7,8,9,0)</p>
<p>y&lt;-c(2,2,2,2,2,2,2,2,2)</p>
<p>data&lt;-data.frame(x,y)</p>
<p>dim(data)</p>
<p><strong>Q12) Explain traceback in R?</strong></p>
<p>Ans) Traceback returns a call stack, a list of functions that R called in the order that it called them. The top function will be the function that caused the error and the bottom function will be the command you entered in command line.</p>
<p>Q13) How to load a package in your R session?</p>
<p>Ans) To use an R package ,one need to use the following command :</p>
<p>library(package name)</p>
<p>To see which packages you currently have in your library, run following command in command line:</p>
<p>library()</p>
<p><strong>Q14) R has various commands for cumulative statistics . Explain following commands with examples?</strong></p>
<ol>
<li>cumsum(x) b) cummax(x)</li>
</ol>
<p>Ans) cumsum(x) : Its gives the cumulative sum of a vector</p>
<p>cummax(x) : The cumulative maximum value</p>
<p>Example:</p>
<p>x&lt;-c(2,3,4,5,6,7,8,9,0)</p>
<p>cumsum(x)</p>
<p>cummax(x)</p>
<p>The output of above command is shown below:</p>
<p><img src="https://lh5.googleusercontent.com/nCfe5fjmrTm1RgNBl24zggdQAfW9InVKRV8gs8i-kXsfHhLpJvRfOmCG0zF-3uyvk7icrxEF2pxjFAo13tNpUSkJdAQKDjk30_-hJPYi-DB2kBomcsq_d2ce2k7Spt5k7kweumC4" alt=""></p>
<p><strong>Q15) Dplyr is one of important libraries of R, name few important functions of this library?</strong></p>
<p>Ans) The R package dplyr is an extremely useful resource for data cleaning, manipulation, visualisation and analysis.Below are some of the imp. Functions in dplyr</p>
<p>select()</p>
<p>filter()</p>
<p>mutate()</p>
<p>group_by()</p>
<p>summarise()</p>
<p>arrange()</p>
<p>join()</p>
<p><strong>Q16) Explain the functionality of set.seed() in R?</strong></p>
<p>Ans) Set the seed of R‘s random number generator, which is useful for creating simulations or random objects that can be reproduced.You have to set seed every time you want to get a reproducible random result.</p>
<p>set.seed(1)</p>
<p>rnorm(4)</p>
<p>set.seed(1)</p>
<p>rnorm(4)</p>
<p><strong>Q17) What is the output of following task ?<br>
x=“ABC”<br>
class(x)</strong></p>
<p>Ans) [1] “character”</p>
<p><strong>Q18) What is rattle library in R?</strong></p>
<p>Ans18) Rattle is a popular GUI for data mining using R. It presents statistical and visual summaries of data, transforms data so that it can be readily modeled, builds both unsupervised and supervised machine learning models from the data, presents the performance of models graphically, and scores new datasets for deployment into production.</p>
<p>A key feature is that all of your interactions through the graphical user interface are captured as an R script that can be readily executed in R independently of the Rattle interface.</p>
<p>Q19)List few commands in R that are used for debugging?</p>
<p>Ans19)browser()</p>
<p>debug()</p>
<p>recover()</p>
<p>setBreakpoint()</p>
<p>traceback().</p>
<p><strong>Q20) How to find missing values in dataset in R?</strong></p>
<p>Ans20) In R , missed values is represented as NA. To find missing values in dataset use function <a href="http://is.na">is.na</a>().</p>
<p>Example:</p>
<p>month &lt;- c(“jan”, “feb”, NA)</p>
<p>sales &lt;- c(450,233,89)</p>
<p>dt &lt;- data.frame(month,sales)</p>
<p><a href="http://is.na">is.na</a>(dt)</p>
<p>Output :</p>
<p><img src="https://lh4.googleusercontent.com/mXhI6EEa97oHpb_cpC9_NYgzmvEmZmUvS04RnM5Sj0kTaINCxzEN3zB3oPeViPODqVYvE3L5jVlv3vDbM5rwa3mecuhQOlbX4Hrgd0sDr2qiIEnQOVbjl1_lyk7GZDgNQ3EYidSF" alt=""></p>
<p><strong>Q21) What will be the output of below codes in R:</strong></p>
<p>month &lt;- c(“jan”, “feb”, “mar”)</p>
<p>all_months&lt;-c(“jan”, “feb”,</p>
<p>“mar”,“apr”,“may”,“june”,“july”,“aug”,“sep”,“oct”,“nov”,“dec”)</p>
<p>month %in% all_months</p>
<p>month==all_months</p>
<p>Ans21) [1] TRUE TRUE TRUE</p>
<p>[1] TRUE TRUE TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE</p>
<p>FALSE</p>
<p>Q22) Explain usage of cbind() in R and write down its syntax ?</p>
<p>Ans22) Column Bind – Cbind in R appends or combines vector, matrix or data</p>
<p>frame by columns.However The number of rows in two dataframes needs</p>
<p>to be same.</p>
<p>Example:</p>
<p>m &lt;- cbind(1, 1:7) # the ‘1’ (= shorter vector) is recycled</p>
<p>M</p>
<p>Q23) What is R Markdown ?</p>
<p>Ans23) R Markdown is a file format for making dynamic documents with R. An R Markdown document is written in markdown (an easy-to-write plain text format) and contains chunks of embedded R code.</p>
<p>RMarkdown uses Markdown syntax. Markdown is a very simple ‘markup’ language which provides methods for creating documents with headers, images, links etc. from plain text files, while keeping the original plain text file easy to read. One can convert Markdown documents to many other file types like .html or .pdf to display the headers, images etc…</p>
<p>Q24) What is difference between matrix and data frames in R?</p>
<p>Ans) Dataframe can contain different type of data but matrix can contain only similar</p>
<p>type of data.</p>
<p>Q25) Explain readline() in R with examples?</p>
<p>Ans) Readline() is used to read some or all text lines from a connection,</p>
<p>including files.This function will return a single element character</p>
<p>vector,however we require we need to take conversations.</p>
<p>Example:</p>
<p>name&lt;-readline ( prompt="what is your name : ")</p>
<p>code&lt;-readline (prompt="enter employee code : ")</p>
<p>my.code &lt;- as.integer(code)</p>
<p>print(paste(“Hi,”, name, my.code, “Welcome.”))</p>
<p>Ques26) Suppose there are twelve multiple choice questions in an English class</p>
<p>quiz.Each question has five possible answers, and only one of them is</p>
<p>correct. Find the probability of having exactly 4 or less correct answers</p>
<p>If a student attempt to answer every question in random ?</p>
<p>Ans) Since only one out of five possible answers is correct,the probability of</p>
<p>answering question correct randomly is ⅕ = .2</p>
<p>Using cumulative probability function for binomial distribution</p>
<p>pbinom(4,size=12,prob=0.2)</p>
<p>Output:</p>
<p>[1] 0.9274445</p>
<p>Ques 27) If there are twelve cars crossing a bridge per minute on average,find</p>
<p>the probability of having seventeen or more cars crossing the bridge in</p>
<p>a particular minute?</p>
<p>Ans) The probability of having sixteen or less cars crossing the bridge in a</p>
<p>particular minute is given by function ppois.</p>
<p>ppois(16, lambda =12 ) # lower tail</p>
<p>[1] 0.89871</p>
<p>Hence the probability of having seventeen of more cars crossing the</p>
<p>bridge in a minute is in the upper trail of probability density function.</p>
<p>ppois(16 , lambda=12,lower=FALSE ) # upper tail</p>
<p>[1] 0.10129</p>
<p>Ques 28) Carefully look at below code and predict the output of the code:</p>
<p>a=3</p>
<p>b=5</p>
<p>f&lt;-function(x)</p>
<p>{</p>
<p>a*x + b</p>
<p>}</p>
<p>g&lt;-function(x)</p>
<p>{</p>
<p>a=2</p>
<p>b=1</p>
<p>f(x)</p>
<p>}</p>
<p>g(2)</p>
<p>Ans28) Above codes demonstrate lexical Scoping in R.</p>
<p>Under lexical scoping rules, if an “unknown” variable is referred to in a</p>
<p>function, the idea is to use the version that is “in scope” in the enclosing piece</p>
<p>of code (and apply this rule recursively) — this is the scoping rule used by R .</p>
<p>Hence in above example f(x) will take values of a and b defined in the function</p>
<p>as g(x) wil have a different environment .Also f(x) will take global variables</p>
<p>.Considering this Output of codes will be :</p>
<p>[1] 11</p>
<p>Ques 29) Explain Confusion Matrix and provide a example in R?</p>
<p>Ans29) A confusion matrix is a summary of prediction results on a classification problem.</p>
<p>The number of correct and incorrect predictions are summarized with count values</p>
<p>and broken down by each class. This is the key to the confusion matrix.</p>
<p>Example :</p>
<p>We use caret library for confusion matix:</p>
<p>library(caret)</p>
<p>expected &lt;- factor(c(1, 1, 0, 1, 0, 0, 1, 0, 0, 0))</p>
<p>predicted &lt;- factor(c(1, 0, 0, 1, 0, 0, 1, 1, 1, 0))</p>
<p>results &lt;- confusionMatrix(data=predicted, reference=expected)</p>
<p>print(results)</p>
<p>Ques 31) Explain rbinom function with example?</p>
<p>Ans 31) R’s rbinom function simulates a series of Bernoulli trials and return the results. The</p>
<p>function takes three arguments:</p>
<ul>
<li>
<p>Number of observations you want to see</p>
</li>
<li>
<p>Number of trials per observation</p>
</li>
<li>
<p>probability of success for each trial</p>
</li>
</ul>
<p>Example :</p>
<h1 id="binomial-simulation-in-r">binomial simulation in r</h1>
<p>rbinom(10, 100,.5)</p>
<p>[1] 52 55 51 50 46 42 50 49 46 56</p>
<p>Ques31) Consider a vector x as an example,use Shapiro-Wilks test to demonstrate</p>
<p>normality of data.Also explain significance of p-value.</p>
<p>Ans31) Shapiro-Wilks is probably the mostly used method to test normality of data.</p>
<p>The function to perform this test, conveniently called</p>
<p>shapiro.test().</p>
<p>set.seed(100)</p>
<p>x &lt;- rbinom(15,5,.6)</p>
<p>shapiro.test(x)</p>
<p>Output:</p>
<p>Shapiro-Wilk normality test data: x W = 0.8816, p-value = 0.0502</p>
<p>This p-value tells you what the chances are that the sample comes from a</p>
<p>normal distribution. The lower this value, the smaller the chance. Statisticians</p>
<p>typically use a value of 0.05 as a cutoff, so when the p-value is lower than 0.05,</p>
<p>you can conclude that the sample deviates from normality.</p>
<p>Ques 32) Explain apriori algorithm and which package is required for using apriori?</p>
<p>Ans 32 ) Apriori envisions an iterative approach where it uses k-Item sets to search for</p>
<p>(k+1)-Item sets. The first 1-Item sets are found by gathering the count of</p>
<p>each item in the set. Then the 1-Item sets are used to find 2-Item sets and</p>
<p>so on until no more k-Item sets can be explored; when all our items</p>
<p>land up in one final observation as visible in our last row of the table</p>
<p>above. One exploration takes one scan of the complete dataset.</p>
<p>The package which is used to implement the Apriori</p>
<p>algorithm in R is called arules</p>
<p>Ques 33)Consider two vectors as defined below:</p>
<p>x&lt;-c(1,2,3,4,5,6)</p>
<p>y&lt;-c(7,8,9)</p>
<p>What is the output of below vector:</p>
<p>z&lt;-x*y</p>
<p>Ans) [1] 7 16 27 28 40 54</p>
<p>Ques 34)Shapefiles is GIS format for geometric/geographic representation, give</p>
<p>example of library that you will use to read shapefile in R along</p>
<p>with code.</p>
<p>Ans34) There are couple of library in R for loading GIS data, rgdal is one</p>
<p>of the widely used library for dealing with shapefiles and other long</p>
<p>and lat data.</p>
<p>Rgdal has following function to read shapefile .</p>
<p>require(rgdal)</p>
<p>shape &lt;- readOGR(dsn = “.”, layer = “SHAPEFILE”)</p>
<p>Ques 35) Assume that the test scores of a college entrance exams fit a normal distribution. Furthermore the mean test score is 72 , and the standard deviation is 15.2. What is the percentage of student scoring 84 or more in the exam?</p>
<p>Ans35) We apply the function pnorm of the normal distribution with mean 72 and sd as 15.3. Since we are looking for student scoring higher than 84, we are interested in upper tail of the normal distribution.</p>
<p>pnorm(84,mean=72,sd=15.2, lower.tail=FALSE)</p>
<p>Output:</p>
<p>[1] 0.21492</p>
<p>Ques 36) What is Chi-Square test ,provide its syntax in R?</p>
<p>Ans 36) The chi-square test is used to analyze the frequency table (i.e. contingency table) formed by two categorical variables. The chi-square test evaluates whether there is a significant association between the categories of the two variables</p>
<p>The basic syntax for creating a chi-square test in R is −</p>
<p>chisq.test(data)</p>
<p>Following is the description of the parameters used −</p>
<ul>
<li>data is the data in form of a table containing the count value of the variables in the observation.</li>
</ul>
<p>Ques 37) Explain logical Regression and how logical regression be done in R ?</p>
<p>Ans 37) The Logistic Regression is a regression model in which the response variable (dependent variable) has categorical values such as True/False or 0/1.</p>
<p>Mathematically :</p>
<p>logit p = log p /1 − p = β0 + β1 x1 + β2 x2 + · · · + βk xk</p>
<p>Where p is probability of success/failure of output β0, β1…… βk are coefficients and x1 ,x2……xk are the input variables.</p>
<p>The basic syntax for glm() function in logistic regression is −</p>
<p>glm(formula,data,family)</p>
<p>Following is the description of the parameters used −</p>
<ul>
<li>
<p>formula is the symbol presenting the relationship between the variables.</p>
</li>
<li>
<p>data is the data set giving the values of these variables.</p>
</li>
<li>
<p>family is R object to specify the details of the model. It’s value is binomial for logistic regression.</p>
</li>
</ul>
<p>Ques 38) Explain white noise and its implementation in R?</p>
<p>Ans 38) White Noise is a sequence of random numbers and cannot be predicted. If the series of forecast errors are not white noise, it suggests improvements could be made to the predictive model.</p>
<p>The arima.sim() function can be used to simulate data from a variety of time series models. ARIMA is an abbreviation for the autoregressive integrated moving average class of models we will consider throughout this course.</p>
<p>Ques 39) List few packages in R for Deep learning implementation.</p>
<p>Ans 39) There are now various packages available for deep learning implementation in R. Few widely used are:</p>
<ol>
<li>
<p>neuralnet</p>
</li>
<li>
<p>MXNetR</p>
</li>
<li>
<p>H20</p>
</li>
<li>
<p>darch</p>
</li>
<li>
<p>Keras</p>
</li>
</ol>
<p>Ques 40) Write a function that tells how many bytes of memory an object occupies and also total size occupied by all objects in memory?</p>
<p>Ans 40) We use pryr library to compute object size</p>
<p>Example:</p>
<p>library(pryr)</p>
<p>object_size(1:10) # to compute object size</p>
<p>mem_used() # total size of all objects in memory</p>
<p>Ques 41) pryr::mem_used() tells you the total size of all objects in memory ,however the size shown is totally different from size consumed shown by OS.Why?</p>
<p>Ans ) There is big mismatch between result of mem_used() and memory usage shown by OS.Following reason attribute to same.</p>
<ol>
<li>
<p>It only includes objects created by R, not the R interpreter itself.</p>
</li>
<li>
<p>R might be holding on to memory because the OS hasn’t yet asked for it back.</p>
</li>
<li>
<p>R counts the memory occupied by objects but there may be gaps due to deleted objects. This problem is known as memory fragmentation.</p>
</li>
</ol>
<p>Ques 42)What is the parent of the global environment? What is the only environment that doesn’t</p>
<p>have a parent?</p>
<p>Ans42) The parent of the global environment is the last package that you loaded. The only</p>
<p>environment that doesn’t have a parent is the empty environment.</p>
<p>Ques 43) Do R Supports object oriented programming ? Explain any 2 approaches for OO</p>
<p>programming?</p>
<p>Ans 43) We can do object oriented programming in R. In fact, everything in R is</p>
<p>an object. An object is a data structure having some attributes and methods</p>
<p>which act on its attributes.</p>
<p>S3 Class &amp; S4 Class are two approaches for OO implementation in R.</p>
<p>The S3 approach is very simple to implement. Just add a class name to an</p>
<p>object. There are no formal requirements about the contents of the object, we</p>
<p>just expect the object to have the right information.</p>
<p>An S4 class gives a rigorous definition of an object. Any valid object of an S4</p>
<p>class will meet all the requirements specified in the definition.</p>
<p>Ques 44) Explain following functions of R : substitute() and deparse() ?</p>
<p>Ans 44) deparse() and substitute() are typically used to create character</p>
<p>strings of argument values. These character strings can then be</p>
<p>used to create more informative output.</p>
<p>Example:</p>
<p>foo1  =  function(a,  …)  {</p>
<p>arg  =  deparse(substitute(a))</p>
<p>dots  =  substitute(list(…))[-1]</p>
<p>c(arg,  sapply(dots,  deparse))</p>
<p>}</p>
<p>foo2  =  function(a,  …)  {</p>
<p>arg  =  deparse(substitute(a))</p>
<p>dots  =  list(…)</p>
<p>c(arg,  sapply(dots,  deparse))</p>
<p>}</p>
<p>x  =  1;  y  =  2;  z  =  3</p>
<p>foo1(x,  y,  z)</p>
<p>Output:</p>
<p>[1] “x” “y” “z”</p>
<p>Ques 45) Explain how environment is different from list?</p>
<p>Ans 45) The most important differences between environments and lists are:</p>
<p>1)environments have reference semantics (i.e. they don’t copy-on-modify).</p>
<p>2)environments have parents</p>
<p>3)the contents of an environment are not ordered</p>
<p>4)the contents of an environment must have unique names</p>
<p>Ques 46) Explain R6 classes ?</p>
<p>Ans) R6 classes are similar to R’s standard reference classes, but are lighter weight,</p>
<p>and avoid some issues that come along with using S4 classes .</p>
<p>Unlike many objects in R, instances (objects) of R6 classes have reference</p>
<p>semantics. R6 classes also support:</p>
<ul>
<li>
<p>public and private methods</p>
</li>
<li>
<p>active bindings</p>
</li>
<li>
<p>inheritance (superclasses) which works across packages</p>
</li>
</ul>
<p>Ques 47) List four functions (not just those in base R) that convert a string into a date</p>
<p>time object.?</p>
<p>Ans 47) At least these functions will do the trick: as.POSIXct(), as.POSIXlt(), strftime(), strptime(), lubridate::ymd_hms(). There might also be some in the timeseries packages xts or zoo and in anytime</p>
<p>Ques 48) For a analysis you need to visualize a world map first, using any library of your choice , write a program in R to show world map?</p>
<p>Ans 48) There are various libraries which can do it,however we are using ggmaps here</p>
<p>library(ggmap)</p>
<p>#using ggmaps extract world map</p>
<p>world_map &lt;- qmap(“World”, zoom = 2)</p>
<p>#see how map look</p>
<p>World_map</p>
<p>Ques 49) How parallelism can be achieved in R?</p>
<p>Ans49) The parallel library can be used to send tasks (encoded as function calls) to each of the processing cores on your machine in parallel. This is done by using the parallel::mclapply function, which is analogous to lapply, but distributes the tasks to multiple processors. Mclapply gathers up the responses from each of these function calls, and returns a list of responses that is the same length as the list or vector of input data (one return per input item).</p>
<p>Q50) What does AES function means in R?</p>
<p>Ans50) AES ( aes() ) stands for Aesthetic Mappings. Aesthetic mappings describe how variables in the data are mapped to visual properties (aesthetics) of geoms.</p>
<p>Often used in ggplot to take in inputs for showing visualizations. Each aesthetic is a mapping between a visual cue and a variable. Examples include:</p>
<ul>
<li>
<p>position (i.e., on the x and y axes)</p>
</li>
<li>
<p>color (“outside” color)</p>
</li>
<li>
<p>fill (“inside” color)</p>
</li>
<li>
<p>shape (of points)</p>
</li>
<li>
<p>line type</p>
</li>
<li>
<p>Size</p>
</li>
</ul>

