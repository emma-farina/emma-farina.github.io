---
layout: page
title: Data story
image: None
nav-menu: true
---

<div id="main" class="alt">
	
<section id="one">
	<div class="inner">
		<header class="major">
			<h1>Data story</h1>
		</header>

<script src="https://apps.elfsight.com/p/platform.js" defer></script>
<div class="elfsight-app-6b75f858-bddf-4337-ac71-6f451970c67c"></div>

<h2 id="intro">Background and motivation</h2>
		
<p align="justify">We have all experienced the negative impact of the lockdown on our health. Furthermore, studies have shown that the COVID-19 pandemic led to changes in people’s dietary habits. Some people took advantage of the lockdown as an opportunity to spend more time cooking [<a href="https://www.sciencedirect.com/science/article/pii/S0195666321006504">1</a>]. However, sticking to the usual recipes quickly became tedious, pushing people to get out of their comfort zone and try new dishes. While some people took the opportunity to improve their diet quality (i.e., consuming more fresh products) [<a href="https://www.sciencedirect.com/science/article/pii/S0195666321006504">1</a>], others became more interested in high-calorie food, most likely out of boredom [<a href="https://www.nature.com/articles/s41467-022-28498-z">2</a>-<a href="https://link.springer.com/article/10.1007/s13679-021-00466-6">3</a>]. Finally, the restrictions related to COVID-19 brought people to make more use of food delivery services [<a href="https://towardsdatascience.com/the-impact-of-covid-19-on-food-delivery-services-in-the-u-s-47eae04655c8">4</a>]. This new habit has transformed customers' experience, likely persisting even after the end of lockdown.</p>
<p align="justify">With the assumption that we can use Wikipedia pageviews and Google Trends data to infer changes in food behavior [<a href="https://www.mdpi.com/2072-6643/13/11/3683/htm">5</a>], we aim at addressing the following questions:</p>
	 <ol>
  		<li>Did healthy food become more popular, in an effort to preserve one’s health, or did unhealthy food receive the most attention?</li>
  		<li>When trying out new dishes, did individuals become more interested in their own history and traditions, or did they want to explore the cuisine of other cultures?</li>
  		<li>Did mobility restrictions during the pandemic influence the frequency of food delivery orders? Did delivery services permanently become part of most people's lives?</li>
	</ol> 
<p align="justify">We will extract Wikipedia categories of foods we are interested in, namely healthy and unhealthy food and typical dishes from different cultures, and analyse their changes in popularity throughout the last 5 years and particularly comparing the period before and during the pandemic. For analysing the rise of food delivery services, instead, we deemed Google Trends a more suitable data source, as customers directly search the names of these companies on Google when they want to order something.</p>
		

