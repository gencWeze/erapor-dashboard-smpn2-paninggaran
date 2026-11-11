# 📊 e-Raport Dashboard: SMP Negeri 2 Paninggaran

> A student report-card dashboard I developed for **SMP Negeri 2 Paninggaran** (Pekalongan Regency) during my KKN community-service program in 2023. Teachers enter grades into one spreadsheet, and a **Google Looker Studio** dashboard turns them into school-wide summaries and **per-student, per-subject progress** that teachers and parents can follow. I also wrote a **guidebook** so the school could keep the dashboard updated after I left.

![Dashboard overview](assets/dashboard-summary.png)

🔗 **Live demo (dummy data):** [[ISI: link Looker Studio versi data dummy]]

> ⚠️ **About the data:** everything in this repository uses **fictional data** (made-up names, IDs and grades). Any real student records belong to the school and are not published.

---

## 📌 Context

| | |
|---|---|
| **Program** | KKN Tim II, Universitas Diponegoro |
| **Location** | Tenogo Village, Paninggaran District, Pekalongan Regency, Central Java |
| **Period** | 3 July – 17 August 2023 |
| **Partner** | SMP Negeri 2 Paninggaran |
| **Users** | School operator, teachers, parents |
| **Tools** | Google Sheets / Excel, Google Looker Studio (formerly Data Studio), Canva |

## ❓ Problem

SMP Negeri 2 Paninggaran is the **only junior high school in Tenogo Village**, and digital tools were barely used there. Grades lived in scattered files, so:
- the school had **no quick overview** of students and results by academic year, intake year or semester, and
- **parents had no easy way to follow** their child's progress, especially subject by subject.

My goals were to help school staff **get comfortable with digital tools** and give teachers and parents a simple way to **evaluate student progress per subject**.

## 🛠️ What I Built

### 1. Grade database (Google Sheets / Excel)
- **One row = one student in one semester**, with identity columns (academic year, class, semester, name, intake year, NISN, local NIS, gender)
- **12 subjects:** Religion (PAI), Civics (PPKN), Indonesian, Physical Education (PJOK), P5 project, English, Math, Science, Social Studies, ICT, Arts and Javanese
- Four scores per subject (**two daily scores, mid-term, final exam**). The **report score** and the **overall average** are calculated automatically with formulas.
- **Data validation** only accepts numbers above 0, so a blank never turns into a zero that drags averages down.

### 2. Dashboard (Google Looker Studio), two pages
| Page | What it shows |
|---|---|
| **Summary** | Filters for academic year, intake year and semester; scorecards for students by gender, total students and average report score; trend of students per academic year; student list |
| **Student** | Filters for academic year, class and NISN; average report score per academic year; **12 charts, one per subject**, showing a student's or class's progress over semesters |

### 3. Guidebook (Canva, 9 pages)
- How to read each page and use every filter
- Step-by-step instructions for the **operator** (enter new students at the start of each year, keep names and IDs consistent) and for **teachers** (enter scores as they come in, leave blanks instead of 0)
- 📄 [Read the guidebook](docs/Buku_Panduan_Dashboard.pdf) (internal links and student data redacted)

![Guidebook preview](assets/guidebook-preview.jpg)

## 📈 Outcome

- Delivered the database template, dashboard and guidebook to the school.
- The school **welcomed the tool**, and staff were introduced to updating and reading it themselves.
- [[CEK: The dashboard was later updated with 2023/2024 data, suggesting the school kept using it after KKN.]]

## 🖼️ Screenshots (dummy data)

| Summary page | Student page |
|---|---|
| ![](assets/dashboard-summary.png) | ![](assets/dashboard-student.png) |

## 🤝 Credits & My Contribution

This dashboard builds on an earlier e-Raport dashboard made by [[ISI: nama teman, atau "a fellow KKN team member"]], which I then modified and extended.

| Original version (by [[ISI: nama teman]]) | What I added or changed |
|---|---|
| [[ISI: mis. desain awal & halaman Summary]] | [[ISI: mis. halaman Student dengan 12 grafik per mapel]] |
| [[ISI]] | [[ISI: mis. struktur database, rumus Raport & validasi data]] |
| | Guidebook for the school operator and teachers |

## 🗂️ Repository Contents

```
├── data/
│   ├── sample_nilai_siswa.xlsx   # fictional dataset, same structure as the real database (with formulas & validation)
│   └── sample_nilai_siswa.csv    # same data as plain values
├── docs/
│   └── Buku_Panduan_Dashboard.pdf  # guidebook (redacted)
└── assets/                       # images for this README
```

## 💡 What I Learned

- **Design for the people who will maintain it.** A dashboard only helps if the school can keep it updated, so the guidebook mattered as much as the charts.
- **Stable IDs make or break tracking.** Following a student across semesters needs an ID that never changes. NISN should be stored as **text** (so leading zeros aren't lost) and entered the same way every semester. The sample dataset follows this rule.
- **Hand over ownership, not just access.** Data sources tied to a volunteer's personal account can break after the program ends. Next time I would move the files and data-source credentials to a school-owned account from day one.
- **Protect minors' data.** Student names and IDs never leave the school's own files. Portfolio versions use fictional data.

---

↩️ Back to [my profile](https://github.com/gencWeze)
