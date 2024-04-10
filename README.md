# landmark_based_slam_dataset

Most of the recent SLAM datasets directly start with many observations and many features to recognize in each observation. Yet, it all started with observing a few landmarks in a few observations.

A good example is the Gutmann dataset [1], which used an Aibo robot walking a trajectory between 5 points, observing 6 landmarks on the corner of a soccer field. This experiment was later the origin of the RoboCup 4-Legged league SLAM challenge in 2004 and 2005.
This dataset is a recreation of these experiments, but now with a Nao robot, on a much larger Standard Platform League soccer field.

## Gutmann dataset

The Gutmann dataset consisted of the following five points on a Soccer field of 3 x 2m: [(0,0), (50,0), (50,-50), (-100,50), (-100,0)] - all cm from the origin at the center of the field. The original dataset was not including the images, it consisted of a textfile containing the relative movement of the robot and the bearings to the observed landmarks.

 <img src="./setup/fieldSetup.png" alt="Gutmann field setup" width="300"/>

The position of the landmarks were specified in the 2003 rules of the 4 Legged league [2]: [(-220,-145), (0, -145), (220, -145), (-220, 145), (0, 145), (220, 145)] - all cm from the origin at the center of the field. The landmarks at   *y=+145cm* and *y=-145cm*  have respectively their pink band at the bottom and top. At *x=+220cm* and *y=-220cm* the bands are respectively  yellow and sky-blue, the distinctive band of the two landmarks at *x=+0cm* is specified as green in the 2003 rules (although a brighter green than the one used in this dataset).

This dataset was published at Radish: the Robotics Data Set Repository initiated by Andrew Howard and Nicholas Roy in 2003 [3], in concert with the OpenSLAM initiative [4] with allowed researchers to publish their SLAM algorithms (initiated by Cyrill Stachniss, Udo Frese, Giorgio Grisetti in 2006). The dataset is no longer available from Radish, but can still be downloaded from a MIT-server: [aibo-slcmp.tar.gz]{https://dspace.mit.edu/bitstream/handle/1721.1/62255/aibo-slcmp.tar.gz?sequence=2}.

Because in 2024 the Standard Platform league plays on a much bigger field, a new dataset is recorded from the original five points: [(0,0), (50,0), (50,-50), (-100,50), (-100,0)], but on a field of 9 x 6m, with the landmarks at locations [(-467.5,-317.5), (0, -317.5), (467.5, -317.5), (-467.5, 317.5), (0, 317.5), (467.5, 317.5)] - all cm from the origin at the center of the field. The landmarks are placed with their center 15cm from the lines marking the outside of the field. This setup makes it more difficult to recognize the 6 landmarks, because of the larger distance, which makes the landmarks smaller objects. 
This could be have been corrected by scaling up of the five points with the same amount as the field, but that was not done (yet), because the next part of the dataset (SLAM challenge of 2004 and 20050 already have a larger spread.

<img src=https://staff.science.uva.nl/a.visser/research/nao/2024/TechnicalFieldWithTags.jpg" alt="Gutmann setup at large field" width="300"/>

[1]  J.-S. Gutmann and D. Fox, “[An experimental comparison of localization methods continued](https://web.archive.org/web/20060105074037id_/http://www.informatik.uni-freiburg.de:80/~gutmann/papers/gutmann-fox-iros02.pdf)”, in Proceedings of the IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS’02), October 2002.

[2] RoboCup Technical Committee, "[Sony Four Legged Robot Football League Rule Book](https://spl.robocup.org/wp-content/uploads/downloads/Rules2003.pdf)", June 9, 2003.

[3] Steffen Gutmann, "[Data set used in localization experiments in the paper by Gutmann and Fox at IROS 2002](https://web.archive.org/web/20130201081843/http://cres.usc.edu:80/radishrepository/view-one.php?name=comparison_of_self-localization_methods_continued)", Radish, April 2006.

[4] Cyrill Stachniss, Udo Frese, Giorgio Grisetti, "[OpenSLAM](https://openslam-org.github.io/links.html), established in 2006.
