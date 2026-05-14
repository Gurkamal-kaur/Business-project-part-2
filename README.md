# Market Basket Analysis and Product Recommendation

## 📌 Project Title
Market Basket Analysis and Product Recommendation

## 🛒 Business Problem
The retail company wants to improve product placement, cross‑selling, upselling, and promotional bundling. By understanding which products are frequently purchased together, the business can design better offers, improve customer experience, and increase overall sales.

## 📂 Dataset Description
- **Source:** Online Retail Transaction Dataset  
- **Accessed via:** [Google Drive Link](https://drive.google.com/file/d/1LgnjuKUWrxb837khcdHDX6ox8o62XOkS/view?usp=sharing)  
- **Description:** Transactional basket data from a UK‑based online retail store.  
- **Columns:**  
  - `TransactionID` – Unique invoice number  
  - `ProductName` – Name of the product purchased  
  - `Quantity` – Number of units purchased  
  - `CustomerID` – Unique customer identifier  
  - `InvoiceDate` – Date of transaction  
- **Granularity:** Each row represents a product purchased in a transaction.  

---

## 🧹 Data Cleaning Summary
- Removed cancelled transactions.  
- Dropped missing product names.  
- Handled invalid quantities (negative or zero).  
- Removed duplicate transaction‑product records.  
- Filtered rare or invalid products if necessary.  
- Converted data types (e.g., dates, numeric fields) to correct formats.  

---

## 🧺 Basket Preparation Method
- Converted raw transaction data into a **basket format** where each row represents a transaction and each column represents a product.  
- Used binary encoding: `1` if the product was purchased in the transaction, `0` otherwise.  

**Example:**

| TransactionID | Bread | Butter | Coffee |  
|---------------|-------|--------|--------|  
| T001          | 1     | 1      | 0      |  
| T002          | 0     | 1      | 1      |  

---

## 📊 Frequent Itemsets Summary
- Generated frequent itemsets using **Apriori algorithm**.  
- Tested different minimum support values (e.g., 0.01, 0.02, 0.05).  
- Observed that lower support values produced more itemsets, while higher support values reduced noise.  
- Selected a reasonable support threshold (e.g., 0.03) to balance meaningful rules with manageable output.  

---

## 🔗 Association Rules Summary
- Generated rules using **Support, Confidence, and Lift** metrics.  
- **Support:** Frequency of the itemset in all transactions.  
- **Confidence:** Probability that the consequent is purchased when the antecedent is purchased.  
- **Lift:** Strength of the rule compared to random chance (Lift > 1 indicates a useful rule).  

---

## ⭐ Top Rules with Interpretation
Here are examples of useful rules:

1. **Almond Pack → Electrolyte Drink**  
   - Support: 0.033 | Confidence: 0.58 | Lift: 8.88  
   - **Meaning:** Customers buying Almond Pack often also buy Electrolyte Drink. Bundle or cross‑sell these items.  

2. **Protein Bar → Almond Pack**  
   - Support: 0.031 | Confidence: 0.53 | Lift: 9.30  
   - **Meaning:** Protein Bar buyers are highly likely to also purchase Almond Pack. Place them together in store.  

3. **Baby Diapers → Baby Lotion**  
   - Support: 0.028 | Confidence: 0.49 | Lift: 8.73  
   - **Meaning:** Baby care products are purchased together. Promote them as a package deal.  

*(Interpret at least 10 rules in your notebook with support, confidence, lift, and business meaning.)*

---

## 💡 Final Business Recommendations
- **Product Bundling:** Bundle complementary items (e.g., Almond Pack + Protein Bar, Baby Diapers + Baby Lotion).  
- **Store Placement:** Place frequently co‑purchased products near each other in aisles.  
- **Cross‑Selling:** Suggest related products during checkout (e.g., batteries with electronics).  
- **Promotional Campaigns:** Run targeted promotions for high‑value product pairs.  
- **Rule Evaluation:** Ignore rules with high confidence but low lift (coincidental). Focus on rules with lift > 1.  
- **Customer Experience:** Personalize recommendations based on past purchases and improve store layout.  

---

## ▶️ How to Run the Project
Clone the repository and install requirements:

```bash
git clone https://github.com/Gurkamal-kaur/business-project-part-2.git
cd business-project-part-2
pip install -r requirements.txt
