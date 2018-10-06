# Global warming is a reality, all over the globe !

### Author
Pierre Raimbaud : https://github.com/pierreraimbaud, GitHub project link : https://github.com/pierreraimbaud/GlobalWarmingIsReal and Projet page : https://pierreraimbaud.github.io/GlobalWarmingIsReal/<br/><br/>
This project is under MIT license.<br/><br/>
<img src="/GlobalWarmingReality.png" alt="World division N-S">
<img src="/World_map_With_Parallels.jpg" alt="World division N-S"><br/>
<h2>Prerequisites, technologies</h2>
<p>The technologies used are d3 (javascript), HTML, CSS and git (nodejs for developing with a local server). There is no specific prerequisites for enjoying the visualization neither for using the code, available in github.</p>
            <p>Here, for the visualization by zones and subzones (detailed visualization), we used this division with the parallels 90, 64, 44, 24 North and South and the Equator.</p>
            <p>This picture is a modified version of <a href="https://upload.wikimedia.org/wikipedia/commons/0/0a/World_map_2004_CIA_large_2m.jpg">an original picture</a> which is published in public domain (author : Central Intelligence Agency).</p>
            <br/><br/>
            <h2>What, why and how ? Understanding this visualization thanks to abstraction</h2>
              <p style="color:#111111;">
              This visualization uses data from data.giss.nasa.gov. The principal objective here is to show or discover some interesting insights about this data, knowing that the principal question asked was:<br/><b>Show that the global warming is a reality, all over the globe!</b>
              <br/><br/>
              The other objetives are more academic: to use d3, to publish the web page on GithubPages etc.
              <br/><br/>
              To be more precise about these insights, in the following paragraphs we will explain what were our data (through data abstraction), why this visualization (through task abstraction) and the reason of how we choice to present the data (idioms : visual encoding and interaction) ; thanks to that, we have been able to answer to the title question : is there the global warming a reality?
              <br/><br/>
              <h2>What ?</h2>
              The dataset type is a <b>table</b>. The dataset availability is <b>static</b> because the dataset available on the website is not modified in real-time, so we just download the file from the website and load it on github. Maybe the data can evolve in the original website but here we will use a static data file, the one on github. Then to separate the dataset in smaller ones, and also to get <b>derive data</b> (promedian over 5 years), we process directly this file in the visualization with d3.<br/><br/>
              Before processing the data in d3, the <b>items</b> represent each one a year, which have the same characteristics about temperature change (global change, change in the North, change in the South, change in the Equator, change in the North-Part1, change in the North-Part2, change in the North-Part3, change in the South-Part1, change in the South-Part2, change in the South-Part3). The years and these characteristics are the <b>attributes</b> (named just above).<br/><br/>
              The attribute year is ordered and quantitative (temporal) and sequential (there is no separation between two groups so no diverging).
              All the other attributes (there are all temperature changes, comparing to the promedian temperature of the years 1950-1980) are ordered and quantitative (because they are numbers) and diverging because there is a separation into two blocks of changes, the positive and the negative ones, which have different meanings each one.<br/><br/>
              After processing the data, we obtain new items : each item is a period of 5 years (quinquennium). The attributes remain quite the same ones : about the year (time period), it becomes a new time period: a quinquennium (a five-year period) with the same characteristics (ordered, quantitative, sequential), and about the different temperature changes it becomes the promedian of temperature change considering the 5 years, remaining with the same characteristics (ordered, quantitative, diverging).<br/><br/>
              <h2>Why ?</h2>
              Which tasks do we want to perform here ? <br/><br/>
              As said in the title, first, the primary task we want to perform here is to show that <b>the global warming is a reality, and in the whole world.</b>
              In terms of Tamara, at a high-level, the action is <b>Present</b> and the target is <b>Trends</b> : we want to show this reality, that in the last decades the temperature on the planet has increased! To be more precise, at a low-level that the action is <b>Identify</b> and the target is <b>Trends</b>. For this behaviour we can use only the dataset <i>Earth zone: Global</i>.
              <br/><br/>
              This is <b>our first insight : the global warming is a reality on the planet.</b>
              <br/><br/>
              To complete this approach, for the primary task, we provided one interaction "Switch dataset" which allow to visualize the data for 3 zones of the planet : North, Equator and South. Thanks to these visualisations, we can show that the global warming is a fact on the whole planet. In terms of Tamara, at a high-level, the action is also <b>Present</b> and the target is <b>Trends</b>, and at a low-level that the action is also <b>Identify</b> and the target is <b>Trends</b>.
              <br/><br/>
              <b>This is our second insight : the global warming is a reality on all the parts of the planet (North, Equator, South).</b>
              <br/><br/>
              One secondary task here, not required/asked here but meaningfull, is to know better about the global warming depending on the zones of the world. We want to know where the global warming has been more important, and where not. In terms of Tamara, at a high-level, this task is <b>Discover (action) Features (target)</b> and at a low-level that the action is <b>Compare</b> and the target is <b>Features</b>. We can perform this task by using the interaction "Switch dataset" and looking at the scale on y axis and see the highest level. 
              <br/><br/>
              As a result, <b>our third insight : the global warming, present everywhere on Earth, is even more important in the North of the planet (more than in Equator, where it is more important than in the South).</b>
              <br/><br/>
              Another secondary task here, not required/asked here but meaningfull, is to search more precisely for each zone, if there are differences between subzones of this one about the global warming. The aim is to be able to determine if the global warming has been more important in some subzones, or not. In terms of Tamara, at a high-level, this task is <b>Discover (action) Features (target)</b> and at a low-level that the action is <b>Compare</b> and the target is <b>Features</b>. We can perform this task by using the interaction "Show dataset details": by clicking you can observe in the same visualization the temperature changes for 2 or 3 subzones of the current one.
              <br/><br/>
              As a result, <b>our fourth insight : the global warming, present everywhere on Earth, is even more important in the North of the North of the planet : the North Pole. It is a confirmation of something that the media are also telling. But more surprisely, in the South of the planet, in the South Pole (the South of the South of the planet), the global warming is not more important (it is less important!) than in the northern parts of the South.</b>
              <br/><br/>
              <h2>How ?</h2>
              We choose <b>bar charts</b> for this visualization.<br/><br/>
              First, we have to say that for all the datasets, in the x axis, we have the quinquennium attribute which is ordered, quantitative, sequential and in the y axis we have the promedian temperature change attribute (sometimes 2 or 3 times), so ordered, quantitative, diverging.<br/><br/>
              As a result, about the visual encoding, the <b>mark</b> we choose is <b>line</b> and the <b>channel</b> is <b>vertical position</b> (which give a bar chart) ; it can be easily explain because this channel is the most <b>effective</b> for the ordered attributes (which should always use magnitude channels, in theory, so from this point of view, we use a good and expressive type).
              We choose to <b>order and align</b> the marks in our representation because it combines well with ordered attributes and with our task (identify trends, identify features, compare features).<br/><br/>
              Then about the interaction, we decide to provide to the user two interactions with two buttons. The first one (switch) is for switching between the dataset, so it’s a <b>Change manipulation</b> : it is usefull for our primary task (show that in the whole world the global warming is a reality) and for a secondary task (compare the global warming between the 3 zones). The second one (show details) is for showing the detail about temperature changes in 2 or 3 subzones of the current zone of the planet : it is usefull for a secondary task (compare subzones in order to see if the global warming has been more important in some subzones). It’s a <b>Superimpose!</b> And, we provide also a <b>“Select” manipulation</b>, with a mouseover which give more detailed information about the current item.</p>
              </p>
