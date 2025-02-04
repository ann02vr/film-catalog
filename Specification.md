# Введение
1. Цели проекта:
- Предоставить удобный поиск, возможность фильтрации и сортировки, чтобы помочь пользователю быстрее определиться с выбором фильма
- Обеспечить возможность добавления фильма в избранное, добавлять оценки и отзывы
- Предоставить актуальную информацию о фильме (год выпуска, длительность, описание, трейлеры)
- Облегчить выбор онлайн-кинотеатра (все возможные варианты должны отображаться в карточке фильма)
- Обеспечить персонализированные рекомендации

2. Целевая аудитория:
- обычные пользователи
- кинолюбители
- подписчики стриминговых сервисов

3. Основные пользователи:
- незарегистрированные пользователи (могут просматривать фильмы, переходить на платформы онлайн-кинотеатров, смотреть отзывы и рейтинги)
- зарегистрированные пользователи (могут сохранять фильмы в собственные коллекции, оставлять оценки и отзывы)
- администраторы (могут удалять, добавлять фильмы, редактировать их содержимое, удалять некорректные отзывы)

4. Обзор системы:
Система представляет из себя каталог фильмов с возможностью поиска, фильтрации и сортировки. Каждый фильм можно открыть в отдельной вкладке и изучить подробную информацию о нем: описание, год выпуска, длительность, трейлеры, отзывы, рейтинг, платформы (онлайн-кинотеатры) для просмотра. Зарегистрированные пользователи могут добавлять фильмы в собственные списки-коллекции, писать отзывы и ставить оценки фильмам.

# Требования

1. Функциональные требования
- Система должна обеспечивать удобный поиск по названию фильма, по актерам и режиссерам.
- Система должна обеспечивать фильтрацию по жанрам, году выпуска, стране производства, по наличию субтитров/озвучки.
- Система должна обеспечивать сортировку по названию, году выпуска, длительности фильма, рейтингу.
- Система должна обеспечить возможность зарегистрироваться через электронную почту, номер телефона или социальные сети.
- Система должна обеспечить возможность добавить фильм в отдельный список-коллекцию для зарегистрированных пользователей.
- Система должна обеспечить возможность добавления отзыва для зарегистрированных пользователей.
- Система должна предоставить права администратора соответствующим пользователям.
- Система должна обеспечить возможность редактирования карточек фильмов администраторами.
- Система должна обеспечить возможность удаления некорректных отзывов администраторами.
- Система должна предоставить возможность выбора платформы для просмотра фильма с переходом на выбранную платформу.
- Система должна обеспечить отображение рекомендаций на основе истории просмотренных фильмов и фильмов, добавленных в списки-коллекции, для зарегистрированных пользователей.
- Система должна обеспечить отображение рекомендаций на основе рейтинга для незарегистрированных пользователей.
- Система должна показывать предупреждение, если незарегистрированный пользователь пытается добавить фильм в список-коллекцию.

2. Нефункциональные требования
- Система должна быть совместима с различными браузерами.
- Система должна быть оптимизирована для работы на мобильных устройствах.
- Максимальное время загрузки страницы должно быть не больше 3 секунд.
- Система должна обеспечивать безопасную аутентификацию (OAuth, JWT).
- Передача данных между клиентом и сервером должна происходить через TLS.
- Система должна поддерживать механизм CORS.

3. Use Case
- Сценарий 1: Авторизация пользователя.
  Актор: незарегистрированный пользователь.
  Описание:
  1) Пользователь нажимает на кнопку "Войти" в шапке веб-приложения.
  2) Происходит переход на страницу авторизации. На этой странице предлагается ввести логин или пароль, либо зайти через социальные сети, либо, если пользователь на сайте в первый раз, зарегистрироваться через электронную почту, номер телефона или социальные сети.
  3) Пользователь вводит логин и пароль и нажимает на кнопку "Войти".
  4) Система проверяет данные и авторизует пользователя.
  5) Если введены ошибочные данные, система показывает сообщение об ошибке.
  Альтернативное описание:
  1) На странице авторизации пользователь нажимает "Войти через социальные сети".
  2) Происходит переадресация на сайт выбранной социальной сети.
  3) Пользователь вводит данные.
  4) Система проверяет данные и совершает обратный переход на страницу кинокаталога.
 
- Сценарий 2: Регистрация пользователя.
  Актор: незарегистрированный пользователь.
  Описание:
  1) Пользователь нажимает на кнопку "Войти" в шапке веб-приложения.
  2) Происходит переход на страницу авторизации. На этой странице предлагается ввести логин или пароль, либо зайти через социальные сети, либо, если пользователь на сайте в первый раз, зарегистрироваться через электронную почту или номер телефона.
  3) Пользователь нажимает кнопку "Зарегистрироваться".
  4) Вводит свои данные в форме регистрации.
  5) Система отправляет код подтверждения на электронную почту или на номер телефона, указанные при регистрации.
  6) Пользователь вводит код подтверждения.
  7) Система создает новую учетную запись.
  8) Происходит вход в новую учетную запись.
     
- Сценарий 3: Поиск фильма.
  Актор: зарегистрированный/незарегистрированный пользователь, администратор.
  Описание:
  1) Пользователь вводит ключевые слова в поисковую строку.
  2) Система ищет совпадение в названиях фильмов, режиссерах и актерах.
  3) Выдает результаты, соответствующие запросу.
  4) Если совпадений нет, отоюражается сообщение о неудачном поиске.
     
- Сценарий 4: Добавление фильма в список-коллекцию.
  Актор: зарегистрированный пользователь.
  Описание:
  1) Пользователь заходит в карточку интересующего его фильма.
  2) Нажимает на кнопку "Добавить в коллекцию".
  3) Появляется диалоговое окно с уже существующими коллекциями данного пользователя и кнопкой "Создать новую коллекцию".
  4) Пользователь выбирает нужную коллекцию и фильм добавляется туда.
  5) Если пользователь нажимает "Создать новую коллекцию", то появляется диалоговое окно, в котором нужно ввести название новой коллекции.
  6) После создания новой коллекции происходит переход к предыдущему диалоговому окну со списком коллекций.
  7) Пользователь выбирает только что созданную коллекцию и фильм добавляет туда.
     
- Сценарий 5: Изменение карточки фильма администратором.
  Актор: администратор.
  Описание:
  1) При переходе на карточку фильма для администратора доступна кнопка "Изменить содержимое карточки".
  2) После нажатия на эту кнопку открывается форма с полями "Постер", "Название", "Год выпуска", "Длительность", "Описание", заполненные текущими данными.
  3) Администратор изменяет нужные поля.
  4) Администратор нажимает на кнопку "Сохранить".
  5) Новые данные сохраняют в базе данных.

# Архитектура данных

Сущности: Фильм, Пользователь, Список-коллекция фильмов, Отзыв, Актер, Режиссер, Жанр, История просмотра.

![image](https://github.com/user-attachments/assets/246bde62-8477-44d6-bd0f-738f80a87962)

Сущность "Фильм" связана со следующими сущностями:
- "Жанр" - связь "один или много" к "один или много";
- "Актер" - связь "один или много" к "много";
- "Режиссер" - связь "один или много" к "один и только один";
- "Отзыв" - связь "один или много" к "один или много";
- "История просмотра" - связь "один или много" к "один и только один";

Сущность "Пользователь" связана со следующими сущностями:
- "Список коллекций" - связь "один и только один" к "один или много";
- "Отзыв" - связь "один и только один" к "один или много";
- "История просмотра" - связь "один и только один" к "один или много";











