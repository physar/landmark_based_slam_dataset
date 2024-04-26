# landmark_based_slam_dataset

Most of the recent SLAM datasets directly start with many observations and many features to recognize in each observation. Yet, it all started with observing a few landmarks in a few observations.

A good example is the Gutmann dataset [1], which used an Aibo robot walking a trajectory between 5 points, observing 6 landmarks on the corner of a soccer field. This experiment was later the origin of the RoboCup 4-Legged league SLAM challenge in 2004 and 2005.
This dataset is a recreation of these experiments, but now with a Nao robot, on a much larger Standard Platform League soccer field.

## RoboCup 2005 SLAM challenge

The locations of the  RoboCup 2005 SLAM challenge consisted of the following five points on a Soccer field of 6 x 4m: [(130,120), (220, -150), (-160,-120), (-210,90), (270,0)] - all cm from the origin at the center of the field. 

 <img src="./setup/SlamChallengeLocations2005.png" alt="RoboCup 2005 SLAM setup" width="500"/><br>
 <i>RoboCup 2005 SLAM challenge setup, Fig. 2 from [Technical Challenges for the RoboCup 2005 Legged League Competition](https://spl.robocup.org/wp-content/uploads/downloads/Challenges2005.pdf)</i>

## RoboCup 2004 SLAM challenge

The locations of the  RoboCup 2004 SLAM challenge consisted of the following five points on a Soccer field 4.5 x 3m: [(160,100), (180, -30), (50,-100), (-210,0), (-100,50)] - all cm from the origin at the center of the field. 

 <img src="./setup/SlamChallengeLocations2004.png" alt="RoboCup 2004 SLAM setup" width="500"/><br>
 <i>RoboCup 2004 SLAM challenge setup, Fig. 2 from [Technical Challenges for the RoboCup 2004 Legged League Competition](https://spl.robocup.org/wp-content/uploads/downloads/Challenges2004.pdf)</i>

## Gutmann dataset

The Gutmann dataset consisted of the following five points on a Soccer field of 3 x 2m: [(0,0), (50,0), (50,-50), (-100,50), (-100,0)] - all cm from the origin at the center of the field. The original dataset was not including the images, it consisted of a textfile containing the relative movement of the robot and the bearings to the observed Aibo landmarks.

 <img src="./setup/fieldSetup.png" alt="Gutmann field setup" width="300"/><br>
 <i> Gutmann dataset setup, Fig. 4 from [An experimental comparison of localization methods continued](https://web.archive.org/web/20060105074037id_/http://www.informatik.uni-freiburg.de:80/~gutmann/papers/gutmann-fox-iros02.pdf)</i>

The colors of the landmarks were specified in the 2003 rules of the 4 Legged league [2], yet Gutmann used a smaller field. The landmark locations were: [(-150,-100), (0, -100), (150, -100), (-150, 100), (0, 100), (150, 100)] - all cm from the origin at the center of the field. The landmarks at   *y=+145cm* and *y=-145cm*  have respectively their pink band (also refered to as the color 'magneta') at the bottom and top . At *x=+220cm* and *y=-220cm* the bands are respectively  yellow and sky-blue (also refered to as the color 'cyan'), the distinctive band of the two landmarks at *x=+0cm* is specified as green in the 2003 rules (although a brighter green than the one used in this dataset). The IDs of the landmarks were coded with the combination of the following numbers  0 -> green 1 -> magenta 2 -> yellow 3 -> blue.

This dataset was published at Radish: the Robotics Data Set Repository initiated by Andrew Howard and Nicholas Roy in 2003 [3], in concert with the OpenSLAM initiative [4] with allowed researchers to publish their SLAM algorithms (initiated by Cyrill Stachniss, Udo Frese, Giorgio Grisetti in 2006). The dataset is no longer available from Radish, but can still be downloaded from a MIT-server: [aibo-slcmp.tar.gz]{https://dspace.mit.edu/bitstream/handle/1721.1/62255/aibo-slcmp.tar.gz?sequence=2}.

Because in 2024 the Standard Platform league plays on a much bigger field [5], a new dataset is recorded from the original five points: [(0,0), (50,0), (50,-50), (-100,50), (-100,0)], but on a field of 9 x 6m, with the landmarks at locations [(-467.5,-317.5), (0, -317.5), (467.5, -317.5), (-467.5, 317.5), (0, 317.5), (467.5, 317.5)] - all cm from the origin at the center of the field. The landmarks are placed with their center 15cm from the lines marking the outside of the field. This setup makes it more difficult to recognize the 6 landmarks, because of the larger distance, which makes the landmarks smaller objects. 
This could be have been corrected by scaling up of the five points with the same amount as the field, but that was not done (yet), because the next part of the dataset (SLAM challenge of 2004 and 2005) already have a larger spread.

<img src="https://staff.science.uva.nl/a.visser/research/nao/2024/TechnicalFieldWithTags.jpg" alt="Gutmann setup at large field" width="600"/>

### Observations

In the Gutmann dataset it is important that the Aibo landmarks were observed. The distance was estimated by the size of the landmark in the image, the orientation by the distance from the center of the image scaled by the field of view of the robot. The field of view of the Nao robot is horizontally 60.97 deg [6].

#### Point 1 - (0,0)

<img src="https://staff.science.uva.nl/a.visser/research/nao/2024/first_recording/guttmann1b.png" alt="Gutmann point 1 - orientation 0" width="300"/> <br>
*Orientation 0 degrees, towards Yellow goal. Only the goal is visible, the penalty marker, the penalty L-intersections, a red dot from the 2004 challenge, and a NaoMark #107. No Aibo landmarks. In Gutmann's log this observation would be noted as "obs: 1 0.0 0.0 0.0 0*

#### Point 2 - (50,0)

<img src="https://staff.science.uva.nl/a.visser/research/nao/2024/first_recording/guttmann2b.png" alt="Gutmann point 2 - orientation 0" width="300"/> <br>
*Orientation 0 degrees, towards Yellow goal. Still the same clues as the goal, the penalty marker, the penalty L-intersections, the red dot from the 2004 challenge, , and NaoMark #107 are visible. No Aibo landmarks. In Gutmann's log this observation would be noted as "obs: 2 500.0 0.0 0.0 0**

<img src="https://staff.science.uva.nl/a.visser/research/nao/2024/first_recording/guttmann2b90.png" alt="Gutmann point 2 - orientation 0" width="300"/> <br>
*Same location, rotated 90 degrees to the side with the landmarks with the pink-band below. Orientation -90 degrees. The Y-intersection at the center line is blocked by a calibration board, another red dot from the 2004 challenge, and a NaoMark #85 is partly obscured by the Aibo landmark 'pink-green'. In Gutmann's log this observation would be noted as "obs: 3 500.0 0.0 -90.0 1 (1:0) (distance bearing)" - for this observation the ground truth is 3214mm and 8.95 deg or 0.156 rad. The landmark can be seen at pixel 190 of 320 wide image, which is equivalent with an angle of 5.75 deg. The difference could be a not perfect 90 degree rotation (can be checked with the angle of the field-boundery line - which is 11 pixels higher at the right, equivalent with an angle of 1.9 deg.).*

#### Point 3 - (50,-50)

<img src="https://staff.science.uva.nl/a.visser/research/nao/2024/first_recording/guttmann3b.png" alt="Gutmann point 2 - orientation 0" width="300"/> <br>
*Same orientation as previous observation. Orientation -90 degrees. The Y-intersection at the center line is still blocked by a calibration board,  NaoMark #85 is less obscured by the Aibo landmark 'pink-green', the red dot from the 2004 challenge is no longer visible. In Gutmann's log this observation would be noted as "obs: 4 500.0 -500.0 -90.0 1 (1:0) (distance bearing)" - for this observation the ground truth is 2721mm and 10.59 deg or 0.185 rad. The landmark can be seen at pixel 243 of 320 wide image, which is equivalent with an angle of 15.91 deg. Quite a large difference. The  90 degree rotation is now nearly perfect (can be checked with the angle of the field-boundery line - which is only slightly higher at the right).*

[1]  J.-S. Gutmann and D. Fox, “[An experimental comparison of localization methods continued](https://web.archive.org/web/20060105074037id_/http://www.informatik.uni-freiburg.de:80/~gutmann/papers/gutmann-fox-iros02.pdf)”, in Proceedings of the IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS’02), October 2002.

[2] RoboCup Technical Committee, "[Sony Four Legged Robot Football League Rule Book](https://spl.robocup.org/wp-content/uploads/downloads/Rules2003.pdf)", June 9, 2003.

[3] Steffen Gutmann, "[Data set used in localization experiments in the paper by Gutmann and Fox at IROS 2002](https://web.archive.org/web/20130201081843/http://cres.usc.edu:80/radishrepository/view-one.php?name=comparison_of_self-localization_methods_continued)", Radish, April 2006.

[4] Cyrill Stachniss, Udo Frese, Giorgio Grisetti, "[OpenSLAM](https://openslam-org.github.io/links.html), established in 2006.

[5] RoboCup Technical Committee, "[RoboCup Standard Platform League (NAO) Rule Book](https://spl.robocup.org/wp-content/uploads/SPL-Rules-2024.pdf)", March 20, 2024.
