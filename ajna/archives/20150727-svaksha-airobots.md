+ [1. AI ROBOTS](#1-ai-robots)
   + [Abstract](#abstract)
+ [2. HYPOTHESIS](#2-hypothesis)
+ [3. QUESTIONS](#3-questions)
+ [4. REFERENCES](#4-references)

----

# 1. AI ROBOTS

### Abstract

The algorithms<sup>{01}</sup> that control artificially intelligent robots rely on critical assumptions, viz. the availability of a complete geometric model, either two-dimensional or three-dimensional, of the object to be manipulated. The algorithm input is a polygonal/polyhedral-model for selecting optimal force-closure contact locations, which is the starting point for grasp analysis and dexterous manipulation methods that are then optimized for the desired properties in terms of dexterity, equilibrium, stability, dynamic behavior.

----

# 2. HYPOTHESIS

The BMI ‘decoder’<sup>{04} 2013, Willet etal</sup> converts neural activity into motor commands, by estimating and decoding the hand position of the subject. Other variables, say, joint torques and muscle activations are also tabulated. The visual observation paradigm uses the subject's neural visual activity data to predict the state of the arm being observed by the subject {2007, Tkach etal} and the user’s desired arm state (DAS) from a recent history of the user’s neural activity <sup>{04} 2013, Willet etal</sup>.

----

# 3. QUESTIONS

### 3.1. Is any data from the CP baby being collected? If yes, what kind of data - brain imaging data, robot/motor movements data, something else..?
+ BMI is seperate from baby work. There is an [EEG](https://en.wikipedia.org/wiki/Electroencephalography) head-net for CPC babies, which gives the electrical current flowing in brain and then make inference which brain area is active.
+ EEG generated data is very coarse level data, incredibly noisy. EEG data is hard to parse and analyze.
+ Neuro physiology maps individual neurons, and MRI imaging for fine scale mapping.

### 3.2. When the child moves what part of the brain activity data is collected? Is this collated with the arm/leg/body movements? How? 
+ In the biomed dept, they can distinguish individual finger movements in adults. An adult follows instructions and does not move if instructed. To train a BMI decoder you instruct "move left finger" and then learn the EEG pattern. With babies its more complicated - they dont follow instructions.
   * Babies are constantly in motion and crawling generates a lot of data. Head movements are a problem, head muscles data is noisy. 
   * Looking at higher level idea - when you are not engaed in a task in some areas the EEG is pulsing at 12Hz and when you turn to engage in a task the pulse vanishes and that is a marker for task engagement. 
   * We see same sort of an effect in children - a peak at 7Hz or so but if they are in a task the peak dissapears. A marker.
   * When the CP child (CPC) is on the robot we hope to use that to solve problems - ex. how to move a muscle to get the ball? 
        * For babies, we want to tell handedness (L. vs R. hand) or kicking (Left vs. Right foot).
   
### 3.3. Is there any link between the [frontal lobe](http://www.medicaldaily.com/battle-waterloo-might-not-have-happened-if-it-wasnt-neurosurgeon-jean-massot-how-345600) (funtioning, processing, etc..) and CP? What role does this play in motor skills?
+ With CP this is a deficit that occurs due to physical damage, and many are premature at birth and it affects the flow of signals to the musculator.
+ The cortex is intact which means the HW is there but there is a lot of development problems. Lack of message passing neuron signals inhibits continued growth. Connections are choosing parameters - how 2 neurons must pass messages and connect in early stage development.
+ A baby learning to crawl is reinforcement learning - they do motor babbling, random movements and we observe what happens. 
   + While crawling, they roll or scoot a bit. 
   + Their eyes see something, and the vestibular system is being activated and these are surprising events (SE).
   + SE are intereting and rewarding. This drives the child to repeat the movement. It helps generate data but each repetition does not generate the exact similar movement and neither is it always consistent. Eventually the baby learns to crawl. 
   + BUT, with CPC their muscle strenth is not good, so they dont get too much rewarding events and they learn to stop trying. 
        + CP kids wont crawl till the age of 2yrs and crawling is important for cognitive movement learning. 
        + Crawling is an important event and helps the child map the event and repeat cognitive patterns. 
        + This drives cognition and spatial representations. This deficit is throughout the childhood and continues into adulthood. 
        + The brain is intact but CP kids dont get the experience to drive cognitive development. 

### 3.4. Differences in CP babies development data?
+ Cortex diferences between CP kids is not available at this stage. 
+ The "Neurons connections" is being affected. 
+ The idea with the intervention robot is to encourage the CP baby to practice movement and give them self-developmet movement so that the cognition deficit reduces.
    
### 3.5. Is data from different kids collected for collative comparision ?
+ An occupational therapist (OT) has developed some measurement scoring process for each kid and that helps detect severity of disease.
+ The info is not directly used to develop the robot.
+ Only used to track if baby has risk of CP or not. 
+ The robot can use that data to provide this assistance.

#### Issues
    - The current issue is that inorder to keep the child interested and engaged, we give the child a certain amount of reward and help during the trial. 
    - The robot can carry the child and if they push the robot it will take them in that direction. CogPsych is that the agent doing the task knows there is an effect then it increases the learning.
    - The third assistance is a suit base assistance - kinematic suit with 12 sensors that allows collection of kinematic real-time data like crawling which is a mild action.
    - The idea that I've been pursuing is to count the number of times the child pushes the robot and that number should be in a range and when the child is not getting a reward (Sensitivity increases) and if above the range then child is getting too much reward (Sensitivity reduces). Adjust the sensitivity to stay with suit based assistance. 
    - Also look at dopamine levels when they reach the toy. When the full body moves forward that is the reward. 
    - For Sensitivity - have heuristic rules with Dr. Colabay, developed set of rules for each hand to study when the robot moves forward. 
    - The new study has a data-driven approach : looking at child actions with a classifier that looks at the data of limb movement and that helps decide if the robot should move forward. It has a threshold above (moves forward), below (does not move).
    - The probability threshold (PT) idea means the experimenter adjusts the setting. 
    - The youngest CPC does not move. Freaks out often.
    
### 3.6. What is the range of improvement over time for PT
+ We have have 16 weeks and are in the middle of data collection.
+ For all the robots - there is a clear point at 6 weeks the performance increases and at that stage they are getting idea from the CNS to muscles and they see the value of moving around. 
+ For CPC they see a similar increase in performance - gradual and not the same as normal child. 
+ Variation is a lot more but they dont measure the statistics. 
+ For CP children the event that caused the injury increases risk - especialy twins. You tend to have more premature babies. 

----

# 4. REFERENCES
+ {00} http://www-symbiotic.cs.ou.edu/publications/publications.html
+ {01} 2004, Antonio Moraleset al, [Vision-based three-finger grasp synthesis constrained by hand geometry](http://www.cs.ou.edu/~fagg/papers/2004/morales_grasp_synthesis_ver_1.pdf).
+ {02} 2009, Byron M. Yu, John P. Cunningham, etal., [Gaussian-process factor analysis for low-dimensional single-trial analysis of neural population activity](http://stat.columbia.edu/~cunningham/pdf/YuNIPS2009.pdf).
+ {03} 2010, Aaron J. Suminski etal., [Incorporating Feedback from Multiple Sensory Modalities Enhances Brain–Machine Interface Control](http://www.cs.ou.edu/~fagg/papers/2010/suminski-etal-2010.pdf).
+ {04} 2013, Francis R Willett, et al., [Improving brain–machine interface performance by decoding intended future movements](http://www.cs.ou.edu/~fagg/papers/2013/Willet-etal-2013-JNE.pdf), .
+ {05} 2013, Ashvin Shah et al, [A Dual Process Account of Coarticulation in Motor Skill Acquisition](http://www.cs.ou.edu/~fagg/papers/2013/ShahBartoFagg-JMotBehav-2013.pdf).
+ {06} 2015, Palmer, T. J., [Learning Action-State Representation Forests for Implicitly Relational Worlds](http://www-symbiotic.cs.ou.edu/papers/2015/Palmer_Thomas_Dissertation_2015.pdf)
+ {07} [Matlab work](http://www.cs.ou.edu/~fagg/summerschool/doc/).














