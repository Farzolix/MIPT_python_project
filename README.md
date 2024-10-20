# Личный Трекер Задач
## Описание проекта
Личный Трекер Задач — это настольное приложение на Python, которое помогает пользователям эффективно управлять своими повседневными задачами. Приложение позволяет создавать, организовывать и отслеживать задачи, повышая продуктивность и обеспечивая своевременное выполнение дел.
## Реализуемый функционал
- Управление задачами:
  - Добавление новых задач с подробным описанием.
  - Редактирование существующих задач.
  - Удаление задач.
- Организация задач:
  - Установка приоритетов (низкий, средний, высокий).  
  - Установка дедлайнов и напоминаний.
  - Категоризация задач по проектам или темам.
- Интерфейс пользователя:
  - Интуитивно понятный графический интерфейс с использованием Tkinter.
  - Отображение списка задач с возможностью сортировки и фильтрации. 
  - Поиск задач по ключевым словам.
- Дополнительные возможности:
  - Экспорт и импорт задач в формате CSV.
  - Отображение статистики выполненных и невыполненных задач.
  - Настройки приложения (например, изменение темы интерфейса).
## Архитектура
Проект построен с использованием объектно-ориентированного подхода и разделен на следующие основные компоненты:
### Классы
1. Task (Задача)
   - Атрибуты:
     - id (int): Уникальный идентификатор задачи. 
     - title (str): Название задачи.
     - description (str): Подробное описание задачи.  
     - priority (str): Приоритет задачи (`"низкий"`, "средний", `"высокий"`).
     - deadline (datetime): Дедлайн выполнения задачи.
     -  category (str): Категория или проект, к которому относится задача.
     - status (str): Статус задачи (`"в процессе"`, `"выполнена"`).
   - Методы:
     - mark_as_completed(): Отметить задачу как выполненную.
     - update(**kwargs): Обновить информацию о задаче.
2. TaskManager (Менеджер задач)
   - Атрибуты:    
     - tasks (List[Task]): Список всех задач пользователя.
   - Методы:
     - add_task(task: Task): Добавить новую задачу.
     - remove_task(task_id: int): Удалить задачу по ID.    
     - get_task(task_id: int) -> Task: Получить задачу по ID.
     - update_task(task_id: int, **kwargs): Обновить задачу.
     - filter_tasks(**criteria) -> List[Task]: Получить список задач по заданным критериям.
     - load_tasks(file_path: str): Загрузить задачи из файла.
     - save_tasks(file_path: str): Сохранить задачи в файл.
3. NotificationManager (Менеджер уведомлений)
   - Методы:
     - schedule_notifications(): Запланировать уведомления для задач с дедлайнами.   
     - send_notification(task: Task): Отправить уведомление пользователю.
### Функции
- GUI функции (в `views/`):
  - `create_mai
