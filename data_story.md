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
		
	<p align="justify">You can have a first overview of the data by looking at the plot below, which shows the evolution of the number of clicks on each of the cuisines considered between 2018 and 2022. You can change the Wikipedia language you are interested in using the dropdown menu.</p>
		
	<iframe src="./plots/PageviewsCultures1.html" height=550 width=1200></iframe>
		
	<p align="justify">Do you notice some re-occurring fluctuations or some interesting spikes? For instance, if you look at the Italian Wikipedia, German cuisine appears to gain popularity each winter, whereas Greek cuisine becomes more popular during the summer. In fact, traditional German cuisine is based on bread, potatoes and meat, especially pork, heavier foods that provide comfort and warmth during the cold months. On the other hand, the most famous Greek recipes include ingredients such as yogurt, cucumber and seafood, which are refreshing and more suitable for the summer. Thai cuisine has a recurrent spike in September, when Thai food festivals are held all around the world. The German and Dutch Wikipedia show seasonal fluctuations for many cuisines, while the English version, being representative of Wikipedia users from every corner of the world, not that much. It can still show some sudden interest shifts that characterized the whole globe, like the great increase in pageviews for Japanese cuisine in correspondence to the Tokyo 2020 Olympic games, or something that went viral for a brief period.</p>
		
		<p align="justify">Explore the plot below to get an idea of the distribution of the weekly pageviews for every cuisine in each language. The missing values for some cuisines are due to the fact that the corresponding pages were not available in the target language. Zoom in and hover over the boxplots to see the minimum, maximum, median, first and third quartiles, and upper and lower fences. Can you see some patterns in the most popular cuisines across different languages?</p>
		
		<iframe src="./plots/DistributionPageviewsCulturesLog.html" height=550 width=1200></iframe>
		
		<p align="justify">Italian food, which appears to be the most popular across the world considering the English Wikipedia, often appears among the most searched, together with the food from the users' own country. For instance German cuisine, followed by Italian cuisine, are the most visited in German. Japanese cuisine is among the top cuisines for many languages as well. In some cases the cuisine of the corresponding country is followed by similar ones, in terms of ingredients and geographical proximity. For example, the second most popular in Turkish is Greek cuisine, which inherits many dishes from Ottoman cuisine.</p>
		
		<h4>Preprocessing</h4>
		
		<p align="justify">For the Italian version of Wikipedia the means of the pageviews distributions vary largely (around 4 orders of magnitude), and we can notice similar characteristics for many other languages. For this reason, we will standardize the data before continuing the analysis, such that the popularity index for each cuisine in each date is relative to the maximum popularity reached by that cuisine across the whole study period.</p>
		
		<p align="justify">The world map below shows the relative popularity of each cuisine in the English language, considered as representative of the world, after standardizing and removing the seasonal component. Use the cursor below the map to scroll across dates and see the evolution of users' interest from 2018 to 2022, and hover over each country to see its top 3 dishes and its popularity index for the corresponding date.</p>
		
		<iframe src="./plots/WorldMap1.html" height=550 width=1200></iframe>
		
		<p align="justify">As we mentioned before, some cuisines show seasonal trends that are repeated every year. We want to capture the underlying information about interest shifts due to the pandemic, regardless of the season, so we decomposed the time series in seasonal component, trend and residuals, as shown in the plot below. PROVA 3</p>
		
<style>
	.center{
	display: block;
	margin: 0 auto;
	width: 50%;
}
	</style}
				
		<p style=center><iframe src="./plots/seasonal_trends.jpeg"></iframe></p>
		
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


<h2 id="q3">Food delivery services</h2>

	<p align="justify">Replicate analysis from publication.</p>

<h2 id="conclusion">Conclusion</h2>

<p align="justify">Conclusion on how did Covid 19 pandemic impact food preferences: more or less healthy, more or less exploring, more or less food ordering.</p>
		
		
