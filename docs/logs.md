### Step 0 - Подготовка окружения
- • 0.1 Создан GitHub-репозиторий.
- • 0.2 Настроен Git.
- • 0.3 Создан SSH-ключ ED25519.
- • 0.4 SSH-ключ добавлен в GitHub.
- • 0.5 Проверено подключение к GitHub.
- • 0.6 Инициализирован локальный Git-репозиторий.
- • 0.7 Подключен удаленный origin.
- • 0.8 Основная ветка переименована в main.

### Скриншоты выполнения 0
- [Создание GitHub-репозитория](../screenshots/step-0/git.JPG)
- [Настройка GitHub (основная ветка)](../screenshots/step-0/git-settings.JPG)
- [Создание SSH-ключа ED25519](../screenshots/step-0/ssh.JPG)
- [Добавление SSH-ключа в GitHub](../screenshots/step-0/git-settings-ssh.JPG)
- [Настройка Git и подключение удаленного репозитория](../screenshots/step-0/connect-git.JPG)
- [Проверка подключения к GitHub по SSH](../screenshots/step-0/test-git-connect.JPG)


### Step 1 — Запуск DefectDojo
- • 1.1 Проверены Docker и Docker Compose.
- • 1.2 Проверено отсутствие запущенных контейнеров.
- • 1.3 Проверены свободные порты `8080`, `8443`, `5432`, `6379`.
- • 1.4 Выполнен запуск DefectDojo через `docker compose up`.
- • 1.5 Проверены запущенные сервисы командой `docker compose ps`.
- • 1.6 Получен пароль администратора из логов `initializer`. (Пароль использовался для первого входа, после чего был заменен на личный.)
- • 1.7 Выполнен вход в веб-интерфейс DefectDojo по адресу `http://localhost:8080`.
- • 1.8 Создан Asset для хранения результатов
- • 1.9 Создан Engagement для объединения результатов

### Скриншоты выполнения 1
- [Docker и Docker Compose](../screenshots/step-1/docker-version.JPG)
- [Проверка портов](../screenshots/step-1/ports.JPG)
- [Запуск DefectDojo через Docker Compose](../screenshots/step-1/docker-compose-up.JPG)
- [Проверка сервисов DefectDojo](../screenshots/step-1/docker-compose-ps.JPG)
- [Проверка логов initializer](../screenshots/step-1/initializer-pass.JPG)
- [Вход в веб-интерфейс DefectDojo](../screenshots/step-1/defectdojo-localhost8080.JPG)
- [Создание asset](../screenshots/step-1/add-asset-defectdojo.JPG), [Asset done](../screenshots/step-1/add-asset-defectdojo-done.JPG)
- [Создание Engagement](../screenshots/step-1/add-engagements-defectdojo.JPG), [Engagement done](../screenshots/step-1/engagements-done.JPG)


Step 2 — SAST и импорт в DefectDojo
- • 2.1 Установлен Semgrep через `pipx`.
- • 2.2 Выполнено тестовое сканирование проекта DefectDojo.
- • 2.3 Первичный результат составил 991 finding.
- • 2.4 После исключения директории `unittests` результат сократился до 44 findings.
- • 2.5 Отчет Semgrep успешно импортирован в DefectDojo.
- • 2.6 Проверено, что после перезапуска Docker Compose данные DefectDojo сохранились.

### Скриншоты выполнения 2
- [Установка Semgrep](../screenshots/step-2/semgrep-install.JPG)
- [Первичное сканирование проекта DefectDojo - 991 findings](../screenshots/step-2/semgrep-scan-991.JPG)
- [Повторное сканирование после исключения директории unittests - 44 findings](../screenshots/step-2/semgrep-scan-44.JPG)
- [Формирование JSON-отчета Semgrep](../screenshots/step-2/semgrep-scan-to-json.JPG)
- [Импорт отчета Semgrep в DefectDojo](../screenshots/step-2/test_semgrep.JPG)
- [Проверка сохранения данных после перезапуска Docker Compose](../screenshots/step-2/report_semgrep.png)


Step 3 — GitHub Actions
- • 3.1 Создан workflow `.github/workflows/security-pipeline.yml`.
- • 3.2 Настроен автоматический запуск pipeline при push в ветку `main`.
- • 3.3 В pipeline добавлены проверки Gitleaks, Semgrep и Trivy.
- • 3.4 Выполнен первый тестовый запуск GitHub Actions.
- • 3.5 Обнаружена проблема с `semgrep-action`.
- • 3.6 Semgrep заменен на установку через `pip` и запуск через CLI.
- • 3.7 Повторный запуск GitHub Actions завершился успешно.


Step 4 — Trivy Filesystem и DefectDojo
- • 4.1 Выполнено файловое сканирование проекта с помощью Trivy.
- • 4.2 Отчет сохранен в формате JSON.
- • 4.3 Создан Test типа Trivy Scan в DefectDojo.
- • 4.4 Отчет Trivy Filesystem успешно импортирован.
- • 4.5 Проверено отображение найденных уязвимостей в DefectDojo.


Step 5 — Trivy Image Scan
- • 5.1 Выполнено сканирование Docker-образа DefectDojo.
- • 5.2 Выполнен анализ уязвимостей Docker-образа.
- • 5.3 Отчет сохранен в формате JSON.
- • 5.4 Создан Test типа Trivy Scan в DefectDojo.
- • 5.5 Отчет Trivy Image успешно импортирован.
- • 5.6 Проверено отображение найденных уязвимостей контейнера в DefectDojo.


Step 6 — VPS Deployment

- • 6.1 Получен VPS для развертывания.
- • 6.2 Развернут DefectDojo через Docker Compose.
- • 6.3 Выполнен запуск сервисов DefectDojo.
- • 6.4 Проверена доступность веб-интерфейса.


Step 7 — DefectDojo Import
- • 7.1 Импортированы результаты Semgrep.
- • 7.2 Импортированы результаты Trivy.
- • 7.3 Импортированы результаты OWASP ZAP.
