Query
-
```postgresql
SELECT Н_УЧЕНИКИ.ГРУППА, CONCAT(Н_ЛЮДИ.ФАМИЛИЯ, ' ', Н_ЛЮДИ.ИМЯ, ' ', Н_ЛЮДИ.ОТЧЕСТВО) AS ФИО FROM Н_ЛЮДИ
    JOIN Н_УЧЕНИКИ ON Н_ЛЮДИ.ИД = Н_УЧЕНИКИ.ЧЛВК_ИД
    JOIN Н_ПЛАНЫ ON Н_УЧЕНИКИ.ПЛАН_ИД = Н_ПЛАНЫ.ИД
    JOIN Н_ФОРМЫ_ОБУЧЕНИЯ ON Н_ПЛАНЫ.ФО_ИД = Н_ФОРМЫ_ОБУЧЕНИЯ.ИД
WHERE Н_УЧЕНИКИ.ПРИЗНАК = 'отчисл'
    AND Н_УЧЕНИКИ.КОНЕЦ > '2012-09-01'
    AND Н_ФОРМЫ_ОБУЧЕНИЯ.НАИМЕНОВАНИЕ IN ('Очная');
```