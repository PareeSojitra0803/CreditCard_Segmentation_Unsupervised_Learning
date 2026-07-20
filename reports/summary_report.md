# 📊 Credit Card Customer Segmentation using Unsupervised Learning

## 🎯 Business Problem

Banks manage thousands of credit card customers, each with different spending habits, repayment behaviour, and credit utilization patterns. Treating every customer the same often results in ineffective marketing campaigns and missed business opportunities. The goal of this project was to identify meaningful customer segments using **Unsupervised Learning** so that banks can personalize offers, improve customer retention, support credit-risk assessment, and make data-driven business decisions.

The project uses the **CC GENERAL** dataset, which contains behavioural information for approximately **8,950 credit card customers**. The dataset includes features such as balances, purchases, cash advances, payment history, credit limits, transaction frequencies, and customer tenure. Since no target variable is available, clustering techniques were used to discover natural customer groups based on behavioural similarities.

---

## ⚙️ Feature Engineering & Preprocessing

To improve segmentation quality, several behavioural features were engineered, including **Purchase_CreditLimit_Ratio**, **Monthly_Avg_Purchase**, **Monthly_Avg_Cash_Advance**, **Limit_Usage**, and **Payment_to_Minpayment_Ratio**. These features better represent customer spending efficiency, repayment behaviour, and credit utilization than the original variables alone.

The preprocessing pipeline included median imputation for missing values, duplicate checking, IQR-based winsorization for outlier handling, and **log1p transformation** to reduce skewness in monetary features. Finally, **StandardScaler** standardized every feature before clustering, ensuring equal importance across variables. **PCA** was also applied, retaining approximately **95% of the total variance** while reducing dimensionality.

---

## 🤖 Model Evaluation

Three clustering algorithms were evaluated:

- **K-Means**
- **Agglomerative Hierarchical Clustering**
- **DBSCAN**

Their performance was compared using **Silhouette Score**, **Davies-Bouldin Index**, and **Calinski-Harabasz Index**.

Among the three methods, **K-Means** produced the most balanced, compact, and interpretable clusters while remaining stable across multiple random initializations. These results also matched business expectations, making K-Means the recommended algorithm for deployment.

---

## 👥 Customer Segments

The final K-Means model identified **three meaningful customer segments**:

- **Premium Transactors** – High purchase activity, larger credit limits, and responsible repayment behaviour. These customers are ideal candidates for premium cards, exclusive rewards, and loyalty programs.

- **Cash-Advance Reliant** – Customers who frequently rely on cash advances and maintain relatively high outstanding balances. EMI conversion plans and repayment assistance would benefit this group.

- **Moderate Card Users** – Customers with average spending behaviour and regular card usage. Cashback offers, seasonal promotions, and reward-point campaigns can encourage higher engagement.

---

## 🚀 Future Scope

Future improvements could include additional customer attributes such as age, occupation, annual income, geographic location, credit bureau score, and merchant transaction categories to create richer customer profiles. Semi-supervised learning could further refine the discovered segments after expert validation. Finally, deploying the trained clustering pipeline as a **real-time prediction API** would enable instant customer segmentation, helping banks deliver personalized financial products and make faster business decisions.