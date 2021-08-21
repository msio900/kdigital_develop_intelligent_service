# 0802 : MARIA DB [SQL]

## `join`

```mariadb
SELECT e.deptno , d.deptname, e.empname FROM emp e INNER JOIN dept d
ON e.deptno = d.deptno;
```

ㄴ `emp`table과 `dept` table과`deptno`기준으로  `join`

```mariadb
SELECT t.titlename, e.empname 
FROM emp e INNER JOIN title t
ON e.titleno = t.titleno;
```

ㄴ `title`table과 `emp`table을 `titleno`을 기준으로 `join`

```mariadb
SELECT t.titlename, e.empname 
FROM emp e INNER JOIN title t
ON e.titleno = t.titleno
WHERE t.titlename='사원' OR t.titlename='대리';
```

* 사원정보를 출력하시오. (이름, 부서명, 지역명, 지위)

```mariadb
SELECT e.empname, d.deptname, d.deptloc, t.titlename
FROM emp e INNER JOIN dept d ON e.deptno = d.deptno
			  INNER JOIN title t ON e.titleno = t.titleno;
```

```mariadb
SELECT e.deptno, ROUND(AVG(salary),0) AS avg_sal
FROM emp e INNER JOIN title t ON e.titleno = t.titleno
WHERE t.titlename='사원' OR t.titlename='대리'
GROUP BY e.deptno
HAVING avg_sal >= 2500;
```

* 서브쿼리

```mariadb
/*
9-1. 서울과 부산에서 근무하는 직원들을 조회 하시오
*/

SELECT * FROM emp
WHERE deptno IN (SELECT deptno FROM dept 
WHERE deptloc = '서울' OR deptloc = '부산');
```

ㄴ `서브쿼리`는 서버에 부하를 줄 수 있음 그래서 `join`을 더 선호

```mariadb
SELECT * FROM emp e
	INNER JOIN dept d ON e.deptno = d.deptno
	WHERE d.deptloc IN ('서울','부산');

```

