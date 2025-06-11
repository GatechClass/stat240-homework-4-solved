# stat240-homework-4-solved
**TO GET THIS SOLUTION VISIT:** [STAT240 Homework 4 Solved](https://mantutor.com/product/stat240-homework-4-solved/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113595&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;STAT240  Homework 4 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
Preliminaries

This file should be in STAT240/homework/hw04 on your local computer.

You should also download education.csv and obesity.csv to STAT240/data on your local computer.

Problem 1

The following chunk is provided for you.

What do each of these four quantities represent in real terms? Do not use technical vocabulary. For example, if it was correct, you could write that “w is the percentage of zip codes in which at least half of female adults have a bachelor’s degree.”

w is… REPLACE THIS TEXT WITH YOUR RESPONSE

x is… REPLACE THIS TEXT WITH YOUR RESPONSE

y is… REPLACE THIS TEXT WITH YOUR RESPONSE

z is… REPLACE THIS TEXT WITH YOUR RESPONSE

Problem 2

Using education_original , create a scatter plot with pct_f_bach on the x axis and pct_m_bach on the y axis. There will be one point for each zip code.

Problem 3

Our goal in this problem is to create a new dataframe called education_long . This dataframe will have the columns:

The steps to generate this new dataframe are:

Start with education_original ,

Drop any rows that have any missing data anywhere.

Pivot the dataframe such that you have TWO rows per zip code; one for each sex within zip. (Hint: We have one row per zip code in education_original , so the dataset is getting longer )

Make the column names after pivoting: zip , sex , and pct_bachelors . (This can be done either with a rename() , or with arguments within pivot_longer() .)

Make the values of sex “female” and “male” rather than “pct_f_bach” and “pct_m_bach” using case_when() . (Alternatively, a slightly easier way could be to rename() the columns to female and male before pivoting; either way is acceptable.) # Write your code here

Problem 4

Right now, the obesity data has one row for every zip-sex-age group combination; age groups are 5 years old – 17 years old, 18-34, 35-54, 55-74, and 75+.

We want to obtain a version of the obesity dataset we can merge with education_long above; so both datasets would have to have one row for every zip-sex combination.

This means we need to summarize() the obesity dataset to obtain one row per zip-sex combination, purposefully “smoothing over” all the age group detail we currently have.

The dataset we are trying to obtain will have the following first few rows:

Start from obesity ,

Remove all rows with data about the youngest age group (05-17), since the education_long dataset is only about adults, so that would be an unfair comparison.

Within each row, calculate obese_percent by taking obese/n . ( n is the number of people we have data for; pop is the total population, so obese/n is just an estimate)

Within each row, calculate obese_pop_estimate by taking obese_percent * pop .

Group and summarize the data, such that you obtain one row per zip-sex combination (like in education_long ), with the information:

Total population within that zip-sex combination: call this total_pop

Total obese population (estimated) within that zip-sex combination: call this total_obese_pop_estimate .

Note that you will have to use na.rm = T when summarizing to avoid NAs.

Remove all rows where there are 0 estimated obese individuals. (Bonus question: Why didn’t we just do this at the beginning? Answer at the bottom of the question.)

# Write your code here!

Answer to bonus question: We needed to know the pop from every single row to calculate total population of a zip-sex combo, even if there were no obese people in that row. If we would have cleared out the 0 obese rows early, we would have lost some population.

Problem 5

Create a new dataframe called joined by joining education_long and obesity_summary (note that their rows should match by zip and sex together) and only keeping rows that match in both dataframes.

Your first four rows of joined should look like this:

zip sex pct_bachelors total_pop total_obese_pop_estimate &lt;dbl&gt; &lt;chr&gt; &lt;dbl&gt; &lt;dbl&gt; &lt;dbl&gt; 1 53001 male 13 755 330.

2 53001 female 23 726 259.

3 53002 male 16.2 1052 404.

4 53002 female 25.4 977 369.

Hint: Just like we can group_by(zip, sex) , we can join_by(zip, sex) .

# Write your code here!

Problem 6

Using joined from the previous problem,

Create a scatter plot of points with pct_bachelors on the x-axis and percentage obese on the y axis. You will have to calculate percentage obese for this problem.

Problem 7

Use joined to compute:

The percentage of the entire Wisconsin adult population with a bachelor’s degree

The percentage of the entire Wisconsin adult population with obesity

Let these values print as output.

Hint: You’ll need to compute some other quantities along the way, including the number of people with a bachelors in each zip-sex, and the total Wisconsin adult population.

It is okay if one percentage is on the 0-1 scale and the other is on the 0-100 scale. You should get the following percentages:

Problem 8