<h2 id="q1">Healthy food</h2>
		
	<p align="justify">In this first section, we ask ourselves whether individuals became more interested in healthy or unhealthy food during the pandemic. Did more time spent at home facilitate unhealthy food habits, or did it on the contrary encourage people to explore healthier diets? This aspect may be highly dependent on one’s country and culture, which makes the Wikipedia dataset an interesting resource to investigate country differences in food behavior during times of crisis.</p>
	
	<h4>Data exploration</h4>
		
	<p align="justify">To answer our question, we defined two lists of Wikipedia categories, one related to healthy food and one related to unhealthy foods. We then extracted the view counts of the pages contained in these categories. You can visualize below the categories we selected. Hover your mouse over each category to see the number of pages they contain on the English Wikipedia. For the other languages, we translated the pages contained in the English categories and collected their view counts.</p>
		
	<iframe src="./plots/healthy_pie.html" height=550 width=1200></iframe>
		
	<iframe src="./plots/unhealthy_pie.html" height=550 width=1200></iframe>
		
	<h4>Preprocessing</h4>
		
	<p align="justify">We removed the outliers as we want to avoid keeping a very sudden and very high increase in the page view count. We indeed interpret this as the result of some short trend, a recipe going viral, or a similar phenomenon. This timescale is too short for such a strong change and it could bias our data as it does not reflect the evolution of the interest and behavior of a large group of people over time.</p>
	<p align="justify">We then perform a z-score standardization on the weekly pageviews of each of our Wikipedia categories using the pageviews of that same category during the corresponding month of 2019: we subtract from our weekly view counts the mean view counts of the same month of 2019 and divide them with the standard deviation of the 2019 pageviews during that month.</p>
	
	<h4>Interest "surplus" during the pandemic</h4>
		
	<p align="justify">We thus consider 2019 as a reference for food interest, free from the influence of covid. With the standardization, we obtain the 'surplus' (positive values) or 'deficit' (negative values) of interest during the pandemic, compared to 2019. This is inspired by another study on food habits during Covid [<a href="https://www.nature.com/articles/s41467-022-28498-z">2</a>].</p>
	<p align="justify">Let us visualize what the sum of the standardized pageviews of each category looks like for each country, first for the healthy categories. We also represent data on the mobility restrictions: the percent change of the time spent at home from baseline. This data will be used again throughout our analysis, as an indication of the severity of the lockdown.</p>
		
		<iframe src="./plots/Standardized_healthy_pageviews_mob.html" height=550 width=1200></iframe>
		
	<p align="justify">Do you agree that the interest shifts in response to mobility restrictions already look quite different between languages?</p>
	<p align="justify">For some countries such as Italy and Serbia, the increase in the percent of time spent at home in March 2020 led to an increase in the interest surplus for healthy food. For Italy, during the period from July 2021 to October 2022, when the residential time was close to normality, the interest for healthy food was mostly in deficit compared to the same months of 2019. This seems to indicate that for Italian people, staying home was associated with paying more attention to the quality of one's diet.</p>
	<p align="justify">For the English data on the other hand, the interest for healthy food seemed more in excess when people spent less time at home. Perhaps having access to more shops and restaurants to find fresh produce is more important for the English-speaking world to maintain a healthy diet.</p>
	<p align="justify">As for Serbia, the interest for healthy food was quite similar to 2019, except for the duration of the first lockdown (from March 16 to May 17, 2020) where it experienced an impressive growth. It appears that the confinement inspired Serbians to improve their health.</p>
	<p align="justify">Finally, for Turkey and the English-speaking internet users, the interest for healthy food is currently in great excess compared to 2019. This result could be useful to advertisers, and may or may not be related to the greater freedom of traveling relative to the previous times. Perhaps you also recently grew a passion for cooking and recognize yourself in this data.</p>
		
		<p align="justify">Then, we produce the same visualization for the unhealthy categories. </p>
		
		<iframe src="./plots/Standardized_unhealthy_pageviews_mob.html" height=550 width=1200></iframe>
		
		<p align="justify">What do you notice about Italy? The interest for unhealthy food categories in Italy was in even greater excess than the interest for healthy food during the first lockdown. Therefore, Italian people in lockdown were perhaps just globally more interested in food in general than during previous times. </p>
		<p align="justify">For Spain and Finland, we can see a clear increase in the interest for unhealthy food following the beginning of the first lockdown. Finally, in Turkey, this interest seems always in great excess during the whole covid period. This could be related to the pandemic (the boredom of staying at home, the discovery of new foods on social media, a heavy usage of delivery apps...), but also to other factors such as the implantation of new fast food chains, new culinary trends in the country…</p>
		
		<h4>Relative interest shifts between healthy and unhealthy foods</h4>
		
		<p align="justify">Now, we build a new metric to compare healthy and unhealthy food interest for the rest of our analysis: we calculate the weekly ratio of the sum of healthy/unhealthy pageviews using the non-standardized data. We visualize this ratio, along with the mobility data.</p>
		
		<iframe src="./plots/healthy_over_unhealthy_pageviews_mob.html" height=550 width=1200></iframe>
		
		<p align="justify">First, pay attention to the range of the ratio for each country. The ratio of healthy/unhealthy pageviews remained below 1 during the entire duration of data collection for Italy, the English-speaking Wikipedia users, German-speaking users, and the Netherlands. For Turkey and Finland, the ratio fluctuated around 1. Finally, for Serbia and Spain, this ratio reached values higher than 2. It might be more meaningful to study the fluctuations of the ratio one language at a time, to rule out the effect of different numbers of pages available. Yet the availability of more pages is also an indicator of interest. It therefore seems that the interest for healthy food takes over that of unhealthy food in Serbia and Spain. On the other hand, in countries speaking Italian, English, German and Dutch, the interest for unhealthy food seemed to take over.</p>
		<p align="justify">When looking at the fluctuations for single language communities, the interest for healthy food seemed to take over the one for unhealthy food in periods when people spent less time at home. Meanwhile, for the Netherlands, Italy and Turkey, the ratio increased during the first lockdown, indicating a relative increase in the curiosity for healthy food.</p>
		<p align="justify">We compared the ratio of healthy/unhealthy food pageviews around 60 days before and after the first mobility restriction in 2020, for each language community, with a t-test. The ratio is significantly different before and after the mobility restriction for all languages except for Catalan. This confirms our previous conclusion that, in Spain, an increase of the ratio seemed more driven by time spent outside after a period of lockdown.</p>
		
		<h4>Correlation between the relative interest and the lockdown severity</h4>
		
		<p align="justify">We then asked ourselves if there was a monotonic correlation between the ratio of healthy/unhealthy pageviews and the severity of the lockdown (defined with the change in the time spent at home from baseline), using Spearman's correlation coefficient. First, we check this correlation on the entire data we have.</p>
		
		<iframe src="./plots/spearman_total.jpeg" height=300 width=1200></iframe>
		
		<p align="justify">Interestingly, the correlation seems shifted to the right, meaning that the interest for healthy food relative to unhealthy food increased with an increase in time spent at home for most Wikipedia users. This trend is however significantly the opposite for Catalan speakers.</p>
		<p align="justify">We next focus our analysis to around 60 days (about 2 months) before and after major events of the pandemic timeline, to capture the influence of the changes caused by the event. First, we study the correlation of the ratio and the mobility data about 2 months before and after the first mobility restriction.</p>
		
		<iframe src="./plots/spearman_58_Mobility.jpeg" height=300 width=1200></iframe>
		
		<p align="justify">This time, the correlations are quite spread out, with a high negative correlation for some languages (German, English and Finnish) and a moderate positive correlation for other languages (Dutch, Serbian and Italian). This once again highlights the fact that people from different cultures reacted differently to restrictions.</p>
		<p align="justify">Next, we analyze the correlations around the first normalcy time point.</p>
		
		<iframe src="./plots/spearman_59_Normalcy.jpeg" height=300 width=1200></iframe>
		
		<p align="justify">The languages for which the correlation was significant had a high positive correlation: the relative interest for healthy food seemed to increase with time spent at home for English, Dutch and Italian-speaking users.</p>
		<p align="justify">Finally, we focus on the correlations around the second normalcy time point.</p>
		
		<iframe src="./plots/spearman_59_Second_Normalcy.jpeg" height=300 width=1200></iframe>
		
		<p align="justify">You must be as surprised as we were when we found this result: the correlation between interest and mobility seemed to be the opposite for Italy compared to the first normalcy. Perhaps, as it was the second normalcy, the relationship between the newly returned freedom and the food preferences was affected by different factors.</p>
		
		<h4>To summarize, did the lockdown encourage a healthier lifestyle?</h4>
		
		<p align="justify">In this study, we did not investigate causality between the lockdown severity and the food interest, only correlations. However, we can say that overall, the interest seems to shift to healthy food rather than unhealthy food as the time spent at home increases. This is especially striking for Italy, where an increase in the mobility restrictions was consistently associated with an increased relative interest in healthy food. 

