# Flutter Interview

<!-- markdownlint-disable MD013 MD033 -->

![Flutter Interview](https://github.com/p0dyakov/flutter_interview/assets/80569772/68dccc7f-b4f2-4eca-932a-8f9fe5559b5f)
[ENGLISH VERSION](https://github.com/p0dyakov/flutter_interview/blob/main/README_EN.md)

**Репозитории:** [Flutter Interview](https://github.com/p0dyakov/flutter_interview), [Flutter Roadmap](https://github.com/p0dyakov/flutter_roadmap), [Flutter Acrticles](https://github.com/p0dyakov/flutter_articles), [Flutter Best Packages](https://github.com/p0dyakov/flutter_best_packages), [Flutter Tools](https://github.com/p0dyakov/flutter_tools)  

<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

- [Общие](#general)
  - [ООП](#-1)
  - [SOLID](#solid)
  - [Git](#git)
    - [Git Flow](#git-flow)
    - [Trunk Based](#trunk-based)
    - [Merge vs Rebase](#merge-vs-rebase)
    - [Cherry-pick](#cherry-pick)
    - [Pull vs Fetch](#pull-vs-fetch)
    - [Reset vs Revert](#reset-vs-revert)
  - [Базы данных](#database)
    - [Реляционные базы данных](#relation-db)  
    - [Нереляционные базы данных](#non-relation-db)
    - [Нормализация баз данных](#normalization-db)
  - [Структуры данных](#-)
  - [Императивное и декларативное программирование](#--1)
  - [Стек и куча](#--2)
  - [DAO, DTO, VO, BO](#dao-dto-vo-bo)
  - [DI и Service Locator](#di-service-locator)
  - [Секреты в мобильной аппе](#mobile-secrets)
- [Dart](#dart)
  - [final и const](#final-const)
  - [Модификаторы классов (`abstract`, `base`, `interface`, `final`, `sealed`)](#class-modifiers)
  - [JIT и AOT](#jit-aot)
  - [Hot Restart и Hot Reload](#hot-restart-hot-reload)
  - [HashCode](#hashcode)
  - [Extension](#extension)
  - [Mixin](#mixin)
  - [Sound Null Safety](#sound-null-safety)
  - [Система типов](#--3)
  - [Late](#late)
  - [Generics](#generics)
  - [Dart VM](#dart-vm)
  - [Зоны](#-2)
  - [Типы ошибок](#--4)
  - [Правила именования](#--5)
  - [Never](#never)
  - [Covariant](#covariant)
  - [Аннотации](#-3)
  - [int8, uint8, int16, uint16...](#int8-uint8-int16-uint16)
  - [Future](#future)
  - [Конструкторы Future](#-future)
  - [Await под капотом](#await-)
  - [Event Loop](#event-loop)
  - [Completer](#completer)
  - [Stream](#stream)
  - [Генераторы (sync* / async*)](#-sync-async)
  - [Многопоточность в Dart и Flutter](#-dart-flutter)
  - [Isolate](#isolate)
  - [Compute](#compute)
  - [Проблемы многопоточности](#--6)
- [Flutter](#flutter)
  - [Stateless и Stateful виджеты](#stateless-stateful-)
  - [Жизненный цикл Stateful виджета](#-stateful-)
  - [BuildContext](#buildcontext)
  - [InheritedWidget](#inheritedwidget)
  - [Деревья](#-4)
  - [Widget](#widget)
  - [Element](#element)
  - [RenderObject](#renderobject)
  - [Виды виджетов](#--7)
  - [Виды элементов](#--8)
  - [Жизненный цикл Element-а](#-element-)
  - [GlobalKeys](#globalkeys)
  - [LocalKeys](#localkeys)
  - [Устройство Flutter под капотом](#-flutter-)
  - [Модель выполнения во Flutter](#-flutter)
  - [CustomPaint](#custompaint)
  - [WidgetsFlutterBinding](#widgetsflutterbinding)
  - [Bindings](#bindings)
  - [Каналы платформы](#--9)
  - [Режимы сборки](#--10)
  - [Package и Plugin](#package-plugin)
  - [FFI Plugin](#ffi-plugin)
  - [Этапы анимации](#--11)
  - [Виды анимаций](#--12)
  - [Что такое Tween](#-tween)
  - [Tween анимации](#tween-)
  - [Построение кадра](#--13)
  - [Расчёт макета](#--14)
  - [BuildOwner](#buildowner)
  - [PipelineOwner](#pipelineowner)
  - [Garbage Collector](#garbage-collector)
  - [Task Runners](#task-runners)
- [Архитектура](#-5)
  - [Основы архитектуры](#-6)
  - [Чистая архитектура](#--15)
  - [DDD](#ddd)
  - [Управление состоянием](#--16)
  - [Dependency Injection](#dependency-injection)
  - [Архитектурные патерны](#--17)
  - [Способы осуществления навигации](#--18)
  - [Хранение данных](#--19)
- [Тестирование](#-7)
  - [Виды тестов](#--20)
  - [TDD](#tdd)
- [Паттерны разработки](#--21)

<!-- TOC end -->

<!-- TOC --><a name="general"></a>

## Общие

<!-- TOC --><a name="-1"></a>

### ООП

`Объектно-ориентированное программирование`  — это парадигма программирования, основанная на представлении программы в виде совокупности объектов, каждый из которых является экземпляром определенного класса, а классы образуют иерархию наследования.

- `Абстракция`
Моделирование взаимодействий сущностей в виде абстрактных классов и интерфейсов для представления системы  
- `Инкапсуляция`
Объединение данных и методов, работающих с ними, в классе  
- `Наследование`
Создания новых классов на основе существующих  
- `Полиморфизм`
Использование объектов с одинаковым интерфейсом без информации о типе и внутренней структуре объекта  

[Подробнее](https://habr.com/ru/post/463125/)

---
<!-- TOC --><a name="solid"></a>

### SOLID

- `Single Responsibility Principle (Принцип единственной ответственности)`
У класса не должно быть более одной причины для изменения.
[Источник](https://objectmentor.com/resources/articles/srp.pdf)
- `Open-Closed Principle (Принцип открытости-закрытости)`
Cущности должны быть открыты для расширения, но закрыты для модификации.
- `Liskov Substitution Principle (Принцип подстановки Барбары Лисков)`
Если класс является наследником, он должен уметь честно заменять родительский класс, не ломая поведение программы.
_Если подставили наследника вместо родителя, ничего не должно сломаться._
- `Interface Segregation Principle (Принцип разделения интерфейса)`
Клиенты не должны имплементировать логику, которую они не используют.
- `Dependency Inversion Principle (Принцип инверсии зависимостей)`
Модули верхних уровней не должны зависеть от модулей нижних уровней. Классы и верхних, и нижних уровней должны зависеть от одних и тех же абстракций (при чём абстракции не должны знать о деталях).
Зависеть нужно от абстракций, а не от конкретных классов.

---
<!-- TOC --><a name="git"></a>

### Git

<!-- TOC --><a name="git-flow"></a>

#### Git Flow

Фича

1. `Начало новой фичи`. Создаём новую ветку `feature/future_name` из `develop`
2. `Завершение фичи`. Сливаем `feature/future_name` в `develop`, удаляем `feature/future_name`
3. `Начало релиза`. Создаём ветку релиза `release/vX.X.X`, ответляя от ветки `develop`
4. `Завершение релиза`. Ветка релиза `release/vX.X.X` сливается в `master`, релиз помечается тегом, ветка релиза сливается в `develop`, ветка релиза удаляется

Фикс

1. `Начало исправления`. От ветки `master` создаём `hotfix/fix_name`
2. `Завершение исправления`. Из ветки `hotfix/fix_name` исправление сливается в `develop` и `master`, ветка фикса удаляется

---
<!-- TOC --><a name="trunk-based"></a>

#### Trunk Based

Фича

1. `Начало новой фичи`. Создаём короткоживущую ветку feature/feature_name от main
2. `Разработка фичи.` Делаем маленькие коммиты, регулярно подтягиваем изменения из main
3. `Завершение фичи.` Как можно быстрее сливаем feature/feature_name обратно в main, ветку удаляем
4. `Незавершённая фича.` Если фича ещё не готова к показу пользователю, прячем её за feature flag или оставляем выключенной в коде

Релиз

1. `Подготовка релиза.` Отдельную долгоживущую release-ветку обычно не создаём
2. `Выпуск релиза.` Релизим прямо из main, нужный коммит помечаем тегом
3. `Стабильность main.` Ветка main всегда должна быть в рабочем состоянии и готова к релизу

Фикс

1. `Начало исправления.` Создаём короткую ветку fix/fix_name от main или фиксируем прямо в main, если процесс это позволяет
2. `Завершение исправления.` Быстро сливаем исправление в main, ставим тег новой версии и выкатываем релиз

---
<!-- TOC --><a name="merge-vs-rebase"></a>

#### Merge vs Rebase

1. Обе команды решают одну задачу. И merge, и rebase нужны, чтобы включить изменения из одной ветки в другую, но делают это по-разному.
2. Merge сохраняет историю как есть и обычно создаёт `merge commit`, который явно показывает, где ветки соединились.
3. Rebase переносит коммиты одной ветки поверх другой, из-за чего история выглядит более линейной и аккуратной.
4. Когда использовать merge. Используй merge, когда важно сохранить настоящую историю разработки и не переписывать уже опубликованные коммиты.
5. Когда использовать rebase. Используй rebase, когда хочешь обновить свою локальную feature-ветку относительно main и получить чистую линейную историю перед вливанием.

Главный риск rebase. rebase переписывает историю, поэтому его опасно делать на ветках, которые уже запушены и которыми пользуются другие разработчики.

1. Золотое правило для команды `git rebase` — никогда не использовать ее в публичных ветках.
2. Не используйте команду git rebase после создания пул-реквеста. Так как после создания PR ветка стала публичной что нарушает золотое правило.

##### Очень простая аналогия

`merge`

```“Вот моя отдельная ветка работы, давайте просто присоединим её к общей истории”```

`rebase`

```“Давайте сделаем вид, что я начинал работу не от старого коммита, а от самого свежего состояния”```

[Подробнее](https://www.atlassian.com/ru/git/tutorials/merging-vs-rebasing)

---
<!-- TOC --><a name="cherry-pick"></a>

#### Cherry pick

1. `Что делает`. `cherry-pick` берёт один конкретный коммит из другой ветки и применяет его в текущую ветку как новый коммит.
2. `Когда использовать.` Используй `cherry-pick`, когда нужно перенести не всю ветку целиком, а только одно нужное изменение. Например, отдельный фикс или маленький полезный коммит.
3. `Как работает.` Git берёт изменения из выбранного коммита и записывает их поверх текущей ветки, создавая новый коммит с другим SHA.

Типичный кейс. Часто используют, когда фикс попал в develop, но его нужно срочно забрать в main без мерджа всей ветки.

Риск. Если blindly делать `cherry-pick`, можно получить дублирование логики или конфликты, потому что переносится не контекст всей ветки, а только выбранный коммит.

`Главная идея.` `cherry-pick` — это точечный перенос коммита, а не объединение веток.

 Команде `git cherry-pick` можно назначить ряд опций.

 `-edit` - Если назначить команде опцию `-edit`, перед выборочным применением Git предложит указать сообщение коммита.

 `--no-commit` - При использовании опции `--no-commit` выборочное применение не создаст новый коммит, а переместит содержимое целевого коммита в рабочий каталог текущей ветки.

 `--signoff` - При выборочном применении опция `--signoff` добавляет строку с подписью в конце сообщения коммита

[Подробнее](https://www.atlassian.com/ru/git/tutorials/cherry-pick)

---
<!-- TOC --><a name="pull-vs-fetch"></a>

#### Pull vs Fetch

**Что делает fetch.**

`git fetch` забирает изменения с удалённого репозитория и обновляет удалённые ссылки локально, но не меняет твою текущую ветку и рабочую директорию.

**Что делает pull.**

`git pull` сначала делает `fetch`, а потом сразу пытается встроить изменения в текущую ветку, обычно через `merge`.

Главная разница. `fetch` только получает изменения и даёт тебе сначала их посмотреть, а `pul`l сразу подтягивает их в твою рабочую ветку. Поэтому fetch считается более безопасным и предсказуемым вариантом.

Важно помнить. git pull можно делать не только через merge: часто используют git pull --rebase, чтобы после fetch изменения встроились через rebase, а история осталась линейнее.

---
<!-- TOC --><a name="reset-vs-revert"></a>

#### Reset vs Revert

1. `Что делает reset.` `git reset` передвигает указатель текущей ветки назад и, в зависимости от режима, может также менять index и рабочую директорию. Это способ “откатить” локальную историю или снять изменения со staging.
2. `Что делает revert.` `git revert` не переписывает историю, а создаёт новый коммит, который отменяет изменения выбранного коммита.
3. `Главная разница.` `reset` меняет историю, а `revert` сохраняет историю и добавляет в неё “обратный” коммит. Поэтому `revert` обычно безопаснее для уже запушенных веток.
4. `Когда использовать reset.` Используй `reset`, когда работа локальная и нужно откатить, переподготовить или переупаковать коммиты до публикации.
5. `Когда использовать revert.` Используй `revert`, когда коммит уже попал в общую ветку и его нужно отменить без переписывания общей истории.
6. `Главный риск reset.` После `reset` можно потерять удобный доступ к коммитам; часто их ещё можно найти через reflog, но это уже аварийное восстановление.

##### Простая запоминалка

`reset` — откатить историю назад

`revert` — добавить коммит-отмену

---
<!-- TOC --><a name="database"></a>

### Базы данных

<!-- TOC --><a name="relation-db"></a>

#### Реляционные базы данных

**Реляционная база данных** — это база данных, где данные хранятся в виде таблиц, связанных между собой через ключи.

Связи между таблицами строятся через `Primary Key` и `Foreign Key`.

##### Основные свойства

1. таблицы
2. строгая схема (schema)
3. связи между таблицами
4. SQL язык запросов
5. ACID транзакции

---
<!-- TOC --><a name="non-relation-db"></a>

#### Нереляционные базы данных

NoSQL — это базы данных, которые не используют табличную модель.

Они могут хранить данные:

1. как документы
2. как ключ-значение
3. как граф
4. как колоночные структуры

---
<!-- TOC --><a name="normalization-db"></a>

#### Нормализация баз данных

`Нормализация` — это процесс структурирования данных, чтобы:

- убрать дублирование
- уменьшить аномалии обновления
- сделать данные консистентными

##### Нормальные формы

1NF — первая нормальная форма

- ячейки должны быть атомарными
- нельзя хранить списки внутри поля

2NF - вторя нормальная форма

- Таблица уже в 1NF
- все поля должны зависеть от всего первичного ключа

3NF - третья нормальная форма

- Таблица в 2NF
- нет транзитивных зависимостей

---
<!-- TOC --><a name="-"></a>

### Структуры данных

Структуры данных нужны для хранения данных в подходящем виде

- `Массивы`  
- `Стеки` (_LIFO_ - последний вошёл, первый вышел)
- `Очереди` (_FIFO_ - первый вошёл, первый вышел)
- `Связные списки`  
- `Деревья`
- `Графы`  
- `Хеш-таблицы`  

[Подробнее](https://habr.com/ru/company/alconost/blog/419685/)

---
<!-- TOC --><a name="--1"></a>

### Императивное и декларативное программирование

- `Императивный стиль` - описываем, **как** добиться желаемого результата  
- `Декларативный стиль` - описываем, **какой именно результат** нам нужен

---
<!-- TOC --><a name="--2"></a>

### Стек и куча

- `Стек` — это область оперативной памяти, в которой хранятся временные данные, таких как локальные переменные и адреса возврата функций. Объем памяти, выделенный под стек, ограничен. Стек работает в порядке LIFO  
- `Куча` — это область оперативной памяти, в которой хранятся данные, созданные во время выполнения программы. Куча используется для динамического выделения памяти для объектов, которые могут изменять размер во время выполнения программы. Размер кучи задаётся при запуске приложения, но, в отличие от стека, он ограничен лишь физически. Выделение памяти в куче происходит медленнее, чем в стеке.

---
<!-- TOC --><a name="dao-dto-vo-bo"></a>

### DAO, DTO, VO, BO

- `DAO (Data Access Object, объект доступа к данным)` — абстрактный интерфейс к какому-либо типу базы данных или иному механизму хранения  
- `DTO (Data Transfer Object, объект переноса данных)` - это объект для передачи данных (объектов без поведения) между слоями  
- `VO (Value Object, объект-значение)` ⎼ это объект без специальных методов, имеющий набор свойств (полей) примитивных типов данных или тоже Value object  
- `BO (Business Object, объект бизнеса)` - это объект, который представляют некую сущность из определенного «домена», то есть отрасли, для которой разработано приложение  

---
<!-- TOC --><a name="di-service-locator"></a>

### DI и Service Locator

- `DI` - передача зависимостей класса через параметры конструктора
- `Service Locator` - синглтон / класс с набором статических методов

Доступ к `Service Locator` может производиться из любого место в коде. В этом заключается его основной минус

---
<!-- TOC --><a name="mobile-secrets"></a>

### Секреты в мобильной аппе

- `Клиент недоверенный.` Всё, что попало в app bundle, APK, IPA, ресурсы или
  бинарник, потенциально извлекаемо. Мобильное приложение работает на
  устройстве пользователя, а значит не является доверенной средой.
- ``dart-define`` не сейф. Это способ передать build-time конфиг через
  compilation configuration environment, а не способ спрятать секрет.
- `App secrets` держим на backend. Настоящие секреты, вроде master API keys,
  signing secrets и service account credentials, не должны жить в клиенте.
  Клиенту лучше выдавать короткоживущие токены, а чувствительные вызовы
  проксировать через сервер.
- `User secrets` храним в secure storage. Токены, приватные ключи и другие
  пользовательские секреты нужно хранить через `Keychain` на iOS и
  `Keystore` на Android, а не в обычных файлах или preferences.
- `Публичные client keys` ограничиваем. Если ключ всё же должен жить в клиенте,
  ему режут scope: отдельный key на приложение и платформу, только нужные API,
  Android package name + signing certificate fingerprint, iOS bundle ID.
- `Obfuscation` не спасает. Она усложняет анализ, но не шифрует ресурсы и не
  превращает встроенный секрет в безопасный.

#### Источники

- [OWASP MASWE-0005: API Keys Hardcoded in the App Package](https://mas.owasp.org/MASWE/MASVS-AUTH/MASWE-0005/)
- [Android Developers: Insecure API usage](https://developer.android.com/privacy-and-security/risks/insecure-api-usage)
- [Dart API: String.fromEnvironment](https://api.dart.dev/dart-core/String/String.fromEnvironment.html)
- [Flutter Docs: Obfuscate Dart code](https://docs.flutter.dev/deployment/obfuscate)
- [Apple: Managing Keys, Certificates, and Passwords](https://developer.apple.com/library/archive/documentation/Security/Conceptual/cryptoservices/KeyManagementAPIs/KeyManagementAPIs.html)
- [Android Developers: Android Keystore system](https://developer.android.com/privacy-and-security/keystore)
- [Google Maps Platform: API security best practices](https://developers.google.com/maps/api-security-best-practices)

<!-- TOC --><a name="dart"></a>

## Dart

<!-- TOC --><a name="final-const"></a>

### final и const

- Если у локальной переменной нет инициализатора или тип неочевиден, тип лучше указать явно.
- `final` означает, что переменной можно присвоить значение только один раз. Это ограничение на переменную или ссылку, а не на способ создания объекта. Сам по себе `final` не означает ни переиспользование объекта, ни обязательное выделение новой памяти.
- Новый объект создаётся при вычислении `не-const` выражения. Например, `final a = [1, 2];` и `final b = [1, 2];` создадут два разных списка, хотя их содержимое одинаковое.
- `const` означает compile-time constant. Константные объекты канонизируются: одинаковые `const`-выражения могут ссылаться на один и тот же экземпляр. Например, `const a = [1, 2]; const b = [1, 2];` и `identical(a, b)` вернёт `true`.
- Важно: `final`-объект может быть изменяемым, если сам тип изменяемый. `const`-объект и его поля должны быть неизменяемыми.

То есть если попытаться изменить const массив, то будет ошибка выполнения.

Источники:
- [Dart docs: Variables](https://dart.dev/language/variables)
- [Effective Dart: Usage -> Variables](https://dart.dev/effective-dart/usage#variables)
- [Dart linter: unnecessary_final](https://dart.dev/tools/linter-rules/unnecessary_final)
- [Dart docs: Variables -> Final and const](https://dart.dev/language/variables#final-and-const)
- [Dart API: identical()](https://api.dart.dev/dart-core/identical.html)
- [Dart docs: Constructors -> Constant constructors](https://dart.dev/language/constructors#constant-constructors)

---
<!-- TOC --><a name="class-modifiers"></a>

### Модификаторы классов (`abstract`, `base`, `interface`, `final`, `sealed`)

- Начиная с Dart 3, модификаторы классов позволяют автору API явно ограничивать, можно ли тип создавать, наследовать, имплементировать или использовать как закрытую иерархию. Исключение - `abstract`: он был в Dart и раньше.
- Важно: ограничения `base` / `interface` / `final` / `sealed` в первую очередь относятся к коду вне библиотеки, где тип объявлен.

Короткая логика:

- `abstract` - сам тип нельзя создать.
- `interface` - можно `implements`, нельзя `extends`.
- `base` - можно `extends`, нельзя `implements`.
- `final` - нельзя ни `extends`, ни `implements`.
- `sealed` - закрытое семейство подтипов для exhaustive `switch`; сам тип не создаётся напрямую.

Шпора:

| Объявление | Создать экземпляр | `extends` вне библиотеки | `implements` вне библиотеки | Когда брать |
| --- | --- | --- | --- | --- |
| `class` | Да | Да | Да | Когда тип специально открыт для любого использования. |
| `abstract class` | Нет | Да | Да | Когда нужен базовый контракт или частичная реализация, но сам тип создавать нельзя. |
| `interface class` | Да | Нет | Да | Когда наружу нужен контракт, но не хочется разрешать наследование реализации. |
| `abstract interface class` | Нет | Нет | Да | Лучший аналог "чистого интерфейса" в Dart. |
| `base class` | Да | Да | Нет | Когда все подтипы обязаны реально наследовать твою реализацию и инварианты. |
| `abstract base class` | Нет | Да | Нет | Абстрактная база с общей реализацией, которую нельзя просто имплементировать. |
| `final class` | Да | Нет | Нет | Когда хочешь полностью закрыть внешнее подтипирование и безопасно развивать API. |
| `abstract final class` | Нет | Нет | Нет | Редкий вариант: нельзя создать и нельзя делать внешние подтипы. Обычно нужен редко. |
| `sealed class` | Нет | Нет | Нет | Когда нужен закрытый набор подтипов и исчерпывающий `switch` / pattern matching. |

Важные нюансы:

- У `base` есть transitivity: любой его потомок тоже должен быть помечен как `base`, `final` или `sealed`.
- `final` включает в себя ограничения `base`: он тоже запрещает внешнюю реализацию интерфейса и закрывает иерархию ещё сильнее.
- `sealed` не "заражает" потомков: ограничение на прямые подтипы действует только для самого `sealed`-типа.
- Если нужен тип, который можно использовать и как класс, и как миксин, смотри в сторону `mixin class`, `abstract mixin class`, `base mixin class` и `base mixin`.
- По официальной справке некоторые комбинации запрещены: например, нельзя сочетать `base`, `interface` и `final` вместе, а `sealed` не комбинируют с `abstract`, `base`, `interface` или `final`.

Источники:
- [Dart docs: Class modifiers](https://dart.dev/language/class-modifiers)
- [Dart docs: Class modifiers for API maintainers](https://dart.dev/language/class-modifiers-for-apis)
- [Dart docs: Class modifiers reference](https://dart.dev/language/modifier-reference)

---
<!-- TOC --><a name="jit-aot"></a>

### JIT и AOT

- `Just-in-time (JIT) компиляция` - это компиляция во время выполнения программы. В Flutter такой режим используется в `debug`: он нужен для быстрого цикла разработки, `hot reload` и удобной отладки.
- `JIT` оптимизирован в первую очередь под скорость разработки, а не под скорость выполнения, размер бинарника или деплой. Поэтому `debug`-сборки могут работать заметно медленнее, чем `profile` или `release`.
- `Ahead-of-time (AOT) компиляция` - это компиляция Dart-кода в нативный машинный код на этапе сборки. В Flutter на нативных платформах `AOT` используется для `profile` и `release` сборок.
- `AOT` даёт более быстрый старт приложения, более предсказуемую производительность и меньший размер итоговой сборки за счёт оптимизаций и `tree shaking`.
- Важно: формулировка про конкретные расширения файлов вроде `.so` и `.dylib` слишком упрощает картину и зависит от платформы и артефактов сборки, поэтому лучше говорить просто: Dart-код компилируется в нативный машинный код для целевой платформы.

Источники:
- [Flutter docs: Build modes](https://docs.flutter.dev/testing/build-modes)
- [Flutter docs: Architectural overview](https://docs.flutter.dev/resources/architectural-overview)
- [Flutter docs: Use the app size tool](https://docs.flutter.dev/tools/devtools/app-size)
- [Dart docs: Glossary -> JIT](https://dart.dev/resources/glossary#just-in-time-compilation-jit)
- [Dart docs: Glossary -> AOT](https://dart.dev/resources/glossary#aot)

---
<!-- TOC --><a name="hot-restart-hot-reload"></a>

### Hot Restart и Hot Reload

- `Hot Reload` загружает изменения в `Dart VM` и ребилдит дерево виджетов, сохраняя состояние. Не перезапускает `main()` и `initState()`
- `Hot Restart` загружает изменения в `Dart VM` и перезагружает всё приложение. Перезапускает `main()` и `initState()`. Состояние не сохраняется

---
<!-- TOC --><a name="hashcode"></a>

### HashCode

`hashCode` - это `int`-геттер у каждого объекта. Он представляет состояние объекта, которое участвует в сравнении через `==`.

Главное:

- по умолчанию `Object.hashCode` основан на identity объекта, так же как и стандартный `==` по умолчанию сравнивает объекты по identity;
- если переопределяешь `==`, нужно переопределить и `hashCode`, иначе объект будет некорректно работать в хэш-структурах данных;
- если `a == b`, то `a.hashCode` и `b.hashCode` обязаны быть одинаковыми;
- если хэш-коды одинаковые, это не значит, что объекты равны: коллизии допустимы;
- `hashCode` используется в хэш-коллекциях, например в стандартных `HashMap`, `LinkedHashMap`, `HashSet` и `LinkedHashSet`.

Обычно `hashCode` собирают из тех же полей, которые участвуют в `==`:
`int get hashCode => Object.hash(runtimeType, field1, field2);`

Для изменяемых классов кастомные `==` и `hashCode` опасны: если поле, влияющее на равенство, поменяется после добавления объекта в `Set` или использования как ключа `Map`, поведение коллекции станет непредсказуемым.

Источники:
- [Dart API: Object.hashCode](https://api.dart.dev/dart-core/Object/hashCode.html)
- [Dart API: Object.operator ==](https://api.dart.dev/dart-core/Object/operator_equals.html)
- [Dart API: Object.hash](https://api.dart.dev/dart-core/Object/hash.html)
- [Dart API: HashSet](https://api.dart.dev/dart-collection/HashSet-class.html)
- [Dart linter: hash_and_equals](https://dart.dev/tools/linter-rules/hash_and_equals)
- [Dart linter: avoid_equals_and_hash_code_on_mutable_classes](https://dart.dev/tools/linter-rules/avoid_equals_and_hash_code_on_mutable_classes)

---
<!-- TOC --><a name="extension"></a>

### Extension

`Extension` — это синтаксический сахар, который позволяет расширить существующий класс (добавить методы, операторы, сеттеры и геттеры)

---
<!-- TOC --><a name="mixin"></a>

### Mixin

`Mixin` - это способ переиспользовать реализацию в нескольких иерархиях классов. В отличие от обычного наследования, миксин не задаёт отношение "is-a", а просто добавляет классу готовые поля и методы.

Главное:

- миксин объявляется через `mixin` и подключается к классу через `with`;
- миксин может содержать методы, поля, геттеры/сеттеры и абстрактные члены;
- `mixin` не может иметь `extends`, а generative constructors в миксинах недопустимы;
- если миксину нужен доступ к API базового класса или к `super`, используют `on`;
- если у нескольких миксинов есть одноимённый метод, побеждает правый: `class C with A, B` возьмёт реализацию из `B`.

Пример с `on`:

```dart
class Animal {
  void move() => print('move');
}

mixin Flyer on Animal {
  void fly() {
    move();
    print('fly');
  }
}

class Bird extends Animal with Flyer {}
```

Стандартные миксины из коробки:

- `ListMixin`, `MapMixin`, `SetMixin` из `dart:collection` помогают быстро реализовать свои коллекции, переопределив минимальный набор методов.
- `SingleTickerProviderStateMixin` из Flutter удобен для `State` с одним `AnimationController`.
- `TickerProviderStateMixin` из Flutter нужен, когда в одном `State` несколько `AnimationController`.
- `AutomaticKeepAliveClientMixin` помогает сохранять состояние элементов в лениво строящихся списках.
- `WidgetsBindingObserver` позволяет получать события жизненного цикла приложения и системные уведомления.
- `RestorationMixin` помогает восстанавливать состояние `StatefulWidget`.

---
<!-- TOC --><a name="sound-null-safety"></a>

### Sound Null Safety

`Sound Null Safety` – это дополнение к языку Dart, которое усиливает систему типов, отделяя типы, допускающие значение `Null`, от типов, не допускающих значения `Null`. Это позволяет разработчикам предотвращать ошибки, связанные с `Null`.  

---
<!-- TOC --><a name="--3"></a>

### Система типов

<p align="left" width="100%">
    <img alt="Dart type system" src="https://github.com/p0dyakov/flutter_interview/assets/80569772/93afb575-ee46-46d0-9717-ea6894e6f1b3" width="30%"/>
</p>
С появлением null safety в Dart, иерархия классов и интерфейсов была изменена для учета новых требований по безопасности типов. Вот основные изменения:

1. **Добавление non-nullable типов**:
   - Non-nullable типы обозначают, что значение не может быть null.
   - Все существующие типы были разделены на non-nullable и nullable версии. Например, `int` стал `int` (non-nullable) и `int?` (nullable)

2. **Новый корень иерархии - "Object?"**:
   - Введен новый корневой класс `Object?`, который может быть null. В предыдущих версиях Dart, корневым классом был `Object`

3. **Изменения в иерархии ошибок**:
   - Введен новый класс `NullThrownError`, который представляет собой ошибку, возникающую при попытке выбросить `null` исключение

4. **`late` и `required`**:
   - Введены ключевые слова `late` и `required` для обозначения переменных, которые могут быть инициализированы позднее и обязательно должны быть проинициализированы при объявлении, соответственно.

---
<!-- TOC --><a name="late"></a>

### Late

`Late` - это ключевое слово в dart, которое позволяет объявить non-nullable переменную и при этом не установить для нее значение. Значение инициализируется только тогда, когда мы к нему обращаемся. 

Если обратиться в такой переменной до ее инициализации - получим LateInitializationError. 
Можно использовать в паре с `final` - `late final`

---
<!-- TOC --><a name="generics"></a>

### Generics

`Generics` - это параметризованные типы: тип принимает один или несколько параметров типа, например `List<String>` или `Map<String, int>`.

Зачем нужны `Generics`:

- дают `type safety`: например, в `List<String>` нельзя безопасно добавить `int`;
- уменьшают дублирование кода: вместо `UserCache`, `StringCache`, `IntCache` можно сделать один `Cache<T>`;
- позволяют писать более точные API и улучшать type inference;
- в Dart generic-типы `reified`, то есть информация о типе сохраняется во время выполнения.

Примеры:

Ограничение типа через `extends`:

```dart
class Repository<T extends Object> {}
```

Здесь `T extends Object` означает, что `T` должен быть non-nullable типом.

Источники:
- [Dart docs: Generics](https://dart.dev/language/generics)
- [Dart docs: The Dart type system -> Generic type assignment](https://dart.dev/guides/language/sound-problems#generic-type-assignment)

---
<!-- TOC --><a name="dart-vm"></a>

### Dart VM

`Dart VM (Dart Virtual Machine)` - это среда выполнения Dart на нативных платформах. Во Flutter она особенно важна в `debug`-режиме и во время разработки.

Базово `Dart VM`:

- выполняет Dart-код;
- управляет памятью и `garbage collector`;
- выполняет runtime-проверки типов;
- управляет `isolates`;
- предоставляет `JIT`, инкрементальную перекомпиляцию, отладку и метрики для инструментов разработки.

Именно поэтому `hot reload` в Flutter работает через обновление кода в работающей `Dart VM`.

Важно: на `web` Dart-код обычно не выполняется в `Dart VM`, а компилируется в `JavaScript` или `WebAssembly` и запускается в среде браузера.

---
<!-- TOC --><a name="-2"></a>

### Зоны

`Zone` - это контекст выполнения, который сохраняется через `async`-границы и позволяет менять поведение асинхронного кода без изменения самого этого кода.

Что дают зоны:

- перехват необработанных ошибок в асинхронном коде через `runZonedGuarded`;
- хранение `zone-local values`, которые доступны через `Zone.current[key]`;
- переопределение части поведения среды через `ZoneSpecification`, например `print`, `scheduleMicrotask`, таймеров и обработки ошибок;
- возможность добавлять обвязку вокруг выполнения callback-ов, что полезно для логирования, профилирования и трассировки.

Важно:

- весь Dart-код выполняется в какой-то зоне; по умолчанию это `Zone.root`;
- зона распространяется на асинхронные callback-и, зарегистрированные внутри неё;
- зоны особенно полезны для server-side кода, error tracking, request-scoped state и инструментов отладки.

Очень маленький пример:

```dart
runZonedGuarded(() {
  Future.microtask(() => throw Exception('boom'));
}, (error, stackTrace) {
  print('caught: $error');
});
```

Пример с `zone-local value`:

```dart
runZoned(() {
  print(Zone.current[#requestId]); // 42
}, zoneValues: {#requestId: 42});
```

Источники:
- [Dart docs: Zones](https://dart.dev/libraries/async/zones)
- [Dart API: Zone](https://api.dart.dev/dart-async/Zone-class.html)
- [Dart API: runZoned](https://api.dart.dev/dart-async/runZoned.html)
- [Dart API: runZonedGuarded](https://api.dart.dev/dart-async/runZonedGuarded.html)
- [Dart API: ZoneSpecification](https://api.dart.dev/dart-async/ZoneSpecification-class.html)

---
<!-- TOC --><a name="--4"></a>

### Типы ошибок

`Exception` - это общий класс для исключений, которые обычно возникают из-за ошибок в программе, и их можно обработать и восстановиться от них:

- DeferredLoadException
- FormatException
- IntegerDivisionByZeroException (помечен как устаревший)
- IOException
- FileSystemException
- PathNotFoundException
- HttpException
- RedirectException
- ProcessException
- SignalException
- SocketException
- StdinException
- StdoutException
- TlsException
- CertificateException
- HandshakeException
- WebSocketException
- IsolateSpawnException
- TimeoutException
- NullRejectionException

`Error` - это класс для ошибок, которые обычно не могут быть восстановлены, и они указывают на серьезные проблемы в программе или системе:

- OSError
- ArgumentError
- IndexError
- RangeError
- AssertionError
- AsyncError
- ConcurrentModificationError
- JsonUnsupportedObjectError
- JsonCyclicError
- NoSuchMethodError
- OutOfMemoryError
- RemoteError
- StackOverflowError
- StateError
- TypeError
- UnimplementedError
- UnsupportedError

---
<!-- TOC --><a name="--5"></a>

### Правила именования

- Переменные и константы - `lowerCamelCase`
- Классы, миксины, enum-ы - `UpperCamelCase`
- Файлы - `snake_case`

---
<!-- TOC --><a name="never"></a>

### Never

`Never` - это bottom type в Dart: у него нет значений, и он является подтипом любого другого типа.

На практике это означает:

- выражение типа `Never` не может успешно завершиться;
- такой код обязательно выбрасывает исключение, завершает выполнение или уходит в бесконечный цикл;
- `Never` полезен как возвращаемый тип для функций, которые точно не возвращают управление;
- `Never` помогает flow analysis и reachability analysis понимать, что код после такого вызова может быть недостижим.

Очень маленький пример:

```dart
Never fail(String message) {
  throw Exception(message);
}
```

Ещё один важный момент: у `throw`-выражения статический тип тоже `Never`.

Источники:
- [Dart docs: Glossary -> Bottom type](https://dart.dev/resources/glossary#bottom-type)
- [Dart docs: Understanding null safety -> Never for unreachable code](https://dart.dev/null-safety/understanding-null-safety#never-for-unreachable-code)
- [Dart API: Error.throwWithStackTrace](https://api.dart.dev/dart-core/Error/throwWithStackTrace.html)

---
<!-- TOC --><a name="covariant"></a>

### Covariant

`covariant` - это модификатор в Dart, который позволяет намеренно сузить тип параметра при переопределении метода, а также применяется к полям и сеттерам.

Важно:

- без `covariant` параметр в переопределённом методе обычно нельзя сужать до подтипа;
- с `covariant` анализатор разрешает такое сужение, а корректность аргумента дополнительно проверяется во время выполнения;
- `covariant` не нужен для возвращаемого типа: return type и так может быть более узким при переопределении.

Пример:

```dart
class Animal {}

class Mouse extends Animal {}

class Cat extends Animal {
  void chase(covariant Mouse mouse) {
    print('catch mouse');
  }
}
```

Чаще `covariant` встречается в базовом классе:

```dart
class Widget {}

class Button extends Widget {}

class Renderer {
  void render(covariant Widget widget) {}
}

class ButtonRenderer extends Renderer {
  @override
  void render(Button widget) {}
}
```

Источники:
- [Dart docs: The Dart type system -> Covariant parameters](https://dart.dev/guides/language/sound-problems#covariant-parameters)

---
<!-- TOC --><a name="-3"></a>

### Аннотации

`Аннотации` — это синтаксические метаданные, которые могут быть добавлены к коду. Другими словами, это возможность добавить дополнительную информацию к любому компоненту кода, например, к классу или методу. Аннотации всегда начинаются с символа `@` (`@override`, `@required`). Любой класс может служить аннотацией, если в нем определен const конструктор.

`package:meta` предоставляет `@Target` — можно указать допустимые «цели»:

``` dart
import 'package:meta/meta_meta.dart';

@Target({TargetKind.classType, TargetKind.method})
class ApiVersion {
  final int major, minor;
  const ApiVersion(this.major, this.minor);
}

@ApiVersion(1, 0)
class Svc {
  @ApiVersion(1, 1)
  void ping() {}
}

```

---
<!-- TOC --><a name="int8-uint8-int16-uint16"></a>

### int8, uint8, int16, uint16

|Спецификатор|Общий эквивалент|Байты|Минимальное значение|Максимальное значение|
|--|--|--|--|--|
|int8|signed char|1|-128|127|
|uint8|unsigned char|1|0|255|
|int16|short|2|-32,768|32,767|
|uint16|unsigned short|2|0|65,535|
|int32|long|4|-2,147,483,648|2,147,483,647|
|uint32|unsigned long|4|0|4,294,967,295|
|int64|long long|8|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|
|uint64|unsigned long long|8|0|18,446,744,073,709,551,615|

---
<!-- TOC --><a name="future"></a>

### Future

`Future` - это обёртка над результатом выполнения асинхронной операции. Код Future НЕ выполняется параллельно, а выполняется в последовательности, определяемой Event Loop.  
Состояния Future:

- Uncompleted - операция не завершена
- Completed with Result - операция завершена успешно
- Completed with Error - операция завершена с ошибкой

---
<!-- TOC --><a name="-future"></a>

### Конструкторы Future

- `Future(FutureOr<T> computation())`: создает объект future, который с помощью метода Timer.run запускает функцию computation асинхронно и возвращает ее результат.
- `FutureOr<T>`: указывает, что функция computation должна возвращать либо объект Future<T> либо объект типа T. Например, чтобы получить объект Future<int>, функция computation должна возвращать либо объект Future<int>, либо объект int
- `Future.delayed(Duration duration, [FutureOr<T> computation()])`: создает объект Future, который запускается после временной задержки, указанной через первый параметр Duration. Второй необязательный параметр указывает на функцию, которая запускается после этой задержки.
- `Future.error(Object error, [StackTrace stackTrace])`: создает объект Future, который содержит информацию о возникшей ошибке.
- `Future.microtask(FutureOr<T> computation())`: создает объект Future, который с помощью функции scheduleMicrotask запускает функцию computation асинхронно и возвращает ее результат.
- `Future.sync(FutureOr<T> computation())`: создает объект Future, который содержит результат немедленно вызываемой функции computation.
- `Future.value([FutureOr<T> value])`: создает объект Future, который содержит значение value.

---
<!-- TOC --><a name="await-"></a>

### Await под капотом

Под капотом `await` перемещает весь последующий код в `then` у `Future`, которую мы дожидаемся

---
<!-- TOC --><a name="event-loop"></a>

### Event Loop

`Event Loop` - вечный цикл, выполняющий все поступающие в изолят задачи.
В нём есть две FIFO очереди задач:

`Очередь MicroTask`  
Используется для очень коротких действий, которые должны быть выполнены асинхронно, сразу после завершения какой-либо инструкции перед тем, как передать управление обратно Event Loop. Очередь MicroTask имеет приоритет перед очередью Event

`Очередь Event`  
Используется для планирования операций, которые получают результат от внешних событий (операции ввода/вывода, жесты, рисование, таймеры, потоки)

---
<!-- TOC --><a name="completer"></a>

### Completer

`Completer` позволяет поставлять Future, отправлять событие о выполнении или событие об ошибке. Это может быть полезно, когда нужно сделать цепочку Future и вернуть результат.

---
<!-- TOC --><a name="stream"></a>

### Stream

`Stream` - это последовательность асинхронных событий. Stream сообщает вам, что есть событие и когда оно будет готово  

- `Single subscription` - это вид потока, при котором может быть только один подписчик.
- `Broadcast` - это вид потока, при котором может быть много подписчиков. При этом Broadcast стримы отдают свои данные вне зависимости от того, подписан ли кто-нибудь на них или нет. Подписчики стрима получают события только с момента подписки, а не с момента старта жизни стрима

---
<!-- TOC --><a name="-sync-async"></a>

### Генераторы (sync*/ async*)  

`Генератор` это ключевое слово, которое позволяет создавать последовательность значений с помощью `yield`

- _sync_* - это синхронный генератор. Возвращает `Iterable`
- _async_* - это aсинхронный генератор. Возвращает `Stream`

---
<!-- TOC --><a name="-dart-flutter"></a>

### Многопоточность в Dart и Flutter

Код в `Dart` выполняется внутри `Isolate`. Внутри одного isolate код исполняется в одном потоке выполнения, но для параллельной работы на других ядрах можно создавать дополнительные isolate.

---
<!-- TOC --><a name="isolate"></a>

### Isolate

`Isolate` - это изолированный контекст выполнения в `Dart`. У каждого isolate свой `Event Loop`, свои глобальные поля и собственный набор объектов. Изоляты не разделяют изменяемое состояние и общаются только сообщениями через `ReceivePort` и `SendPort`.

#### Isolate Group

`Isolate group` - это группа isolate, которые запускаются с одним и тем же исполняемым кодом. Это позволяет рантайму переиспользовать код и часть внутренних структур, поэтому `Isolate.spawn()` обычно быстрее, чем `Isolate.spawnUri()`, а обмен сообщениями между isolate из одной группы обычно дешевле.

- `Isolate.spawn()` создаёт isolate в той же `isolate group`
- `Isolate.spawnUri()` создаёт isolate в новой `isolate group`
- `Isolate.exit()` работает только между isolate из одной группы

Важно: `isolate group` - это оптимизация рантайма, а не shared mutable memory. Даже внутри одной группы isolate по-прежнему не разделяют изменяемое состояние и общаются только сообщениями.

#### Основные способы запуска isolate

- `Isolate.spawn()` - запускает isolate с тем же кодом, что и текущий. Новый isolate попадает в ту же `isolate group`, поэтому стартует быстрее, а обмен сообщениями обычно дешевле
- `Isolate.spawnUri()` - запускает isolate из отдельной точки входа (`Uri`). Такой isolate создаётся в новой `isolate group`, поэтому он тяжелее и медленнее, но подходит для отдельного `entrypoint`, своего `packageConfig` или `environment`
- `Isolate.run()` - высокоуровневый API для одной вычислительной задачи. Как он работает, описано в отдельном подразделе ниже
- `Isolate.exit(port, message)` - завершает текущий isolate и в качестве последнего действия отправляет сообщение. Для isolate из одной группы это может происходить без копирования объекта

`Isolate.spawn()` и `isolate group` не превращают `Dart` в shared-memory multithreading. Даже внутри одной группы публичная модель остаётся прежней: данные передаются сообщениями, а не через общую изменяемую память.

Для `spawnUri()`:

- `uri` указывает на `Dart`-файл или библиотеку, где top-level `main` является entrypoint нового isolate
- Целевой `main` должен быть вызываем с 0, 1 или 2 аргументами: `main()`, `main(List<String> args)`, `main(List<String> args, dynamic message)`
- `args` - это именно `List<String>`, который передаётся вторым аргументом в `Isolate.spawnUri(uri, args, message, ...)`
- `message` - это отдельное начальное сообщение любого sendable-типа, которое передаётся третьим аргументом `spawnUri()`
- Если runtime-тип `message` нельзя присвоить второму параметру `main`, запуск завершится ошибкой времени выполнения

#### Передача данных

- Для isolate, созданных через `spawn()`, допускается почти любой отправляемый объект, кроме объектов с нативными ресурсами (`Socket` и т.д.), `ReceivePort`, `DynamicLibrary`, `Finalizer` и некоторых unsendable типов
- Для `spawnUri()` ограничения строже: безопаснее считать, что можно передавать только простые значения, коллекции, `SendPort`, `Capability`, `TransferableTypedData` и совместимые `Type`
- Для больших бинарных данных используют `TransferableTypedData`, чтобы не копировать весь буфер при пересылке
- Замыкания могут неявно захватывать лишнее состояние. Из-за этого isolate может не стартовать или стартовать дороже, чем ожидалось

#### Ошибки и жизненный цикл

- Ошибка создания isolate приходит в `Future`, который возвращают `spawn()` и `spawnUri()`. Здесь можно получить, например, `IsolateSpawnException`
- Неотловленные ошибки внутри уже запущенного isolate не "пролетают" обычным `try/catch` вокруг `spawn`. Их нужно слушать через `onError`, `addErrorListener()` или `isolate.errors`
- `addErrorListener()` присылает список из двух элементов: строковое представление ошибки и строковый `stack trace`. `isolate.errors` оборачивает это в `RemoteError`
- Если важно не потерять первую ошибку, задавайте `onError` и `onExit` прямо в `spawn()` или `spawnUri()` либо запускайте isolate с `paused: true`, затем вешайте listeners и только потом вызывайте `resume()`
- Обычно неотловленная ошибка завершает isolate. Если это поведение важно для вашего сценария, задайте `errorsAreFatal` явно или вызовите `setErrorsFatal(false)` до начала работы
- Для отслеживания завершения isolate используют `onExit` или `addOnExitListener()`
- `await Isolate.run(...)` можно оборачивать в `try/catch`: ошибка самой `computation` вернётся в `Future`, а uncaught async error может прийти как `RemoteError`

#### Isolate.run()

`Isolate.run()` - это удобная обёртка над короткоживущим isolate для одной задачи.

Как работает под капотом:

- В текущем isolate создаются `Completer` и `RawReceivePort`
- В исходнике SDK дальше вызывается `Isolate.spawn(_RemoteRunner._remoteExecute, _RemoteRunner<R>(computation, resultPort.sendPort), ...)`
- В `spawn()` сразу прокидываются `onError`, `onExit`, `errorsAreFatal: true` и `debugName`
- Новый isolate выполняет `computation`; если она возвращает `Future`, рантайм дожидается его завершения уже внутри нового isolate
- При успехе результат отправляется обратно через `Isolate.exit(...)`, поэтому значение возвращается без дополнительного копирования
- Если `computation` выбрасывает обычную ошибку, `Future` от `Isolate.run()` завершается этой же ошибкой
- Если внутри computation происходит uncaught async error, она приходит как `RemoteError`, потому что `addErrorListener()` не передаёт исходный объект ошибки
- Если отправка `computation` в новый isolate не удалась, возвращаемый `Future` тоже завершится ошибкой

#### Коротко

- `Isolate.run()` удобно для одноразовой CPU-задачи с результатом
- `Isolate.spawn()` - для долгоживущего worker isolate и двустороннего обмена сообщениями
- `Isolate.spawnUri()` - для отдельного `entrypoint` и отдельной `isolate group`

Источник SDK: [sdk/lib/isolate/isolate.dart](https://github.com/dart-lang/sdk/blob/main/sdk/lib/isolate/isolate.dart)

---
<!-- TOC --><a name="compute"></a>

### Compute

`compute()` - это `Flutter`-обёртка для одноразового фонового вычисления.

- На native-платформах `await compute(fn, message)` эквивалентен `await Isolate.run(() => fn(message))`
- На `web` отдельный isolate не создаётся: callback выполняется в текущем `event loop`
- `callback`, `message` и результат должны быть sendable между isolate
- `compute()` удобен для тяжёлой однократной CPU-задачи, но не подходит для долгоживущего worker isolate и сложного протокола обмена сообщениями

---
<!-- TOC --><a name="--6"></a>

### Проблемы многопоточности

- `Deadlock` — каждый из потоков ожидают событий, которые могут предоставить другие потоки
- `Race conditions` — проявление недетерминизма исполнителя программы при различном относительном порядке исполнения команд в различных потоках
- `Lock Contention` — основное время потока проводится не в исполнении полезной работы, а в ожидании блокированного другим потоком ресурса
- `Live Lock` — поток захватывает ресурс, но после того, как убедится, что завершить работу не может, освобождает ресурс, аннулируя результаты

<!-- TOC --><a name="flutter"></a>

## Flutter

<!-- TOC --><a name="stateless-stateful-"></a>

### Stateless и Stateful виджеты

- `StatelessWidget` - это виджет, который не имеет состояния, в процессе работы приложения не изменяет своих свойств. Они могут изменяться лишь посредством внешних событий, которые возникают в родительских виджетах
- `StatefulWidget` - это виджет, который хранит состояние, в процессе работы приложения он может его изменять динамически с помощью `setState()`.

---
<!-- TOC --><a name="-stateful-"></a>

### Жизненный цикл Stateful виджета

1. `createState()` вызывается единожды и создает изменяемое состояние для этого виджета в заданном месте в дереве
2. `mounted is true`
3. `initState()` вызывается единожды при инициализации
4. `didChangeDependencies()` вызывается единожды после инициализации и далее при уведомлениях от Inhherited-виджетов вверху по дереву, от которых зависит виджет
5. `build()` вызывается каждый раз при перерисовке
6. `didUpdateWidget(Widget oldWidget)` вызывается каждый раз при обновлении конфигурации виджета
7. `setState()` вызывается императивно для перерисовки
8. `deactivate()` вызывается, когда ранее активный элемент перемещается в список неактивных элементов, при этом удаляясь из дерева
9. `dispose()` вызывается, когда этот объект удаляется из дерева **навсегда**
10. `mounted is false`

---
<!-- TOC --><a name="buildcontext"></a>

### BuildContext

`BuildContext` - это интерфейс, который имплементирует `Element`.

`BuildContext` может быть полезен, когда нужно:

- Получить ссылку на объект `RenderObject`, соответствующий виджету (или, если виджет не является Renderer, то виджету-потомку)
- Получить размер `RenderObject`
- Обратиться к дереву и получить ближайший родительский `InheritedWidget`. Это используется фактически всеми виджетами, которые обычно реализуют метод of (например, `MediaQuery.of(context)`, `Theme.of(context)` и т.д.)

---
<!-- TOC --><a name="inheritedwidget"></a>

### InheritedWidget

`InheritedWidget` — это виджет, который предоставляет своим потомкам возможность взаимодействовать с данными, хранящимися в нём. Решает проблему с передачей данных через конструкторы. Может уведомлять виджетов внизу по дереву об изменениях в собственных данных, тем самым провоцируя их перерисовку.  
Для получения Inherited виджета необходимо вызвать `context.dependOnInheritedWidgetOfExactType<T extends InheritedWidget>()` в `didChangeDependencies()`

_Сложность у операции получения InheritedWidget - O(1). Такая скорость достигается за счёт того, что Inherited виджеты хранятся в виде хэш-таблицы в `Element`-е_

---
<!-- TOC --><a name="-4"></a>

### Деревья

![Деревья Flutter](https://docs.flutter.dev/assets/images/docs/arch-overview/trees.png)

- `Widget Tree` состоит из `Widget`, которые используются для описания пользовательского интерфейса
- `Element Tree` состоит из `Element`, которые управляют жизненым циклом виджета и связывают виджеты и объекты рендеринга.
- `Render Tree` состоит из `RenderObject`, которые используются для определения размеров, положения, геометрии, определения зон экрана, на которые могут повлиять жесты

[Подробнее](https://habr.com/ru/company/surfstudio/blog/533210/)

---
<!-- TOC --><a name="widget"></a>

### Widget

`Widget` - это иммутабельное описание части пользовательского интерфейса. Виджет связан с элементом, который управляет рендерингом. Виджеты образуют сруктуру, а не дерево

---
<!-- TOC --><a name="element"></a>

### Element

`Element` - это мутабельное представление виджета в определенном месте дерева. Управляют жизненым циклом, связывают виджеты и объекты рендеринга.

---
<!-- TOC --><a name="renderobject"></a>

### RenderObject

`RenderObject` - это мутабельный объект дерева визуализации. У него есть родительский объект, а также поле с данными, которое родительский объект использует для хранения специфичной информации, касающейся самого этого объекта, например, его позицию. Данный объект отвечает за  отрисовку, учёт размеров и ограничений, прослушивание и обработку нажатий. При необходимости перерисовки помечается как `dirty`. Перерисовывается, используя свой метод `layer`

---
<!-- TOC --><a name="--7"></a>

### Виды виджетов

`Proxy` - это виджеты, которые хранят некоторую информацию и делают её доступной для потомков. Эти виджеты не принимают непосредственного участия в формировании пользовательского интерфейса, но используются для получения информации, которую они могут предоставить.

- `InheritedWidget`
- `ParentDataWidget` (`LayoutId`, `Flexible`, `KeepAlive` и т.д.)
- `NotificationListener`

`Renderer` - это виджеты, которые имеют непосредственное отношение к компоновке экрана, поскольку они определяют размеры, положение, отрисовку

- `Row`
- `Column`
- `Stack`
- `Padding`
- `Align`
- `Opacity`

`Component` - это виджеты, которые предоставляют непосредственно не окончательную информацию, связанную с размерами, позициями, внешним видом, а скорее данные (или подсказки), которые будут использоваться для получения той самой финальной информации

- `RaisedButton`
- `Scaffold`
- `Text`
- `GestureDetector`
- `Container`

---
<!-- TOC --><a name="--8"></a>

### Виды элементов

![image](https://user-images.githubusercontent.com/80569772/205450564-87d6c2d0-a994-4d1d-bbaa-2c8f7fb07385.png)
`ComponentElement` - компоновочный элемент, который явно не содержит логику рисования/отображения. Есть метод `build()`, который возвращает виджет. Образуется только при создании виджетов `StatelessWidget`, `StatefulWidget`, `InheritedWidget`.

- `ProxyElement`
- `StatelessElement`
- `StatefulElement`

`RenderObjectElement` - отображающий элемент, явно участвующий в рисовании компонентов на экране. Содержит `renderObject` и наследуется от класса `Element`. Образуется при создании виджетов `Padding`, `Column`, `Row`, `Center` и др.

- `LeafRenderObjectElement`
- `ListWheelElement`
- `MultiChildRenderObjectElement`
- `RootRenderObjectElement`
- `SingleChildRenderObjectElement`
- `SliverMultiBoxAdaptorElement`
- `SlottedRenderObjectElement`

---
<!-- TOC --><a name="-element-"></a>

### Жизненный цикл Element-а

1. Элемент создаётся посредством вызова метода `Widget.createElement` и конфигурируется экземпляром виджета, у которого был вызван метод.
2. С помощью метода `mount` созданный элемент добавляется в заданную позицию родительского элемента. При вызове данного метода также ассоциируются дочерние виджеты и элементам сопоставляются объекты дерева рендеринга.
3. Виджет становится активным и должен появиться на экране.
4. В случае изменения виджета, связанного с элементом (например, если родительский элемент изменился), есть несколько вариантов развития событий. Если новый виджет имеет такой же `runtimeType` и `key`, то элемент связывается с ним. В противном случае, текущий элемент удаляется из дерева, а для нового виджета создаётся и ассоциируется с ним новый элемент.
5. В случае, если родительский элемент решит удалить дочерний элемент, или промежуточный между ними, это приведет к удалению объекта рендеринга и переместит данный элемент в список неактивных, что приведет к деактивации элемента.
6. Когда элемент считается неактивным, он не находится на экране. Элемент может находиться в неактивном состоянии только до конца текущего фрейма, если за это время он остается неактивным, он демонтируется, после этого считается несуществующим и больше не будет включен в дерево.
7. При повторном включении в дерево элементов, например, если элемент или его предки имеют глобальный ключ, он будет удален из списка неактивных элементов, будет вызван метод `activate`, и рендер объект, сопоставленный данному элементу, снова будет встроен в дерево рендеринга. Это означает, что элемент должен снова появиться на экране.

---
<!-- TOC --><a name="globalkeys"></a>

### GlobalKeys

`GlobalKeys` - это ключи, которые предоставляют доступ к виджетам. Для виджетов с отслеживанием состояния глобальные ключи также предоставляют доступ к состоянию. Позволяют виджетам менять родителей в любом месте приложения без потери состояния. Должны быть уникальны для всего приложения.

---
<!-- TOC --><a name="localkeys"></a>

### LocalKeys

`LocalKeys` - это ключи, которые нужны для идентификации виджетов в коллекции с одинаковыми значениеми должны быть уникальными среди виджетов с одним и тем же родительским виджетом. Могут использоваться для тестов:

- `ValueKey` - это ключ, который использует значение определенного типа для идентификации самого себя. Переопределяет оператор сравнения. Если value одниковое, то ключи одинаковые
- `UniqueKey` - это ключ, который равен только самому себе
- `ObjectKey` - это ключ, который используется для привязки идентификатора виджета к идентификатору объекта, используемого для создания этого виджета

---
<!-- TOC --><a name="-flutter-"></a>

### Устройство Flutter под капотом

![image](https://user-images.githubusercontent.com/80569772/203052487-937d5923-9571-4752-9762-f0d6637b675e.png)

`Уровень фреймворка` — всё, с чем мы работаем в момент написания приложения, и все служебные классы, позволяющие взаимодействовать написанному нами с уровнем движка. Всё, относящееся к данному уровню написано на Dart. `Flutter Framework` взаимодействует с `Flutter Engine` через слой абстракции, называемый `Window`
  
`Уровень движка` — более низкий уровень, чем уровень фреймворка, содержит классы и библиотеки, позволяющие работать уровню фреймворка. В том числе `виртуальная машина Dart`, `Skia` и тд.  
  
`Уровень платформы` — специфичные механизмы, относящиеся к конкретной платформе запуска.

`Flutter Engine` уведомляет `Flutter Framework`, когда:

- Событие, представляющее интерес, происходит на уровне устройства (изменение ориентации, изменение настроек, проблема с памятью, состояние работы приложения…)
- Какое-то событие происходит на уровне стекла (жест)
- Канал платформы отправляет некоторые данные
- Но также и в основном, когда Flutter Engine готов к рендерингу нового кадра

---
<!-- TOC --><a name="-flutter"></a>

### Модель выполнения во Flutter

1. Создается и запускается новый процесс — `Thread (Isolate)`. Это единственный процесс, в котором будет выполняться ваше приложение.
2. Инициализируются две очереди с `MicroTask` и `Event`, тип очередей `FIFO` (прим.: first in first out, т.е. сообщение, пришедшие раньше, будут раньше обработаны)
3. Исполняется функция `main()`
4. Запускается `Event Loop`. Он управлет порядком исполнения вашего кода, в зависимости от содержимого двух очередей: `MicroTask` и `Event`. Представляет собой "бесконечный" цикл.
5. `Event Loop` с определённой частотой проверяет `MicroTask` и `Event`. Если есть что-то в `MicroTask`, то оно выполняется перед очередью `Event`.

---
<!-- TOC --><a name="custompaint"></a>

### CustomPaint

`CustomPaint` - это класс, который создает «холст» для рисования. В методе `paint` в качестве аргументов поступает `canvas`, который позволяет рисовать различные фигуры

---
<!-- TOC --><a name="widgetsflutterbinding"></a>

### WidgetsFlutterBinding

`WidgetsFlutterBinding` — конкретная реализация привязки приложений на основе инфраструктуры виджетов. По сути своей — это клей, соединяющий фреймворк и движок Flutter. `WidgetsFlutterBinding` состоит из множества связей: `GestureBinding`, `ServicesBinding`, `SchedulerBinding`, `PaintingBinding`, `SemanticsBinding`, `RendererBinding`, `WidgetsBinding`.

Метод `scheduleAttachRootWidget` является отложенной реализацией `attachRootWidget`. Принадлежит данный метод `WidgetsBinding`. В описании к нему сказано, что он присоединяет переданный виджет к `renderViewElement` — корневому элементу дерева элементов.

Метод `scheduleWarmUpFrame` принадлежит `SchedulerBinding` и используется для того, чтобы запланировать запуск кадра как можно скорее, не ожидая системного сигнала `Vsync`.

---
<!-- TOC --><a name="bindings"></a>

### Bindings

![image](https://user-images.githubusercontent.com/80569772/203303949-aadb037a-c818-4f63-8ad8-67c3812a96ad.png)

`Bindings` - это классы для обмена данными между `Flutter Framework` и `Flutter Engine`. Каждая привязка отвечает за обработку набора конкретных задач, действий, событий, сгруппированных по области деятельности.

`BaseBinding` — базовый абстрактный класс, давайте тогда рассмотрим конкретные реализации биндингов. Среди них мы увидим:  
  
`ServicesBinding` отвечает за перенаправление сообщений от текущей платформы в обработчик данных сообщений (`BinaryMessenger`);  
  
`PaintingBinding` отвечает за связь с библиотекой отрисовки.  
  
`RenderBinding` отвечает за связь между деревом рендеринга и движком Flutter.  
  
`WidgetBinding` отвечает за связь между деревом виджетов и движком Flutter.  
  
`SchedulerBinding` — планировщик очередных задач, таких как:  

- вызовы приходящих колбеков, которые инициирует система в `Window.onBeginFrame` — например события тикеров и контроллеров анимаций;
- вызовы непрерывных колбеков, которые инициирует система `Window.onDrawFrame`, например, события для обновления системы отображения после того, как отработают приходящие колбеки;
- посткадровые колбеки, которые вызываются после непрерывных колбеков, перед возвратом из `Window.onDrawFrame`;
- задачи не связанные с рендерингом, которые должны быть выполнены между кадрами.

`SemanticsBinding` отвечает за связь слоя семантики и движком Flutter.  
  
`GestureBinding` отвечает за работу с подсистемой жестов.

---
<!-- TOC --><a name="--9"></a>

### Каналы платформы

![image](https://user-images.githubusercontent.com/80569772/202891758-b7cc7db9-3b4c-4ce3-9f91-37f9a1a614a1.png)
**(!)** Платформенные взаимодействия возможны только в главном изоляте. Этот тот изолят, который создается при запуске вашего приложения.

`Канал платформы` — это двусторонний канал связи между кодом на dart и нативом, который объединяет имя канала и кодек для кодирования сообщений в двоичную форму и обратно. Вызовы асинхронны. Каждый канал должен иметь уникальный идентификатор.  

`Каналы сообщений` - это каналы платформы, предназначенные для обмена сообщениями между нативным кодом и flutter-приложением.  
`Кодеки сообщений`:

- `BinaryCodec` Реализуя сопоставление идентификаторов в байтовых буферах, этот кодек позволяет вам наслаждаться удобством объектов канала в тех случаях, когда вам не требуется кодирование/декодирование. Каналы сообщений Dart с этим кодеком имеют тип BasicMessageChannel<ByteData>.
- `JSONMessageCodec` Работает с «JSON-подобными» значениями (строки, числа, логические значения, null, списки этих значений и мапы строка-ключ с этими данными). Списки и мапы неоднородны и могут быть вложены друг в друга. Во время кодирования значения преобразуются в строки JSON, а затем в байты с использованием UTF-8. Каналы сообщений Dart имеют тип BasicMessageChannel<dynamic> с этим кодеком.
- `StandardMessageCodec` Работает с несколько более обобщенными значениями, чем кодек JSON, поддерживая также однородные буферы данных (UInt8List, Int32List, Int64List, Float64List) и мапы с нестроковыми ключами. Обработка чисел отличается от JSON тем, что целые числа Dart поступают на платформу как 32- или 64-битные целые числа со знаком, в зависимости от величины никогда как числа с плавающей запятой. Значения кодируются в специальном, достаточно компактном и расширяемом двоичном формате. Стандартный кодек предназначен для выбора по умолчанию для канала связи во Flutter. Что касается JSON, каналы сообщений Dart, созданные с использованием стандартного кодека, имеют тип BasicMessageChannel<dynamic>.  

`Каналы методов` — это каналы платформы, предназначенные для вызова нативного кода из flutter-приложения.
`Кодеки методов`:

- `StandardMethodCodec` делегирует кодирование значений полезной нагрузки (payload) в `StandardMessageCodec`. Поскольку последний является расширяемым, то же самое можно сказать и о первом.
- `JSONMethodCodec` делегирует кодирование значений полезной нагрузки (payload) в `JSONMessageCodec`.  

`Каналы событий` — это специализированные каналы платформы, предназначенные для использования в случае представления событий платформы Flutter в виде потока Dart. Работает как обычный `Stream`

[Подробнее](https://habr.com/ru/post/666272/)

---
<!-- TOC --><a name="--10"></a>

### Режимы сборки

- `Debug` (`JIT`) для разработки
- `Release` (`AOT`) для публикации приложения
- `Profile` (`AOT`) для анализа производительности

---
<!-- TOC --><a name="package-plugin"></a>

### Package и Plugin

- `Package` написан только на dart
- `Plugin` использует dart и специфичный код для платформы

---
<!-- TOC --><a name="ffi-plugin"></a>

### FFI Plugin

- `FFI Plugin` - плагин, в котором для написания специфичных платформенных частей используется [Dart FFI](https://dart.dev/guides/libraries/c-interop). Позволяет запустить код на C / C++

---
<!-- TOC --><a name="--11"></a>

### Этапы анимации

- `Ticker` просит `SchedulerBinding` зарегистрировать обратный вызов и сообщить `Flutter Engine`, что надо разбудить его, когда появится новый обратный вызов.
- Когда `Flutter Engine` готов, он вызывает `SchedulerBinding` через запрос `onBeginFrame`.
- `SchedulerBinding` обращается к списку обратных вызовов `ticker` и выполняет каждый из них.
- Каждый `tick` перехватывается "заинтересованным" контроллером для его обработки.
- Если анимация завершена, то `ticker` "отключён", иначе `ticker` запрашивает `SchedulerBinding` для планирования нового обратного вызова.
- ...

---
<!-- TOC --><a name="--12"></a>

### Виды анимаций

- `Tween animation`. Начало, конец, время, скорость заранее определенно  
- `Physics-based animation`. Имитируют реальное поведение

---
<!-- TOC --><a name="-tween"></a>

### Что такое Tween

`Tween` - это объект, который описывает между какими значениями анимируется виджет и отвечает за вычисление текущего значения анимации

---
<!-- TOC --><a name="tween-"></a>

### Tween анимации

- `Implicit Animations` - это набор `Implicitly Animated Widgets`, которые анимируются самостоятельно при их перестройке с новыми аргументами. (`AnimatedAlign`, `AnimatedContainer`, `AnimatedPadding` и т.д.)
- `Explicit Animations` -  это набор элементов управления анимационными эффектами. Предоставляют куда больше контроля над анимацией, чем `Implicit Animations`. Для использования необходимо подмешать к стейту вашего виджета `SingleTickerProviderStateMixin` / `TickerProviderStateMixin`, создать `AnimationController` и зависящие от него `Animation`, передать анимацию в `Transition Widget` (`AlignTransition`, `DecoratedBoxTransition`, `SizeTransition` и т.д.)
`SingleTickerProviderStateMixin` / `TickerProviderStateMixin` создает `Ticker`  
`Ticker` вызывает callback на каждый фрейм анимации  
`AnimationController` пределяет все фреймы анимации - управляет анимацией (forward, reverse, repeat, stop, reset и т.д.)  
`Animation` отдает текущее значение анимации, а также позволяет подписаться на обновления значения/статуса анимации

---
<!-- TOC --><a name="--13"></a>

### Построение кадра

1. Некоторые внешние события приводят к необходимости обновления отображения.
2. `Schedule Frame` отправляется к `Flutter Engine`
3. Когда `Flutter Engine` готов приступить к обновлению рендеринга, он создает `Begin Frame` запрос
4. Этот `Begin Frame` запрос перехватывается `Flutter Framework`, который выполняет задачи, связанные в основном с `Tickers` (например, анимацию)
5. Эти задачи могут повторно создать запрос для более поздней отрисовки (пример: анимация не закончила своё выполнение, и для завершения ей потребуется получить еще один `Begin Frame` на более позднем этапе)
6. Далее `Flutter Engine` отправляет `Draw Frame`, который перехватывается `Flutter Framework`, который будет искать любые задачи, связанные с обновлением макета с точки зрения структуры и размера
7. После того, как все эти задачи выполнены, он переходит к задачам, связанным с обновлением макета с точки зрения отрисовки
8. Если на экране есть что-то, что нужно нарисовать, то новая сцена для визуализации отправляется в `Flutter Engine`, который обновит экран
9. Затем `Flutter Framework` выполняет все задачи, которые будут выполняться после завершения рендеринга (`PostFrame callbacks`), и любые другие последующие задачи, не связанные с рендерингом
10. …

---
<!-- TOC --><a name="--14"></a>

### Расчёт макета

- Ограничения спускаются вниз по дереву, от родителей к детям.
- Размеры идут вверх по дереву от детей к родителям.
- Родители устанавливают положение детей.  

---
<!-- TOC --><a name="buildowner"></a>

### BuildOwner

`BuildOwner` — менеджер сборки и обновления дерева элементов. Он активно участвует в двух фазах — сборки и завершения сборки. Поскольку `BuildOwner` управляет процессом сборки дерева, в нем хранятся списки неактивных элементов и списки элементов, нуждающихся в обновлении.  
Методы:

- `scheduleBuildFor` даёт возможность пометить элемент как нуждающийся в обновлении.
- `lockState` защищает элемент от неправильного использования, утечек памяти и пометки на обновления в процессе уничтожения.
- `buildScope` осуществляет пересборку дерева. Работает с элементами, которые помечены как нуждающиеся в обновлении.
- `finalizeTree` завершает построение дерева. Удаляет неиспользуемые элементы и осуществляет дополнительные проверки в режиме отладки — в том числе на дублирование глобальных ключей.
- `reassemble` обеспечивает работу механизма `HotReload`. Этот механизм позволяет не пересобирать проект при изменениях, а отправлять новую версию кода на `DartVM` и инициировать обновление дерева.

---
<!-- TOC --><a name="pipelineowner"></a>

### PipelineOwner

`PipelineOwner` — менеджер сборки, который занимается работой с деревом отображения.

---
<!-- TOC --><a name="garbage-collector"></a>

### Garbage Collector

`Garbage Collector` - это алгоритм, наблюдает за ссылками и очищает память с целью предотвращения её переполнения.

**(!)** В процессе сборки мусора слой `Dart Framework` создает канал взаимодействия со слоем `Flutter Engine`, посредством которого узнает о моментах простоя приложения и отсутствия пользовательского взаимодействия. В эти моменты `Dart Framework` запускает процесс оптимизации памяти, что позволяет сократить влияния на пользовательский опыт и стабильность приложения.

**Сборщик молодого мусора**  
![image](https://user-images.githubusercontent.com/80569772/203299873-834979fb-a548-476a-8f69-8be50c7ebd64.png)

Используемый объём памяти можно разделить на два пространства: активное и неактивное. Новые объекты располагаются в активной части, где по мере её заполнения, живые объекты переносятся из активной области памяти в неактивную, игнорируя мёртвые объекты. Затем неактивная половина становится активной. Этот процесс имеет цикличный характер.

**Сборщик старого мусора (Parallel Marking and Concurrent Sweeping)**  
![image](https://user-images.githubusercontent.com/80569772/203300039-95a12d39-d502-4064-8a31-e903407fa04a.png)

1. Осуществляется обход дерева объектов, используемые объекты помечаются специальной меткой.
2. Во время второго этапа происходит повторный проход по дереву объектов, в ходе которого непомеченные в первом этапе объекты перерабатываются
3. Все метки стираются  

[Подробнее](https://habr.com/ru/company/rshb/blog/668600/)

---
<!-- TOC --><a name="task-runners"></a>

### Task Runners

![image](https://user-images.githubusercontent.com/80569772/211004726-1eeef86f-cebf-41de-8bb3-a8485257565f.png)  

- `Platform Task Runner`: Основной поток платформы. Здесь выполняется код плагинов. Для получения дополнительной информации см. документацию по UIKit для iOS или документацию по MainThread для Android. Этот поток не отображается в наложении производительности.
- `UI Task Runner`: Поток UI выполняет код Dart в виртуальной машине Dart VM. Этот поток включает в себя код, написанный вами, и код, выполняемый фреймворком Flutter от имени вашего приложения. Когда ваше приложение создает и отображает сцену, поток UI создает дерево слоев - легкий объект, содержащий команды рисования, не зависящие от устройства, и отправляет дерево слоев в растровый поток для отображения на устройстве. Не блокируйте этот поток! Показан в нижней строке оверлея производительности.
- `Raster Task Runner`: Растровый поток получает дерево слоев и отображает его, обращаясь к GPU (графическому процессору). Вы не можете напрямую обращаться к растровому потоку или его данным, но если этот поток работает медленно, то это результат того, что вы сделали в коде Dart. В этом потоке работают графические библиотеки Skia и Impeller. Они показаны в верхней строке оверлея производительности. Ранее этот поток был известен как "GPU-поток", поскольку он выполняет растеризацию для GPU. Однако он выполняется на центральном процессоре. Мы переименовали его в "растровый поток", поскольку многие разработчики ошибочно (но вполне обоснованно) полагали, что этот поток работает на GPU.
- `IO Task Runner`: Выполняет дорогостоящие задачи (в основном ввод-вывод), которые в противном случае блокировали бы работу потоков пользовательского интерфейса или растровых потоков. Этот поток не отображается в оверлее производительности.

[Подробнее](https://www.programmersought.com/article/81813680395/), [Подробнее 2](https://medium.com/flutter-community/the-layer-cake-widgets-elements-renderobjects-7644c3142401)

<!-- TOC --><a name="-5"></a>

## Архитектура

<!-- TOC --><a name="-6"></a>

### Основы архитектуры

Архитектура - это набор решений по организации программы. Таких, как деление программы на слои, построение связей между ними, управление состоянием, связь с UI. Хорошая архитектура делает слои в приложении слабо связанными, что упрощает внесение изменений, повышает тестируемость кода, упрощает систему  

---
<!-- TOC --><a name="--15"></a>

### Чистая архитектура

Чистая архитектура - архитектура, которая следует `SOLID` и делится на три независимых слоя:  

- `Data (datasources, models, repositories)` получение данных извне
- `Domain (entities, repositories interfaces, usecases)` бизнес правила
- `Presentation (bloc, pages, widgets)` отображение

[Пример](https://github.com/ResoCoder/flutter-tdd-clean-architecture-course)  

---
<!-- TOC --><a name="ddd"></a>

### DDD

`DDD (Domain-Driven Design)` - это подход, при котором код строят вокруг бизнес-смысла, а не вокруг таблиц, экранов или API.

`Проще:` сначала разбираемся, как реально работает бизнес, какие там есть правила и термины, и только потом переносим это в код.

Основные понятия:

- `Ubiquitous Language` - единый язык, общий для разработчиков, аналитиков и бизнеса. Одни и те же термины должны использоваться и в обсуждении, и в коде
- `Entity` - сущность с идентичностью, которая важна сама по себе. Например, `User`, `Order`
- `Value Object` - объект-значение без собственной идентичности. Важен набор данных, а не конкретный экземпляр. Например, `Money`, `Email`, `Address`
- `Aggregate` - группа связанных объектов, которые изменяются как единое целое
- `Aggregate Root` - главная точка доступа к агрегату. Снаружи работают только через него
- `Repository` - абстракция для получения и сохранения агрегатов
- `Domain Service` - доменная логика, которая не подходит одной конкретной сущности или value object
- `Bounded Context` - чёткая граница модели. В разных частях системы один и тот же термин может значить разное

`Простой пример:`

Представим приложение доставки еды.

- В контексте `Ordering` есть `Order`, `OrderItem`, `Money`
- В контексте `Delivery` есть `Courier`, `Route`, `Delivery`
- Слово `status` в этих контекстах может означать разное: у заказа это "создан", "оплачен", "отменён", а у доставки - "назначена", "в пути", "доставлена"

Идея `DDD` в том, что мы не сваливаем всё в одну общую модель, а держим отдельные понятные контексты и бизнес-правила внутри них.

`Когда полезен DDD:`

- Когда предметная область сложная и в ней много бизнес-правил
- Когда важно, чтобы код отражал реальные бизнес-термины
- Когда систему разрабатывают несколько команд или домен можно разделить на контексты

`Когда DDD избыточен:`

- Для простых CRUD-приложений без сложной доменной логики
- Когда стоимость поддержки сложной модели выше, чем польза от неё

`DDD` не равен просто разбиению на папки `data/domain/presentation`. Это именно подход к моделированию домена, инвариантов и языка системы.

Источники:

- [Microsoft Learn: Design a DDD-oriented microservice](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/ddd-oriented-microservice)
- [Microsoft Learn: Use tactical DDD to design microservices](https://learn.microsoft.com/en-us/azure/architecture/microservices/model/tactical-domain-driven-design)
- [Domain Language: The Big Blue Book by Eric Evans](https://www.domainlanguage.com/ddd/blue-book/)

---
<!-- TOC --><a name="--16"></a>

### Управление состоянием

#### Vanilla

`Плюсы`  

- Низкий порог вхождения.
- Не требуются сторонние библиотеки.  

`Минусы`  

- При изменении состояния виджета дерево виджетов каждый раз целиком пересоздается.
- Нарушает принцип единственной ответственности. Виджет отвечает не только за создание UI, но и за загрузку данных, бизнес-логику и управление состоянием.
- Решения о том как именно отображать текущее состояние принимаются прямо в UI коде. Если состояние станет более сложным, то читаемость кода сильно понизится.  

`Использование:`

- Widget State

#### BLoC

`Плюсы`  

- Четкое разделение ответственности
- Предсказуемые преобразования Event to State
- Реактивность. Нет необходимости в вызове дополнительных методов

`Минусы`

- Обязательность состояния в Bloc-е
- Частые изменения библиотеки
- Зависимость от сторонней библиотеки

`Использование:`

- Widget State
- App State

#### Redux

`Плюсы`  

- Единое состояние
- Все экшены доступны всем  

`Минусы`  

- Единое состояние
- Зависимость от сторонней библиотеки
- Большое количество boilerplate кода
- Все экшены доступны всем  

`Использование:`

- Widget State
- App State

#### Provider

`Плюсы`  

- Скоупы на поддеревья
- Flutter ориентирован
- Нет статики
- Готовые провайдеры

`Минусы`  

- Завязка на фреймворк
- Только 1 провайдер одного типа
- Зависимость от сторонней библиотеки

`Использование:`

- App State
- Частично DI

#### Riverpod

`Плюсы:`  

- Скоупы на поддеревья
- Flutter ориентирован
- Нет статики
- Готовые провайдеры

`Минусы:`

- Зависимость от сторонней библиотеки
- Циклические зависимости падают в runtime-е

`Использование:`

- Widget State
- App State
- DI

---
<!-- TOC --><a name="dependency-injection"></a>

### Dependency Injection  

`Dependency injection (DI)` - это механизм, который позволяет сделать взаимодействующие в приложении объекты слабосвязанными с помощью интерфейсов. Это делает всю систему более гибкой, более адаптируемой и расширяемой

---
<!-- TOC --><a name="--17"></a>

### Архитектурные патерны  

![Архитектурные паттерны](https://fuzeservers.ru/wp-content/uploads/2/6/8/268a107e69309f0529c18aae72769bdb.png)

#### MVVM

`Части:`

- `Model` содержит в себе всю логику приложения, она хранит и обрабатывает данные, при этом не взаимодействуя с пользователем напрямую
- `View` отображает данные, которые ему передали
- `ViewModel` связывает модель и представление (передаёт данные между ними)

`Использование:`

- Используется в ситуации, когда возможно связывание данных без необходимости ввода специальных интерфейсов представления (т.е. отсутствует необходимость реализовывать IView);
- Частым примером является технология WPF.

[Подробнее](https://habr.com/ru/post/427327/)  [Пример](https://github.com/jitsm555/Flutter-MVVM)

#### MVC

`Части:`

- `Model` содержит в себе всю логику приложения, она хранит и обрабатывает данные, при этом не взаимодействуя с пользователем напрямую
- `View` отображает данные, которые ему передали
- `Controller` перехватывает событие извне и в соответствии с заложенной в него логикой, реагирует на это событие изменяя Mодель, посредством вызова соответствующего метода. После изменения Модель использует событие о том что она изменилась, и все подписанные на это события Представления, получив его, обращаются к Модели за обновленными данными, после чего их и отображают

`Использование:`

- Используется в ситуации, когда невозможно связывание данных (нельзя использовать Binding);

[Пример](https://github.com/flutter-devs/Flutter_MVC)

#### MVP

`Части:`

- `Model` содержит в себе всю логику приложения, она хранит и обрабатывает данные, при этом не взаимодействуя с пользователем напрямую
- `View` отображает данные, которые ему передали
- `Presenter` подписывается на события представления, по запросу изменяет модель, обновляет представление

`Использование:`

- Используется в ситуации, когда связь между представление и другими частями приложения невозможна (и Вы не можете использовать MVVM или MVP);

---
<!-- TOC --><a name="--18"></a>

### Способы осуществления навигации

#### Navigator

- Идёт из коробки  

#### Go Router

- Парсинг пути и параметров запроса (например, "user/:id")
- Поддержка deep-links
- Поддержка перенаправления - вы можете перенаправить пользователя на другой URL-адрес в зависимости от состояния приложения
- Именованные роуты

#### Auto Route

- Парсинг пути и параметров запроса (например, "user/:id")
- Поддержка deep-links
- Защищённые маршруты
- Именованные роуты
- Разные варианты анимаций

---
<!-- TOC --><a name="--19"></a>

### Хранение данных

#### Нереляционные (NoSQL)

##### Hive

`Плюсы:`

- Реализация на чистом Dart, без платформенного кода, за счёт чего одинаково работает на разных платформах
- Прост в использовании
- Быстрая запись / чтение
- Мало boilerplate кода
- Наличие кодогенерации
- Поддерживается на всех платформах

`Минусы:`

- Связи между объектами нужно поддерживать вручную
- Ограничение по количеству адаптеров для объектов - 224
- Ограничение по количеству полей в адаптере - 255
- Плохо подходит для работы с большим объемом данных
- Выгружает всю бд в память
- Нельзя получить доступ к box-у, созданному в другом изоляте
- Наличие кодогенерации
- Нет миграций

`Использование:`

- Небольшой объём данных
- Необходимость в сохранении своих дата моделей

##### Shared Preferences

`Плюсы:`

- Прост в использовании
- Синхронное чтение из кэша в памяти
- Поддерживается на всех платформах

`Минусы:`

- Разные реализации для Android/iOS и других платформ
- Обращение к платформенному коду
- Не гарантируется запись на диск после успешного выполнения метода
- Нельзя сохранять сложные объекты из коробки

`Использование:`

- Небольшой объём данных
- Необходимость в быстром внедрении решения
- Сохранение настроек приложения в виде примитивных данных

#### Реляционные (SQL)

##### SQFLite

`Плюсы`

- Есть миграции
- Поддерживает связи между сущностями
- Не выгружает бд в оперативную память
- Возможность написания сложных запросов на SQL

`Минусы:`

- Сложен в использовании
- Не поддерживается в Web, Linux, Windows
- Скорость работы ниже чем у NoSQL
- На разных OS и версиях могут быть разные версии SQLite

`Использование:`

- Большой объём данных
- Хранение сложно структурированных данных

##### Drift

- Есть миграции
- Поддерживает связи между сущностями
- Не выгружает бд в оперативную память
- Возможность написания сложных запросов на SQL

`Плюсы`

- Есть миграции
- Быстрый
- Поддерживается на всех платформах

`Минусы:`

- Сложен в использовании
- Скорость работы ниже чем у NoSQL

`Использование:`

- Большой объём данных
- Хранение сложно структурированных данных

<!-- TOC --><a name="-7"></a>

## Тестирование

<!-- TOC --><a name="--20"></a>

### Виды тестов

- `Модульный тест` тестирует одну функцию, метод или класс. Его цель - проверить правильность работы определенной функции, метода или класса. Внешние зависимости для тестируемого модуля обычно передаются как параметр.
- `Виджет тест` тестирует один виджет. Цель такого теста — убедиться, что пользовательский интерфейс виджета выглядит и взаимодействует, как запланировано. Тестирование виджета происходит в тестовой среде, которая обеспечивает контекст жизненного цикла виджета. Также тестируемый виджет должен иметь возможность получать действия и события пользователя и отвечать на них .
- `Интеграционный тест` тестирует все приложение или его большую часть. Цель интеграционного теста — убедиться, что все тестируемые виджеты и сервисы работают вместе, как ожидалось. Кроме того, вы можете использовать интеграционные тесты для проверки производительности вашего приложения. Как правило, интеграционный тест выполняется на реальном устройстве или эмуляторе.

---
<!-- TOC --><a name="tdd"></a>

### TDD

`TDD` — это методика разработки приложений, при которой сначала пишется тест, покрывающий желаемое изменение, а затем — код, который позволит пройти тест.

`Проще:` сначала формулируем в тесте, как программа должна себя вести, и только потом пишем реализацию.

Классический цикл:

1. `Red` - пишем тест на новое поведение и убеждаемся, что он падает
2. `Green` - пишем минимальный код, чтобы тест прошёл
3. `Refactor` - улучшаем код, не меняя поведение, и снова прогоняем тесты

`Простой пример:`

Нужно проверить, что функция скидки даёт `10%`, если сумма заказа больше `1000`.

1. Сначала пишем тест: `expect(calculateDiscount(1200), 120)`
2. Тест падает, потому что функции ещё нет или логика не реализована
3. Пишем минимальный код, чтобы тест стал зелёным
4. Если код получился грязным, упрощаем его и снова прогоняем тесты

То есть тест здесь сначала описывает ожидаемое поведение, а код уже подстраивается под него.

`Плюсы TDD:`

- Код изначально проектируется более тестируемым и с меньшей связанностью
- Тесты служат живой спецификацией поведения
- Регрессии находятся раньше
- Проще безопасно рефакторить код

`Ограничения:`

- TDD плохо подходит для неясных требований и exploratory-разработки UI
- Не заменяет интеграционные и e2e-тесты
- Если писать тесты на детали реализации, а не на поведение, они становятся хрупкими

`Практика во Flutter:`

- Чаще всего TDD удобно применять к `domain`, `use cases`, `repositories`, форматтерам и другой бизнес-логике
- Для UI обычно полезнее тестировать состояние, сценарии и контракты, а не пиксели и внутренние вызовы

Источники:

- [Martin Fowler: Test-Driven Development](https://martinfowler.com/bliki/TestDrivenDevelopment.html)
- [Flutter Docs: Testing overview](https://docs.flutter.dev/testing/overview)

<!-- TOC --><a name="--21"></a>

## Паттерны разработки

*Порождающие_. Отвечают за удобное и безопасное создание новых объектов или даже целых семейств объектов.  

- Factory Method (Фабричный Метод). Порождающий паттерн проектирования, который определяет общий интерфейс для создания объектов в суперклассе, позволяя подклассам изменять тип создаваемых объектов.
- Abstract Factory (Абстрактная Фабрика). Порождающий паттерн проектирования, который позволяет создавать семейства связанных объектов, не привязываясь к конкретным классам создаваемых объектов.
- Builder (Строитель). Порождающий паттерн проектирования, который позволяет создавать сложные объекты пошагово. Строитель даёт возможность использовать один и тот же код строительства для получения разных представлений объектов.
- Prototype (Прототип). Порождающий паттерн проектирования, который позволяет копировать объекты, не вдаваясь в подробности их реализации.
- Singleton (Одиночка). Порождающий паттерн проектирования, который гарантирует, что у класса есть только один экземпляр, и предоставляет к нему глобальную точку доступа.

_Структурные_. Отвечают за построение удобных в поддержке иерархий классов.  

- Adapter (Адаптер). Структурный паттерн проектирования, который позволяет объектам с несовместимыми интерфейсами работать вместе.
- Bridge (Мост). Структурный паттерн проектирования, который разделяет один или несколько классов на две отдельные иерархии — абстракцию и реализацию, позволяя изменять их независимо друг от друга.
- Composite (Компоновщик). Структурный паттерн проектирования, который позволяет сгруппировать множество объектов в древовидную структуру, а затем работать с ней так, как будто это единичный объект.
- Decorator (Декоратор). Структурный паттерн проектирования, который позволяет динамически добавлять объектам новую функциональность, оборачивая их в полезные «обёртки».
- Facade (Фасад). Структурный паттерн проектирования, который предоставляет простой интерфейс к сложной системе классов, библиотеке или фреймворку.
- Flyweight (Легковес). Паттерн проектирования, который позволяет вместить бóльшее количество объектов в отведённую оперативную память. Легковес экономит память, разделяя общее состояние объектов между собой, вместо хранения одинаковых данных в каждом объекте.
- Proxy (Заместитель). Структурный паттерн проектирования, который позволяет подставлять вместо реальных объектов специальные объекты-заменители. Эти объекты перехватывают вызовы к оригинальному объекту, позволяя сделать что-то до или после передачи вызова оригиналу.

_Поведенческие_. Решают задачи эффективного и безопасного взаимодействия между объектами программы.  

- Chain of Responsibility (Цепочка Обязанностей). Поведенческий паттерн проектирования, который позволяет передавать запросы последовательно по цепочке обработчиков. Каждый последующий обработчик решает, может ли он обработать запрос сам и стоит ли передавать запрос дальше по цепи.
- Command (Команда). Поведенческий паттерн проектирования, который превращает запросы в объекты, позволяя передавать их как аргументы при вызове методов, ставить запросы в очередь, логировать их, а также поддерживать отмену операций.
- Iterator (Итератор). Поведенческий паттерн проектирования, который даёт возможность последовательно обходить элементы составных объектов, не раскрывая их внутреннего представления.
- Mediator (Посредник). Поведенческий паттерн проектирования, который позволяет уменьшить связанность множества классов между собой, благодаря перемещению этих связей в один класс-посредник.
- Memento (Снимок). Поведенческий паттерн проектирования, который позволяет сохранять и восстанавливать прошлые состояния объектов, не раскрывая подробностей их реализации.
- Observer (Наблюдатель). Поведенческий паттерн проектирования, который создаёт механизм подписки, позволяющий одним объектам следить и реагировать на события, происходящие в других объектах.
- State (Состояние). Поведенческий паттерн проектирования, который позволяет объектам менять поведение в зависимости от своего состояния. Извне создаётся впечатление, что изменился класс объекта.
- Strategy (Стратегия). Поведенческий паттерн проектирования, который определяет семейство схожих алгоритмов и помещает каждый из них в собственный класс, после чего алгоритмы можно взаимозаменять прямо во время исполнения программы.
- Template Method (Шаблонный Метод). Поведенческий паттерн проектирования, который определяет скелет алгоритма, перекладывая ответственность за некоторые его шаги на подклассы. Паттерн позволяет подклассам переопределять шаги алгоритма, не меняя его общей структуры.
- Visitor (Посетитель). Поведенческий паттерн проектирования, который позволяет добавлять в программу новые операции, не изменяя классы объектов, над которыми эти операции могут выполняться.

[Подробнее](https://refactoring.guru/ru/design-patterns/catalog)  
