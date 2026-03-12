# ML System Design — ResumeMatching

![ML System Design](https://img.shields.io/badge/ML-System%20Design-blue)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Vector DB](https://img.shields.io/badge/Vector%20DB-Qdrant-orange)
![License](https://img.shields.io/badge/License-Apache%202.0-green)

Этот репозиторий содержит **ML System Design документ** для сервиса **ResumeMatching** — системы автоматического сопоставления резюме и вакансий.

Документ описывает проектирование ML-системы для решения задачи **semantic matching и поиска кандидатов** в рекрутинге.

---

## Обзор

Система построена по двухэтапной архитектуре поиска кандидатов:

Система построена по двухэтапной архитектуре обработки и поиска кандидатов.

**1. Обработка и структурирование данных**

- извлечение текста из PDF-резюме  
- извлечение **именованных сущностей** (навыки, опыт, образование, позиция, город)  
- **структурирование документов** резюме и вакансий  
- **сопоставление резюме и вакансии 1-к-1** для оценки релевантности кандидата

**2. Semantic retrieval**

- bi-encoder генерирует embeddings резюме и вакансий  
- embeddings сохраняются в **Qdrant vector database**  
- выполняется поиск наиболее похожих кандидатов

**3. Reranking**

- cross-encoder оценивает релевантность пары *(резюме, вакансия)*  
- формируется итоговый рейтинг кандидатов

---

## Архитектура системы

![Architecture](diagrams/arch.png)

---

## ML pipeline

![ML pipeline](diagrams/ml_pipe1.png)

---

## Пользовательский сценарий

![User flow](diagrams/user_path.png)

---

## Документ

Полное описание системы находится в документе:

**[ml_system_design_doc.md](ml_system_design_doc.md)**

Документ включает:

- постановку задачи  
- ML pipeline  
- обучение моделей  
- архитектуру системы  
- метрики качества  
- пилот и внедрение

---

## Назначение репозитория

Репозиторий создан как **пример ML System Design документа**.
