# Learning-Analytics-Final-Project
Code and dataset information for final project on preschool predictors of kindergarten word problem solving

# Introduction
Math knowledge at school entry is one of the strongest predictors of academic achievement (Classens et al., 2009) and low math knowledge at kindergarten entry and exit is associated with high rates of math disability by 5th grade (Morgan et al., 2009). Most studies of risk for math disabilities in very young children (e.g., pre-K and kindergarten) investigate number sense or numbers and operations as outcomes. However, beginning in the elementary grades, math word problems are prevalent on high stakes math testing (Driver & Powell, 2017). Given the importance of math word problem solving, little is known about early math word problem solving and what predicts it; this project examines preschool predictors for word problem solving in kindergarten.

The data used in this project is from a large-scale randomized control trial that followed over 500 students with very low math performance from the beginning of pre-K into kindergarten (original study described in Barnes et al., 2016). Measures of early math skills (e.g., genenal math skills, numeracy), language skills (phonological awareness and word reading) and cognition (e.g., attention, inhibition, visual spatial working memory) were collected at the beginning of pre-K, end of pre-K and end of kindergarten. Additionally, a measure of word problem solving was also collected for 493 students in kindergarten.

## Research Question
Given measures of math, language and cognition for pre-K students entering pre-K with very low math scores, how well can we predict whether the student will have low or high word problem solving scores in kindergarten?

# Variables of Interest
Three "types" of measures are available in the dataset - math-related, language-related and cognitive variables. Variables are named to reflect the construct/measure and time point (preK or K). More information on the measures can be found in Barnes et al. (2016; 2020).

## Math-related predictor
Test of Early Math Ability, 3rd edition (TEMA) is a standardized assessment of early math skills. This project uses the scaled TEMA score from the beginning of pre-K (math_preK).

## Language-related predictors
Phonological awareness was assessed in English or Spanish using the TOPEL or SPELA, respectively. Scaled scores for each student were transformed into z-scores for the entire sample at the beginning of pre-K (PA_preK).

Word reading was assessed in English or Spanish using the Letter Word ID subtest of the Woodcock Johnson III or the Identificación de letras y palabras from
the Batería III Woodcock-Muñoz, respectively. Scaled scores for each student are used in this project (LWID_preK).

## Cognitive predictors
The dataset includes measures of visual-spatial working memory (VSWM_preK), nonverbal IQ (iq_preK), Approximate number sense (ANS) acuity and attention all collected at the beginning of pre-K. 

VSWM was assessed using a task similar to a standard Corsi-Blocks task. VSWM_preK is a raw score, ranging from 0-8.

Nonverbal IQ was tested using the matrices subtest of the Kaufman Brief Intelligence Test, 2nd edition (KBIT-2). The KBIT-2 is a standardized assessment and iq_preK are scaled scores.

ANS acuity refers to an individual's ability to perceive and discriminate differences in quantity without counting. Research has shown that deficits in ANS acuity can help distinguish between students at-risk for math disability and those not at risk. Here, ANS acuity was measured using Panamath, a computerized task, with congruent (ANS_cong_preK) and incongruent (ANS_inco_preK) trials. Accuracy (proportion correct) on each type of trial is used for analyses. 

Attention is often used as an umbrella term for sustained attention, inhibitory control, and impulsivity. Tasks that measure attention usually tap into one of these constructs and can be either direct assessments (e.g., flanker task) or questionnaires filled out by teachers or caregivers (e.g., Child Behavior Questionnaire). The dataset contains three assessments of attention - Computerized flanker task (Child-ANT), computerized continuous performance task (CPT) and the teacher version of the Child Behavior Questionnaire (CBQ). 

Accuracy scores on congruent and incongruent trials of a computerized flanker task (Child-ANT), respectively, are measures of sustained attention and inhibition. Theoretically, ChANT_att_wv1 and ChANT_inhib_wv1 can range from 0-1.

Two types of errors are possible in a CPT - omission and comission errors. Omission errors occur when a participant misses a trial with a target stimulus, which indicates a loss in sustained attention (CPT_att_preK). Comission errors occur when a participant responds to a trial without a target stimulus, indicating a deficit in impulse or inhibitory control (CPT_inhib_preK). As expected, CPT scores are inversely proportional to a participant's sustained attention and inhibitory control skills. For this project, a raw score of number of omission and comission errors is used.

The Child Behavior Questionnaire (CBQ) has subscales for sustained attention (CBQ_att_preK), inhibitory control (CBQ_inhib_preK) and impulsivity (CBQ_impul_preK). Higher scores indicate better sustained attention and inhibitory control and greater impulsivity.

## Outcome of interest
The primary outcome of interest is math word problem solving (WPS). This was collected as an add-on subtest to the Child Math Assessment and is only available for the kindergarten time point. Students were asked 3 addition and 3 subtraction word problems and scored 1 if they answered correctly and 0 if incorrect, for a maximum score of 6. In this dataset, scores range from 0-6 but are not normally distributed. Consequently, logistic regression is used instead of linear regression.

# Analysis plan
First, a principal component analysis (PCA) will be conducted for dimensionality reduction. Then, a logistic regression will be used to answer the primary research question.
