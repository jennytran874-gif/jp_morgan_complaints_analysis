# JP.Morgan Complaint Analysis
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/b9b5e72c-f651-481a-9e4c-2d9b9712fc06" />
" />

--- 
## 🌟 Project Overview

This project analyzes more than **1 million consumer financial complaints** from the **Consumer Financial Protection Bureau (CFPB)** and then zooms in on **JPMorgan**.

The workflow has **three main steps**:

1. **Big-picture analysis (all companies) with Power BI**  

2. **Deep-dive into JPMorgan complaints with Python**   

3. **Sentiment-based dispute prediction model**  

This project shows how **visual analytics + NLP + machine learning** can turn raw complaint data into useful business insights.

---

## 📊 Power BI Dashboard

👉 **Live dashboard (all companies):**  
https://app.powerbi.com/view?r=eyJrIjoiNGQ1ODNmZDYtODgxMS00YWM4LTk3NDMtMzQ5MTI3MDYzZjQzIiwidCI6ImRiMjMwNmZkLWFmMjUtNGUyOS05Y2NiLWJmMjg2YWY2MjFjMCJ9

---
## 🧷 Data

### Big Picture – All Companies

For the high-level, industry-wide analysis in Power BI, I used data downloaded directly from the official CFPB complaint portal:

🔗 https://www.consumerfinance.gov/data-research/consumer-complaints/

From this site, I exported the full consumer complaint dataset (all companies, all products) as CSV and loaded it into Power BI to explore

### Deep Dive – JPMorgan Complaints

For the second step, I focused specifically on **JPMorgan**.

🔗 JPMorgan CSV API link (used in this project): https://www.consumerfinance.gov/data-research/consumer-complaints/search/api/v1/?date_received_max=2025-10-02&date_received_min=2011-12-01&field=company&format=csv&no_aggs=true&search_term=jpmorgan&size=149956 

From this CSV: 

- I cleaned and standardized the data in Excel (Power Query). 

- Then used this cleaned dataset for sentiment analysis and logistic regression modeling.

--- 
## 📈 Results & Findings

### ⭐ 1. JPMorgan Complaint Analysis

 **Overall Complaint Characteristics**
- Complaints span **2011–2025**, covering a wide range of financial products.
- JPMorgan receives almost **150,000 of complaints**, making it one of the most frequently reported banks.

 **Products with the Most Complaints**
 
Top product categories for JPMorgan include:

1. **Checking or Savings Accounts**  
2. **Mortgage Issues**  
3. **Credit Cards**  
4. **Bank Account Services**  
5. **Credit Card / Prepaid Card**

➡ Checking/savings and mortgage issues drive the majority of complaints.

### **Top Sub-Issues**
Common problem areas include:

- Problems with **deposits and withdrawals**
- **Account closures** initiated by the company
- **Unresolved credit card disputes**
- **Unauthorized transactions**
- **Debit/ATM card issues**

These issues point to **transaction errors, account access problems, and dispute handling** as core pain points.

### **State-Level Complaint Hotspots**
JPMorgan complaints are concentrated in:

- **California**  
- **New York**  
- **Florida**  
- **Texas**  
- **Illinois**

 <img width="1094" height="450" alt="image" src="https://github.com/user-attachments/assets/d9e07fed-284e-4b0f-87fa-85cfe78c009a" />


These states also have the highest JPMorgan customer bases, but California stands out with especially high volume.

### **Response Types & Timeliness**
- Most complaints are closed **“with explanation.”**
- Only a small percentage receive **monetary or non-monetary relief**.
- JPMorgan responds **on time** for the majority of cases.
- However, some customers still **dispute** the company’s response, indicating unresolved concerns.

---
## ⭐ 3. Statistical Modeling – Logistic Regression

### Statistical Results
                         Logistic Regression Coefficients
