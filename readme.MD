# انگارش‌نامه | Math-Atlas

### An Open Mathematics Knowledge Base with Python Implementations

---

## دیباچه | Preface

### فارسی

**انگارش‌نامه (Math-Atlas)** یک پروژهٔ خودبسنده و پیش‌بردپذیر برای فراهم‌آوری، سامان‌دهی، آموزش و پیاده‌سازی رایانشی دانش انگارش است. این پروژه میکوشد پلی میان سه زمینه بسازد: همیافته‌های انگارشی و شناسانش‌ها و دیسوله‌ها و نگرینه‌ها و برهان‌ها؛ الگوریتم‌ها و روش‌های رایانشی؛ و پیاده‌سازی کاربُردی با Python. آماج، ساختن یک سرچشمهٔ ساخت‌یافته است که هم برای یادگیری انگارش شایسته باشد و هم توانمندیِ آزمایش، دوان کردن، و وارسیِ رایانشی ویده‌های انگارشی را فراهم کند.

### English

**Math-Atlas** is an independent and extensible project for gathering, organizing, teaching and computationally implementing mathematical knowledge. The project seeks to build a bridge between three domains: mathematical concepts, definitions, formulas, theorems and proofs; algorithms and computational methods; and practical implementation in Python. The goal is to build a structured resource suitable both for learning mathematics and for experimenting, running and computationally verifying mathematical ideas.

---

## 🌱 Vision

The vision of Math-Atlas is to build a comprehensive scientific and educational resource that presents mathematical knowledge from its earliest foundations to advanced topics, together with its computational applications.

In this project, mathematics is not limited to a set of formulas; rather, it seeks to reveal the connections between theoretical concepts (همیافته‌ها), problem-solving methods, algorithms (الگوریتم‌ها) and their practical implementations.

---

## 📚 Mathematical Domains

The project will gradually cover various mathematical domains:

| Domain | Persian |
|---|---|
| Foundations | بنیادها |
| Arithmetic | همارش |
| Algebra | جبر |
| Geometry | هندسه |
| Trigonometry | سکنج‌سنجی |
| Functions | کارکنش‌ها |
| Calculus | ریگماره |
| Linear Algebra | جبر تانه‌ای |
| Probability | شکیبمندی |
| Statistics | آمار |
| Discrete Mathematics | انگارش گسسته |
| Number Theory | نگرهٔ شماره‌ |
| Mathematical Logic | سخنگاه انگارشی |
| Optimization | بهینه‌سازی |
| Machine Learning Mathematics | انگارش یادگیری دستگاه |

This categorization will expand as the project develops.

---

## 🐍 Python Implementations

One of the core features of Math-Atlas is providing practical implementations of mathematical concepts (همیافته‌ها) and algorithms (الگوریتم‌ها) in Python.

Wherever practical, each topic (سخن‌سار) includes, in addition to theoretical explanations, executable (پساختی) code (شناسه) and computational examples.

Implementations follow three levels:

**Level 1 — From Scratch**  
Educational implementation of algorithms (الگوریتم‌ها) in Python, with NumPy where needed, focusing on understanding the mathematical logic and computational steps.

**Level 2 — Modular Implementation**  
Structured, reusable and extensible implementations following programming principles.

**Level 3 — Scientific Libraries**  
Use of specialized libraries (نسکخانه‌ها) such as NumPy, SciPy, SymPy, Matplotlib, Pandas and Scikit-learn.

The goal is for readers to understand algorithms (الگوریتم‌ها) from the ground up while also becoming familiar with standard scientific computing tools.

---

## 🧩 Standard Topic Structure

Where appropriate to the subject (جستار), each topic (سخن‌سار) will consist of the following sections:

1. **Introduction:** overview and application of the topic
2. **Mathematical Definitions (شناسانش‌ها):** precise definitions
3. **Properties (داشتارها):** features and characteristics
4. **Formulas (دیسوله‌ها):** mathematical relations and formulas
5. **Theorems and Proofs (نگرینه‌ها و برهان‌ها):** theorems and their proofs
6. **Derivations (برگرفتگی‌ها):** derivation and inference of relations
7. **Algorithms (الگوریتم‌ها):** related algorithms
8. **Python Implementation:** practical implementation
9. **Worked Examples (نمونه‌های کار‌شده):** solved examples
10. **Experiments and Visualization (آزمایش‌ها و دیدآوری):** computational experiments and plots
11. **Exercises (ورزه‌ها):** practice problems
12. **References (سرچشمه‌ها):** sources and references

Not all topics (سخن‌سارها) necessarily require all sections; the structure will be adapted to the nature of each subject (جستار).

---

## 🗂️ Repository Structure

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