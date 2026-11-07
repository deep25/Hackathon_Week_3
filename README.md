# Hackathon_Week_3

**Childhood heart tracker**

A tracker that follows a child's daily activity, resting heart rate, breathing and symptoms over time, and flags when the last 7 days stop matching that child's usual pattern. Built for the hackathon's tracker topic (topic 2), adapted to children's heart health.
**Why I built this**

I want to start with why i went with this project, a healthcare project. Few months ago my father had a heart surgery due to a damaged valve. Upon many tests, they found out it was since childhood he had this issue. Many symptoms over the year were missed. Had those symptoms were recognized earlier, illness would have been treated sooner and recovery would be much easier.That is why I built a tracker that follows everyday signs in children and flags changes that are worth asking a pediatrician about. The symptom information comes from Mayo Clinic, CDC, NHLBI and NHS pages, and the real data comes from CirCor DigiScope, UCI Heart Disease and WHO estimates.

Important : I want to emphasize that certain data was simulated like symptoms, daily child data. It is based on random data that has been simulated. 

**What the project does**

Analyses real pediatric murmur data to see how murmur relates to age and BMI.
Uses those real numbers to simulate 300 children with 30 days of daily logs and symptoms.
Tracks each child against their own usual pattern and flags changes in the last 7 days.
Lets you pick any child and see their trends, symptom days and flag message.
Adds context with WHO death rates for rheumatic heart disease, which damages heart valves.

**How the project works**

I grouped the children in different groups to make the calculation and finding more compact.
First, I calculated the murmur rate, BMI to check relation between murmur rate and a child's BMI.
I also, calculated, the mean, p-value, t-test. As noticed, children with lower BMI had a murmur. And the difference is significant as per the p-value.
I also included an adult data but didn;t really used it in children data. 

**Symptoms Data**
Symptoms data came from NHLBI, Mayo Clinic, CDC and NHS. The daily changes are my assumptions and based on to analyze data more effectively. I researched on common symptoms linked to it, but only included 4 for the base of this project.
I built a symptom table (fast breathing, tires easily, short of breath in activity, poor weight gain) with the age groups each applies to and a chance of each symptom per day. 

Worse weeks. So the tracker has something to catch, 40% of murmur-flagged children get a worse final week: less activity, a higher heart rate and more symptom days.

The ChildTracker class holds one child's logs, adds a new day and checks for flags (see the rules below).

  A dropdown shows any child's trends and message, and a second dropdown compares rheumatic heart disease death rates across countries.

  Each child is compared with their own earlier days. The last 7 days are the recent window and every earlier day is the child's usual level. A flag appears when any of these is true:

average active minutes in the last 7 days are below 80% of the usual level,
average resting heart rate is above 110% of the usual level, or
a symptom appears on 4 or more of the last 7 days.

These thresholds are my design choices, not medical rules.

Results from the simulation

In the simulated data, murmur-flagged children had lower activity and a higher resting heart rate.

These patterns were built into the simulation, so the tests show that the tracker can detect them. They are not medical findings.

Hackathon requirements covered
Simulated user profiles and logs (NumPy and Pandas)
Cleaning and exploration of real and simulated data
SciPy tests: ttest_ind, mannwhitneyu, chi2_contingency, f_oneway
Functions and a class (user_profile, ChildTracker)
Matplotlib and Seaborn charts, plus interactive dropdowns
A tracker that records new days and flags changes over time
Limitations
The children, daily logs, symptoms and worse weeks are simulated, and the size of the gaps between murmur-flagged and other children is my assumption.
The tracker's thresholds are design choices, so some false alarms and misses are expected.
Poor weight gain is simulated as a daily yes or no, though in real life it is a slow trend.
CirCor is a screening study of children in one region, and some age groups (like Neonate) have very few children.
WHO death rates are not about when a condition is diagnosed. They give context, not proof.
UCI Heart Disease is adult data from a different study, so it is a side analysis and is not mixed with the children's data.
How to run
Put these files in a Google Drive folder named hackathon: training_data.csv (CirCor), processed.cleveland.data (UCI) and the WHO death-rate CSV.
Open the notebook in Google Colab.
Choose Runtime, then Run all. Allow Drive access when asked.
Files
Hackathon_Week_3.ipynb: the full notebook (analysis, simulation, tracker and charts)
README.md: this file
Sources
CirCor DigiScope Phonocardiogram Dataset, PhysioNet: https://physionet.org/content/circor-heart-sound/
UCI Heart Disease: https://archive.ics.uci.edu/dataset/45/heart-disease
Our World in Data, rheumatic heart disease death rate (WHO Global Health Estimates): https://ourworldindata.org/grapher/death-rate-from-rheumatic-heart-disease-who-ghe-age-standardized
NHLBI, congenital heart defects symptoms: https://www.nhlbi.nih.gov/health/congenital-heart-defects/symptoms
Mayo Clinic, congenital heart defects in children: https://www.mayoclinic.org/diseases-conditions/congenital-heart-defects-children/symptoms-causes/syc-20350074
CDC, congenital heart defects: https://www.cdc.gov/heart-defects/about/index.html
NHS, congenital heart disease: https://www.nhs.uk/conditions/congenital-heart-disease/
Disclaimer

This is an educational project. It does not diagnose any condition and is not medical advice. If a child has blue lips, fainting or trouble breathing, get urgent medical care.


**Important to note**

This is the file where i started working first and built the intial project and code. Later on I organized my code with the help of AI. Also, with my code, I built an interactive HTML file(it's sitting in a 2nd branch). I also, did some research on medical sysmptoms, conditions. What to analyze and how to read it. However, due to time limitation, I used some data from google research and AI to analyze and built a tracker.

