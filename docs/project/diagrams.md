# Диаграммы

## Диаграмма последовательности

```mermaid
sequenceDiagram
    actor User as Пользователь
    participant App as Приложение
    participant AI as ИИ-модель

    User->>App: Отправить текст и выбрать длину
    App->>App: Проверить текст
    alt Текст корректный
        App->>AI: Передать текст и настройки
        AI-->>App: Вернуть пересказ
        App-->>User: Показать результат
    else Пустой текст
        App-->>User: Сообщение об ошибке
    end
```

## Диаграмма классов

```mermaid
classDiagram
    class User {
        +int id
        +string name
    }
    class TextDocument {
        +int id
        +string content
    }
    class SummaryRequest {
        +int id
        +string length
        +string status
    }
    class SummaryResult {
        +int id
        +string summary
    }
    User "1" --> "*" SummaryRequest : creates
    TextDocument "1" --> "*" SummaryRequest : source
    SummaryRequest "1" --> "0..1" SummaryResult : produces
```