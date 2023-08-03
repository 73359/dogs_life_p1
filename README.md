# dogs_life_p1

url: https://deliveringtechnology2018.atlassian.net/wiki/spaces/CC21S/pages/2487877633/2023+Material

8*b?>)_XU+

{"timestamp":"2023-08-03T13:05:11.271+00:00","message":"Named parameter not bound : user_idAND; nested exception is org.hibernate.QueryException: Named parameter not bound : user_idAND","details":"uri=/api/v1/bondtrades/for/1/duetomature"}

@Query("SELECT t FROM Trades t " +
       "JOIN BookUsers bu ON t.book_id = bu.book_id " +
       "JOIN Users u ON bu.user_id = u.user_id " +
       "JOIN Security s ON t.security_id = s.security_id " +
       "WHERE u.user_id = :userId " +
       "AND s.maturity_date BETWEEN :startDate AND :endDate")
List<Trades> findTradesByUserIdAndMaturityDateBetween(@Param("userId") Long userId,
                                                      @Param("startDate") Date startDate,
                                                      @Param("endDate") Date endDate);
