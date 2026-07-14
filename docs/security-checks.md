# Security Checks
## Проверка секретов

Для поиска случайно опубликованных секретов в репозитории используется **Gitleaks**.
Проверка выполняется автоматически через GitHub Actions.


## Проверка файловой системы и Docker образов

В рамках проекта выполнялись:
- проверка файловой системы проекта;
- анализ Docker-образа DefectDojo.


## Интеграция с CI/CD

Security Checks реализованы в GitHub Actions.

Workflow:
.github/workflows/security-pipeline.yml

Pipeline запускается при:

- push в ветку main;
- ручном запуске workflow.

В рамках проверки выполняются:

- Gitleaks — поиск секретов;
- Semgrep — SAST анализ;
- Trivy — проверка безопасности.
