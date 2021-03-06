Prospectus
================
Ruth Simberloff
10/18/2021

This is a solo project in which I will analyze data from my Master’s
thesis project and visualize the results of my analysis.

### What is the data?

In the spring of 2020 I mapped the territories of 38 white-crowned
sparrows at both urban and rural sites in the San Francisco Bay Area. I
have 80-90 locations from each bird, which I can use to construct a
utilization distribution of each bird’s home range. I also have data on
each bird’s age & body condition, as well as a noise level reading at
the approximate center of each territory. Additionally, I have been able
to use other data from this project to calculate the communication
distance (i.e. distance from which their song is audible) of most of
these birds.

### What will I do?

I plan to estimate territory area for each bird, evaluate my sample
size, and do statistical analysis to determine whether factors such as
bird age, territory noise level, communication distance, and habitat
type (urban/rural), explain any of the variation in territory size. I
also hope to visualize the results of this analysis, but may have to do
so in a more specialized spatial software like qGIS.

### Expected technical challenges

I have never analysed spatial data. I’m unfamiliar with the specialized
data classes necessary for this analysis
(e.g. `sp::SpatialPointsDataFrame`) and am new to virtually every aspect
of the packages designed to handle these data (e.g. `adehabitatHR`).

### What will the finished project look like?

The finished project will look like a simplified first draft of a
manuscript, minus the components that would not be relevant to this
course (like field methods or in-depth discussion). It will be in an R
notebook.

### Does this go beyond what you would have done anyways?

Doing this work as part of this class will give me time to incorporate
more sophisticated estimation of the utilization distribution, allowing
me to explore methods that account for the sequential nature of the
observed locations (movement-based kernel estimation).

I will also try to make use of R’s recent and expanding functionality
for visualizing spatial data. This is a black box to me at the moment,
but I know that relatively new packages are allowing R users to make
more flexible and attractive maps. This would be a useful skill to me,
as it would allow me to keep analysis, results, and visualization all in
the same workflow.

Overall, I will place much greater emphasis on data reproducibility than
if I hadn’t taken this course. My hope is that, by the end of this
project, my data and code will be ready to submit and publish as
supplements to a manuscript on territory size.

### Why does this matter?

Though a growing body of literature documents effects of urban noise
upon birdsong, few studies do more than speculate about the broader
implications of these phenomena.

Song is universally considered to be a competitive territorial signal,
but the link between song and territorial outcomes remains poorly
understood. If territory size is reduced for urban birds, this could
impact not only individual-level traits such as reproductive fitness,
but also population-level traits such as population density and habitat
use. This project would forge an essential link between communication
and its adaptive function.

Not only is this an active frontier in animal behavior research, it is
also essential to understanding the myriad complex ways in which the
human landscape interacts with the natural world. Urban habitat occupies
over half a million square kilometers and could increase by over 500% by
the end of the century. The world is growing noisier, and in order to
effectively manage and conserve wildlife, we must understand not only
the first-order impacts of this environmental change, such as impaired
communication, but also the cascading second- and higher-order impacts
such as reduced competitive ability and smaller territories.
