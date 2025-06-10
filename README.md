# Conditional App

Простое Spring Boot приложение, реализующее условную конфигурацию сервисов в зависимости от профиля (dev или production). Приложение соответствует принципам SOLID и DRY, обеспечивая чистый и расширяемый код.

## Описание

Приложение предоставляет REST API с эндпоинтом `/profile`, который возвращает текущий профиль системы. Выбор профиля (`DevProfile` или `ProductionProfile`) осуществляется через свойство `netology.profile.dev` в `application.properties` с использованием аннотации `@ConditionalOnProperty`.

## Технологии

* Spring Boot: 3.5.0
* Java: 17
* Gradle: 8.10
* Spring Web: для REST API
* Spring DevTools: для удобства разработки

## Установка и запуск

1. Склонируйте проект или создайте его в IntelliJ IDEA с Gradle.
2. Убедитесь, что установлена Java 17.
3. Откройте проект, дождитесь синхронизации Gradle.
4. Запустите `ConditionalAppApplication.java`.

## Проверка эндпоинта

Откройте в браузере или воспользуйтесь `curl`:

```bash
http://localhost:8080/profile
Результат:

Если netology.profile.dev=true, возвращает: Current profile is dev
Если netology.profile.dev=false, возвращает: Current profile is production
Настройка профиля
В файле src/main/resources/application.properties задайте:

properties

# Для DevProfile
netology.profile.dev=true
или

properties

# Для ProductionProfile
netology.profile.dev=false
Принципы
SOLID: Интерфейс SystemProfile и его реализации (DevProfile, ProductionProfile) обеспечивают модульность и независимость.
DRY: Конфигурация централизована в ProfileConfig.java с использованием @ConditionalOnProperty.
Чистый код с минимальной связностью и максимальной расширяемостью.
Автор
art4000xxx “`
