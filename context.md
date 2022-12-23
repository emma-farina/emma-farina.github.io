---
layout: page
title: Context
image: None
nav-menu: true
---

<!-- Main -->
<div id="main" class="alt">

<!-- One -->
<section id="one">
	<div class="inner">
		<header class="major">
			<h1>Context</h1>
		</header>

<!-- Content -->
<!--<h2 id="content">Elements</h2>-->
		
<p align="justify">During the pandemic, there were significant changes in people's daily routines and habits, including the way they shopped for and prepared food. For example, some people may have started cooking at home more often due to stay-at-home orders or concerns about going out to eat, which could have led to an increase in clicks on food-related topics as people sought information on cooking and recipe ideas. On the other hand, some people may have been less interested in food-related topics due to stress or other distractions related to the pandemic, which could have led to a decrease in pageviews.</p>
	
		
<!--<div class="row">-->
	<!--
	
	<div class="6u 12u$(small)">
		<h3>Sem turpis amet semper</h3>
		<p>Nunc lacinia ante nunc ac lobortis. Interdum adipiscing gravida odio porttitor sem non mi integer non faucibus ornare mi ut ante amet placerat aliquet. Volutpat commodo eu sed ante lacinia. Sapien a lorem in integer ornare praesent commodo adipiscing arcu in massa commodo lorem accumsan at odio massa ac ac. Semper adipiscing varius montes viverra nibh in adipiscing blandit tempus accumsan.</p>
	</div>
	<div class="6u$ 12u$(small)">
		<h3>Magna odio tempus commodo</h3>
		<p>In arcu accumsan arcu adipiscing accumsan orci ac. Felis id enim aliquet. Accumsan ac integer lobortis commodo ornare aliquet accumsan erat tempus amet porttitor. Ante commodo blandit adipiscing integer semper orci eget. Faucibus commodo adipiscing mi eu nullam accumsan morbi arcu ornare odio mi adipiscing nascetur lacus ac interdum morbi accumsan vis mi accumsan ac praesent.</p>
	</div> -->
		
	<!-- Break -->
	<!--
	<div class="4u 12u$(medium)">
		<h3>Healthy food</h3>
		<p>Did healthy food become more popular, in an effort to preserve one’s health, or did unhealthy food receive the most attention?</p>
	</div>
	<div class="4u 12u$(medium)">
		<h3>Cultural interests</h3>
		<p>When trying out new dishes did individuals become more interested in their own history and traditions, or did they want to explore the cuisine of other cultures?</p>
	</div>
	<div class="4u$ 12u$(medium)">
		<h3>Delivery services</h3>
		<p>Did mobility restrictions during the pandemic influence the frequency of food delivery orders? Did delivery services permanently become part of most people's lives?</p>
	</div>
</div>
-->
		
		
<p align="justify">Let's first have a look at how different countries were affected by COVID-19, to get an idea of the timeline of the pandemic.</p>
		
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
* {
  box-sizing: border-box;
}

body {
  font-family: Helvetica, sans-serif;
}

/* The actual timeline (the vertical ruler) */
.timeline {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
}

/* The actual timeline (the vertical ruler) */
.timeline::after {
  content: '';
  position: absolute;
  width: 6px;
  background-color: white;
  top: 0;
  bottom: 0;
  left: 50%;
  margin-left: -3px;
}

/* Container around content */
.container {
  padding: 10px 40px;
  position: relative;
  background-color: inherit;
  width: 50%;
}

/* The circles on the timeline */
.container::after {
  content: '';
  position: absolute; /* position settings for circles on the timeline */
  width: 25px;
  height: 25px;
  right: -13px;
  background-color: #232943;
  border: 4px solid white;
  top: 15px;
  border-radius: 50%;
  z-index: 1;
}

/* Place the container to the left */
.left {
  left: 0; /* changed here from 0 */
}

/* Place the container to the right */
.right {
  left: 50%;
}

/* Add arrows to the left container (pointing right) */
.left::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  right: 30px;
  border: medium solid white;
  border-width: 10px 0 10px 10px;
  border-color: transparent transparent transparent white;
}

/* Add arrows to the right container (pointing left) */
.right::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  left: 30px;
  border: medium solid white;
  border-width: 10px 10px 10px 0;
  border-color: transparent white transparent transparent;
}

/* Fix the circle for containers on the right side */
.right::after {
  left: -12px;
}

/* The actual content */
.content-timeline {
  padding: 20px 20px;
  background-color: white;
  position: relative;
  border-radius: 6px;
}

