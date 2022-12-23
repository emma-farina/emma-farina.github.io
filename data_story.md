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
<p align="justify">We will extract Wikipedia categories of foods we are interested in, namely healthy and unhealthy food and typical dishes from different cultures, and analyse their changes in popularity throughout the last 5 years and particularly comparing the period before and during the pandemic. For analysing the rise of food delivery services, instead, we deemed Google Trends a more suitable data source [<a href="https://towardsdatascience.com/the-impact-of-covid-19-on-food-delivery-services-in-the-u-s-47eae04655c8">6</a>], as customers directly search the names of these companies on Google when they want to order something.</p>


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
		
	<iframe src="./plots/healthy_pie.html" height=550 width=1200></iframe>
		
	<iframe src="./plots/unhealthy_pie.html" height=550 width=1200></iframe>

<h2 id="q2">Cultural interests</h2>
		
	<p align="justify">In this section, we will investigate the interests shifts during COVID-19 in terms of cuisines from all around the world. When trying out new dishes, did individuals become more interested in their own history and traditions, or did they want to explore the cuisine of other cultures? To answer this question, we extracted the pageviews for the Wikipedia pages related to 24 different cuisines.</p>
		
	<h4>Data exploration</h4>
		
	<p align="justify">You can have a first overview of the data by looking at the plot below, which shows the evolution of the number of clicks on each of the cuisines considered between 2018 and 2022. The missing values for some cuisines are due to the fact that the corresponding pages were not available in the target language. You can change the Wikipedia language you are interested in using the dropdown menu.</p>
		
	<iframe src="./plots/PageviewsCultures1.html" height=550 width=1200></iframe>
		
	<p align="justify">Do you notice some re-occurring fluctuations or some interesting spikes? For instance, if you look at the Italian Wikipedia, German cuisine appears to gain popularity each winter, whereas Greek cuisine becomes more popular during the summer. In fact, traditional German cuisine is based on bread, potatoes and meat, especially pork, heavier foods that provide comfort and warmth during the cold months. On the other hand, the most famous Greek recipes include ingredients such as yogurt, cucumber and seafood, which are refreshing and more suitable for the summer. Thai cuisine has a recurrent spike in September, when Thai food festivals are held all around the world. The German and Dutch Wikipedia show seasonal fluctuations for many cuisines, while the English version, being representative of Wikipedia users from every corner of the world, not that much. It can still show some sudden interest shifts that characterized the whole globe, like the great increase in pageviews for Japanese cuisine in correspondence to the Tokyo 2020 Olympic games, or something that went viral for a brief period. We can even already notice some interesting differences comparing the period before COVID-19 to the pandemic period. For example, the interest of Italians in Austrian cuisine seems to drastically decrease with COVID onset.</p>
		
		<p align="justify">Explore the plot below to get an idea of the distribution of the weekly pageviews for every cuisine in each language. Zoom in and hover over the boxplots to see the minimum, maximum, median, first and third quartiles, and upper and lower fences. Can you see some patterns in the most popular cuisines across different languages?</p>
		
		<iframe src="./plots/DistributionPageviews.html" height=550 width=1200></iframe>
		
		<p align="justify">Italian food, which appears to be the most popular across the world considering the English Wikipedia, often appears among the most searched, together with the food from the users' own country. For instance German cuisine, followed by Italian cuisine, are the most visited in German. Japanese cuisine is among the top cuisines for many languages as well. In some cases the cuisine of the corresponding country is followed by similar ones, in terms of ingredients and geographical proximity. For example, the second most popular in Turkish is Greek cuisine, which inherits many dishes from Ottoman cuisine.</p>
		
		<h4>Preprocessing</h4>
		
		<p align="justify">For the Italian version of Wikipedia the means of the pageviews distributions vary largely (around 4 orders of magnitude), and we can notice similar characteristics for many other languages. For this reason, we will standardize the data before continuing the analysis, such that the popularity index for each cuisine in each date is relative to the maximum popularity reached by that cuisine across the whole study period.</p>
		
		<p align="justify">The world map below shows the relative popularity of each cuisine in the English language, considered as representative of the world, after standardizing and removing the seasonal component. Use the cursor below the map to scroll across dates and see the evolution of users' interest from 2018 to 2022, and hover over each country to see its top 3 dishes and its popularity index for the corresponding date.</p>
		
		<iframe src="./plots/WorldMap1.html" height=550 width=1200></iframe>
		
		<p align="justify">As mentioned before, some cuisines show seasonal trends that are repeated every year. We want to capture the underlying information about interest shifts due to the pandemic, regardless of the season, so we decomposed the time series in seasonal component, trend and residuals, as shown in the plot below.</p>
				
		<iframe src="./plots/SeasonalDecomp.html" height=800 width=1200></iframe>
		
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
				<td>0.103</td>
				<td>0.226</td>
			</tr>
			<tr>
				<td>German (de)</td>
				<td>-0.619</td>
				<td>3.65e-16</td>
			</tr>
			<tr>
				<td>Dutch (nl)</td>
				<td>-0.035</td>
				<td>0.682</td>
			</tr>
			<tr>
				<td>Serbian (sr)</td>
				<td>-0.337</td>
				<td>4.91e-05</td>
			</tr>
			<tr>
				<td>Turkish (tr)</td>
				<td>0.399</td>
				<td>1.02e-06</td>
			</tr>
			<tr>
				<td>Catalan (ca)</td>
				<td>-0.044</td>
				<td>0.606</td>
			</tr>
			<tr>
				<td>Finnish (fi)</td>
				<td>-0.283</td>
				<td>0.000704</td>
			</tr>
			<tr>
				<td>English (en)</td>
				<td>-0.052</td>
				<td>0.541</td>
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
		
		<p align="justify">Considering the significant difference in people's interest in food delivery and the observed correlation with mobility restrictions, it seems appropriate to verify the latter's causality in influencing people's preferences. For this purpose, we will run a test of Granger's causality. According to Granger causality, if a series X "Granger-causes" a series Y, then past values of X should contain information that helps predict Y. A prerequisite for performing the Granger causality test is that the time series have to be stationary. For this purpose, we look at the p-value of the Augmented Dickey-Fuller test and differentiate the time series in the case of non-stationarity.</p>
		<p align="justify">Considering the long pandemic period and the different COVID-19 waves of various entities, we imagine a possible difference in people's responses in the long run. For this reason, we divide the pandemic period into three sub-time intervals:
	<ul>
  		<li>An initial period, also called the 'COVID-19 Shock Period', which corresponds to the onset of COVID-19, and extends up to the end of the first hardest mobility restrictions;</li>
  		<li>A second period, also called 'Second waves', that starts from the end of the first hardest mobility restrictions, includes the return of the covid and extends until the new return to normal in the autumn of 2021;</li>
  		<li>A third period that extends until November 1, 2022.</li>
	</ul>
		Below we show the matrix summarizing the results of the Granger causality test, therefore showing the p-values for each test and the corresponding week lag.</p>
		
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
	
	<p align="justify">To quantify the performances of our model, we computed the mean percentage error and the Pearson product-moment correlation coefficients for each forecasting, which measure the strength and direction of association between two variables. The results are shown below. Generally, the general trend of interest is correctly predicted.</p>
	
	<table class="alt" style="width: 50%; margin: 0 auto; text-align:center">
		<thead> 
			<tr> 
				<th style="text-align:center">Language</th>
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
 

<h2 id="conclusion">Conclusion</h2>

<p align="justify">Conclusion on how did Covid 19 pandemic impact food preferences: more or less healthy, more or less exploring, more or less food ordering.</p>
		
<h2 id="conclusion">Outlook</h2>

<p align="justify">Our ideas for future work.</p>
		
		
		
