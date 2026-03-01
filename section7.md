# Розділ 7. Модель даних

Реляційна модель бази даних включає основні таблиці та зв'язки між ними.

## Таблиці

- **Users** (`id`, `name`, `email`, `password_hash`, `role`, `created_at`)
- **Books** (`id`, `title`, `author`, `isbn`, `publisher`, `year`, `category`, `status`)
- **Loans** (`id`, `user_id`, `book_id`, `issued_at`, `due_date`, `returned_at`, `fine`)
- **Reservations** (`id`, `user_id`, `book_id`, `reserved_at`, `status`)
- **Reports** (`id`, `type`, `generated_at`, `params`)
- **Notifications** (`id`, `user_id`, `message`, `sent_at`, `status`)

## Відносини

- `Users` 1—* `Loans` (кожен користувач може мати багато книг)
- `Books` 1—* `Loans` (книга може бути видана багато разів, але одночасно лише в одному записі відкритої видачі)
- `Users` 1—* `Reservations`
- `Books` 1—* `Reservations`