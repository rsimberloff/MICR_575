Homework 6: Data Visualization
================

## A successful plot

From **Lipshutz SE & Rosvall KA. 2021. Nesting strategy shapes
territorial aggression but not testosterone: A comparative approach in
female and male birds.** Published in *Hormones and Behavior*.

![successful](https://github.com/rsimberloff/MICR_575/blob/master/hw_6_files/successful.jpg?raw=true)

#### Description

This is a box plot (`geom_boxplot`) overlaid with a scatter plot
(`geom_point`).

Each point represents testosterone level in an individual bird.  
\* *x*-axis is mapped to the bird species (4 levels) and is further
subsetted by sex (categorical, un-ordered)  
\* *y*-axis is mapped to the level of testosterone in circulation
(continuous, log-transformed)  
\* color is mapped to sex

## An unsuccessful plot

From **Clink DJ, Ahmad AH, and Klinck H. 2020. Brevity is not a constant
in animal communication: evidence for compression depends on the unit of
analysis in small ape vocalizations.** Published in *Royal Society Open
Science*.

![unsuccessful](https://github.com/rsimberloff/MICR_575/blob/master/hw_6_files/unsuccessful.png?raw=true)

#### Description

This is a scatterplot (`geom_point`) with a regression line
(`geom_smooth`).

Each point represents a vocalized phrase by a gibbon.  
\* *x*-axis is mapped to the number of notes in a phrase (continuous
data, log-transformed)  
\* *y*-axis is mapped to the mean duration of notes in the phrase
(continuous data, log-transformed)  
\* Point color is mapped to the individual gibbon who made the phrase
(categorical data, un-ordered)

#### Evaluation

**Why is it bad?**  
*Too many colors.*  
The authors have given each of **13** different factor levels a
different color. As Wilke points out, qualitative color scales work best
when there are 3 to 5 colors. Here, it’s barely possible to distinguish
the different levels, and matching each point to a color in the legend
involves a lot of squinting and uncertainty. This is worsened by their
decision to make the points transparent.

*Poor color choice.*  
*(A) Ordered color scale for un-ordered categories.*  
This plot uses a sequential color palette for a categorical variable
with no inherent order. This is visually misleading us about the
relationship of the factor levels, and also makes it nearly impossible
to distinguish the individual colors. This exacerbates the issue with
the number of colored levels, as it means the neighboring colors are
extremely similar. If they *had* to map color to individual, they at
least should have chosen colors as dissimilar as possible (e.g. the
“qualitative” ColorBrewer sets).

*(B) Colors fail to distinguish between two overarching categories.*  
If they wanted to do something actually useful with color, the authors
could have distinguished between individuals from the two sites. This
plot suggests that the two sites are showing very different patterns,
but it’s impossible to tell with the current color mapping. They could
have mapped each site to a color, even if they kept different colors for
each individual (e.g. “D” gibbons could be shades of blue and “M”
gibbons shades of red.)

*Overplotting.*  
The authors tried to address overplotting by reducing the alpha of the
points, but this was not very successful. Overplotting is exacerbated by
the color choice (extremely similar colors) and the data structure
(*x*-axis values are integers). As a result, it’s impossible to tell how
many data points are represented in the plot. They should have reduced
the size of the points. reducing point alpha could be an effective
solution if they fixed the color problem.

*“Telling a story and making a point”*  
From the text, it seems the authors intended this plot to make the point
that note duration decreases as the number of notes in a phrase
increases (“Menzerath’s Law, tah-dah!”). However, I don’t think the plot
communicates this effectively – it mostly made me question their
analysis & data set.

**Why is it wrong?**  
*Linear axis labels for log-transformed data.*  
The authors are showing log-transformed data but don’t seem to have
changed the *x*-axis ticks & labels? This is particularly noticeable
because “number of notes in a phrase” can only have integer values.
As-is, the plot implies that you can have a fraction of a note, which is
meaningless here.

*Mystifying axis labels*  
The transformation should be included in the axis label, not just the
caption. The *x*-axis starts at “0”, and implies that a phrase with no
notes at all somehow has a high mean note duration. The *y*-axis
suggests that phrase duration is somehow negative. You can figure out
what the authors mean from the caption, but the plot as it stands is
inaccurate.
