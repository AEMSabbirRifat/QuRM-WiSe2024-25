# Quantitative Research Methods (QuRM): Interactive Course, Winter Semester 2024/25

**Open, interactive lessons that take students from a research question to a tested hypothesis in R.**

[![LiaScript](https://img.shields.io/badge/Built_with-LiaScript-000000?style=flat-square&logo=markdown)](https://liascript.github.io/)
[![R](https://img.shields.io/badge/Statistics_in-R-276DC3?style=flat-square&logo=r&logoColor=white)](https://www.r-project.org/)
[![University](https://img.shields.io/badge/Otto_von_Guericke_University-Magdeburg-F39200?style=flat-square)](https://www.ovgu.de/)

This repository holds the lesson materials I co-authored as a tutor for the **Quantitative Research Methods** course (ITVET programme) at **Otto von Guericke University Magdeburg**, under responsible teacher M.A. Hannes Tegelbeckers, together with fellow tutors Masub Makhdoom and Mahwish Kanwal.

Every lesson is a plain Markdown file written in **[LiaScript](https://liascript.github.io/)**. That means it opens in the browser as a full interactive course, with slides, quizzes, embedded videos and narration, without any learning platform or installation.

---

## 📚 Lessons (click to open the interactive version)

| # | Lesson | What students learn |
|---|---|---|
| 1 | [Research Questions, Literature Review & Hypothesis Formulation](https://liascript.github.io/course/?https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-WiSe2024-25/main/Quantitative%20Research%20Questions%2C%20Literature%20Review%20%26%20Hypothesis%20Formulation.md) | Types of research, quantitative question types, variables, literature search, writing testable hypotheses |
| 2 | [Research Design & Sampling Methods](https://liascript.github.io/course/?https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-WiSe2024-25/main/Research%20Design%20and%20Sampling%20Methods.md) | Descriptive, correlational, experimental and quasi-experimental designs; validity and reliability; probability vs. non-probability sampling |
| 3 | [Online Questionnaires, Ethics & Missing Data](https://liascript.github.io/course/?https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-WiSe2024-25/main/Creating%20an%20Online%20Questionnaire%2C%20Ethical%20Considerations%20%26%20Handling%20Missing%20Data.md) | Designing and running a survey step by step, research ethics, strategies for missing data |
| 4 | [Descriptive Data Analysis in R](https://liascript.github.io/course/?https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-WiSe2024-25/main/Week06.md) | Central tendency, variability, frequency tables and plots on a real course dataset |
| 5 | [Group Comparison I: t-tests](https://liascript.github.io/course/?https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-WiSe2024-25/main/Part%201-%20Group%20Comparison%20in%20Quantitative%20Research%20Using%20R%20%28T-test%29.md) | Assumption checks, one-sample, independent and paired t-tests with worked R examples |
| 6 | [Group Comparison II: ANOVA & non-parametric tests](https://liascript.github.io/course/?https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-WiSe2024-25/main/Part%202%20-%20Group%20Comparison%20in%20Quantitative%20Research%20Using%20R.md) | One-way, two-way and repeated-measures ANOVA, post-hoc tests, MANOVA, chi-squared, Mann-Whitney U, Kruskal-Wallis, Fisher's exact test |
| 7 | [Correlation & Regression Analysis](https://liascript.github.io/course/?https://raw.githubusercontent.com/AEMSabbirRifat/QuRM-WiSe2024-25/main/Correlation%20%26%20Regression%20Analysis%20in%20Quantitative%20Research.md) | Pearson vs. Spearman, simple and multiple linear regression, checking model assumptions |

Each lesson ends with a **hands-on exercise**: students formulate a hypothesis on their own dataset, run the test in R, and interpret the result, using AI assistants as a tutor and then critically checking their feedback.

## ✨ Teaching approach

- **Active learning:** short concept slides alternate with in-class tasks, quizzes and peer discussion.
- **Real data:** exercises use the course's own survey data and R's built-in datasets (`airquality`, `mtcars`, `sleep`).
- **AI-literate:** students are encouraged to use AI tools step by step, then verify and justify every result.
- **Open by default:** everything is reusable Markdown under version control, ready to be adapted by other teachers.

## 🔧 Recent maintenance (2026)

- Restored lesson images that pointed to a deleted repository; they now load from the team's [Quantitative_Methods_with_R](https://github.com/OVGU-VET-TechEd/Quantitative_Methods_with_R) repository.
- Added worked R code to the previously empty t-test and correlation slides.
- Fixed the video slide in the descriptive-analysis lesson, a copy-paste error in the correlation exercise, and typos.
- Removed an old audio test file.

> Known gap: three diagrams in lesson 7 were lost with the old repository. The lesson still works without them.

## 🧑‍🏫 Want to reuse or adapt this course?

1. Fork the repository.
2. Edit any `.md` file. The [LiaScript docs](https://liascript.github.io/course/?https://raw.githubusercontent.com/liaScript/docs/master/README.md) explain the syntax.
3. Open `https://liascript.github.io/course/?<raw-URL-of-your-file>` to see your version live.

To export a lesson as a PDF or a SCORM package for Moodle/ILIAS, see my one-click [LiaScript export pipeline](https://github.com/AEMSabbirRifat/automation-test-1).

---

### 📬 About me

I'm **Sabbir Rifat**, a quantitative researcher and marketing/business analyst at Otto von Guericke University Magdeburg. I design data-driven courses, analyse survey data in R, and build AI-supported learning and automation workflows.
Looking for a research assistant, an analyst, or support with course design and statistics? **[a.e.m.sabbirrifat@gmail.com](mailto:a.e.m.sabbirrifat@gmail.com)** · [LinkedIn](https://www.linkedin.com/in/aemsabbirrifat) · [Portfolio](https://scaleupwithsabbir.github.io/)
