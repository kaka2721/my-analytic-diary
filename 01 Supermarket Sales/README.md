# 20250914 Supermarket Sales Analysis
> 咱就是说，差点儿开始即结束 🥶 <br>
> ![Static Badge](https://img.shields.io/badge/mood-lost-brightgreen)

---

## data description & preparation 
  💻 1000 line, 3-month supermarket sales data downloaded from Kaggle [lovishbansal123](https://www.kaggle.com/datasets/lovishbansal123/sales-of-a-supermarket) <br>
  
  the data set is already clean&uniformed, so i did not do much modification except combined sales' date&time into one field 'transtime'

## calculation & analysis
  🏁 the goal is to find out which **factor(s) contributes more into sales and margins**, or how are sales&margins affected <br>
  
  ➕ sum of 'Sales' by day, week, and month is the dependent variable

### blind start 🤣
  i started with the simplest assumption that Dates(weekday/weekends) might influnce customer purchase. <br>
  📊 by draging variables around in Tableau has shown messy line graph (sales-day/week-product line), which already given signs of WRONG-thought-pathway. <br>
  i insisted 🤣 ，just to try out the process <br>
  🤡 i thought i could go like : <br>
  
```mermaid

flowchart LR
    A["ANOVA (test to see if sales differ by day of the week)"] -- "Yes (p_val<0.05)" --> B{"Tukey's HSD test result"}
    A -- "No (p_val>0.05)" --> C["Check weekday vs weekends (two-group T-test)"]
    C -- "Yes" --> D[ ✌️ ]
    C -- "No (kinda assured ANOVA:sales DO NOT differ by day)" --> E["Kruskal-Wallis test (sales not normally distributed)"]
    E --> F[continue...]
    
```
