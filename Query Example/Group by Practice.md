## Group By Practice & Aggragation
> 교수와 학생은 서로 사는 County가 같은데,  
> 그 교수는 자신이 사는 County에서 가장 나이가 많고, 학생은 자신이 사는 County에서 점수가 가장 높은 학생이다.  

```SQL
SELECT Profinfo.name, Studinfo.name
FROM (SELECT professors.name, Agetable.county
      FROM (SELECT professors.county, MAX(professors.age) AS elder_age
            FROM professors
	    GROUP BY professors.county) Agetable, professors
      WHERE professors.age = Agetable.elder_age AND professors.county = Agetable.county) Profinfo,
      (SELECT students.name, Scoretable.county
       FROM (SELECT students.county, MAX(students.score) AS highest_score
	     FROM students
	     GROUP BY students.county) Scoretable, students
       WHERE students.score = Scoretable.highest_score AND students.county = Scoretable.county) Studinfo
WHERE Profinfo.county = Studinfo.county;
```

> COVID-19 감염자의 수가 가장 많은 도시 3곳을 뽑아,  
> 그 도시에 사는 학생을 출력한다.  
```SQL
SELECT students.name, TOP_three.city, TOP_three.patients_number
FROM (SELECT city, COUNT(city) AS patients_number
      FROM covid
      GROUP BY city   
      ORDER BY patients_number DESC
      LIMIT 3) TOP_three, students, counties
WHERE counties.city = TOP_three.city AND students.county = counties.countyName
ORDER BY patients_number DESC;
```
