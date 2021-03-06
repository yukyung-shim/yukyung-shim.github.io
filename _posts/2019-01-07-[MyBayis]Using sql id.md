---
title: "[MyBatis]반복되는 쿼리 묶기 (sql id, include)"
layout: posts
toc: false
categories:
  - Database
last_modified_at: 2019-01-07T15:47:00+09:00

---

같은 쿼리를 다른 쿼리에서 중복되어 사용될 때 사용할 수 있다.  

다음과 같이 사용할 수 있다.  

1. 반복되는 검색 조건 묶기  

``` markdown
<mapper>
...
  <sql id="selectAll">  <!-- 전체 검색 -->
    SELECT
      * <!-- 현재 * 로 표시했지만 중복 조회되는 컬럼 등을 사용할 수 있다. -->

  </sql>

  <select id="selectAllList" resultType="java.util.Map">
    <include refid="selectAll" /> <!-- TB_EXAMPLE table 전체 검색 -->
      FROM TB_EXAMPLE
     WHERE 1=1

  </select>
  ...
</mapper>  
```

2. 입력받은 파라미터값 동적할당하기

``` markdown
<mapper>
...
  <sql id="orderByNo">  <!-- 입력받은 orderByType: asc or desc 에 따라 sort -->
    ORDER BY NO ${orderByType}
  </sql>

  <select id="selectAllList" parameterType="java.util.Map" resultType="java.util.Map">
    SELECT <!-- 조회된 리스트를 입력받은 orderByType에 따라 정렬 -->
      *
      FROM TB_EXAMPLE
     WHERE 1=1
      AND ...
    <include refid="orderByNo" />
  </select>
  ...
</mapper>  
```
