#MOTIVATION ANALYSIS OF PARTICIPANTS IN CROWDSOURCING NASA CHALLENGES


![image](https://user-images.githubusercontent.com/80006583/158819878-3706cfd9-72f5-473d-bf94-49df52ab8205.png)

#Project : MOTIVATION ANALYSIS OF PARTICIPANTS IN CROWDSOURCING NASA CHALLENGES

Abstract—The purpose of the study focused on determining types of participants’ motivation in crowdsourcing challenges and the relationship between intrinsic vs. extrinsic motivation within the level of participants’ engagement. Astrobee Challenge Series dataset from NASA contains challenge names, years of experiences, participants’ backgrounds, and a text field that supported research to analyze the reason for participating and extract differences in motivations. To conclude whether years of experience indicate the type of motivation and motivation indicate the level of participation of solvers, this group project did some analysis on text mining and research design to measure the data. More specifically, we use Quasi-experimental Design, Stratified Sampling, Term Frequency (TF-IDF), N-grams, Principal Component Analysis (PCA), and Generic Machine Learning Model (GML) in our pilot analysis. We found that years of experience in Design and Mechanical Engineering are significant explanatory variables determining intrinsic motivation. However, the limitation of making a concrete conclusion to this research paper is the lack of self-reported hour data; it became difficult to evaluate based on all the information we have in the cleaned dataset. As a result, the research paper had passed the basic process to enter the further complicated analysis in the future.
Keywords—Crowd, design, intrinsic motivation, extrinsic motivation, NASA.

I.	INTRODUCTION
Astrobee Challenge Series was organized by NASA in May 2018. This contest contains 16 robotics challenges, which encouraged participants who have talents in designing or interests in trying new things. NASA also looked for the best design and excellent solutions to assist astronauts on the International Space Station (ISS). Prizes are awarded to the winner of each challenge depending on its difficulty level. For example, the winner of SRA (Autonomous deployment, attachment, and positioning systems) received $5,000 as a reward. However, EBD (Electronics box design) offered a $250 bonus. 
In this paper, based on the Merged_Master_Survey data collected in Szajnfarber et al., [1], we decided to analyze the type of participants’ motivations in the Astrobee Challenge. The most important reason we chose to work on this project is that we want to know what motivates freelancers to participate in the NASA crowdsourcing challenges? In other words, we tried to demonstrate how the relationship among types of motivation, years of experience, and level of participation link together. The data collected was demographic survey, education, reasons to register, problem chosen by the solver, solution submitted, and performance in competition. There are ten fields of background that participants could choose to tell us about their career backgrounds, for instance, Electrical Engineering (EE), Design (D), Material Science (MatS), or Robotics (Rob), etc. According to the dataset, the level of participation was based on seven criteria: “Downloaded”, “Discarded”, “Incomplete”, “Conceptually_Complete”, “Mixed_Detail”, “Detailed”, and “Winner”. Therefore, the data of the level of participants indicated the quality of result in terms of making good progress. People could download the file, but they could not complete the challenge. Or, if they did more than the “Downloaded” stage, you will see “TRUE” in other levels of the participation column. 
Working on this project helps us understand whether the motivation for participating in the program is voluntary, passionate, or from other purposes such as prize and recognition. In addition, the other question that we would like to answer after inquiring about the dataset. Does discipline background and years of experience affect the participants’ performances. People who have more experience in Robotics would present better solutions. Those are all hypothesis questions that we tried to assume before the analysis. 
We used Quasi-experimental Design and Stratified Sampling for our research design to measure types of motivation from raw text and the level of participation. The reason for using those methods is because they represented different categories of challenges, avoided unbalance in categorical variables, and had a better representation of the population. We also included Term Frequency (TF-IDF) to obtain the importance of a word (“keyword”) in documents. Along with TF-IDF, we created Bigrams to find the relevant phrase that is repeated. We applied Kohen’s kappa statistic to measure the inter-rater reliability until we got the statistic result more than 0.7.
We applied Principal Component Analysis (PCA) in our pilot analysis to get a dimensional reduction on years of experience. We could reduce the large dataset yet contain the most information from the origin. Finally, we demonstrated the Generic Machine Learning Model (GML) result. The purpose of presenting GML at the end is to see the interrelationships between variables. The failure of using K-mean Clustering gave us an idea of how challenging to measure the motivation depending on two groups (experienced and inexperienced). We will take an in-depth analysis in the methodology section to be able to give the most accurate answer to two of our main project questions:
1)	What types of motivation are activated by the NASA crowdsourcing challenge?
o	Do years of experience indicate the type of motivation?
2)	Does motivation is indicative of the level of participation of solvers?

