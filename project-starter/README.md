Project title
================
by Team name

## Summary

Here's the summary with all hyphens removed:

---

## Summary

This project explores the question of how sapflow rates vary across urban tree species in Chicago. Sapflow refers to the movement of water and nutrients through the tissue of a plant — in this case, trees. Measuring sapflow is a useful way to understand how trees are responding to their environment, since the rate at which water moves through a tree reflects the conditions it's growing in. Studying differences in sapflow rates between species and sites can tell us a lot about the environments these trees need to thrive, and whether those needs are being met in urban settings.
The data for this project came from a CROCUS node dashboard. CROCUS is a team at Argonne National Laboratory that conducts multi-scale observational science and creates highly accurate climate models. The dashboard hosts data from sapflow sensors that are installed directly into trees, with probes inserted into the trunk to capture water movement at two different depths — an inner and an outer measurement, both recorded in centimeters per hour. The data covers the period from April 1st through April 30th, 2026. In total, I worked with 16 trees across 4 sites in Chicago: CSU, NU, NEIU, and UIC. The trees represented several species, including American Elm, Cottonwood, Honey Locust, Maple, Oak, Sugar Maple, and White Oak.
Before any analysis could be done, the data required significant wrangling. Each tree had its own CSV file, and the files were inconsistent — some were stored in a wide format with one column per sensor type, while others were already in a long format. To handle this, I wrote a function that reads each file, detects which format it's in, and standardizes everything to a long format. I then parsed the file paths to extract the site and species for each tree, filtered down to only the sapflow measurements (excluding things like battery voltage and signal data that were also recorded), and computed daily averages per tree, per sensor.
After exploring the data, I decided to drop the NEIU site from my analysis. The Sugar Maples and White Oak at NEIU were unique to that location, meaning I couldn't compare them to trees of the same species at the other sites. Additionally, several sensors across all sites had been offline during parts of the study period, and that data couldn't be recovered. These limitations narrowed the final dataset to 12 trees across 3 sites and 5 species.
Based on the data exploration, I posed three research questions: Do sapflow rates differ between urban tree species in Chicago? How does site location affect sapflow rates across species? And are there consistent patterns across the data between species and sites?
To answer these questions, I used a combination of methods covered in EAES 480, including summary statistics, exploratory visualization, and linear regression. I started by visualizing daily sapflow over time, faceted by species, which made it clear that some species (especially Maple) showed much more variability than others. I then built summary tables of mean, standard deviation, minimum, and maximum sapflow values for each species-site-sensor combination.
The main statistical analysis was two linear models — one for the inner sensor and one for the outer sensor — using species and site as predictors of daily sapflow. The results revealed some interesting findings. For the inner sensor, Maple and Oak had significantly higher sapflow than American Elm, while Cottonwood was significantly lower. Site effects were also significant, with NU trees showing lower sapflow than CSU and UIC trees showing higher. The model explained 33% of the variation. For the outer sensor, the species effects were different — Cottonwood was actually significantly higher than American Elm, and the other species weren't significantly different. The site effects were consistent with the inner sensor, and the model explained 28% of the variation.
Three key findings emerged. First, sapflow rates differ significantly between both species and sites, with the two factors together explaining around 28 to 33% of the variation. Second, the inner and outer sensors tell different stories — Cottonwood in particular showed opposite patterns between sensors, suggesting the two sensors capture different aspects of water movement through the tree. And third, site matters as much as species. The consistent pattern of NU trees showing lower sapflow and UIC trees showing higher sapflow across all species suggests that local environmental conditions play a major role in tree water use, regardless of species.

#Write-up of your project and findings go here. Think of this as the text
#of your presentation. The length should be roughly 5 minutes when read 
#out loud. Although pacing varies, a 5-minute speech is roughly 750
#words. To use the word count addin, select the text you want to count
#the words of (probably this is the Summary section of this document, go
#to Addins, and select the `Word count` addin). This addin counts words
#using two different algorithms, but the results should be similar and as
#long as you’re in the ballpark of 750 words, you’re good! The addin will
#ignore code chunks and only count the words in prose.

#You can also load your data here and present any analysis results /
#plots, but I strongly urge you to keep that to a minimum (maybe only the
#most important graphic, if you have one you can choose). And make sure
#to hide your code with `echo = FALSE` unless the point you are trying to
#make is about the code itself. Your results with proper output and
#graphics go in your presentation, this space is for a brief summary of
#your project.

## Presentation

Our presentation can be found [here](presentation/presentation.html).

## Data

Include a citation for your data here. See
<http://libraryguides.vu.edu.au/c.php?g=386501&p=4347840> for guidance
on proper citation for datasets. If you got your data off the web, make
sure to note the retrieval date.

## References

List any references here. You should, at a minimum, list your data
source.
