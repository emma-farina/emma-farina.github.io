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

<p align="justify">During the pandemic, there were significant changes in people's daily routines and habits, including the way they shopped for and prepared food. For example, some people may have started cooking at home more often due to stay-at-home orders or concerns about going out to eat, which could have led to an increase in Wikipedia pageviews for food-related topics as people sought information on cooking and recipe ideas. On the other hand, some people may have been less interested in food-related topics due to stress or other distractions related to the pandemic, which could have led to a decrease in Wikipedia pageviews.

It is also worth noting that Wikipedia pageviews can be influenced by a variety of factors beyond the pandemic, such as the availability of alternative sources of information, changes in search trends, and the overall popularity of a topic.

Bla bla about what we want to know and why we think Wikipedia and Google Trends are representative of people's interests.</p>


<h2>Datasets</h2>
<dl>
	<dt>Wikipedia</dt>
	<dd>
		<p align="justify">Description of the pages we are selecting (categories) and languages. Description of how we are querying them?</p>
	</dd>
	<dt>Google Trends</dt>
	<dd>
		<p align="justify">Description of the pages we are selecting and how it works, which information we get.</p>
	</dd>
	<dt>Interventions data</dt>
	<dd>
		<p align="justify">Description of what information they provide and for which countries.</p>
	</dd>
	<dt>Mobility data</dt>
	<dd>
		<p align="justify">Description of data structure.</p>
	</dd>
</dl>

<h2 id="q1">Healthy food</h2>

	<p align="justify">Pie chart that shows which pages we are considering for the two categories.<br>
Table showing for each language the food that displays the most impressive changes from pre covid to covid (to post?) + show interventions<br>
Text analysing in detail the most interesting results.<br>
Geographic interactive map or just geographic map with colors: calculate ratio healthy/ unhealthy for different stages (pre covid, lockdown, post covid, etc), t-test with interventions and cross-correlation with mobility data.<br>
Barplots (one bar per language) with healthy and unhealthy bar on top of each other (one pre covid, one lockdown, one post covid).<br>
	Text comparing results for countries with and without lockdown.</p>

