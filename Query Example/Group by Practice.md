## Group By Practice & Aggragation

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
