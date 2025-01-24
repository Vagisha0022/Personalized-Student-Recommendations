# **Personalized-Student-Recommendations**

## **Description**
This project is a Python-based solution designed to analyze quiz performance and provide personalized recommendations for students to improve their preparation. The system processes quiz metadata, user submission data, and historical performance data to identify weak areas, track improvement trends, and suggest actionable feedback. The insights are backed by detailed visualizations for better understanding.

---

## **Features**
Fetches data from multiple API endpoints (current quiz data, user submissions, historical data).
Identifies weak areas based on average topic accuracy.
Tracks improvement trends using rolling averages of accuracy over time.
Highlights performance gaps by comparing user performance with overall averages.
Generates actionable recommendations for weak topics, performance gaps, and general improvement strategies.
Provides visualizations to track trends and pinpoint gaps in performance


## **Setup Instructions**
-Python 3.7 or higher
-Libraries:
    1.pandas
    2.matplotlib
    3.requests


### **Installation Steps**
1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-repository/personalized-quiz-analysis.git
  cd personalized-quiz-analysis
   ```

2. **Install the required Python libraries:**
   If Poetry is not installed, you can install it using:
   ```bash
   pip install pandas matplotlib requests
   ```
  

3. **Run the main script:**
   ```bash
   python main.py
   ```

---



### **Project Approach**
**Step 1: Fetching Data**
-Data is fetched from three API endpoints:
1.Quiz Metadata: Details of quizzes, topics, and difficulty levels.
2.User Submissions: A user’s latest quiz performance.
3.Historical Data: Performance data from past quizzes
-Example of fetched JSON data:
   ```bash
  {
  "quiz": {
    "id": "quiz_001",
    "title": "Biology Basics",
    "topic": "Biology",
    "difficulty_level": "Medium",
    "questions_count": 10
  }
}
   ```
**Step 2: Parsing Data**
-Extracts and structures the fetched data into Pandas DataFrames:
-Quiz metadata: quizzes_df
-User submission details: submission_df, response_map_df
-Historical data for trends analysis: submissions_df
**Step 3: Analyzing Data**
-Weak Areas:
1.Topics with the lowest average accuracy are flagged.
2.Example: "Cell Biology" with an accuracy of 40%.

-Improvement Trends:
1.A rolling average (window size = 3) of accuracy is calculated to track long-term trends.
2.Example: A steady increase in accuracy indicates improvement.

-Performance Gaps:
1.Identifies quizzes where the user's performance is below the overall average accuracy.
2.Example: Quiz ID quiz_001 with 45% accuracy.

**Step 4: Generating Recommendations**
-Combines insights to provide:
-Suggestions for weak topics (e.g., "Focus on Cell Biology").
-Feedback on quizzes with performance gaps.
-General improvement tips like consistent practice and goal setting.
**Step 5: Visualizing Data**
-Improvement Trends: A line graph showing rolling accuracy over time.
-Performance Gaps: A bar chart comparing accuracy and scores for underperforming quizzes.



### **Key Visualizations**
**1. Improvement Trends**
A line graph that shows user accuracy and rolling accuracy over time, helping track long-term performance changes.
**2. Performance Gaps**
A bar chart highlighting quizzes where the user’s accuracy and scores are below average, pinpointing areas for review.


