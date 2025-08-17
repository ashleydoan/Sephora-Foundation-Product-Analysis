# 🛍️ Sephora Foundation Analysis  

**Authors:** Ashley Doan & Selene Nguyen  

This project analyzes **consumer preferences and pricing trends** for foundation products at **Sephora**.  
We collected, cleaned, and analyzed Sephora’s foundation product data to uncover patterns in pricing, popularity, brand influence, and inclusivity.  

---

## 📊 Project Overview  

The analysis focused on:  
- Retrieving product data directly from Sephora’s foundation pages.  
- Cleaning and preprocessing product details for analysis.  
- Performing exploratory data analysis (EDA) on ratings, reviews, brands, and prices.  
- Building predictive models for **price** and **popularity**.  
- Identifying brand, ethical, and societal implications of Sephora’s product offerings.  

---

## ⚙️ Data Retrieval & Cleaning  

1. **Data Retrieval**  
   - Scraped JSON product information from Sephora’s foundation product pages.  
   - Compiled **262 observations** across **11 variables**.  

2. **Data Cleaning**  
   - Filtered only products with “foundation” in the name.  
   - Removed brushes, samples, and accessories.  
   - Converted booleans (`isLimitedEdition`, `isSephoraExclusive`, etc.) into binary format.  
   - Extracted full-size product prices (used higher value for ranges).  
   - Converted numerical columns: `Price`, `Num_Colors`, `Rating`, `Reviews`.  
<img width="1440" height="345" alt="image" src="https://github.com/user-attachments/assets/18ac35b2-91e4-4305-b437-c5424c378e37" />

---

## 🔎 Exploratory Data Analysis  

### Distributions  
- **Number of Shades (Colors)**  
<img width="729" height="314" alt="image" src="https://github.com/user-attachments/assets/d949677d-4ddb-4977-ad63-5eff4e88c2b9" />


- **Ratings**  
<img width="998" height="406" alt="image" src="https://github.com/user-attachments/assets/3bd3d988-146a-47db-820a-40afa0c99f23" />


- **Reviews**  
 <img width="729" height="300" alt="image" src="https://github.com/user-attachments/assets/c9a3e6a8-fe11-4ebd-9c0d-54518b71f026" />


### Brand Insights  
- Top 10 brands with the most foundation products.  
<img width="562" height="396" alt="image" src="https://github.com/user-attachments/assets/15f3b944-adb7-45f0-aa8d-319c5ab46625" />


- Heatmap of variable relationships.  
<img width="640" height="512" alt="image" src="https://github.com/user-attachments/assets/649dbf9f-4b38-4be0-ae9d-d776133ea9ed" />


---

## 🤖 Modeling  

### 1. **Price Prediction Model**  
<img width="708" height="741" alt="image" src="https://github.com/user-attachments/assets/4d400356-b978-4afd-ab93-630bc71f1b9e" />

- **Most influential features:**  
  - Rating ⭐
  - Brand Name 🏷️  
  - Number of Reviews 💬

    <img width="696" height="539" alt="image" src="https://github.com/user-attachments/assets/81de6c09-5b0b-4179-b54e-e699d0200144" />

- **Key finding:**  
  - Price is strongly tied to **brand reputation** and **consumer perception** (ratings/reviews).  
  - The **number of colors** did **not** significantly affect pricing.  

### 2. **Product Clustering**  
- Used **K-Means clustering** with the elbow method → Optimal `k = 2`.
  <img width="859" height="487" alt="image" src="https://github.com/user-attachments/assets/7955ded8-b942-44a7-8c31-32a75caa0db7" />

- **Cluster 0 (Blue):**  
  - Higher price range ($23 – $150).  
  - Fewer reviews, more niche/premium products.  
- **Cluster 1 (Green):**  
  - Affordable products (< $50).  
  - Large review counts → Popular, mass-market products.  

<img width="827" height="504" alt="image" src="https://github.com/user-attachments/assets/0baaae19-da53-4bcb-a0da-6e8ac5b58e7f" />
 

### 3. **Popularity Classification**  
- Defined *popular* products as:  
  - Reviews > **2255** (top 25%)  
  - Rating ≥ **4.35** (top 25%)
- Model: **Random Forest Classifier**  
- Accuracy: **96%** 
  
<img width="629" height="244" alt="image" src="https://github.com/user-attachments/assets/a851f8a3-667d-4c24-8428-cf6a35810aa4" />

- **Most important features:** Reviews > Rating > Num_Colors > Price  
<img width="629" height="138" alt="image" src="https://github.com/user-attachments/assets/ca6e8a9a-619a-49b9-8980-adfc5e419df9" />

---

## 🌍 Implications  

### Brand & Pricing  
- Strong **brand reputation** and **positive reviews** allow premium pricing.  
- **Number of shades** does not increase price, but inclusivity remains important.  

### Ethical Considerations  
- Lack of transparency in “natural” / “organic” claims → potential **greenwashing**.  
- Limited-edition products drive **overconsumption**.  
- Inclusivity gaps may exclude underrepresented consumers.  

### Societal Implications  
- Popular, high-rated products dominate → may **limit consumer choice**.  
- Push toward eco-friendly products could improve sustainability.  

---

## 📝 Conclusion  

- **Premium brands** dominate high pricing, supported by strong ratings and reviews.  
- **Inclusivity (shade ranges)** does not directly affect price, but remains a **societal priority**.  
- **Popularity** is highly predictable using reviews and ratings.  
- Sephora and stakeholders should balance **brand reputation**, **ethical practices**, and **consumer inclusivity**.  

