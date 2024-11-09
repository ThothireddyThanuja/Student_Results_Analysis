# Student Results Analysis

This project analyzes a dataset of student scores and demographic information to explore the relationships between various demographic factors and academic performance.
The project involves data cleaning, processing, exploratory data analysis (EDA), and visualization to derive insights that could support educational decision-making.

# Table Contents

1. Objective
2. Features
3. Libraries Used
4. Data Processing
5. Exploratory Data Analysis (EDA)
6. Data Analysis & Visualization
7. Conclusion

# Objective

The primary objective of this project is to analyze the impact of demographic factors like gender, parental education, marital status, ethnicity, and study habits on student academic performance in subjects such as Math, Reading, and Writing.

# Features

Key columns in the dataset include:
  * Gender: The gender of the student (e.g., Male, Female).
  * EthnicGroup: The ethnic group the student belongs to (e.g., group A, B, C, D, E).
  * ParentEduc: The education level of the student's parents.
  * ParentMaritalStatus: The marital status of the student's parents.
  * WklyStudyHours: Weekly study hours reported by the student.
  * MathScore, ReadingScore, WritingScore: The student's scores in Math, Reading, and Writing.

# Libraries Used
  To run this project, the following Python libraries are required:

     * pandas: For data loading, manipulation, and summarization
     * numpy: For numerical operations
     * matplotlib and seaborn: For creating visualizations
     * datetime: For handling date data
     
# Data Processing
## Steps:

    * Data Loading: The dataset is loaded using Pandas.
    * Data Cleaning: Dropped unnecessary columns, e.g., Unnamed: 0.
                     Standardized the WklyStudyHours column to correct data formats.
    * Missing Values: Checked for and reported any missing values, although no imputation was needed for this dataset.

# Exploratory Data Analysis (EDA)

EDA was conducted to understand the dataset’s structure and explore the relationships between different variables.

  * Gender Distribution: A bar plot was used to visualize the number of male and female students in the dataset.
  * Parental Education and Student Scores: Grouped data by ParentEduc and calculated mean scores for Math, Reading, and Writing.
    Created a heatmap to visualize the relationship between parental education and student scores.
  * Parental Marital Status and Student Scores: Grouped data by ParentMaritalStatus and calculated mean scores.
    Created a heatmap to show the impact of parental marital status on student performance.
  * Ethnic Group Distribution: Visualized the distribution of ethnic groups using a pie chart and a count plot.

# Data Analysis & Visualization

## Code Examples

  ## Gender Distribution

      plt.figure(figsize=(5,5))
      ax = sns.countplot(data=df, x="Gender")
      ax.bar_label(ax.containers[0])
      plt.title("Gender Distribution")
      plt.show()
      
  ## Parental Education vs. Student Scores Heatmap

      gp = df.groupby('ParentEduc').agg({'MathScore': 'mean', 'ReadingScore': 'mean', 'WritingScore': 'mean'})
      sns.heatmap(gp, annot=True, cmap='coolwarm')
      plt.title("Relationship b/w Parent's Education and Student's Score", c="m")
      plt.show()
      
  ## Parental Marital Status vs. Student Scores Heatmap

      gp = df.groupby('ParentMaritalStatus').agg({'MathScore': 'mean', 'ReadingScore': 'mean', 'WritingScore': 'mean'})
      sns.heatmap(gp, annot=True, cmap="plasma")
      plt.title("Relationship b/w Parent's Marital Status and Student's Score", c="b")
      plt.show()

  ## Ethnic Group Distribution

      my_list = [GroupA["EthnicGroup"], GroupB["EthnicGroup"], GroupC["EthnicGroup"], GroupD["EthnicGroup"], GroupE["EthnicGroup"]]
      plt.pie(my_list, labels=l, autopct="%1.2f%%")
      plt.title("Distribution of Ethnic Groups")
      plt.show()
      
# Conclusion

  This project highlights how demographic factors influence student performance in key subjects. Some key takeaways include:

    * Gender Distribution: The gender ratio in the dataset provides context for comparing male and female student performance.
    * Parental Education Influence: Higher parental education levels generally correlate with higher student scores across subjects.
    * Marital Status Impact: Students’ scores are influenced by parental marital status, which might provide insights into additional support needs.
    * Ethnic Group Diversity: The ethnic diversity in the dataset allows for an understanding of performance trends across different groups.







