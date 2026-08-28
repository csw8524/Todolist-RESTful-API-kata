# 任務二

## 作業一

```sql
CREATE TABLE classes (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50) NOT NULL
);

CREATE TABLE students (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    class_id INTEGER NOT NULL,
    gender VARCHAR(1) NOT NULL,
    age INTEGER NOT NULL,
    FOREIGN KEY (class_id) REFERENCES classes(id)
);

INSERT INTO classes (name) VALUES
    ('三年一班'),
    ('三年二班');
    
INSERT INTO students (name, class_id, gender, age) VALUES
    ('小明', 1, '男', 8),
    ('小華', 2, '女', 9),
    ('小美', 1, '男', 8),
    ('小強', 1, '女', 8),
    ('小智', 2, '男', 9);
```

## 作業二

```sql
ALTER TABLE classes
ADD teacher VARCHAR(50) NOT NULL;

UPDATE classes SET teacher = '廖洧杰' WHERE id = 1;
UPDATE classes SET teacher = '卡斯伯' WHERE id = 2;

```

## 作業三

```sql
CREATE TABLE parents(
    id SERIAL PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    phone VARCHAR (20),
    gender VARCHAR (1) NOT NULL
);

ALTER TABLE students
ADD parent_id INTEGER;

ALTER TABLE students
ADD CONSTRAINT fk_students_parents
FOREIGN KEY (parent_id) REFERENCES parents(id);
```