This analysis revealed very interesting cultural differences on food behavior. For instance, Spain and Italy are often considered to have closely related cultures. Yet in this study, we found that the relation between healthy food interest and mobility restriction is the opposite for these two countries. 

Furthermore, the interest in Spain for healthy food seems to beat the one for unhealthy food as the ratio is over 1, unlike in Italy. We notice that in Spain and Italy, the relative interest for the preferred type of food decreases during the most severe periods of lockdown. This suggests that, at least in these countries, these periods disturb people's food consumption habits instead of reinforcing their existing ones.

These results could be investigated in further studies, to find the factors that can influence differently food preferences in periods of great changes. We continue to research the cultural aspects of food interest during the pandemic with the next question.</p>



<h2 id="q2">World cuisines</h2>
		
	<p align="justify">In this section, we will investigate the interests shifts during COVID-19 in terms of cuisines from all around the world. When trying out new dishes, did individuals become more interested in their own history and traditions, or did they want to explore the cuisine of other cultures? To answer this question, we extracted the pageviews for the Wikipedia pages related to 24 different cuisines.</p>
		
	<h4>Data exploration</h4>
		
	<p align="justify">You can have a first overview of the data by looking at the plot below, which shows the evolution of the number of clicks on each of the cuisines considered between 2018 and 2022. The missing values for some cuisines are due to the fact that the corresponding pages were not available in the target language. You can change the Wikipedia language you are interested in using the dropdown menu.</p>
		
	<iframe src="./plots/PageviewsCultures1.html" height=550 width=1200></iframe>
		
	<p align="justify">Do you notice some re-occurring fluctuations or some interesting spikes? For instance, if you look at the Italian Wikipedia, German cuisine appears to gain popularity each winter, whereas Greek cuisine becomes more popular during the summer. In fact, traditional German cuisine is based on bread, potatoes and meat, especially pork, heavier foods that provide comfort and warmth during the cold months. On the other hand, the most famous Greek recipes include ingredients such as yogurt, cucumber and seafood, which are refreshing and more suitable for the summer. Thai cuisine has a recurrent spike in September, when Thai food festivals are held all around the world. The German and Dutch Wikipedia show seasonal fluctuations for many cuisines, while the English version, being representative of Wikipedia users from every corner of the world, not that much. It can still show some sudden interest shifts that characterized the whole globe, like the great increase in pageviews for Japanese cuisine in correspondence to the Tokyo 2020 Olympic games, or something that went viral for a brief period. We can even already notice some interesting differences comparing the period before COVID-19 to the pandemic period. For example, the interest of Italians in Austrian cuisine seems to drastically decrease with COVID onset.</p>
		
		<p align="justify">Explore the plot below to get an idea of the distribution of the weekly pageviews for every cuisine in each language. Zoom in and hover over the boxplots to see the minimum, maximum, median, first and third quartiles, and upper and lower fences. Can you see some patterns in the most popular cuisines across different languages?</p>
		
		<iframe src="./plots/DistributionPageviews.html" height=550 width=1200></iframe>
		
		<p align="justify">Italian food, which appears to be the most popular across the world considering the English Wikipedia, often appears among the most searched, together with the food from the users' own country. For instance German cuisine, followed by Italian cuisine, are the most visited in German. Japanese cuisine is among the top cuisines for many languages as well. In some cases the cuisine of the corresponding country is followed by similar ones, in terms of ingredients and geographical proximity. For example, the second most popular in Turkish is Greek cuisine, which inherits many dishes from Ottoman cuisine.</p>
		
		<h4>Preprocessing</h4>
		
		<p align="justify">For the Italian version of Wikipedia the means of the pageviews distributions vary largely (around 4 orders of magnitude), and we can notice similar characteristics for many other languages. For this reason, after outliers removal, we will standardize the data, such that the popularity index for each cuisine in each date is relative to the maximum popularity reached by that cuisine across the whole study period.</p>
		
		<p align="justify">The world map below shows the relative popularity of each cuisine in the English language, considered as representative of the world, after standardizing and removing the seasonal component. Use the cursor below the map to scroll across dates and see the evolution of users' interest from 2018 to 2022, and hover over each country to see its top 3 dishes and its popularity index for the corresponding date.</p>
		
		<iframe src="./plots/WorldMap1.html" height=550 width=1200></iframe>
		
		<p align="justify">As mentioned before, some cuisines show seasonal trends that are repeated every year. We want to capture the underlying information about interest shifts due to the pandemic, regardless of the season, so we decomposed the time series in seasonal component, trend and residuals, as shown in the plot below.</p>
				
		<iframe src="./plots/SeasonalDecomp.html" height=800 width=1200></iframe>
		
		<p align="justify"><br>Since we are interested in variations from regular fluctuations that could be related to COVID-19, we decided to filter out the seasonal component. We do this for all the cuisines that show some relevant periodic fluctuations, whereas for the few cuisines that seem more constant we skip this step in order to avoid losing information. The remaining components are the trend and the residuals. The residuals represent the deviation of the data with respect to the model composed of trend and seasonal component, so they are very fluctuating and sometimes present huge spikes. In this context, where we are looking for an underlying behavior that is on a longer timescale compared to weekly variations, considering only the residuals might lead us to overinterpret this information. The trend would be more suitable to analyze changes in habits that can take a few weeks to occur, but we might discard relevant information by smoothening the signal so much. For instance, the interest for Greek cuisine in 2020 actually dropped way more than the trends shows. Furthermore, we use the mobility data to analyze the correlation between mobility restrictions and interest in different kinds of food, and the restrictions during the pandemic sometimes had abrupt changes. For these reasons, for the following analysis we will consider the sum of trend and residuals, only filtering out the seasonal component.</p>
		
		<h4>What kinds of food did people try out during the pandemic?</h4>
		
		<p align="justify">To address our main question regarding cultural interests, we calculate for each Wikipedia language the ratio between the pageviews for the corresponding cuisine and the sum of the pageviews for all others. You can see these ratios in the plot in the following paragraph, together with the mobility data. We performed a t-test to see whether there were interest shifts, based on this ratio, between pre-COVID and COVID periods. The results are shown in the following table.</p>
		
	<table class="alt" style="width: 50%; margin: 0 auto; text-align:center">
		<thead>
			<tr>
				<th style="text-align:center">Language</th>
				<th style="text-align:center">t-statistics</th>
				<th style="text-align:center">p-value</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>Italian (it)</td>
				<td>0.738997</td>
				<td>0.769632</td>
			</tr>
			<tr>
				<td>German (de)</td>
				<td>3.683396</td>
				<td>0.999847</td>
			</tr>
			<tr>
				<td>Dutch (nl)</td>
				<td>-3.485403</td>
				<td>0.000321</td>
			</tr>
			<tr>
				<td>Serbian (sr)</td>
				<td>-0.854973</td>
				<td>0.196706</td>
			</tr>
			<tr>
				<td>Turkish (tr)</td>
				<td>-0.427367</td>
				<td>0.334828</td>
			</tr>
			<tr>
				<td>Catalan (ca)</td>
				<td>0.792671</td>
				<td>0.785632</td>
			</tr>
			<tr>
				<td>Finnish (fi)</td>
				<td>3.783060</td>
				<td>0.999900</td>
			</tr>
			<tr>
				<td>English (en)</td>
				<td>-5.270606</td>
				<td>2.003964e-07</td>
			</tr>
		</tbody>
	</table>
		
	<p align="justify"><br>Interestingly, a significant change was found in the Dutch Wikipedia and especially in the English Wikipedia, so there seems to be an interest shift of the whole world population. The t-statistics is negative, meaning that the mean of the pageviews ratio distribution before COVID-19 is lower than the mean of the pageviews ratio distribution during the pandemic. This shows that people tended to search more dishes related to their own cuisine and tradition, rather than more exotic food. For instance, in Italy many people started cooking typical food such as pizza and focaccia at home, especially in the first weeks of lockdown. This is probably a result of the combination of having more time available for cooking, having less chances to buy these products in shops or restaurants, and looking for something to unite the country during such difficult times.</p>
		
	<h4>Was the interest shift related to mobility restrictions?</h4>
		
	<p align="justify">Now that we have noticed a change for some countries, to address our research question we want to check whether different degrees of mobility restrictions have an effect on the interest in other cuisines. To do this, we use the mobility data starting from the first mobility restriction decided in the corresponding country. In particular, we take into account the mobility within residential areas, which will be higher when people are forced to stay at home. Therefore, higher values in these mobility data mean higher mobility restrictions. Explore the trends in pageviews and the associated mobility data in the graph below, selecting the language using the dropdown menu. You can change the timescale using the buttons at the top and the cursor at the bottom. Do you notice any possible effect related to how strictly people were forced to stay at home? The vertical lines represent the beginning of lockdown (or of the hardest mobility restrictions for the countries that didn't have lockdown), the end of the first period of restrictions, and the end of the second period of restrictions.</p>

	<iframe src="./plots/Ratio&Mobility.html" height=550 width=1200></iframe>
		
	<p align="justify">If you look at the German Wikipedia, there is a noticeable spike in the pageviews ratio just a few weeks after the beginning of lockdown, and another increase around the beginning of 2021, matching the second round of mobility restrictions. A similar trend can be observed for English, whereas other languages such as Turkish and Catalan don't seem to show any particular matching pattern. We calculated the Spearman correlation to check if there is a significant relationship between pageviews ratio and mobility data for any of the languages. The results are collected in the table below.</p>
		
	<table class="alt" style="width: 50%; margin: 0 auto; text-align:center">
		<thead>
			<tr>
				<th style="text-align:center">Language</th>
				<th style="text-align:center">Spearman's correlation</th>
				<th style="text-align:center">p-value</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>Italian (it)</td>
				<td>-0.015</td>
				<td>0.865</td>
			</tr>
			<tr>
				<td>German (de)</td>
				<td>0.712</td>
				<td>8.74e-23</td>
			</tr>
			<tr>
				<td>Dutch (nl)</td>
				<td>0.319</td>
				<td>0.000128</td>
			</tr>
			<tr>
				<td>Turkish (tr)</td>
				<td>-0.240</td>
				<td>0.00442</td>
			</tr>
			<tr>
				<td>Catalan (ca)</td>
				<td>-0.098</td>
				<td>0.252</td>
			</tr>
			<tr>
				<td>Finnish (fi)</td>
				<td>0.493</td>
				<td>6.97e-10</td>
			</tr>
			<tr>
				<td>English (en)</td>
				<td>0.373</td>
				<td>6.21e-06</td>
			</tr>
		</tbody>
	</table>
		
	<p align="justify"><br>The Spearman's correlation results confirm what we just observed for German, together with Dutch, Finnish, and English. The positive correlation coefficient means that the two variables increase together, so as the mobility restrictions are higher people in these countries tend to search more for their own dishes, as compared to foreign ones. On the other hand, Turkish shows a significant negative correlation coefficient, highlighting an opposite trend of mobility data against pageviews ratio.</p>
		
	<h4>Did lockdown make people more "nationalistic"?</h4>
		
	<p align="justify"><br>Since people's interest shift might respond to the mobility restrictions with a delay, we want to know what time lag yields the highest correlation between our ratio and the mobility data. We use a Granger causality test to determine whether the mobility time series precedes the pageviews variations with a time lag of a certain amount of weeks. According to Granger causality, if a series X "Granger-causes" a series Y, then past values of X should contain information that helps predict Y. A prerequisite for performing the Granger causality test is that the time series have to be stationary. For this purpose, we look at the p-value of the Augmented Dickey-Fuller test and differentiate the time series in the case of non-stationarity.</p>
		<p align="justify">Considering the long pandemic period and the different COVID-19 waves of various entities, we imagine a possible difference in people's responses in the long run. For this reason, we divide the pandemic period into three sub-time intervals:
	<ul>
  		<li>An initial period, also called the 'COVID-19 Shock Period', which corresponds to the onset of COVID-19, and extends up to the end of the first hardest mobility restrictions;</li>
  		<li>A second period, also called 'Second waves', that starts from the end of the first hardest mobility restrictions, includes the return of the covid and extends until the new return to normal in the autumn of 2021;</li>
  		<li>A third period that extends until November 1, 2022.</li>
	</ul>
	The results are presented in the table below.</p>
		
	<table class="alt" style="width: 50%; margin: 0 auto; text-align:center">
		<thead>
			<tr>
				<th style="text-align:center">Language</th>
				<th style="text-align:center">Time lag</th>
				<th style="text-align:center">p-value</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>Italian (it)</td>
				<td>Week 1</td>
				<td>0.373483</td>
			</tr>
			<tr>
				<td>German (de)</td>
				<td>Week 2</td>
				<td>0.002779</td>
			</tr>
			<tr>
				<td>Dutch (nl)</td>
				<td>Week 1</td>
				<td>0.865405</td>
			</tr>
			<tr>
				<td>Turkish (tr)</td>
				<td>Week 2</td>
				<td>0.191701</td>
			</tr>
			<tr>
				<td>Catalan (ca)</td>
				<td>Week 2</td>
				<td>0.037245</td>
			</tr>
			<tr>
				<td>Finnish (fi)</td>
				<td>Week 1</td>
				<td>0.053010</td>
			</tr>
			<tr>
				<td>English (en)</td>
				<td>Week 2</td>
				<td>0.000213</td>
			</tr>
		</tbody>
	</table>
		
	<p align="justify"><br>We have significant causal relationship for German, Catalan and English, for which people's interest follows mobility restrictions by two weeks. Overall, we can say an increased investigation of one's own country's traditions is observed after a period of around two weeks after strict mobility measures are in place. This result is surprising, as one might expect these kind of changes to occur on a longer time scale.</p>
		
	<p align="justify">You might now ask whether, when Wikipedia users weren't searching for their own country's cuisine, they showed more interest for similar cultures, rather than completely different ones. To get a first idea of how similar the cuisines we considered are, you can have a look at the following heat map, based on shared ingredients between pairs of cuisines.</p>
		
	<iframe src="./plots/Cuisine_similarity.jpeg" height=500 width=600></iframe>
		
	<p align="justify">It would be interesting to use this discrimination to further analyze interest shifts, as people might associate the tastes they are used to to comfort, and turn towards them in difficult times.
		
		<h4>Conclusion</h4>
	
	<p align="justify">In conclusion, our investigation into the impact of COVID-19 on cultural interests, specifically in terms of cuisine, revealed that there was a significant shift in interest towards traditional and local cuisines for some Wikipedia languages, such as Dutch and English. This shift was observed through the analysis of pageview ratios for different cuisines on Wikipedia, and was found to be correlated with the severity of mobility restrictions in some cases, as determined by Spearman correlation and Granger causality tests. Interestingly the results showed that these shifts happen on a small timescale of 1-2 weeks. Overall, our findings suggest that the COVID-19 pandemic has influenced people's cultural interests, with a tendency towards more traditional and local cuisines in some cases, potentially due to the combination of increased time at home and a desire for familiarity and comfort during difficult times.</p>

<h2 id="q3">Food delivery services</h2>

For this objective, we will consider the behavior of eight different countries, respectively: Italy, England, Germany, Holland, Serbia, Turkey, Spain, and Finland, and we will consider the trend of interest in food delivery using Google Trends. 

	<p align="justify">The COVID-19 pandemic has turned people's lives upside down, completely changing their habits and forcing them to stay home for long periods. With the ability to go outdoors and conduct social life activities halted, the restaurant industries have had to take drastic measures to stay afloat. In this context, home food delivery services have taken advantage of the opportunity, continuing to provide individuals with the pleasure of a good sushi or a still hot pizza that arrives at home. While platforms like Uber Eats, Glovo, Grubhub, etc. were mostly unknown until 2019, it is currently impossible to meet a person who has never ordered using a home food service yet.</p>
	<p align="justify">All over the world, the pandemic has changed the way we shop and eat. As the restaurant industry emerges from COVID-19, which dining habits will decline in popularity, and which will remain?<br>
Now that we are getting ready for the end of the pandemic, it is natural to wonder what life will be like in a post-Covid world. Was the rise of the food delivery sector in 2020 the beginning of a real change in consumer behavior?</p>
	<p align="justify">For this objective, we will consider the behavior of eight different countries, namely: Italy, England, Germany, Netherlands, Serbia, Turkey, Spain, and Finland, and we will consider the trend of interest in food delivery using Google Trends.</p>
		
		<h4>Food delivery data</h4>
		
		<p align="justify">Considering the impossibility of accessing performance data such as weekly revenue, orders placed, or app activity, we felt Google trends as a suitable proxy for a company's popularity. Indeed, an individual could search for food delivery companies on Google to order directly from their website or to download the application. We retrieved the weekly Trends values for each company and each country, dating from the beginning of 2018 to the autumn of 2022. Each Google trend query gives an interest from 0 to 100, where 100 is related to the week the company searched the most in the given period and location. Thus, we cannot compare the absolute interest (or the number of searches) across countries but only look at the relative interest in the same region.</p>
		<p align="justify">In particular, the food delivery companies we considered in this study are: Door Dash, Uber Eats, Grubhub, Postmates, Seamless, Just Eat, Deliveroo, Glovo, Zomato, Yemeksepeti, Trendyol Yemek, Lieferando, Hello Fresh, Gorillas. This list has been constructed after carefully researching the most popular food delivery companies in each country under study. Each company may be more or less known or spread across different countries. As a result, Google's Food Delivery Trends gave null values for some countries. However, our goal is to determine each nation's general interest in food delivery rather than specific interest in a particular food delivery company. Therefore, we only considered Google searches that returned non-zero values and evaluated the weekly sum. Thus, each country might have a different maximum value, depending on how many queries have no NaN values. Nevertheless, this can be a good proxy to check how many companies are spread in each country.</p>
		
		<h4>Tracing the influence of COVID-19</h4>
		
		<p align="justify">To track the influence of the pandemic on food delivery preferences, we opted to use Google's Community Mobility Reports, which Google made publicly available during the pandemic. The data show the variation in visitors to the categorized places or time spent in these places compared to the reference days. The reference day is the average value for the five weeks from January 3 to February 6, 2020.</p>
		<p align="justify">For each geographical area-category pair, the reference does not correspond to a single value but to seven individual values. Therefore, we grouped the data by date and considered their average to obtain time series for each geographic area. For this question, we will consider the category 'retail_and_recreation_percent_change_from_baseline', which contains data regarding travel trends for places such as restaurants, bars, shopping centers, theme parks, museums, libraries, and cinemas.</p>
		
		<h4>Data exploration</h4>
		
		<p align="justify">You can have a first overview of the data by looking at the plots below, which shows the evolution of the food delivery interest for each country between 2018 and 2022 against the Google mobility data.</p>
		
		<iframe src="./plots/Food_delivery_against_Mobility_data.html" height=550 width=1200></iframe>
		
		<p align="justify">Looking at the graphs for the different countries, a clear difference in general interest in food delivery between the period before and after the first restrictions on mobility is immediately visible. Furthermore, the negative correlation between the two time series in the pandemic period is very evident. It is also interesting to note that in Serbia, Turkey, and Spain, with the easing of restrictions in the last period of the pandemic, even greater mobility is being recorded compared to the baseline considered by Google. In any case, while for Spain and Turkey, this increase in mobility is followed by a decrease in interest in food delivery, for Serbia, this maintains a positive trend.</p>
		<p align="justify">To give a general overview, all countries show a steep increase in food delivery searches immediately after the first restrictive measures. From that moment on, the interest in food delivery looks closely related to mobility. However, Serbia is the only country where the food delivery trend remains growing. Again in Serbia, we don't find the steep increase mentioned, but a significant peak around October 2022, when the nation experienced a considerable wave of COVID-19 infections. Turkey has a unique behavior, as it is the only country where restrictions seem to be positively correlated with food delivery.</p>
		<p align="justify">But let's analyze in more detail what we have visualized in the plots. Having initially explored the data, we will now investigate the presence of a structural change in the levels of interest for food delivery before and after the starting of the mobility restrictions. Later, we will explore whether causality exists between mobility and the food delivery interest. To conclude, to have a proactive and forward-looking perspective, we thought of building a forecasting model that allows expecting the future and could be helpful for investors, journalists or researchers.</p>
		<p align="justify">For this part, the only preprocessing step consists in outliers removal, as there are no noticeable seasonal trends to remove.</p>
		
		<h4>Has interest in food delivery increased during the pandemic?</h4>
		
		<p align="justify">We used a t-test to test the null hypothesis that pre- and post-pandemic interests in food delivery have the same average value. For all countries, the resulting p-value was less than 0.05, therefore rejecting the null hypothesis.</p>
			
		<table class="alt" style="width: 50%; margin: 0 auto; text-align:center"> 
			<thead> 
				<tr> 
					<th style="text-align:center">Country</th> 
					<th style="text-align:center">t-statistics</th> 
					<th style="text-align:center">p-value</th> 
				</tr> 
			</thead> 
			<tbody> 
				<tr> 
					<td>Italy (it)</td> 
					<td>-13.1903</td> 
					<td>8.2663e-31</td> 
				</tr> 
				<tr> 
					<td> Great Britain (en)</td> 
					<td>-25.8633</td>
					<td>6.9344 e-73</td>
				</tr> 
				<tr>
					<td>Germany (de)</td> 
					<td>-36.2818</td> 
					<td>6.028e-97</td> 
				</tr> 
				<tr> 
					<td>Netherlands (nl)</td> 
					<td>-35.5214</td> 
					<td>1.3719e-85</td> 
				</tr> 
				<tr> 
					<td>Serbia (sr)</td> 
					<td>-16.6632</td> 
					<td>2.769e-36</td> 
				</tr> 
				<tr> 
					<td>Turkey (tr)</td>
					<td>-10.2825</td> 
					<td>8.7905e-20</td> 
				</tr>
				<tr> 
					<td>Spain (ca)</td> 
					<td>-9.4295</td> 
					<td>7.4483e-18</td> 
				</tr> 
				<tr> 
					<td>Finland (fi)</td> 
					<td>-9.6796</td> 
					<td>4.0300e-19</td> 
				</tr> 
			</tbody> 
		</table> 
		
		<h4>Did people order more food when they couldn't go to restaurants?</h4>
		
		<p align="justify">Now, we want to verify the hypothesis that the lockdown and all the mobility restrictions due to the pandemic might have affected people's interest in food delivery services. Therefore, we run a Spearman test between the mobility data related to retail and recreation and the Google searches for food delivery services.</p>
		
		<table class="alt" style="width: 50%; margin: 0 auto; text-align:center">
                	<thead> 
				<tr> 
					<th style="text-align:center">Country</th> 
					<th style="text-align:center">Spearman's correlation</th> 
					<th style="text-align:center">p-value</th> 
				</tr> 
			</thead> 
			<tbody> 
				<tr> 
					<td>Italy (it)</td> 
					<td> -0.776</td> 
					<td> 1.82e-29</td> 
				</tr> 
				<tr>
					<td> Great Britain (en)</td> 
					<td>-0.605</td>
					<td>2.31e-15</td> 
				</tr> 
				<tr> 
					<td>Germany (de)</td> 
					<td>-0.352</td> 
					<td>1.95e-05</td> 
				</tr> 
				<tr> 
					<td>Netherlands (nl)</td> 
					<td>-0.283</td> 
					<td>6.92e-04</td> 
				</tr> 
				<tr> 
					<td>Serbia (sr)</td> 
					<td>0.758</td>
					<td>3.54e-27</td> 
				</tr> 
				<tr> 
					<td>Turkey (tr)</td> 
					<td>0.758</td>
					<td>2.41e-27</td> 
				</tr> 
				<tr> 
					<td>Spain (ca)</td> 
					<td>-0.799</td> 
					<td>2.86e-32</td>
				</tr> 
				<tr> 
					<td>Finland (fi)</td> 
					<td>-0.043</td> 
					<td>0.617</td> 
				</tr> 
			</tbody> 
		</table>
		
		<p align="justify"><br>The correlation with mobility data appears significant for all countries except for Finland. Furthermore, as previously visualized through the plots, Serbia and Turkey are the only countries with a positive correlation coefficient. This singular behavior is counterintuitive and deserves further exploration.</p>
		<p align="justify">One factor to consider is Turkey's economy relies on its migrant workforce while benefiting greatly from remittances and the strong ties between expatriate Turks and families back home. The Coronavirus measures at home and abroad have significantly upset this balance, thus strongly impacting the Turkish economy. In general, workers' incomes have decreased, working hours have changed, and their financial difficulties have worsened, significantly affecting their livelihoods. This could be one of the reasons why food delivery companies have recorded a sharp decrease in interest during the initial "Covid shock period".</p>
		<p align="justify">As far as Serbia is concerned, it should be considered that in the pre-pandemic period, searches were close to zero, underlining the scarce diffusion of food delivery services in the country. For this reason, it may be that the restrictions have acted as a vehicle for its spread. Still, unlike in other countries, it has taken a while for people to become aware of this possibility's existence. This could explain the significant peak in the third covid wave and the growing trend.</p>
		
		<h4>Can we say the mobility restrictions caused the rise of food delivery services?</h4>
		
		<p align="justify">Considering the significant difference in people's interest in food delivery and the observed correlation with mobility restrictions, it seems appropriate to verify the latter's causality in influencing people's preferences. For this purpose, we will run a test of Granger's causality. Below we show the matrix summarizing the results of the Granger causality test, therefore showing the p-values for each test and the corresponding week lag.</p>
		
		<iframe src="./plots/p-values Granger causality.html" height=550 width=1200></iframe>
	<p> </p>
		<iframe src="./plots/week lag Granger causality.html" height=550 width=1200></iframe>
	
		<p align="justify"><br>Considering the whole pandemic period, the restrictions on Italy, Great Britain, Germany, and Spain significantly influence the interest in food delivery at a 1-week lag. Interestingly, Germany maintains this condition in the first and second periods of the pandemic but not in the last one. Spain and Great Britain also maintain the significant influence of the restrictions, although not during the 'Second waves' period. On the other hand, Italy's mobility restrictions have considerably impacted food delivery only in the last period. Good results are also obtained for the Netherlands, demonstrating significant causality in the last two pandemic periods. Finland shows a causality relation only in the second period, while Serbia and Turkey still behave differently from the other countries, showing insignificant results in each period under study. Interestingly but not surprisingly, most of the significant results were obtained after a week of lag between mobility and food delivery interest, demonstrating the short influence range between restrictions and people's responses to eating behaviors.</p> 
	
		<h4>Is it possible to forecast the interest for food delivery services based on mobility data?</h4>
	
		<p align="justify">For the food delivery interest forecasting, we use the vector autoregression (VAR) model, an extension of the ARMA model utilized for univariate time series forecasting. In the VAR model, each time series is modeled as a linear combination of past values of itself and the past values of other time series in the system, in our case, the mobility date. To implement the VAR model, we must check for stationarity and Granger causation, which we already found for Italy, Great Britain, Spain, and Germany. Considering that Netherlands' Granger causality was not significant only for the 'Shock period', we will take this country into account for the forecasting. Then, we should look at the cointegration test to determine the presence of a statistically significant connection between multiple time series, which is the basic premise on which VAR models is based on.</p>
		<p align="justify">After checking for the Granger causality and significance of the cointegration test, we will proceed by fitting the model and reserving the last four (one month) observation data for the test set, to verify the reliability of our forecasting. As a final step, we have to check for serial correlation to ensure that the model can sufficiently explain the variances and patterns in the time series. To do so, we measure Durbin Watson's Statistic, which can vary between 0 (positive serial correlation) and 4 (negative serial correlation). The closer it is to the value 2, the better it is, meaning there is no significant serial correlation. Below are represented the results of the serial correlation test.</p>
	
	<table class="alt" style="width: 50%; margin: 0 auto; text-align:center"> 
		<thead> 
			<tr> 
				<th style="text-align:center">Country</th> 
				<th style="text-align:center">Delivery</th> 
				<th style="text-align:center">Mobility</th> 
			</tr> 
		</thead> 
		<tbody> 
			<tr>
				<td>Italy (it)</td> 
				<td> 2.0</td> 
				<td> 12.02</td> 
			</tr> 
			<tr> 
				<td> Great Britain (en)</td> 
				<td>1.98</td> 
				<td>1.97</td> 
			</tr> 
			<tr> 
				<td>Spain (ca)</td>
				<td>1.97</td> 
				<td>1.99</td> 
			</tr> 
			<tr>
				<td>Netherlands (nl)</td> 
				<td>1.91</td> 
				<td>2.0</td> 
			</tr> 
			<tr> 
				<td>Germany (de)</td> 
				<td>1.92</td> 
				<td>2.02</td> 
			</tr> 
		</tbody> 
	</table> 
	
	<p align="justify"><br>Considering the good results of the serial correlation, we can proceed with the forecast. Below, you can find the forecasting results compared to the four observations left as a test set.</p>
	
	<iframe src="./plots/Food delivery Forecasting.html" height=550 width=1200></iframe>
	
	<p align="justify">To quantify the performances of our model, we computed the mean percentage error and the Pearson product-moment correlation coefficients for each forecasting, which measure the strength and direction of association between two variables. The results are shown below. Generally, the general trend of interest is correctly predicted.</p>
	
	<table class="alt" style="width: 50%; margin: 0 auto; text-align:center">
		<thead> 
			<tr> 
				<th style="text-align:center">Country</th>
				<th style="text-align:center">MPE</th> 
				<th style="text-align:center">CORR</th> 
			</tr> 
		</thead> 
		<tbody> 
			<tr> 
				<td>Italy (it)</td>
				<td> -0.0063</td> 
				<td> 0.986</td> 
			</tr> 
			<tr> 
				<td> Great Britain (en)</td>
				<td>-0.3003</td> 
				<td>0.5406</td>
			</tr> 
			<tr> 
				<td>Spain (ca)</td> 
				<td>-0.0481</td> 
				<td>0.9201</td> 
			</tr> 
			<tr> 
				<td>Netherlands (nl)</td> 
				<td>-0.4248</td> 
				<td>-0.9385</td> 
			</tr> 
			<tr> 
				<td>Germany (de)</td>
				<td>-0.388</td> 
				<td>0.8046</td> 
			</tr> 
		</tbody> 
	</table> 
 
	<h4>Conclusion</h4>
	
	<p align="justify"><br>As far as we have noticed, except for Serbia, it is generally possible to point out a correlation and a 'causality' of the mobility data on food delivery. Indeed, in the third period, with a loosening of restrictions on mobility, there was a general reduction in interest in food delivery. In any case, it should be emphasized that even if there is a slightly negative trend, the average interest rate is still far higher than the pre-covid period. Therefore, we can conclude that mobility data is generally a good key to predicting interest in food delivery. In any case, we must admit the presence of different drivers with respect to health regulations and closures, which could continue to favor the affirmation of food delivery compared to the previous period. These can be the convenience of ordering from home and waiting for food while sitting on the sofa, or the presence of continuous and convenient offers in food delivery services that encourage people, once discovered, to make purchases on that application.</p>
		
		
		
