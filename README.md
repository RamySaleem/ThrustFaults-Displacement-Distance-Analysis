# ThrustFaults-Displacement-Distance-Analysis
This study offers critical automatic workflows to examine the displacement–distance profiles and insert the mechanical stratigraphy.

## Abstract 

Displacement distribution and profile patterns are controlled by mechanical stratigraphy on a regional scale. Here, we present a detailed analysis of isolated thrust faults in multilayer stratigraphy and their displacement-distance profiles in coal mines, the lower Rhine basin, Ruhr sub-basin, Germany, where claystone, sandstone with siltstones, coarse sandstone and rhyolite tuff act as mechanically controlling elements of stratigraphy to an array of thrust faults. Faults generally show systematic variations in displacement approaching their tips. These variations can be displayed on displacement–distance diagrams - where offsets between multiple pairs of footwall and hanging-wall cut-offs are cross-plotted against a distance measured along the fault surface from a reference point. Coloured displacement-distance profiles according to the stratigraphic lithology and displacement length can help understand the mechanical controls on displacement distribution along thrust faults. Conducting such studies across interpreted subsurface cross-sections can provide more robust constraints in adequately determining displacement-distance profiles, their patterns and displacement-length relationships. Idealised displacement–distance profiles for single isolated faults show diminishing offsets to fault tip-line. However, our results are more complex, with varying profiles that deviate from the idealised pattern. A constant displacement–distance pattern is common in sandstone layers, while variable displacement–distance patterns are more common in the finer-grained units. Thinly interbedded successions display the most complex displacement–distance relationships. Displacement distance profiles, local gradient, thrust length and maximum displacement are considered against the lithological stratigraphy through which each fault cuts. Analysis of fold-thrust displacement profiles shows that the multilayered stratigraphy influences displacement–distance patterns, presumably because additional strain components are heterogeneously developed in the rock wall. A Python script to automatically plot displacement distance profiles with their associated lithology has been developed to aid the analysis of displacement–distance profiles for faults. As our demand for subsurface use increases for a range of activities, including CO2 storage, nuclear waste disposal and energy storage, the importance of understanding fault displacements in multilayered stratigraphy also increases. The work here is designed to aid data collection and analysis in multilayer stratigraphy. 


# 1	Introduction
Understanding the geometry and movement of thrust faults is crucial for a range of structural geology applications in the geoscience discipline. For example, these structures control the traps and prospects of hydrocarbon (e.g. Boyer 1985; Khan et al. 2015), promote hydrocarbon leakage at the compressional zone (e.g. Sun et al. 2021), restrict the seal potential of the caprock that confines the injected CO2 at each potential storage site of carbon capture and storage (CCS) projects (e.g. Kaldi et al. 2013) and control the occurrence and possibility of geothermal resources (e.g. Corbel et al. 2012).

The patterns of the displacement-distance profiles were originally derived from displacement variations vertically along the thrust trace, and the distance from the reference point to the tips of the thrust, wherein any large thrust displacement reduces towards the two ends of the thrust trace (Williams and Chapman 1983). More specifically, the recognition that the displacement-distance profiles were at a maximum near the centre and diminished outwards in all directions to the edge of the thrust where the displacement is zero led to the understanding that the displacement-distance profile permanently had a simple shape of normal distribution in the idealised model (e.g. Williams and Chapman 1983). More recent observations, primarily from regional and outcrop field studies (e.g. Spotila and Sieh 2000; Mazzoli et al. 2005; Watkins et al. 2017) and seismic reflection data (e.g. Bergen and Shaw 2010), have supported an alternative, more complex displacement profile pattern (Shankar Mitra 2002; Kim and Sanderson 2008; Bergen and Shaw 2010). In this, the displacement profiles show variations from the normal distribution by increasing or decreasing the displacement in which the displacement-distance profiles are possibly controlled by mechanical stratigraphy (Couzens and Wiltschko 1996; Farzipour-Saein et al. 2009; Cawood and Bond 2018). However, another explanation could be inaccurate interpretations in which the relation between faults and horizons is misinterpreted, resulting in abnormal fold-thrust geometries and displacement distribution (Shaw et al. 2005; Totake et al. 2018; Cunningham et al. 2021). A third, more kinematic explanation posits that the displacement is transferred either by fault to fault interaction (hard linkage) (Kim and Sanderson 2005; Mouslopoulou et al. 2007; Xu et al. 2014; Totake et al. 2018) or fault to fold interaction (soft linkage) (Kim and Sanderson 2005; Qayyum et al. 2015; Watkins et al. 2017; Totake et al. 2018) which also resulting in a complex displacement profile pattern.