II.	LITERATURE REVIEW

“How intrinsic motivation and extrinsic incentives affect task effort in crowdsourcing contests: A mediated moderation model” [2]
The article emphasized the importance of extrinsic and intrinsic motivation for task accomplishment in crowdsourcing contests. It defined intrinsic motivation as the enjoyment of learning new things and gaining new skills. While extrinsic motivations are known as external incentives, which possibly provide participants monetary rewards or work opportunities. 
According to hypothesis 2.4 – “Intrinsic motivation is positively associated with engagement in crowdsourcing contests”, the authors indicated that people were more likely to focus most of their efforts on the contest without the external incentives. However, the effect of intrinsic motivation on task effort will lower when external elements appear. It is obvious to explain since the dilatation of external stimuli reduces task effort [2]. Another finding from the article is that engagement is a novel aspect, as a mediator for intrinsic and extrinsic motivation on task effort. They strongly agree that after adding the mediating role of attention, intrinsic and extrinsic motivation presented a negative interaction.  The last theory, which was admitted to contributing a significant effect to the task effort, is external rewards such as monetary. It also brought a result in an increase in participants’ challenge effort. 
We found that the papers related to our subject analysis supported our project by clearly distinguishing between internal and external motivation. This helped our project list keywords while categorizing each text data. Also, there is a strong relationship between two factors and the participants’ engagement.

III.	METHODS
A.	Data Collection:
In May 2018, NASA launched a series of 17 prize competitions to design a robotic system. The
The competition was launched on the Freelance.com community, and a registration survey was given to participants interested in registering. The survey consisted of basic demographic information, educational background, years of experience in different disciplines, and an open question regarding what motivated them to participate. Appendix A
Summarize the different challenges in the competition. Although 9000 initial participants showed interest to register
In the competition, 255 submitted a proposal design [1].

B.	Data Cleaning:
Before stepping in to do the analysis, our data needed to be clean first. Clearing all null values and cleaning raw text were necessary for building or fitting models. The primary motivation text (WhyReg) contains, in some cases, symbols, grammatical errors, and special characters. We used Natural Language Processing (NLP) for tokenization, parsing, classification, stemming and created word cloud to overview the text dataset, “Fig 1”. Machine learning systems must understand human language and get easier on analyzing after being cleaned 

 
Fig 1. Motivation text word cloud

The word cloud shows clearly that the word “NASA”, “want”, “contest”, “interested”, “challenge”, “robotics”, “space”, “design”, and “work” were the main point of the text data. It also appeared frequently. 
C.	Exploratory Data Analysis and Data Visualization
The distribution of the years of experience in the different disciplines helped us to identify that in average, participants have less than 1 year of experience. However, important outliers are detected, representing years of experience greater than 10 years.



 
Fig. 2. Distribution Years of Experience 
D.	Measures: 
      Each participant responded, in most of the cases, to why they registered in the competition. A preliminary review of the text motivation showed two different types: intrinsic and extrinsic motivation. Thus, this project proposed an observational study that measures the different types of motivation in the text data. 
We stratified sampled 320 participants and annotated the type of motivation by identifying keywords indicative of the type of motivation. Besides, we identified subcategories of each type of motivation. Table 1 shows a summary of keywords, categories, and subcategories found in the sample text. 

TABLE I. MOTIVATION CATEGORIES AND KEYWORDS

Intrinsic Motivation Sub-categories	Keywords
Attraction	“love”, “NASA”, “space”, “design”
Challenge	“contest”, “challenge”
Skills	“capability”, “skills”
Novelty	“new”, “new things”

Extrinsic Motivation Sub-Categories	Keywords
Monetary	“love”, “NASA”, “space”,“design”
Career	“contest”, “job”
Recognition	“capability”, “skills”

       Additionally, a second measure was proposed in this project. The level of participation was measured by creating a scale of the variables that described completeness in [1]. Zero indicates that participants only filled the survey, while Six indicates participants won the competition. Appendix B summarizes the definitions of [1] and how we adapted to this project. “Fig 2” shows the number of participants in the different scales.

 
Fig. 2. Levels of Participation Scale 
E.	Measurement Validation:
Kohen’s Kappa is used to evaluate the reliability of motivation measurement. The reliability of the motivation type construct ranges from 0.89 and 0.91 for intrinsic and extrinsic motivation respectively. The reliability scores were above the recommended threshold value of 0.70 [3] suggesting a high level of reliability. 