<h2 id="q2">Cultural interests</h2>
		
	<p align="justify">In this section, we will investigate the interests shifts during COVID-19 in terms of cuisines from all around the world. When trying out new dishes, did individuals become more interested in their own history and traditions, or did they want to explore the cuisine of other cultures? To answer this question, we extracted the pageviews for the Wikipedia pages related to 24 different cuisines.</p>
		
	<h4>Data exploration</h4>
		
	<p align="justify">You can have a first overview of the data by looking at the plot below, which shows the evolution of the number of clicks on each of the cuisines considered between 2018 and 2022. The missing values for some cuisines are due to the fact that the corresponding pages were not available in the target language. You can change the Wikipedia language you are interested in using the dropdown menu.</p>
		
	<iframe src="./plots/PageviewsCultures1.html" height=550 width=1200></iframe>
		
	<p align="justify">Do you notice some re-occurring fluctuations or some interesting spikes? For instance, if you look at the Italian Wikipedia, German cuisine appears to gain popularity each winter, whereas Greek cuisine becomes more popular during the summer. In fact, traditional German cuisine is based on bread, potatoes and meat, especially pork, heavier foods that provide comfort and warmth during the cold months. On the other hand, the most famous Greek recipes include ingredients such as yogurt, cucumber and seafood, which are refreshing and more suitable for the summer. Thai cuisine has a recurrent spike in September, when Thai food festivals are held all around the world. The German and Dutch Wikipedia show seasonal fluctuations for many cuisines, while the English version, being representative of Wikipedia users from every corner of the world, not that much. It can still show some sudden interest shifts that characterized the whole globe, like the great increase in pageviews for Japanese cuisine in correspondence to the Tokyo 2020 Olympic games, or something that went viral for a brief period.</p>
		
		<p align="justify">Explore the plot below to get an idea of the distribution of the weekly pageviews for every cuisine in each language. Zoom in and hover over the boxplots to see the minimum, maximum, median, first and third quartiles, and upper and lower fences. Can you see some patterns in the most popular cuisines across different languages?</p>
		
		<iframe src="./plots/DistributionPageviews.html" height=550 width=1200></iframe>
		
		<p align="justify">Italian food, which appears to be the most popular across the world considering the English Wikipedia, often appears among the most searched, together with the food from the users' own country. For instance German cuisine, followed by Italian cuisine, are the most visited in German. Japanese cuisine is among the top cuisines for many languages as well. In some cases the cuisine of the corresponding country is followed by similar ones, in terms of ingredients and geographical proximity. For example, the second most popular in Turkish is Greek cuisine, which inherits many dishes from Ottoman cuisine.</p>
		
		<h4>Preprocessing</h4>
		
		<p align="justify">For the Italian version of Wikipedia the means of the pageviews distributions vary largely (around 4 orders of magnitude), and we can notice similar characteristics for many other languages. For this reason, we will standardize the data before continuing the analysis, such that the popularity index for each cuisine in each date is relative to the maximum popularity reached by that cuisine across the whole study period.</p>
		
		<p align="justify">The world map below shows the relative popularity of each cuisine in the English language, considered as representative of the world, after standardizing and removing the seasonal component. Use the cursor below the map to scroll across dates and see the evolution of users' interest from 2018 to 2022, and hover over each country to see its top 3 dishes and its popularity index for the corresponding date.</p>
		
		<iframe src="./plots/WorldMap1.html" height=550 width=1200></iframe>
		
		<p align="justify">As mentioned before, some cuisines show seasonal trends that are repeated every year. We want to capture the underlying information about interest shifts due to the pandemic, regardless of the season, so we decomposed the time series in seasonal component, trend and residuals, as shown in the plot below.</p>
				
		<iframe src="./plots/SeasonalDecomp.html" height=550 width=1200></iframe>
		
		<p align="justify"><br>Since we are interested in variations from regular fluctuations that could be related to COVID-19, we decided to filter out the seasonal component. We do this for all the cuisines that show some relevant periodic fluctuations, whereas for the few cuisines that seem more constant we skip this step in order to avoid losing information. The remaining components are the trend and the residuals. The residuals represent the deviation of the data with respect to the model composed of trend and seasonal component, so they are very fluctuating and sometimes present huge spikes. In this context, where we are looking for an underlying behavior that is on a longer timescale compared to weekly variations, considering only the residuals might lead us to overinterpret this information. The trend would be more suitable to analyze changes in habits that can take a few weeks to occur, but we might discard relevant information by smoothening the signal so much. For instance, the interest for Greek cuisine in 2020 actually dropped way more than the trends shows. Furthermore, we use the mobility data to analyze the correlation between mobility restrictions and interest in different kinds of food, and the restrictions during the pandemic sometimes had abrupt changes. For these reasons, for the following analysis we will consider the sum of trend and residuals, only filtering out the seasonal component.</p>
		
		<h4>What kinds of food did people try out during the pandemic?</h4>
		
		<p align="justify">To address our main question regarding cultural interests, we calculate for each Wikipedia language the ratio between the pageviews for the corresponding cuisine and the sum of the pageviews for all others. You can see these ratios here (insert anchor link), together with the mobility data. We performed a t-test to see whether there were interest shifts, based on this ratio, between pre-COVID and COVID periods. The results are shown in the following table.</p>
		
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
		
	<p align="justify">Now that we have noticed a change for some countries, to address our research question we want to check whether different degrees of mobility restrictions have an effect on the interest in other cuisines. To do this, we use the mobility data starting from the first mobility restriction decided in the corresponding country. In particular, we take into account the mobility within residential areas, which will be higher when people are forced to stay at home. Explore the trends in pageviews and the associated mobility data in the graph below, selecting the language using the dropdown menu. You can change the timescale using the buttons at the top and the cursor at the bottom. Do you notice any possible effect related to how strictly people were forced to stay at home? The vertical lines represent the beginning of lockdown (or of the hardest mobility restrictions for the countries that didn't have lockdown), the end of the first period of restrictions, and the end of the second period of restrictions.</p>

	<iframe src="./plots/Ratio&Mobility.html" height=550 width=1200></iframe>
		
	<p align="justify">If you look at the German Wikipedia, there is a noticeable spike in the pageviews ratio just a few weeks after the beginning of lockdown, and another increase around the beginning of 2021, matching the second round of mobility restrictions. A similar trend can be observed for English, whereas other languages such as Turkish and Catalan don't seem to show any particular matching pattern. We calculated the Spearman correlation to check if there is a significant relationship between pageviews ratio and mobility data for any of the languages. The results are collected in the table below, confirming what we just observed for German and showing a barely significant correlation for Finnish, too.</p>
		
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
				<td>0.006</td>
				<td>0.948</td>
			</tr>
			<tr>
				<td>German (de)</td>
				<td>0.569</td>
				<td>2.69e-13</td>
			</tr>
			<tr>
				<td>Dutch (nl)</td>
				<td>-0.017</td>
				<td>0.838</td>
			</tr>
			<tr>
				<td>Turkish (tr)</td>
				<td>-0.051</td>
				<td>0.555</td>
			</tr>
			<tr>
				<td>Catalan (ca)</td>
				<td>0.003</td>
				<td>0.969</td>
			</tr>
			<tr>
				<td>Finnish (fi)</td>
				<td>0.169</td>
				<td>0.047</td>
			</tr>
			<tr>
				<td>English (en)</td>
				<td>0.058</td>
				<td>0.497</td>
			</tr>
		</tbody>
	</table>
		
	<p align="justify"><br>Since people's interest shift towards other cultures might respond to the mobility restrictions with a delay, we want to know what time lag yields the highest correlation between our ratio and the mobility data. We use a Granger causality test to determine whether the mobility time series precedes the pageviews variations with a time lag of a certain amount of weeks. We therefore assume that there are no latent confounding effects and look for a linear causal relationship between the two time series. The results are presented in the table below.</p>
		
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
				<td>Serbian (sr)</td>
				<td>Week 1</td>
				<td>0.000493</td>
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
		
	<p align="justify"><br>We have significant causal relationship for German, Catalan and English, for which people's interest follows mobility restrictions by two weeks, and for Serbian, for which the time lag is only one week. Overall, we can say an increased curiosity towards foreign cuisines is observed after a period of around two weeks after strict mobility measures are in place. As compared to the results for the other research questions, ...</p>
	

<h2 id="q3">Food delivery services</h2>

	<p align="justify">The COVID-19 pandemic has turned people's lives upside down, completely changing their habits and forcing them to stay home for long periods. With the ability to go outdoors and conduct social life activities halted, the restaurant industries have had to take drastic measures to stay afloat.
In this context, home food delivery services have taken advantage of the opportunity, continuing to provide individuals with the pleasure of a good sushi or a still hot pizza that arrives at home. While platforms like Uber Eats, Glovo, Grubhub etc. were mostly unknown until 2019, it is currently impossible to meet a person who has never ordered using a home food service yet.</p>
	<p align="justify">All over the world, the pandemic has changed the way we shop and eat. As the restaurant industry emerges from COVID-19, which dining habits will decline in popularity, and which will remain?<br>
Now that we are getting ready for the end of the pandemic, it is natural to wonder what life will be like in a post-Covid world. Was the rise of the food delivery sector in 2020 the beginning of a real change in consumer behavior?</p>
	<p align="justify">For this objective, we will consider the behavior of eight different countries, namely: Italy, England, Germany, Netherlands, Serbia, Turkey, Spain, and Finland, and we will consider the trend of interest in food delivery using Google Trends.</p>

<h2 id="conclusion">Conclusion</h2>

<p align="justify">Conclusion on how did Covid 19 pandemic impact food preferences: more or less healthy, more or less exploring, more or less food ordering.</p>
		
<h2 id="conclusion">Outlook</h2>

<p align="justify">Our ideas for future work.</p>
		
		
		