The rheological and mechanical heterogeneity of the stratigraphy surrounding thrust faults can influence the pattern of the displacement profiles and the final geometry of thrusts (Fig. 1) (Muraoka and Kamata 1983; Williams and Chapman 1983). More precisely, the displacement-distance profile of thrust that cuts through competent layers (e.g. rhyolite tuffs) and less competent layers (e.g. claystone or sandstone with siltstones) where they mechanically interact can be with a complex pattern of displacement profile, a situation common in multi-layers sedimentary sequences (Couzens and Wiltschko 1996; Farzipour-Saein et al. 2009; Cawood and Bond 2018). This behaviour can result in anomalous displacement values, inconsistency in the ratio between the maximum displacement and thrust length, as well as variable patterns in the displacement-distance profile (Shankar Mitra 2002; Kim and Sanderson 2008; Bergen and Shaw 2010). For example, a thrust may preferentially propagate laterally along-strike in competent layers, thereby restricting its vertical height limiting its ability to accumulate displacement and thus causing the thrust faults to appear “under-displaced” (Redpath et al. 2022). Mechanical interactions between stratigraphy and thrusts and between thrust and neighbouring folds can also influence thrust geometry and displacement-distance profile (Mazzoli et al. 2005).

In this study, we use a high-resolution coal mines dataset as a series of subsurface cross-sections interpreted by Drozdzewski et al. (1980) from Ruhr coalfield in the Carboniferous, Lower Rhine Basin, Germany (Fig. 2), to investigate the geometry of and displacement patterns on several thrust faults. These data allow us to assess how the mechanical properties of the stratigraphy, inferred from the stratigraphic column and interpreted cross-sections, influence displacement-distance profiles and ultimate thrust geometry, thereby allowing us to test displacement profiles patterns. These thrusts occur in a multipayer stratigraphy dominated by claystone, sandstone with siltstone and coal seams, within which mechanical layering is imposed by regionally developed coarse sandstones and rhyolite tuffs (Fig. 3). The thrusts formed in a broadly similar stress regime, and therefore that any differences in their geometry and kinematics, which result in differences in their displacement profile patterns, likely reflect the stratigraphic heterogeneity and local mechanical interactions. We show that displacement profile patterns and the ratio between the maximum displacement and thrusts length vary on even closely spaced thrusts. We explore why displacement profile patterns of thrusts can significantly vary and how they are distributed on the maximum displacement versus length relationship plot, even when they presently have strong maximum displacement and length relationships that broadly follow other studies (Shankar Mitra 2002; Benedicto et al. 2003; Kim and Sanderson 2008; Bergen and Shaw 2010). Our study shows that displacement-distance profiles alone do not allow us to determine the reasons for variations, complexity and types of displacement profiles patterns. However, coloured the displacement-distance profiles using lithology strata and the analysis of thrusts of varying scales (small, medium and large) within a single population together provide more robust kinematic constraints.


# 2	Data and Methods 

## 2.1	Data