| Feature | Coefficients | P-value  | Interpretation
| ------- | ------- |------- |------- |
| Anger Score | +0.255 | < 0.05 | Higher Anger -> Higher dispute probability |
| Trust Score | +0.043 | < 0.05 | Higher Trust -> Lower dispute probability |
| Sentiment Polarity | +0. 104 | < 0.1 | Positive sentiment -> Higher engagement |

# Key Results

- Model Accuracy: 99.1% dispute prediction accuracy

- Sentiment is the strongest predictor (coefficient = -0.571)
   
- More positive sentiment → Lower dispute probability
   
- Overall dispute rate: 0.7%

- Statistical Significance: Trust levels inversely correlate with dispute probability

# Top Complaint Categories

- Credit reporting services (35.5%)

- Credit card issues (11.4%)

- Debt collection (10.3%)
  
- Banking services (6.7%)
  
---

## ⭐ 4. Sentiment Analysis Results
### Sentiment Distribution Analysis

<img width="450" height="450" alt="Screenshot 2025-08-02 at 12 22 35 AM" src="https://github.com/user-attachments/assets/0b4b2984-9c05-4fb7-be28-ae4b2cb4eb28" />

**Sentiment Distribution Histogram**
- **Pattern**: Sharp peak at 0.0 (neutral sentiment) with normal distribution
- **Finding**: Most JP Morgan complaints are factual and unemotional rather than angry rants
- **Range**: -0.8 to +0.6 sentiment polarity
- **Insight**: Professional, measured complaint language dominates customer feedback

### Sentiment Categories

<img width="838" height="504" alt="Screenshot 2025-08-02 at 12 39 21 AM" src="https://github.com/user-attachments/assets/845dd843-4cb2-4d12-ba38-c8992d87f9d7" />


**Sentiment Categories Pie Chart**
- **Neutral (59.2%)**: Majority of JP Morgan complaints are factual, business-like reporting
- **Positive (25.8%)**: Quarter of complaints show constructive or satisfied tone
- **Negative (15.0%)**: Smallest segment represents frustrated or dissatisfied customers
- **Insight**: 85% of complaints are neutral/positive, indicating professional customer communication

### Emotion Analysis & Dispute Patterns

<img width="320" height="320" alt="Screenshot 2025-08-02 at 12 43 04 AM" src="https://github.com/user-attachments/assets/2d5a7c2d-6cf9-4919-acfa-3c768134f0da" />
<img width="320" height="320" alt="Screenshot 2025-08-02 at 12 43 18 AM" src="https://github.com/user-attachments/assets/6ed09672-74a9-4dae-b4e5-db825908b498" />


**Left - Average Emotion Scores:**
- **Trust (0.443)**: Moderate trust levels in JP Morgan customer feedback
- **Anger (0.032)**: Very low anger scores indicate calm, professional complaints
- **Ratio**: Trust is 14x higher than anger, showing constructive customer relationships

**Right - Dispute Rate by Sentiment:**
- **Neutral sentiment**: Highest dispute rate (~0.008) - factual complaints more likely escalated
- **Negative sentiment**: Moderate dispute rate (~0.006) - emotional complaints sometimes resolved
- **Positive sentiment**: Lowest dispute rate (~0.005) - satisfied customers rarely dispute

### Anger vs Trust Relationship

<img width="375" height="416" alt="Screenshot 2025-08-02 at 1 57 58 AM" src="https://github.com/user-attachments/assets/0d81c4c8-a7d2-4461-bd43-f14b6c422313" />


**Anger vs Trust Scatter Plot**
- **Pattern**: No clear correlation between anger and trust scores
- **Distribution**: Points scattered across all combinations (0.0 to 1.0 range)
- **Finding**: Anger and trust are independent emotions in JP Morgan complaints
- **Insight**: Customers can express anger while maintaining trust, or vice versa

# Recommendations

- Early Warning System: Flag complaints with anger scores > 0.5

- Response Prioritization: Fast-track high-risk complaints

- Trust Building: Implement transparent communication protocols

- Training Programs: Develop emotional intelligence for customer service
