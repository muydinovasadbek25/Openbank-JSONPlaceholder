# JSONPlaceholder API Tests

## Описание
Эта коллекция Postman содержит автоматизированные тесты для работы с API JSON Placeholder.  
Тесты включают следующие сценарии:
- Создание поста (POST /posts)
- Проверка созданного поста (GET /posts/{{postId}})
- Обновление поста (PUT /posts/{{postId}})
- Удаление поста (DELETE /posts/{{postId}})
- Получение комментариев поста (GET /posts/1/comments)
- Проверка пользователей (GET /users)

Все тесты используют переменные окружения для динамических данных (`postId`, `userId`, `title`, `body`).

---

## Требования
- Установленный Postman  
- JSON файлы:
  - `JSONPlaceholder API Tests.postman_collection.json` (коллекция)
  - `Environment.postman_environment.json` (окружение)

---

## Инструкция по импорту

### 1. Импорт окружения
1. В Postman перейдите во вкладку **Environments** → **Import**  
2. Выберите файл `Environment.postman_environment.json`  
3. Активируйте импортированное окружение (сделайте его текущим)

### 2. Импорт коллекции
1. В Postman откройте вкладку **Collections** → **Import**  
2. Выберите файл `JSONPlaceholder API Tests.postman_collection.json`

---

## Запуск тестов
1. Откройте коллекцию **JSONPlaceholder API Tests**  
2. Кликните **Run** (Collection Runner)  
3. Включите опцию **Run in order**, чтобы запросы выполнялись последовательно:  
   1. POST /posts  
   2. GET /posts/{{postId}}  
   3. PUT /posts/{{postId}}  
   4. DELETE /posts/{{postId}}  
   5. GET /posts/1/comments  
   6. GET /users  

4. Нажмите **Start Run**  
5. Результаты тестов можно просматривать в **Tests** табе каждого запроса или в Collection Runner

---

## Проверки
- Статус код запроса (200, 201)  
- Проверка соответствия данных (title, body, userId, id)  
- Проверка структуры объектов (поля `id`, `userId`, `title`, `body`)  
- Проверка корректности email адресов (для пользователей)  
- Проверка, что комментарии принадлежат нужному `postId`

---

## Переменные окружения
| Переменная | Значение | Описание |
|------------|----------|----------|
| baseURL    | https://jsonplaceholder.typicode.com | Базовый URL для всех запросов |
| postId     | 1      | ID поста, создаваемого в тесте |
| userId     | 1        | ID пользователя |
| postTitle  | Title at nam consequatur ea labore ea harum | Заголовок поста |
| postBody   | Body cupiditate quo est a modi nesciunt soluut | Тело поста |

---

Теперь коллекция готова к использованию и полностью динамическая благодаря переменным окружения.