The study area is explored by high-resolution, closely spaced, coal mines with an aerial extent of 323.29 km2 and a depth of 2 km (Fig. 2). The subsurface data are provided by mine-workings (galleries, adits and shafts) as well as accompanying boreholes and seismic reflection profiles, which are supported by surface exposure enhanced by open-cast pits. These data were interpreted by Drozdzewski et al. (1980), who reported these observations and erected their own geological interpretations on a series of paper maps and cross-sections. They are a set of 12 serial cross-sections with a spacing of 1 to 2 km and tied by two cross-lines (Fig. 2). Further, Drozdzewski et al. (1980) indicate the levels of confidence in their interpretations critically using descriptive criteria. The stratigraphic column present in this study is put together and generated after Drozdzewski et al. (1980), Drozdzewski (1993), Suess et al. (2007), Cleal et al. (2009) and Uhl and Cleal (2010) (Fig. 3). The lithology, formations names, coal seams and stratigraphic units in this stratigraphic column are constrained by correlating the stratigraphic units from Drozdzewski et al. (1980) to other recent studies (e.g. Cleal et al. 2009; Uhl and Cleal 2010). 


**Dataset can be found in the following links:**
1. **Interpreted Images** https://drive.google.com/drive/folders/1j4PBXQyVx89rkVTvMS7Yjl7e7y5OTDrC?usp=sharing
2. **Digitised Cross Sections** https://drive.google.com/drive/folders/1EabQCWqC1JExdLTRCJRx8MDAGHAhHy5N?usp=sharing
3. All the maps and cross-section of the Ruhr subbasin, lower Rhine basin is available in the North Rhine-Westphalia Geological Survey – State Office – (GD NRW) for a fee https://www.gd.nrw.de/pr_kd.htm

## 2.2	Displacement-distance calculations and plots

We study 14 subsurface cross-sections (12 in-lines and 2 cross-lines) that are located in the Ruhr coalfield and documented for coalmines exploration, the latter of which is only 2D structurally interpreted and studied along the western side of the coalfield (Fig. 2a). Within these 14 cross-sections, we investigate 346 thrust faults traces and plot the displacement-distance profiles for 98 of them, where we have 848 measurement points. 323 of these data points were measured in the rhyolite tuff layer, 289 within sandstone with siltstones, 149 in the coarse sandstone and 87 within the claystone. We focus on 98 exceptionally well-identified thrust faults that form part of a larger array of fold-thrust structures (Fig. 4). These thrust faults are also selected because we can comprehensively calculate the displacement of coal seams horizons and the distance from a reference point to the tips of the fault trace, therefore, generating displacement-distance profiles that allow us to constrain displacement distributions across their surfaces (e.g. Williams and Chapman 1983; Chapman and Williams 1984; Totake et al. 2018) and analyse the displacement distribution related to lithological changes in this multi-layered system. 
We accurately calculated the offset between multiple pairs of footwall and hanging-wall cut-offs for the coal seams horizons vertically along faults traces using Petroleum Experts’ Move Suite structural modelling software (Fig. 4). We, therefore, investigate their offset distribution (displacement, throw and heave), including geometry measurements (i.e. fault length, dip angle and azimuths), with reasonable precision (Appendix - Tables 1 and 2). Further, we used the stratigraphic column (Fig. 3) to colour the displacement-distance profiles (Fig. 5) and infer at which stratigraphic levels the maximum displacement of the thrust occurs, which may relate to the depth at which the thrusts nucleated (e.g. Bigi et al. 2010; Ferrill et al. 2016).

In most cases, thrust faults in the study area have a complicated trajectory, and some faults consist of multiple fault traces or contain fault-related folding (Fig. 2). This makes it difficult to confidently analyse the variation of displacement due to lithologic control (Fig. 4). One reason for that is some measured points of displacement are missing within a single fault segment as a consequence of repeated movements or the effects of this ductile or continuous deformation due to related foldings (e.g. Walsh and Watterson 1991; Hongxing and Anderson 2007; Forster and Lister 2008; Jackson et al. 2017; Lăpădat et al. 2017; Pan et al. 2022). Since many of the thrust faults in the study area have complicated geometry, where extensive thrusting and folding occur at the top of the coal seams formations (Fig. 2 c and d), it may be the case that displacement variations become significantly higher than the idealised original fault model (e.g. Williams and Chapman 1983) (Fig. 1).

