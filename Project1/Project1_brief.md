# 🧠 Social Learning Task — Reimplementation Project (Based on Henco et al., 2020)

## 🎯 Project Overview
This project challenges your team to **recreate the probabilistic social and non-social learning task** described in  
**Henco et al. (2020), _PLOS Computational Biology_**.

Your goal is to design and implement a behavioral experiment that can **reliably collect participant data** suitable for later modeling with the **Hierarchical Gaussian Filter (HGF)**.  

This project is as much about **building a robust experiment** as it is about **working effectively as a team** using good coding and project management practices.

---

## 🧩 Objectives
- Implement a working behavioral task inspired by *Henco et al. (2020)*.  
- Ensure the task runs **smoothly and without crashes**.  
- Collect **structured, high-quality behavioral data** (ready for modeling).  
- Maintain **modular, well-documented code**.  
- Use **Git** for transparent and collaborative development.  
- Present your team’s workflow, decisions, and results clearly.

---

## ⚙️ Technical Requirements
- **Language:** Python (PsychoPy or Pygame recommended) or MATLAB  
- **Output:** One `.csv` or `.txt` log file per participant, including: trial, phase_type, cue_type, gaze_direction, chosen_card, correct_card, reward, response_time, accuracy
- **Structure:**
- `/src` → code modules  
- `/data` → raw log files  
- `/docs` → documentation & presentation  
- `/config` → optional parameter settings  

---

## 📈 Key Performance Indicators (KPI)

These are the **core success metrics** for evaluating your project:

| Area | KPI Description |
|------|-----------------|
| **1. Task Functionality** | The task runs without errors, follows the described experimental structure, and transitions correctly between stable/volatile phases. |
| **2. Data Quality** | Data logs contain complete, consistent, and interpretable information for each trial (no missing or corrupted values). |
| **3. Code Quality** | Code is modular, readable, and documented (functions, parameters, and outputs clearly explained). |
| **4. Team Collaboration** | Git is used effectively — branches, commits, and merge requests show collaborative and organized workflow. |
| **5. Documentation & Presentation** | README and team presentation clearly explain how the task works, how the team collaborated, and lessons learned. |

> The **most important KPI** is that the **task functions correctly and reliably collects usable behavioral data**.

---

## 🧑‍💻 Collaboration & Version Control
Each team should:
1. Create a shared Git repository.  
2. Use **branches per feature or developer**.  
3. Write **meaningful commit messages**.  
4. Use **merge requests (pull requests)** for code review.  
5. Tag a final release (`v1.0`) when the project is complete.  

---

## 📄 Deliverables
1. **Functional task code** (ready to run).  
2. **Example output data** (at least 5 simulated or pilot participants).  
3. **README.md** explaining setup, dependencies, and how to run the task.  
4. **Team presentation (10–15 min)** summarizing:
 - Task design and implementation choices  
 - Git workflow and team roles  
 - Challenges and solutions  
 - Live demo or recorded run of the task  

---

## 📚 Reference
> Henco, L., Diaconescu, A.O., Lahnakoski, J.M., et al. (2020).  
> *Aberrant computational mechanisms of social learning and decision-making in schizophrenia and borderline personality disorder.*  
> PLOS Computational Biology, 16(9): e1008162.  
> [https://doi.org/10.1371/journal.pcbi.1008162](https://doi.org/10.1371/journal.pcbi.1008162)

---

## 💬 Note
Reading and understanding the original paper is **part of the assignment**.  
You are expected to extract the task structure and design logic from the article.

---

## 💡 Tip
Aim for a **scientifically faithful, technically reliable, and team-driven** implementation.  
A perfectly coded but non-functional task scores lower than a simple one that **runs smoothly and collects clean data**.
