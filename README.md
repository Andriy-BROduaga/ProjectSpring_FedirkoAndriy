# ProjectSpring_FedirkoAndriy

### 1. Функціональні вимоги (Functional Requirements)

#### Основні функції:
1. **Створення завдань (Tasks)**:
    - Користувач може створити нове завдання з вказівкою назви, опису, дати та часу початку, дати та часу закінчення, пріоритету.
2. **Редагування завдань**:
    - Користувач може редагувати існуюче завдання (змінювати назву, опис, дати, часи, пріоритет).
3. **Видалення завдань**:
    - Користувач може видалити завдання.
4. **Перегляд списку завдань**:
    - Користувач може переглядати список своїх завдань за день, тиждень або місяць.
5. **Нагадування**:
    - Система повинна мати можливість надсилати нагадування користувачеві за певний час до початку завдання.
6. **Категорії та мітки**:
    - Користувач може додавати категорії та мітки до завдань для кращої організації.

### 2. Поведінка системи (System Behaviors)

1. **Авторизація та аутентифікація**:
    - Система повинна перевіряти користувача при вході через логін та пароль або використовуючи OAuth.
2. **Створення та зберігання завдань**:
    - При створенні нового завдання, система повинна зберігати його в базі даних.
3. **Редагування та оновлення завдань**:
    - Коли користувач редагує завдання, система повинна оновлювати відповідні записи в базі даних.
4. **Видалення завдань**:
    - При видаленні завдання, система повинна видаляти відповідний запис з бази даних.
5. **Перегляд завдань**:
    - Система повинна генерувати список завдань на основі заданих користувачем критеріїв (день, тиждень, місяць) і відображати його.
6. **Нагадування**:
    - Система повинна мати механізм для надсилання сповіщень (можливо, через email або push-сповіщення) відповідно до налаштувань користувача.
7. **Обробка категорій та міток**:
    - Система повинна зберігати та обробляти категорії та мітки, щоб користувач міг ефективно їх використовувати.

### 3. REST API кінцеві точки (REST API Endpoints)

#### Авторизація та аутентифікація
1. **POST /api/auth/login**:
    - Вхід користувача. Приймає `username` та `password`. Повертає токен аутентифікації.
2. **POST /api/auth/register**:
    - Реєстрація нового користувача. Приймає `username`, `email` та `password`.

#### Завдання (Tasks)
1. **GET /api/tasks**:
    - Отримати список завдань користувача. Приймає параметри фільтрації (дата, пріоритет, категорії тощо).
2. **POST /api/tasks**:
    - Створити нове завдання. Приймає дані завдання (`title`, `description`, `start_time`, `end_time`, `priority`, `category`, `tags`).
3. **GET /api/tasks/{id}**:
    - Отримати деталі конкретного завдання за його `id`.
4. **PUT /api/tasks/{id}**:
    - Оновити інформацію про завдання за його `id`. Приймає оновлені дані завдання.
5. **DELETE /api/tasks/{id}**:
    - Видалити завдання за його `id`.

#### Категорії та мітки (Categories and Tags)
1. **GET /api/categories**:
    - Отримати список всіх категорій користувача.
2. **POST /api/categories**:
    - Створити нову категорію. Приймає `name` категорії.
3. **DELETE /api/categories/{id}**:
    - Видалити категорію за її `id`.

4. **GET /api/tags**:
    - Отримати список всіх міток користувача.
5. **POST /api/tags**:
    - Створити нову мітку. Приймає `name` мітки.
6. **DELETE /api/tags/{id}**:
    - Видалити мітку за її `id`.

#### Нагадування (Reminders)
1. **POST /api/reminders**:
    - Створити нове нагадування. Приймає `task_id` та `reminder_time`.
2. **DELETE /api/reminders/{id}**:
    - Видалити нагадування за його `id`.

Цей підхід забезпечує повний функціонал для планування робочого дня, включаючи управління завданнями, нагадуваннями, категоріями та мітками.
