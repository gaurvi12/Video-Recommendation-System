# 🎥Video Recommendation System  

## 🎯Overview  
This project implements a **Video Recommendation System** using a blend of **content-based filtering**, **collaborative filtering**, and a **hybrid approach**. The system aims to recommend videos to users by analyzing their viewing, liking, and rating history. Evaluation metrics such as **Mean Absolute Error (MAE)** and **Root Mean Square Error (RMSE)** are used to measure the accuracy of recommendations.

---

## Features  
- **Content-Based Filtering**: Recommends videos based on user-provided ratings and a defined threshold.
- **Collaborative Filtering**: Analyzes user interactions (viewed and liked videos) to recommend content similar to that of other users with similar behavior.
- **Hybrid Filtering**: Combines content-based and collaborative filtering to improve recommendation precision.
- **Evaluation Metrics**:
  - **Mean Absolute Error (MAE)**: Measures the average magnitude of errors in the recommendations.
  - **Root Mean Square Error (RMSE)**: Provides a more sensitive measure of errors.

---

## Project Structure  
- **`data_fetching.py`**: Manages data fetching from the API and preprocessing.  
- **`recommendation_system.py`**: Contains logic for content-based, collaborative, and hybrid filtering methods.  
- **`evaluation_metrics.py`**: Computes the evaluation metrics (MAE and RMSE) for the system.  
- **`requirements.txt`**: Includes the list of dependencies required for the project.  

---

## 📊Datasets  
The system retrieves data from APIs that provide:  
1. **Rated Videos**: Includes ratings assigned by users to various videos.  
2. **Viewed Videos**: Tracks user-specific viewing history.  
3. **Liked Videos**: Contains videos liked by users.  
4. **Inspired Videos**: Details videos that users found inspiring.

**Note**: API responses are processed and converted into pandas DataFrames for further use.

---

## Steps Involved
1. **Data Fetching**:
   - Authenticated API calls fetch data for rated, viewed, liked, and inspired videos.
   - Handles nested JSON responses and converts them into structured pandas DataFrames.
2. **Content-Based Filtering**:
   - Filters videos with rating_percent above a given threshold (default: 80%).
3. **Collaborative Filtering**:
   - Utilizes a user-item matrix and k-nearest neighbors (kNN) to recommend videos based on similar user behavior.
4. **Hybrid Filtering**:
   - Combines results from content-based and collaborative methods to generate final recommendations.
5. **Evaluation**:
   - MAE and RMSE are calculated to evaluate the system's performance.

---

## Results
The Video Recommendation System successfully demonstrates its ability to recommend videos to users by leveraging their rating, viewing, and liking history. Below are the results based on the system's execution and evaluation:
- Recommendations:
  Using the hybrid filtering approach, the system generated recommendations for users by combining content-based and collaborative filtering methods. Example output:

  **Recommended Posts**:  [771, 516, 517, 772, 773, 774, 775, 776, 13, 14, 15, 16, 785, 19, 788, 789, 790, 26, 796, 29, 797, 798, 32, 1059, 36, 548, 39, 551, 811, 812, 813, 558, 814, 560, 815, 816, 817, 56, 58, 59, 838, 583, 844, 845, 847, 848, 82, 84, 861, 359, 363, 365, 627, 629, 376, 379, 383, 129, 130, 132, 652, 142, 143, 148, 151, 152, 159, 164, 422, 167, 168, 171, 691, 692, 693, 694, 696, 697, 698, 213, 252]
- Evaluation Metrics:
  The system's performance was evaluated using two common metrics:
  - Mean Absolute Error (MAE): Measures the average magnitude of errors in the recommendation system.

    Result: 0.175

    This value indicates that the system's predictions are relatively close to the actual user ratings on average.
  - Root Mean Square Error (RMSE): Evaluates the system's error sensitivity by giving larger weight to bigger errors.

    Result: 0.180

    The RMSE result confirms that the system produces minimal errors, demonstrating robust performance.
