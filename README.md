# dogs_life_p1

url: https://deliveringtechnology2018.atlassian.net/wiki/spaces/CC21S/pages/2487877633/2023+Material

8*b?>)_XU+

@Query(nativeQuery = true, value = "SELECT t.* FROM trades t JOIN book_users bu ON t.book_id = bu.book_id JOIN users u ON bu.user_id = u.user_id JOIN security s ON t.security_id = s.security_id WHERE u.user_id = :user_id AND s.maturity_date BETWEEN CURDATE() - INTERVAL 5 DAY AND CURDATE() + INTERVAL 5 DAY")
List<Trade> getTradesByUserIdAndMaturityDateInRange(@Param("user_id") int userId);


@Query("SELECT t FROM Trade t " +
       "JOIN BookUsers bu ON t.book_id = bu.book_id " +
       "JOIN Users u ON bu.user_id = u.user_id " +
       "JOIN Security s ON t.security_id = s.security_id " +
       "WHERE u.user_id = :user_id " +
       "AND s.maturity_date BETWEEN FUNCTION('DATE_SUB', CURRENT_DATE, 5) AND FUNCTION('DATE_ADD', CURRENT_DATE, 5)")
List<Trade> getTradesByUserIdAndMaturityDateInRange(@Param("user_id") int userId);