We follow the method of Williams and Chapman (1983) to construct displacement-distance plots that show how displacement varies vertically on a given thrust trace for multiple horizons, as well as the patterns of displacement profiles (e.g. Fig. 5). We also calculated displacement gradients (i.e. change in displacement/distance on fault trace over which the change occurs) across the thrust surface, noting that relatively high variation gradients may reflect mechanical interactions with adjacent thrust faults or host stratigraphy layers (e.g. Couzens and Wiltschko 1996; Farzipour-Saein et al. 2009; Cawood and Bond 2018). 
To investigate the patterns of displacement profiles, we coloured the displacement-distance profiles for the lithology of the strata. The displacement-distance profiles were coloured by giving each coal seam horizon a colour code and then applying this colour code between the points of displacement measures to reflect the information of the mechanical stratigraphy (Fig. 5). Then we measured thrust length (L) as the vertical distance from the thrust trace upper to lower tip, thrust angle, thrust average plunge dip and azimuth, and hanging-wall and foot-wall bedding plane dip and azimuth (Appendix - Tables 1 and 2). Further, we identified the uncertainty in each measured point by three classes (Proven, Assumed and Secured) after Drozdzewski et al. (1980). Using these geometric data, we examined displacement variations along thrust traces and lithology, which again can be used to infer whether the displacement profile patterns related to displacement transfer to adjacent faults by hard-linkage, fold by soft-linkage or mechanical interactions and changes in mechanical properties of the stratigraphy (Couzens and Wiltschko 1996; Farzipour-Saein et al. 2009; Cawood and Bond 2018).


# 3	Geological Setting 

## 3.1	Western Ruhr coalfield in the lower Rhine basin 

The crystalline basement rocks located in the Northwest of Germany can be divided by approximately NW-SE to SW-NE running graben and horst systems from the Hercynian and Rhenish geological mountain-building events (Brink 2021). The sea flooded these systems, and primarily marine carbonates were deposited on the horsts and Stillwater shales in the grabens during the Late Devonian and Early Carboniferous times (Brink 2021). The terrain became a coal-rich foreland basin throughout the Late Carboniferous Variscan Orogeny, where the grabens responded through thrusting and folding with different anticlinal patterns (Wrede 2005). These grabens were the location of the Late Carboniferous sub-basins, including the Ruhr coal-rich sub-basin in the western sector (Fig. 2 and 3) (Brink 2021). Therefore it probably acted as a perfect example to study thrust complex structures.


During the Devonian, a strong influx from the northern source areas resulted in the deposition of multi-layered clastics in the Ruhr sub-basin (e.g. Drozdzewski et al. 1980; Franke et al. 1990; Drozdzewski 1993; Wrede 2005). These clastic sediments were deposited in entirely marine conditions, with the exception of the areas in the northeastern corner deposited in continental conditions. They formed a broad shelf region that, during the Lower Devonian period, included the whole present-day Rhenish Massif (Franke et al. 1990). The shallow coastal clastic facies retreated to the northwest during the Devonian, giving way to hemipelagic sequences formed of silt-sized grains, sandstone turbidites and condensed shales or carbonates. During the Mid Devonian period, the production of platform and reef carbonates on the clastic shelf was caused by a decrease in clastic inflow, where several reefs developed on volcanic mounds in the hemipelagic domain. At least from the Mid Devonian, a southern source region (the Mid-German Crystalline Rise) has deposited clastics into the northwest basins. Subsidence in the foreland basin was balanced by clastic influx by the Carboniferous age. Sedimentation proceeded in the environment of the Ruhr sub-basin coal-bearing to the Upper Carboniferous (Franke et al. 1990).


