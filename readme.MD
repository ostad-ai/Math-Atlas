# انگارش‌نامه | Math-Atlas

### An Open Mathematics Knowledge Base with Python Implementations

**انگارش‌نامه (Math-Atlas)** یک پروژهٔ خودبسنده و پیش‌بردپذیر برای فراهم‌آوری، سامان‌دهی، آموزش و پیاده‌سازی شمارشیِ دانش انگارش (Mathematics) است.

این پروژه می‌کوشد پلی میان سه زمینه بسازد:

- **Mathematics:** همیافته‌های انگارشی، شناسانش‌ها (Definitions)، دیسوله‌ها (Formulas)، نگرینه‌ها (Theorems) و برهان‌های انگارشی
- **Algorithms:** الگوریتم‌ها و روش‌های شمارشیِ برآمده از انگارش
- **Python:** پیاده‌سازی کاربُردیِ همیافته‌ها و الگوریتم‌ها با Python

آماج (Goal)، ساختن یک سرچشمهٔ ساخت‌یافته است که هم برای یادگیری و خواندن انگارش شایسته باشد و هم توانمندیِ آزمایش، گرداندن و وارسیِ شمارشیِ ایده‌های انگارشی را فراهم کند.

---

## 🌱 Vision | بینش

بینش Math-Atlas ساختن یک سرچشمهٔ دانشی و آموزشیِ فراگیر است که دانش انگارش را از بنیادهای نخستین تا سخن‌سارهای (Topics) پیشرفته، همراه با کاربُردهای شمارشیِ آن پیشکش کند.

در این پروژه، انگارش تنها به هنگتی (Set) از دیسوله‌ها کرانمند نمی‌شود؛ بساکه می‌کوشد پیوند میان همیافته‌های نظری، روش‌های گشایش پرسمان (Problem Solving)، الگوریتم‌ها و پیاده‌سازی کاربُردیِ آن‌ها را آشکار کند.

## 📚 Mathematical Domains | دامنه‌های انگارشی

پروژه کم‌کم دامنه‌های گوناگون انگارش را پوشش خواهد داد:

| Domain | دامنه |
|---|---|
| Foundations | بنیادها |
| Arithmetic | شمار |
| Algebra | جبر |
| Geometry | هندسه |
| Trigonometry | سکنج‌سنجی |
| Functions | کارکنش‌ها |
| Calculus | ریگماره |
| Linear Algebra | جبر تانه‌ای |
| Probability | شکیبمندی |
| Statistics | آمار |
| Discrete Mathematics | انگارش گسسته |
| Number Theory | نگرهٔ شماره‌ها |
| Mathematical Logic | سخنگاه انگارشی |
| Optimization | بهینه‌سازی |
| Machine Learning Mathematics | انگارش یادگیری دستگاه |

این رمک‌بندی (Categorization) در درازای پیش‌برد پروژه گسترش خواهد یافت.

## 🐍 Python Implementations | پیاده‌سازی با Python

یکی از ویژگی‌های بنیادی Math-Atlas پیشکشانیِ پیاده‌سازی کاربُردیِ همیافته‌ها و الگوریتم‌های انگارشی با Python است.

تا حد توانمندی، هر سخن‌سار افزون بر روشنگری‌های نظری، دربردارندهٔ شناسه‌های (Codes) پساختی و نمونه‌های شمارشی خواهد بود.

پیاده‌سازی‌ها در سه پایه دنباله‌روی می‌شوند:

### Level 1 — From Scratch

پیاده‌سازی آموزشی الگوریتم‌ها با Python و در رخ‌آمد نیاز NumPy، با هموندساری (Focus) بر دانستن سخنگاه انگارشی و گام‌های شمارش.

### Level 2 — Modular Implementation

پیاده‌سازی ساخت‌یافته، بازکاربُردپذیر و پیش‌بردپذیر با دنباله‌روی از پایه‌های برنامه‌نویسی.

### Level 3 — Scientific Libraries

بهره‌گیری از نسکخانه‌های (Libraries) کارشناسی مانند:

- NumPy
- SciPy
- SymPy
- Matplotlib
- Pandas
- Scikit-learn

آماج این است که خواننده هم بتواند الگوریتم را از پایه دریابد و هم با ابزارهای استاندارد شمارش دانشی آشنا شود.

## 🧩 Standard Topic Structure | ساختار استاندارد سخن‌سار

در رخ‌آمد همسنگی با سخن‌سار، هر جستار (Subject) از بخش‌های زیر ساخته خواهد شد:

1. **Introduction:** آشنایی و کاربُرد سخن‌سار
2. **Mathematical Definitions:** شناسانش‌های انگارشی
3. **Properties:** داشتارها
4. **Formulas:** دیسوله‌ها
5. **Theorems and Proofs:** نگرینه‌ها و برهان‌ها
6. **Derivations:** برآیی‌ها
7. **Algorithms:** الگوریتم‌های مرتبط
8. **Python Implementation:** پیاده‌سازی کاربُردی با Python
9. **Worked Examples:** نمونه‌های گشوده‌شده
10. **Experiments and Visualization:** آزمایش‌های شمارشی و نمودارها
11. **Exercises:** ورزه‌ها
12. **References:** سرچشمه‌ها

همهٔ سخن‌سارها به‌ناچار به همهٔ این بخش‌ها نیاز ندارند؛ ساختار همسنگ با سرشت هر جستار پیشکش خواهد شد.

## 🗂️ Repository Structure | ساختار گنجینه

ساختار پیشنهادی نخستین:

```text
Math-Atlas/
│
├── README.md
├── GLOSSARY.md
├── LICENSE
├── CONTRIBUTING.md
├── requirements.txt
│
├── Foundations/
├── Algebra/
├── Geometry/
├── Trigonometry/
├── Calculus/
├── Linear_Algebra/
├── Probability/
├── Statistics/
├── Discrete_Mathematics/
├── Number_Theory/
├── Optimization/
│
├── Machine_Learning/
│   ├── Regression/
│   ├── Classification/
│   ├── Clustering/
│   └── Model_Evaluation/
│
├── Algorithms/
├── Problem_Bank/
├── Worked_Examples/
├── Notebooks/
├── Projects/
└── References/