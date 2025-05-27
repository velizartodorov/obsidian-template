# Reflection talk DD-MM-YYYY template
---
## What went good in last year? ✅
---

### features/bugfixes ✨🐛

- conversion of EML/MSG files to PDFs
- integrating Textract as a text recognition service
- fixing Google OCR bugs
- splitting documents
- updating READMEs, refactoring

---

### infrastructure/architecture 🚀🏗

- Sonarqube clean-up for the audit commission
- Sonarlint coupling to Sonarqube lightning talk
- built C4 diagram

---

## What went bad in the last year? 😭

- tasks took longer than I expected
- team was busy, so couldn't always review my stuff properly
- sometimes the others had to finish my work
- sometimes I lose focus and refactor more than needed
    * [Nobody Ever Gets Credit for Fixing Problems that Never Happened](https://web.mit.edu/nelsonr/www/Repenning=Sterman_CMR_su01_.pdf)
      ![[productivity chart.png]]

---

### refactoring + implementation

```mermaid
gitGraph
   commit id: "commit1"
   commit id: "commit2"
   branch develop
   checkout develop
   commit id: "commit3"
   commit id: "commit4"
   commit id: "commit5"
   commit id: "commit6"
   commit id: "commit7"
   commit id: "commit8"
   commit id: "commit9"
   commit id: "commit10"
   commit id: "commit11"
   commit id: "commit12"
   commit id: "commit13"
   commit id: "commit14"
   commit id: "commit15"
   checkout main
   merge develop
   commit id: "commit16"
   commit id: "commit17"
```

---

### refa ctoring and implementation separate tickets

```mermaid
gitGraph
   commit id: "commit1"
   commit id: "commit2"
   branch feature1
   checkout feature1
   commit id: "commit3"
   commit id: "commit4"
   commit id: "commit5"
   commit id: "commit6"
   commit id: "commit7"
   commit id: "commit8"
   commit id: "commit9"
   checkout main
   merge feature1
   commit id: "commit10"
   branch refactoring
   checkout refactoring
   commit id: "commit11"
   commit id: "commit12"
   commit id: "commit13"
   commit id: "commit14"
   commit id: "commit15"
   commit id: "commit16"
   commit id: "commit17"
   checkout main
   merge refactoring
```

---

## What can we improve? 🚀

- Learning S3/DynamoDB/State machine in details
- Finishing the C4 diagram
- Work together with John towards improving internal procedures/architecture etc.

---

## What actions can we take? 📌

* ...

---

## Sidenotes 📚

Zen mode on TV: `Fn + F8`
Presentation mode on TV: `Fn + F9`