# SQL Table Manipulation and Cleaning
This is a project on various edits made to the column of a table including the tables entries

## Table Creation
```SQL
INSERT INTO Sales
(Name, Age, Gender)

VALUES
('Tinu', 25, 'female'),
('Aminu', 19, 'male'),
('Temi', 27, 'female');
```

<img width="270" height="173" alt="1" src="https://github.com/user-attachments/assets/21556fdb-958c-489f-90ac-31fb27332585" />

### 1. To Delete the Gender column in the table

```SQL
ALTER TABLE Sales
DROP COLUMN Gender;
```

<img width="231" height="177" alt="3" src="https://github.com/user-attachments/assets/5a41369c-d86f-4936-a2d4-9d5ef9b23136" />

### 2. To Rename the Name column to Humans

```SQL
ALTER TABLE Sales
RENAME COLUMN Name
TO Humans;
```

<img width="224" height="174" alt="5" src="https://github.com/user-attachments/assets/5ee895f8-875f-44e9-8fb8-5da5917b2625" />

### 3. To Add a new column to the table

```SQL
ALTER TABLE Sales
ADD COLUMN Gender;
```

<img width="242" height="173" alt="7" src="https://github.com/user-attachments/assets/38edc94f-37b2-4200-8dc6-558ddd35a8fe" />

### 4. To fill the NULL gender column above

### Feamle 

```SQL
UPDATE Sales
SET Gender = 'Female'
WHERE Humans IN ('Tinu', 'Temi');
```
<img width="219" height="169" alt="9" src="https://github.com/user-attachments/assets/0c96ea63-5edf-45d0-888c-655051677137" />

### Male

```SQL
UPDATE Sales
SET Gender = 'Male'
WHERE Humans LIKE '%Aminu%';
```

<img width="239" height="175" alt="11" src="https://github.com/user-attachments/assets/7ff036fd-65ba-49f0-90f3-ac52c810efd7" />

### 5. Introducing CASE 

I used the age factor to classify both genders with one SQL Code

```SQL
SELECT Humans, Age, 
CASE
WHEN Age <=19 THEN 'Male'
ELSE 'Female'
END AS Gender
FROM Sales;
```
<img width="177" height="112" alt="Image" src="https://github.com/user-attachments/assets/5aca7079-eb2d-429e-ad09-ef0d95fb279c" />
