# filmorate-ER-diagramm
Диаграмма базы данных по промежуточному заданию 11го спринта  
Ниже ссылки на диаграмму в Miro и на картинку.  
### Для извлечения всех пользователей можно написать код:  
'''
SELECT *  
FROM user;  
'''
Для получения 10 самых популярных фильмов:  
SELECT f.name,  
      COUNT(l.user_id) AS likes  
FROM film AS f  
LEFT OUTER JOIN likes AS l ON f.film_id = l.film_id  
GROUP BY film_id  
ORDER BY likes DESC  
LIMIT 10;  
Для получения общих друзей пользователей с ID = 3 и c ID = 5:  
SELECT *  
FROM user AS u  
INNER JOIN friends AS f ON u.user_id = f.friend_id  
WHERE f.user_id = 3  
INNER JOIN friend ON f.user_id = f.friend_id  
WHERE f.user_id = 5;  
Followers - это те кто подал заявки в друзья, но она пока не подтверждена.

[Ссылка на Miro](https://miro.com/app/board/uXjVPjUyfgk=/?share_link_id=576475642129)

![Ссылка на картинку](https://github.com/RybkinMike/filmorate-ER-diagramm/blob/main/Filmoratr%20(2).jpg)
