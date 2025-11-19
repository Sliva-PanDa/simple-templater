# Простой шаблонизатор (ЛР №3)

Простое консольное Java-приложение, которое генерирует итоговый текст на основе файла-шаблона и файла-данных.

## Технологии
- Java 17
- Gradle
- JUnit 5 (для тестов)
- JaCoCo (для анализа покрытия кода)
- GitHub Actions (для CI/CD)

## Пример работы

**Файл шаблона (`template.txt`):**
```
Hello, ${user.name}!
Your order ${order.id} is confirmed.
```

**Файл данных (`data.properties`):**
```properties
user.name=Bob
order.id=A-123
```

**Результат выполнения:**
```
Hello, Bob!
Your order A-123 is confirmed.
```

## Сборка проекта

Для сборки проекта используйте Gradle Wrapper:
```bash
./gradlew build
```
Собранный исполняемый JAR-файл появится в директории `build/libs/`.

## Конфигурация проекта

Конфигурация приложения осуществляется через файл `app.properties`, который должен находиться в корне проекта.

- `template.file.path` - путь к файлу шаблона.
- `data.file.path` - путь к файлу с данными.
- `data.format` - формат файла данных. Может быть `PROPERTIES` или `JSON`.

**Пример `app.properties`:**
```properties
template.file.path=./examples/template.txt
data.file.path=./examples/data.properties
data.format=PROPERTIES
```

## Запуск тестов

Для запуска тестов и генерации отчета о покрытии кода выполните:
```bash
./gradlew test jacocoTestReport
```
Отчет о покрытии будет доступен в `build/reports/jacoco/index.html`.

## Запуск приложения

После сборки проекта вы можете запустить его следующей командой:
```bash
java -jar build/libs/simple-templater-1.0.0.jar
```
Убедитесь, что файл `app.properties` настроен корректно.