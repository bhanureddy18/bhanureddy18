<html><head>
    <!-- Page setup -->
    <meta charset="utf-8">
    <title>Person Detection for Social Distancing using Computer Vision </title>
    <meta name="description" content="Computer Vision with Animals">
    <meta name="author" content="project1 csueb">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
  
    <!-- Stylesheets -->
    <!-- Reset default styles and add support for google fonts -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css" rel="stylesheet" type="text/css">
    <link href="http://fonts.googleapis.com/css?family=Roboto" rel="stylesheet" type="text/css">
   
    <!-- Custom styles -->
    <link href="style.css" rel="stylesheet" type="text/css">

    <!-- jQuery -->
    <script src="https://code.jquery.com/jquery-3.4.1.min.js" integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo=" crossorigin="anonymous"></script>    

    <!-- Want to add Bootstrap? -->
    <!-- Visit: https://getbootstrap.com/docs/4.3/getting-started/introduction/ -->
    
  </head>
  
  <body>

    <header id="header">
      <h1>Computer Vision and Animals</h1>
      
      <!-- Menu link fragment #id should match a div id. Example: <a href="#home"> links to <div id="home"></div>  -->
      <ul class="main-menu">
        
        <li><a href="#home" class="">Home</a></li>
        <li><a href="#architecture" class="">Architecture</a></li>
        <li><a href="#methodology" class="active">Methodology</a></li>
        <li><a href="#conclusion and future scope" class="">Conclusion and Future Scope</a></li>
        <li><a href="#result" class="">Result</a></li>
        <li><a href="#quiz" class="">Quiz</a></li>
      </ul>                 
    </header>
	background-image: url('https://scx1.b-cdn.net/csz/news/800/2017/theoreticala.jpg');
    color: #FFFFFF;
   
    <div id="container">
      <div class="inner">
        <div id="content"> 
          
          <div id="home" class="content-region hide" style="display: none;">
            <h2>Introduction</h2>
            <p>
              Coronavirus is a large family virus that harms humans and animals. Covid-19 is known as a family member of coronavirus, first spread to Wuhan, China in December 2019. The outbreak then rapidly affected many countries in the world and had been declared as a pandemic by the World Health Organization (WHO). Based on the information from WHO, the coronavirus is spreading from a person to a person via small droplets from the nose and mouth. In other words, social distancing is the best practice where people can minimize physical contact with possible coronavirus carriers, by keeping the distance at least one meter away from each other.
The project “Person Detection for Social Distancing” is proposed to support the actions on Covid-19 spread mitigation. It provides a solution for detecting people gathering in public places such as banks, shopping malls, clinics etc. The concept of person detection algorithm is used to accurately detect a person’s presence in areas of interest and is then followed by measuring the distance between the detected persons.
</p>
<h2>Existing System</h2>
  <p>Since the novel coronavirus pandemic began, many countries have been taking the help of technology based solutions in different capacities to contain the outbreak. Many developed countries, including India and South Korea, for instance, utilizing GPS to track the movements of the suspected or infected persons to monitor any possibility of their exposure among healthy people. In India, the government is using Arogya Setu app, which works with the help of GPS and Bluetooth to locate the presence of Covid-19 patients in vicinity area. It also helps others to keep safe distance from the infected person.
On the other hand, some law enforcement departments have been using drones and other surveillance cameras to detect mass gatherings of people, and taking regulatory actions to disperse the crowd. Human detection using visual surveillance system is an established area of research which is relying upon manual methods of identifying unusual activities. However, it has limited capabilities.
 
   </p><h2>Problems in existing system</h2><p>
•	Time Consuming
•	Brings a unique set of threats to the public and is challenging to the workforce
</p> 
 <h2>Proposed System</h2>
  <p>
  In the proposed system, a deep learning based framework is proposed that utilizes object detection and tracking models to aid in the social distancing remedy for dealing with the escalation of Covid-19 cases. In order to maintain the balance of speed and accuracy, SSD (Single Shot Detector) algorithm is utilized as object detection and tracking approaches while surrounding each detected object with the bounding boxes.
Later, these bounding boxes are utilized to compute the pair wise L2 norm with computationally efficient vectorized representation for identifying the clusters of people not obeying the order of social distancing.
</p><h2>	Benefits of Proposed System</h2>
<p>
•	Reduces the transmission of viruses by following a non-pharmaceutical way
•	Time saving
•	User friendly</p>
 
</div>
          
          <div id="architecture" class="content-region hide" style="display: none;">
            <h2>Software Architecture</h2>
            <p>
              Software architecture exposes the structure of a system while hiding the implementation details. Architecture also focuses on how the elements and components within a system interact with one other. Software design delves deeper into the implementation details of the system</p>
			<p>
              <img src="Software Architecture.png" alt="lidar img1" width="750" height="1200">    
            </p>
            
            
			<h2>Technical Architecture</h2>
              <p>
			  The technical architecture of the platform is modelled following the well-known and field tested three-tier architecture. This model proposes logical and physical separation of concerns (data access, business logic and presentation) in layers, with an
 emphasis on maintainability and decoupling of components. The separation in layers (logical separation) and/or tiers (physical separation) allows for separate evolution, or even replacement, of the different components of the system, with changes in one layer not compromising other layers.
