# CI/CD Pipeline
## Общая схема

GitHub → GitHub Actions → Security Checks → Reports → DefectDojo (VPS)


## GitHub Actions

Описание workflow:

Файл:
.github/workflows/security-pipeline.yml


Триггер:
push в main


## Этапы pipeline
### 1. Code

Получение исходного кода из GitHub репозитория для дальнейшего выполнения проверок.


### 2. Gitleaks

Поиск секретов.


### 3. Semgrep

SAST анализ.


### 4. Trivy

Проверка зависимостей, файловой системы и Docker-образов.


### 5. OWASP ZAP

Динамический анализ запущенного веб-приложения (DAST).


## Deployment

Развертывание DefectDojo через Docker Compose на VPS.
