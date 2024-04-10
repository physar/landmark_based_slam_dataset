# landmark_based_slam_dataset

Most of the recent SLAM datasets directly start with many observations and many features to recognize in each observation. Yet, it all started with observing a few landmarks in a few observations.

A good example is the Gutmann dataset [1], which used an Aibo robot walking a trajectory between 5 points, observing 6 landmarks on the corner of a soccer field. This experiment was later the origin of the RoboCup 4-Legged league SLAM challenge in 2004 and 2005.
This dataset is a recreation of these experiments, but now with a Nao robot, on a much larger Standard Platform League soccer field.

## Gutmann dataset

The Gutmann dataset consisted of the following five points on a Soccer field of 3 x 2m: [(0,0), (50,0), (50,-50), (-100,50), (-100,0)] - all cm from the origin at the center of the field. The original dataset was not including the images, it consisted of a textfile containing the relative movement of the robot and the bearings to the observed landmarks.

 <img src="./setup/fieldSetup.png" alt="Gutmann field setup" width="300"/>

The position of the landmarks were specified in the 2003 rules of the 4 Legged league [2]: [(-220,-145), (0, -145), (220, -145), (-220, 145), (0, 145), (220, 145)] - all cm from the origin at the center of the field. The landmarks at   *y=+145cm* and *y=-145cm*  have respectively their pink band at the bottom and top. At *x=+220cm* and *y=-220cm* the bands are respectively sky-blue and yellow, the distinctive band of the two landmarks at *x=+0cm* is specified as green in the 2003 rules (although a brighter green than the one used in this dataset).

[1]  J.-S. Gutmann and D. Fox, “[An experimental comparison of localization methods continued](https://web.archive.org/web/20060105074037id_/http://www.informatik.uni-freiburg.de:80/~gutmann/papers/gutmann-fox-iros02.pdf)”, in Proceedings of the IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS’02), October 2002.
[2] RoboCup Technical Committee, "[Sony Four Legged Robot Football League Rule Book](https://spl.robocup.org/wp-content/uploads/downloads/Rules2003.pdf)", June 9, 2003.
