Программироание корпортаивных систем

Тучин Владислав ЭФБО-06-23

Отчет по Практической работе №10

Скриншот первого запуска:


<img width="495" height="1093" alt="без_зам" src="https://github.com/user-attachments/assets/2d4b755d-0284-4bf2-afcb-c0ae7e4b32d6" />


Скриншот после добавления заметки:


<img width="495" height="1100" alt="создал" src="https://github.com/user-attachments/assets/093e39bb-a6eb-4083-b354-015c9844bc11" />



Скриншот окна редактирования и итоговой записи:



<img width="488" height="1107" alt="изменение" src="https://github.com/user-attachments/assets/381b59b9-3581-44a5-81f5-42786844107e" />
<img width="493" height="1099" alt="после" src="https://github.com/user-attachments/assets/89db367d-e5cb-4e45-aa41-c10a3e80c30c" />


Скриншот после удаления:

<img width="491" height="1102" alt="удл" src="https://github.com/user-attachments/assets/9214851d-9de7-4b48-b914-eecca3aca3b0" />
<img width="495" height="1100" alt="послеудл" src="https://github.com/user-attachments/assets/28e1f76e-0d9a-4d0c-a650-8d550e8c6612" />

Расположение файла DB:

Файл базы данных app.db хранится в директории документов приложения, путь к которой зависит от платформы

Доступ к DB:

static Future _open() async {

final docs = await getApplicationDocumentsDirectory();

final dbPath = p.join(docs.path, _dbName);

return await openDatabase(dbPath, version: _dbVersion, onCreate: _onCreate);

}

Таблица notes:

CREATE TABLE notes(

id INTEGER PRIMARY KEY AUTOINCREMENT,

title TEXT NOT NULL,

body TEXT NOT NULL,

created_at INTEGER NOT NULL,

updated_at INTEGER NOT NULL

);

Индексы:

CREATE INDEX idx_notes_created_at ON notes(created_at DESC);

CRUD операции:

Создание - INSERT


<img width="792" height="178" alt="image" src="https://github.com/user-attachments/assets/6dea46ab-db12-4b82-ba3a-4f92c29ad093" />

Чтение - SELECT


<img width="1058" height="169" alt="image" src="https://github.com/user-attachments/assets/6b87ce31-2b50-46f3-88ae-f18e8ca45849" />

Обновление - UPDATE


<img width="745" height="318" alt="image" src="https://github.com/user-attachments/assets/d89ad54f-4ca1-4b00-a854-6265b48f93a3" />

Поиск заметок: не делал