Front end provides the visibility of application to the user and whereas middle ware provides the linkage between back end and front end and back end stores the data for the application.

			  </p>
            <p>
              <img src="Technical Architecture.png" alt="lidar img1" width="750" height="1200">    
            </p>
          
            <p>
            </p>
			<div id="methodology" class="tabcontent">
  <h2>Trained Model</h2>
  <p>In order to have a robust detector, a set of rich training datasets are required. This should include people with a variety in gender and age with millions of accurate annotation and labelling. We selected SSD_MobileNet model trained with two large datasets of MS COCO(Common Objects in Context) and Pascal VOC dataset.
</p>

<h2>People Detection
</h2>
<p>
The SSD_MobileNet model is able to detect humans (people) with various types of challenges such as variations in clothes, postures, at far and close distances, with or without occlusion, and under different lighting conditions.

</p>
<h2>Inter-distance Estimation
</h2>
<p>
After detection, the bounding box information, mainly centroid information is used to compute each bounding box centroid distance. Euclidean distance can be used to calculate the distance between each detected bounding box of peoples.
Following computing centroid distance, a predefined threshold is used to check either the distance among any two bounding box centroids is less than the configured number of pixels or not. 
If two people are close to each other and the distance value violates the minimum social distance threshold then the bounding box information is stored in a violation set and the color of the bounding box is updated or changed to red.
</p>
<img src="Model.png" alt="lidar img1" width="750" height="1200">    
            

</div>

          <div id="Conclusion and Future Scope" class="tabcontent">
  <h2>Conclusion</h2>
  <p>
  Social distancing is one of the important precautions in reducing physical contact that may lead to the spread of coronavirus. Consequences of non-compliance with these guidelines will be causing the higher rates of virus transmission. The proposed project has an efficient real-time deep learning based framework to automate the process of monitoring the social distancing via object detection, where each individual is identified in the real-time with the help of bounding boxes.
Thus, this project can reduce the on ground efforts of the police and they can entirely focus on supervising conditions exclusively on those areas where conditions are unfavorable and thus, they can utilize time wisely and save energy for equitable situations.
</p>
  
  <h2>Future Scope</h2>
<p>
A single viewpoint obtained from a single camera cannot reflect the result more effectively. Therefore, the proposed application may be set for different views through many cameras in the future to get more accurate results.
 

</p>
</div>

          
          <div id="result" class="content-region hide" style="display: none;">
            
            <p>
              <img src="output1.png" alt="r1 img1">
			  <img src="ip1.png" alt="r1 img1">
            <img src="op1.png" alt="r1 img1">
            
            </p>
            
                  
          </div>
          
          <div id="quiz" class="content-region hide" style="display: none;">
            <h2>Quiz</h2>
            <p>
              According to studies, how many road kills happen per day in Canada? 
            </p>
            <p>
              a.	1-4 <br>
              b.	4-8 <br>
              c.	8-12 <br>
              d.	12-16 <br>
            </p>
            
            <p>
              What are the main advantages of choosing LiDAR as a sensor
            </p>
            <p>
              a.	LiDAR has strong Signal to Noise ratio under various temperatures <br>
              b.	LiDAR has adjustable lens <br>
              c.	LiDAR can see through shadows, sunlight, or headlights <br>
              d.	LiDAR can analyze images for road sign <br>
            </p>
            
            <p>
              Both LiDAR and camera can apply AI algorithms and neural networks to collected data (True or False) 
            </p>
            <p>
              a.	True <br>
              b.	False
            </p>
            
            <p>
              What are the orderings in size for multiple layers to pass through kernels?
            </p>
            <p>
              a.	1x1, 3x3, 1x1 <br>
              b.	3x3, 1x1, 1x1 <br>
              c.	1x1, 1x1, 3x3 <br>
              d.	3x3, 1x1, 3x3 <br>
            </p>
            
            <p>
              What is generated by having each feature map passing through the 3x3 convolution layer?
            </p>
            <p>
              a.	RPN <br>
              b.	RoIAlign Layer <br>
              c.	Pyramid feature map <br>
              d.	ReLU activation unit <br>
            </p>
            
            <p>
              How to avoid jittering and unstable lane detection?
            </p>
            <p>
              a.	Apply edge detection and capture region of interest <br>
              b.	Create detected line across two sides of the lane <br>
              c.	Use bounding box to determine whether the lanes are consistence <br>
              d.	Calculate a moving average to smooth out the lane detection <br>
            </p>
            
            <p>
              If the vehicle is driving on a lane that is inclining towards the horizon of the road and hence has a gradient, the predicted line won’t be affected for measuring predicted feedback. (True or False)
            </p>
            <p>
              a.	True <br>
              b.	False <br>
            </p>
            
            <p>
              What are the two parameters used in the tutorial to analyze results from Mask R-CNN output? (Multiple Choice)
            </p>
            <p>
              a.	Recalls <br>
              b.	Processing Speed <br>
              c.	Performance <br>
              d.	Predictions <br>
            </p>
            
          
          </div>
            
        </div>
      </div>
    </div>

    <footer>
      <h4> IEEE Citation </h4>
      <p>
      Web References Research paper
	https://ieeexplore.ieee.org/document/9204934 </p>
	<p>
Social distancing
	https://www.pyimagesearch.com/2020/06/01/opencv-social-distancing- detector/
	</p>
	<p>
Object detection
	https://www.activestate.com/blog/how-to-monitor-social-distancing-using- python-and-object-detection
</p>
    </footer>
    
    <!-- Load additional JS scripts here -->
    <script type="text/javascript" src="script.js"></script>
    
  

</body></html>