F.	Research design
A quasi-experimental research design is proposed for this project. Although randomized samples are not representative due to class unbalance in the challenge variable, stratified sampling is suggested. 320 samples were collected consisting of 20 participants for each of the 16 challenges. Data were annotated by 2 raters, and keywords were identified. Annotations were scaled-up to the entire 9,000 participants by matching keywords that relate to intrinsic and extrinsic motivation. Finally, it was proposed to evaluate causal relationships of motivation type and level of participation with the years of experience of the different disciplines, and the motivation type respectively. “Fig 3” shows the histogram of type of challenges, and “Fig 4” shows the result of measuring motivation.

 
Fig 3. Bar plot of the Challenges and number of participants


 
Fig. 4. Keywords and bigrams that expressed motivation type
IV.	PRELIMINARY RESULTS
We used Generalized Linear Models to test the hypotheses and define two models. In the first step, years of experience variables were transformed with log(x+1) to correct skewness. Next, as a second step, dimensionality was reduced using Principal Components Analysis (PCA). PCA loads were obtained and are presented in Table 2. Finally, two Logit GLM models were regressed.  

TABLE II.	Principal Components Loads
	PC1	PC2	PC3
Electrical Engineering	0.24	0.17	0.13
Engineering Drawing	0.54	-0.15	0.11
Design	0.63	-0.24	-0.53
Industrial Engineering	0.30	-0.021	0.15
Manufacturing	0.41	-0.086	0.18
Material Science	0.18	-0.004	0.07
Mechanical Engineering	0.43	-0.159	0.24
Project Management	0.38	0.16	0.02
Robotics	0.25	0.11	0.13
Computer Science	0.27	0.78	-0.12
Others	0.04	0.01	-0.03


Binary classification models were regressed to find the significance of the years of experience as explanatory variables of types of motivation. Results obtained indicate that the type of the challenge, years of experience in Design, and Mechanical Engineering are significant explanatory variables (p<0.05). 
On the other hand, the second model regressed tested the significance of the motor type and years of experience to explain the level of participation. Results obtained showed that Intrinsic Motivation, Manufacturing, and Mechanical Engineering are significant to explain the level of participation in the different challenges.
V. DISCUSSION AND CONCLUSIONS

       The preliminary analysis results showed valuable information that we can obtain from this dataset. Although a better method to annotate the entire dataset is needed, we could obtain evidence of the explanatory variables that can be used to determine the intrinsic motivation and level of participation in this project. 
Results showed that the years of experience in Design and Mechanical Engineering are significant explanatory variables that determine Intrinsic Motivation. Multiple models are suggested as the next step for this project because annotated data contains information of Intrinsic and Extrinsic subcategories, and more different disciplines could be significant in different intrinsic or extrinsic subcategories.
Moreover, intrinsic motivation and years of experience in Mechanical Engineering, Manufacturing, and the type of challenge could be an indicative of the level of participation suggested by results of the second regression model. Results are shown in APPENDIX C. 
Future work in this project includes to refine annotations and mechanism of scaling annotations up. Suggestions could be using machine learning to annotate the dataset. Moreover, future work includes the classification models for the different subcategories on each of the motivations. 
	
REFERENCES

[1] Szajnfarber, Zoe, Lihui Zhang, Suparna Mukherjee, Jason Crusan, Anthony Hennig, and Ademir Vrolijk. “Who Is in the Crowd? Characterizing the Capabilities of Prize Competition Competitors.” IEEE transactions on engineering management (2020): 1–15.
[2] Liang, Huigang, Meng-Meng Wang, Jian-Jun Wang, and Yajiong Xue. “How Intrinsic Motivation and Extrinsic Incentives Affect Task Effort in Crowdsourcing Contests: A Mediated Moderation Model.” Computers in human behavior 81 (2018): 168–176. 
[3] Nunnally, 1978 J. Nunnally. Psychometric theory (2nd ed), McGraw-Hill, New York (1978).








 
APPENDIX A
 
APPENDIX B
Level	Definition	Scale
Winner	The design is detailed and was selected as the winning solution	6
Detailed	Design of the entire system has been specified	5
Mixed	Detailed completed, but some aspects remain at the conceptual level	4
Conceptual Complete	The conceptual design is complete. It could become a detailed design	3
Incomplete	Solution has design content, but it is not responsive to the problem as posed	2
Did not submit/discarded	Downloaded the problem, showing some interest, but did not submit any design content	1
Did not downloaded	Complete registration, but never downloaded any challenge	0












APPENDIX C
 

 
![image](https://user-images.githubusercontent.com/80006583/158651592-d85c94d3-2493-48a1-9c3f-157fc2007b20.png)