/* Media queries - Responsive timeline on screens less than 600px wide */
@media screen and (max-width: 600px) {
  /* Place the timelime to the left */
  .timeline::after {
  left: 31px;
  }
  
  /* Full-width containers */
  .container {
  width: 100%;
  padding-left: 70px;
  padding-right: 25px;
  }
  
  /* Make sure that all arrows are pointing leftwards */
  .container::before {
  left: 60px;
  border: medium solid white;
  border-width: 10px 10px 10px 0;
  border-color: transparent white transparent transparent;
  }

  /* Make sure all circles are at the same spot */
  .left::after, .right::after {
  left: 15px;
  }
  
  /* Make all right containers behave like the left ones */
  .right {
  left: 0%;
  }
}
</style>
		
<section id="timeline">
	<section>
		<!--<hr class="major" />-->
<div class="timeline">
  <div class="container left" transition='opacity 1.5s ease'>
    <div class="content-timeline" transition='opacity 1.5s ease'>
      <h4 style="color: #232943">January 2020</h4>
      <small style="color: #232943">First COVID-19 cases in Italy, Germany, France, Spain, Sweden, Finland, Korea, and Japan.</small>
    </div>
  </div>
  <div class="container right" data-aos="fade-up" data-aos-delay="200">
    <div class="content-timeline">
      <h4 style="color: #232943">February 2020</h4>
      <small style="color: #232943">First COVID-19 cases in Norway, Denmark, and the Netherlands. First deaths in Italy, France, Spain, Norway, Korea, and Japan.<br><br>
	School closure in Korea and Japan. Public events banned in Japan.</small>
    </div>
  </div>
  <div class="container left">
    <div class="content-timeline">
      <h4 style="color: #232943">March 2020</h4>
      <small style="color: #232943">First COVID-19 cases in Serbia. First deaths in Germany, Serbia, Netherlands, Denmark, Sweden, and Finland.<br><br>
	    School closure and public events banned in European countries. Beginning of lockdown in all countries considered, except for the Netherlands, Sweden, Finland, Korea, and Japan, which never had lockdown.</small>
    </div>
  </div>
  <div class="container right">
    <div class="content-timeline">
      <h4 style="color: #232943">April 2020</h4>
      <small style="color: #232943">Back to normality in Korea.</small>
    </div>
  </div>
  <div class="container left">
    <div class="content-timeline">
      <h4 style="color: #232943">May 2020</h4>
      <small style="color: #232943">Back to normality in Serbia, Finland, and the Netherlands.</small>
    </div>
  </div>
  <div class="container right">
    <div class="content-timeline">
      <h4 style="color: #232943">June 2020</h4>
      <small style="color: #232943">Back to normality in Italy, Denmark, Norway, and Japan.</small>
    </div>
  </div>
  <div class="container left">
    <div class="content-timeline">
      <h4 style="color: #232943">July 2020</h4>
      <small style="color: #232943">Back to normality in France and Germany.</small>
    </div>
  </div>
</div>
		
<p>                                                                                                                                                                        </p>
<p align="justify">Using Wikipedia pageviews and Google Trends data from 2018 to 2022, we will investigate the evolution of food habits caused by the COVID-19 pandemic to address the following questions.</p>
		
<!--<hr class="major" />-->
		
<section id="research_questions" class="spotlights">
	<section>
		<a href="data_story.html#q1" class="image">
			<img src="{% link assets/images/food_healthy.jpg %}" alt="" data-position="center center" />
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Healthy food</h3>
				</header>
				<p align="justify">Did healthy food become more popular, in an effort to preserve one’s health, or did unhealthy food receive the most attention?</p>
				<ul class="actions">
					<li><a href="data_story.html#q1" class="button">Learn more</a></li>
				</ul>
			</div>
		</div>
	</section>
	<section>
		<a href="data_story.html#q2" class="image">
			<img src="{% link assets/images/food_cultures2.jpeg %}" alt="" data-position="top center" />
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>World cuisines</h3>
				</header>
				<p align="justify">When trying out new dishes, did individuals become more interested in their own history and traditions, or did they want to explore the cuisine of other cultures?</p>
				<ul class="actions">
					<li><a href="data_story.html#q2" class="button">Learn more</a></li>
				</ul>
			</div>
		</div>
	</section>
	<section>
		<a href="data_story.html#q3" class="image">
			<img src="{% link assets/images/food_delivery_box.jpeg %}" alt="" data-position="25% 25%" />
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Food delivery services</h3>
				</header>
				<p align="justify">Did mobility restrictions during the pandemic influence the frequency of food delivery orders? Did delivery services permanently become part of most people's lives?</p>
				<ul class="actions">
					<li><a href="data_story.html#q3" class="button">Learn more</a></li>
				</ul>
			</div>
		</div>
	</section>
<!--</section>-->

