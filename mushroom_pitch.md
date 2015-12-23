Predicting mushroom quality
========================================================
author: Sayandeb Banerjee
date: 22 December 2015

Part of the project submission for the Data Products Course of the Data Science Specialisation by Johns Hopkins University via Coursera.

Why do we predict mushrooms?
========================================================
Every year, many people fall ill or die from ingesting poisonous mushrooms. Since many mushrooms are very similar to each other, even experienced mushroom gatherers often fall victim.

There are no clear rules by which to identify poisonous mushrooms. One of the strengths of rule learnign algorithms is that they generate easy to understand rules, therefore are a fit candidate to analyse mushrooms by their characteristics and an accurate predictions can be life savers for foragers.

For the exercise we use the mushroom dataset available at the UCI Machine Learning Repository.


A word about the dataset
========================================================
The original data set comprises information on 8,124 samples of mushroom from 23 species of gilled mushrooms listed in the <i> Audubon Society Field Guide to North American Mushrooms (1981) </i>

The original data had the following features:

```
 [1] "type"                     "cap_shape"               
 [3] "cap_surface"              "cap_color"               
 [5] "bruises"                  "odor"                    
 [7] "gill_attachment"          "gill_spacing"            
 [9] "gill_size"                "gill_color"              
[11] "stalk_shape"              "stalk_root"              
[13] "stalk_surface_above_ring" "stalk_surface_below_ring"
[15] "stalk_color_above_ring"   "stalk_color_below_ring"  
[17] "veil_type"                "veil_color"              
[19] "ring_number"              "ring_type"               
[21] "spore_print_color"        "population"              
[23] "habitat"                 
```



Working with a simplified dataset
========================================================
However this data is encoded. Therefore, we decoded the data from the notes and also created a simplified version of it with only 4 most important distinguishing features that separate poisonous mushrooms from edible ones.


```
[1] "type"              "odor"              "gill_size"        
[4] "gill_color"        "spore_print_color"
```

The 'type' feature has two levels 'poisonous' and 'edible'. This is the class on which the learning and prediction are done.

Classification rules
=========================================================
We ran the RIPPER rule learning algorithm. The 'RWeka' package provides a function 'JRip()' which is a Java based implementation of RIPPER.

TO simplify matters we ran JRip on the whole set and determined the 4 most distinguishing features of the data set. Then we created the model fit only on those 4 features. 

In the shiny application (https://sayandeb.shinyapps.io/mushroomsApp), we ask the user to input only those features and output our prediction of the qulaity of the mushroom.


