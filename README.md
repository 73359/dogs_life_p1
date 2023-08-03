# dogs_life_p1

url: https://deliveringtechnology2018.atlassian.net/wiki/spaces/CC21S/pages/2487877633/2023+Material

8*b?>)_XU+




2023-08-03 14:53:18.612  WARN 5564 --- [nio-8080-exec-2] o.h.engine.jdbc.spi.SqlExceptionHelper   : SQL Error: 90022, SQLState: 90022
2023-08-03 14:53:18.612 ERROR 5564 --- [nio-8080-exec-2] o.h.engine.jdbc.spi.SqlExceptionHelper   : Function "DATE_SUB" not found; SQL statement:
SELECT t FROM Trades t JOIN book_users bu ON t.book_id = bu.book_id JOIN users u ON bu.user_id = u.user_id JOIN security s ON t.security_id = s.security_id WHERE u.user_id = ? AND s.maturity_date BETWEEN DATE_SUB(CURRENT_DATE, 5) AND DATE_ADD(CURRENT_DATE, 5) [90022-212]
