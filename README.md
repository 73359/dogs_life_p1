# dogs_life_p1

url: https://deliveringtechnology2018.atlassian.net/wiki/spaces/CC21S/pages/2487877633/2023+Material

8*b?>)_XU+

@Query(nativeQuery = true, value = "SELECT t.* FROM trades t JOIN book_users bu ON t.book_id = bu.book_id JOIN users u ON bu.user_id = u.user_id JOIN security s ON t.security_id = s.security_id WHERE u.user_id = :user_id AND s.maturity_date BETWEEN CURDATE() - INTERVAL 5 DAY AND CURDATE() + INTERVAL 5 DAY")
List<Trade> getTradesByUserIdAndMaturityDateInRange(@Param("user_id") int userId);


{"timestamp":"2023-08-03T13:40:49.951+00:00","message":"could not prepare statement; SQL [SELECT t.* FROM trades t JOIN book_users bu ON t.book_id = bu.book_id JOIN users u ON bu.user_id = u.user_id JOIN security s ON t.security_id = s.security_id WHERE u.user_id = ? AND s.maturity_date BETWEEN CURDATE() - INTERVAL 5 DAY AND CURDATE() + INTERVAL 5 DAY]; nested exception is org.hibernate.exception.SQLGrammarException: could not prepare statement","details":"uri=/api/v1/bondtrades/for/1/duetomature"}


2023-08-03 14:40:49.949  WARN 896 --- [nio-8080-exec-2] o.h.engine.jdbc.spi.SqlExceptionHelper   : SQL Error: 42001, SQLState: 42001
2023-08-03 14:40:49.950 ERROR 896 --- [nio-8080-exec-2] o.h.engine.jdbc.spi.SqlExceptionHelper   : Syntax error in SQL statement "SELECT t.* FROM trades t JOIN book_users bu ON t.book_id = bu.book_id JOIN users u ON bu.user_id = u.user_id JOIN security s ON t.security_id = s.security_id WHERE u.user_id = ? AND s.maturity_date BETWEEN CURDATE() - INTERVAL [*]5 DAY AND CURDATE() + INTERVAL 5 DAY"; expected "-, +, string"; SQL statement:
SELECT t.* FROM trades t JOIN book_users bu ON t.book_id = bu.book_id JOIN users u ON bu.user_id = u.user_id JOIN security s ON t.security_id = s.security_id WHERE u.user_id = ? AND s.maturity_date BETWEEN CURDATE() - INTERVAL 5 DAY AND CURDATE() + INTERVAL 5 DAY [42001-212]
