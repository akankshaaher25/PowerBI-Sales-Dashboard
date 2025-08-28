# Power BI Sales Dashboard

A clean, interactive **Sales Dashboard** built in **Power BI** to track revenue, orders, and performance across products, regions, and time. It’s designed for quick decision-making with drill-through analysis, filters, and KPI cards.

---

## 🔍 What this dashboard shows
- **KPIs:** Total Sales, Total Orders, Average Order Value, YoY/MoM Growth
- **Trends:** Monthly/Quarterly sales trends with time intelligence
- **Breakdowns:** Product, Category, Region, and Customer segments
- **Top Insights:** Top products/regions, contribution analysis, Pareto 80/20 view
- **Interactivity:** Slicers, drill-through, and tooltips for deeper analysis

> Replace screenshots below with your own images after exporting from Power BI (File → Export → PDF/PNG) and save them in an `assets` folder.

---

## 🖼️ Preview (add your images)
![Overview](assets/overview.png)
![Trends](assets/trends.png)
![Top Products](assets/top-products.png)

---

## 📁 Project structure
```
.
├── Power BI Sales Project.pbix        # Main Power BI report
├── data/                              # (Optional) Sample data files
├── assets/                            # Screenshots used in README
└── README.md
```

> Rename your `.pbix` file if you like, and update the structure accordingly.

---

## 🧰 Requirements
- **Power BI Desktop** (latest version)
- Windows 10/11
- (Optional) **Git LFS** if your `.pbix` file is larger than 100 MB

---

## 🚀 How to open & use
1. **Clone or download** this repository.
2. Open **`Power BI Sales Project.pbix`** in **Power BI Desktop**.
3. If your data source paths changed, go to **Transform data → Data source settings** and **Update** the paths/credentials.
4. Click **Refresh** to load the latest data.
5. Explore the report using **slicers**, **drill-through**, and **tooltips**.
6. (Optional) Publish to the **Power BI Service**: **Home → Publish** to share with your team.

---

## 🧮 Key DAX measures (examples)
> Put these in a dedicated **Measures** table in Power BI for clarity.

```DAX
Total Sales = SUM('Sales'[Sales Amount])

Total Orders = DISTINCTCOUNT('Sales'[Order ID])

Average Order Value (AOV) = DIVIDE([Total Sales], [Total Orders])

Sales (LY) = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))

YoY Growth % = DIVIDE([Total Sales] - [Sales (LY)], [Sales (LY)])

Sales (Prev Month) = CALCULATE([Total Sales], DATEADD('Date'[Date], -1, MONTH))

MoM Growth % = DIVIDE([Total Sales] - [Sales (Prev Month)], [Sales (Prev Month)])
```

> Update table/column names to match your model (e.g., `'Sales'[Sales Amount]`, `'Date'[Date]`).

---

## 🧱 Data model (describe yours)
- **Fact table:** `Sales` (Order ID, Date, Product ID, Customer ID, Quantity, Price, Sales Amount, Region…)
- **Dimensions:** `Date`, `Product`, `Customer`, `Region/Geography`, `Category`
- Relationships: One-to-many from dimensions to `Sales` using keys (e.g., `Product[Product ID]` → `Sales[Product ID]`)

> Add a screenshot of your model here: `assets/model.png`

---

## ✨ Features
- KPI cards with trends and conditional formatting
- YoY/MoM time intelligence
- Product and region deep-dive pages
- Drill-through from summary to detail
- Tooltip pages for quick context
- Dynamic titles synced to slicers

---

## 📦 Setup for GitHub
- Keep the `.pbix` file in the root (or `reports/` folder).
- Add screenshots to `assets/` and reference them in this README.
- If your `.pbix` > 100 MB, enable **Git LFS**:
  ```bash
  git lfs install
  git lfs track "*.pbix"
  git add .gitattributes
  git add "Power BI Sales Project.pbix"
  git commit -m "Track PBIX with LFS"
  git push
  ```

---

## 🛣️ Roadmap
- [ ] Add Profit, Margin% measures
- [ ] Add Customer Cohort analysis
- [ ] Add Forecasting visual
- [ ] Add RLS (Row-Level Security) roles
- [ ] Add automated data refresh via gateway (if using local files)

---

## 🤝 Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you’d like to change.

---

## 📄 License
This project is licensed under the **MIT License**. See `LICENSE` for details.

---

## 📬 Contact
**Your Name** – your.email@example.com  
GitHub: [your-username](https://github.com/your-username)

---

### 🧭 How to customize this README (step-by-step)
1. **Rename** the project in the top heading.
2. **Replace** screenshots in `assets/` and update the image paths.
3. **Edit** DAX measure names and columns to match your model.
4. **Describe** your own data model and relationships.
5. **Fill in** your contact details and license choice.
6. **Commit & push** the updated README to GitHub.