Volcanic rocks are also observed within the sub-basin sedimentary sequence (Franke et al. 1990) (Fig. 3) as throughout the Devonian to the Early Carboniferous, the area was affected by extensive volcanic activities. The rhyolites represent the initial volcanic activity that occurred in the Lower Devonian. However, most volcanic rocks are basaltic, ranging in age from the Mid Devonian to the Variscan, with peaks in the Late Devonian. Moreover, Lower Carboniferous lavas were reported in the area by  Franke et al. (1990). This volcanic lineament, lavas and tufts partly occurred at trending NNW-SSE following the orientation of the faults (Franke et al. 1990; Wrede 2005). These volcanic rocks possibly represent a narrow basin oceanic floor (see Franke et al. 1990).
In the Ruhr sub-basin, the whole palaeozoic sequence was folded at the end of the Carboniferous. Folding in the Ruhr basin is strongly disharmonic, defined by large synclines and anticlines with intense minor folding (e.g. Fig. 2c and d). These folding display a wide range of amplitudes and wavelengths. Thrust faults are generally restricted to the limbs of the anticlines with dimensions ranging from several metres to a few kilometres. Isolated thrusts occur at different stratigraphic levels and are not linked to detachment thrusts. Thrusts are involved in fold Geometry and are deformed more or less concurringly to folding (Fig. 2c and d). The thrusts we study were probably formed in response to the contractional phase of the Variscan Orogeny. 

# 4.	Conclusion

Our data strongly suggest that displacement profiles patterns are controlled by mechanical stratigraphy, where thrust propagation within each lithological unit is characterised by specific displacement gradients for each such unit. This conclusion is consistent with a number of studies based on observations of the nature of thrusts (Chapman and Williams 1984; Couzens and Wiltschko 1996; Teixell and Koyi 2003; Cawood and Bond 2018, 2020; Parker and Pearson 2021; Wigginton et al. 2021). Collectively, data from the coalfield mines as isolated thrusts within multi-layered system suggest that:

•	Displacement profiles have complex profile shapes with a wide range of profile patterns controlled by the mechanical stratigraphy of the units.

•	Displacement gradients increase steeply on the upper parts of the thrusts and drop sharply on the lower parts of the thrusts while the gradient remains almost constant or has local variations on the middle parts of the profile. 

•	Correlation between the maximum displacement and length of thrusts exhibits a linear relationship controlled by mechanical stratigraphy where the displacement profiles patterns spread around this regression line.

Accordingly, our gradient values are much lower within the clay units than within the coarse sandstone or the Rhyolite tuff layers. However, the variation in the displacement gradients in the silty sandstone layers investigated here displays a wide range of variations with respect to the other lithologies, which is expected given the heterogeneity of the lithology content of these units. Indeed, the complexity of displacement-distance relationships is generally likely to rise with the increase in the heterogeneity of the lithology units. Nevertheless, the gradients obtained in this study increase with increasing the interaction of thinly interbedded successions. This indicates that the effect of the mechanical stratigraphy is combined by other parameters such as rock strength or by a heterogeneous stress distribution in relation to the layering. In light of these results, the displacement distance analysis and its gradient variations of thrusts faults in multilayer systems and with the support of its mechanical stratigraphy is the key to gaining further insights into thrust faults evolution.

Future work
===========
To develop a workflow and web-based front end for the script, which will allow the rapid upload of geological data into the forward seismic modelling to generate synthetic seismic data.

Acknowledgements 
=================
The work contained in this repositories contains work conducted during a PhD study undertaken as part of the Natural Environment Research Council (NERC) Centre for Doctoral Training (CDT) in Oil & Gas funded 50% through its National Productivity Investment Fund grant number NE/R01051X/1 and 50% by the University of Aberdeen through its PhD Scholarship Scheme. The support of both organisations is gratefully acknowledged. The work is reliant on Open-Source Python Libraries, particularly numpy, OpenCV, cv2 matplotlib, bruges and pandas and contributors to these are thanked, along with Jovian and GitHub for open access hosting of the Python scripts for the study.

![University of Aberdeen]([https://pbs.twimg.com/profile_images/1572172791801061377/UPSWmPyN_400x400.jpg](https://i.imgur.com/PILyj4m.jpg))

![NERC-CDT](https://nerc-cdt-oil-and-gas.ac.uk/wp-content/uploads/news/2015-news-NERC-funding.jpg)

![NERC](https://auracdt.hull.ac.uk/wp-content/uploads/2019/11/UKRI_NER_Council-Logo_Horiz-RGB.png)

![CDT](https://i.imgur.com/QDOhcN3.png)

