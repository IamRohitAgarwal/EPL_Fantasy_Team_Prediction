# EPL_Fantasy_Team_Prediction
This repository contains our work on predicting Fantasy Premier League (FPL) outcomes for the 2024/25 season.

Problem: Fantasy Premier League (FPL) is a strategic game where participants build virtual teams composed of real-life football players, earning points based on their performance in actual matches. The challenge lies in selecting the optimal combination of players who will maximize fantasy points over the course of a season.

This project addresses the problem of predicting the ideal fantasy football team at the end of the 2024/25 season, using historical and real-time match data. Rather than relying on subjective judgment or static heuristics, we aim to build a data-driven pipeline that: 
• Predicts match scores per Gameweek (GW) using machine learning models 
• Translates match outcomes into fantasy points for individual players 
• Aggregates these points to identify the highest-performing team across the season

The primary design goal of this project is to build a robust, scalable, and data-driven pipeline that enables accurate prediction of Fantasy Premier League (FPL) outcomes for the 2024/25 season. This involves: 
• Data Collection and Storage: Collect structured match and player data from public repositories to ensure timely and comprehensive coverage of all Gameweeks. Store all datasets and intermediate outputs in Google Drive for easy access, sharing, and collaboration. 
• Data Preparation: Merge Gameweek-level data into a unified DataFrame. Join fixture, player, and event tables to compute match outcomes. Generate season-level summaries for modelling and evaluation. 
• Create a Custom Fantasy Point System: Apply a position-aware scoring system based on player actions and match events. Ensure scoring logic reflects realistic fantasy dynamics and positional weighting.

• Match Score Prediction: Develop a machine learning model to predict match scores per Gameweek (GW) and predict the EPL Team of the season based on the Fantasy Points. 
• Reproducibility and Extensibility: Design the pipeline to be modular, version-controlled, and reproducible. Also, enable future enhancements such as live data integration, injury tracking, and transfer modelling. 

High Level Design: The Fantasy Premier League prediction system is structured as a modular pipeline that integrates data engineering, feature engineering, and machine learning to deliver end-to-end predictions and team optimization. At a high level, the design consists of the following stages: 
1. Data Collection & Storage 
2. Data Preparation 
3. Fantasy Point Calculation 
4. Feature Engineering 
5. EDA 
6. Machine Learning Models 
7. Optimization and Output 
This high-level design ensures the system is scalable, modular, and reproducible, bridging the gap between raw football data and actionable fantasy team recommendations.

Big Data Platforms used: Spark, Python, Colab, Kaggle, ML Pipeline, MatPlotLib

ML Methods used:  
▪ Player Prediction 
The objective here was to predict whether a player would participate in a given Gameweek (GW). 1. Logistic Regression was used as a baseline classifier due to its ability to model binary outcomes with interpretable coefficients. 
2. Decision Tree models were applied to capture non-linear relationships and feature interactions, offering intuitive rule-based predictions. 
3. Random Forest was used to improve robustness by aggregating multiple decision trees, reducing overfitting and enhancing generalization. Logistic Regression achieved the highest accuracy (~83%), making it the most reliable model for this task. 
▪ Fantasy Point Prediction 
The goal was to estimate the fantasy points a player would earn based on match attributes and our custom scoring system. 
1. Linear Regression was chosen for this task as it effectively models continuous outcomes and provides interpretable relationships between player attributes and 
fantasy points. 
▪ Match Result Prediction 
This task focused on predicting the outcome of matches (win, loss, or draw) based on team and fixture attributes. 
1. Decision Tree models were used to capture categorical splits and provide interpretable decision rules. 
2. Random Forest was employed to improve prediction stability by combining multiple trees, though performance remained modest due to the inherent unpredictability of football outcomes. 
Random Forest achieved ~50.5% accuracy, slightly outperforming Decision Tree (~47.3%), but both highlight the complexity of match result prediction compared to player-level tasks.
