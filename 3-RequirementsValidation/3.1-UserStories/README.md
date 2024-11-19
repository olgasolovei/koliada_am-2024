Feature: Система моніторингу погодних умов на будівельному майданчику

  # US1.0 – Збір даних про погодні умови
  Scenario: Збір даних про погодні умови в реальному часі
    Як керівник проєкту
    Я хочу, щоб система моніторингу збирала дані про погодні умови в реальному часі
    Щоб мати актуальну інформацію для оцінки ризику перекидання крана на будівельному майданчику

    Given система увімкнена
    When починається збір даних про погодні умови
    Then система повинна оновлювати дані кожні 2 секунди

  # US1.1 – Постійне оновлення даних
  Scenario: Постійне оновлення даних про погодні умови
    Як керівник проєкту
    Я хочу, щоб система оновлювала погодні дані кожні 2 секунди
    Щоб мати доступ до точної інформації для своєчасного аналізу ризиків

    Given система збирає дані
    When проходить дві секунди
    Then система повинна оновити дані про швидкість вітру, температуру, тиск

  # US1.2 – Сповіщення про високий ризик
  Scenario: Сповіщення про небезпечні погодні умови
    Як керівник проєкту
    Я хочу, щоб система сповіщала працівників про перевищення безпечного рівня погодних умов
    Щоб попередити можливе перекидання крана та забезпечити безпеку на майданчику

    Given поріг швидкості вітру встановлено на 15 м/с
    When швидкість вітру перевищує 15 м/с
    Then система повинна надіслати сповіщення працівникам на майданчику

  # US2.0 – Оцінка ризику перекидання крана
  Scenario: Оцінка ризиків перекидання крана
    Як керівник проєкту
    Я хочу, щоб система оцінювала ризик перекидання крана на будівельному майданчику
    Щоб уникнути аварійних ситуацій та вчасно попереджати працівників

    Given система збирає погодні дані
    When рівень ризику стає високим
    Then система повинна попередити всіх користувачів про небезпеку

  # US3.0 – Зберігання історії ризиків
  Scenario: Зберігання даних про події з високим ризиком
    Як керівник проєкту
    Я хочу, щоб система зберігала всі події, пов'язані з ризиками на майданчику
    Щоб працівники мали можливість аналізувати історичні дані для підвищення безпеки в майбутньому

    Given система моніторить погодні умови
    When відбувається подія з високим ризиком
    Then система повинна зберегти дані про цю подію в історії для подальшого аналізу