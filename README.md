# Pewlett Hackard Analysis

## Overview

Due to a large number of employees soon to be eligible for retirement, Pewlett Hackard has asked us to perform an analysis to determine the number of retiring employees by their job title as well as the number of employees who are eligible for the mentorship program.

## Results

- From the analysis we found the total number of employees eligible to retire was 72,458

    ![alt text](https://github.com/tmidcalf/Pewlett-Hackard-Analysis/blob/main/Results/count_of_eligible_employees.png?raw=true)

- From the table below, we can see the number of employees eligible for retirement by their job description. 

    ![alt text](https://github.com/tmidcalf/Pewlett-Hackard-Analysis/blob/main/Results/count_of_eligible_employees_by_title.png?raw=true)

- The total number of employees eligible for mentorship came out ot 1549

    ![alt text](https://github.com/tmidcalf/Pewlett-Hackard-Analysis/blob/main/Results/count_of_mentorship_employees.png?raw=true)

- From the table below, we can see the number of employees eligible for mentorship by their job title.
  
    ![alt text](https://github.com/tmidcalf/Pewlett-Hackard-Analysis/blob/main/Results/count_of_mentorship_employees_by_title.png?raw=true)

## Summary

- If all eligible employees end up retiring, then Pewlett Hackard would need to fill nearly 72,000 jobs in order to maintain the same number of employees for each role.

- As there are currently 1,549 eligible employees to join the membership program and 72,458 employees eligible to retire, each mentor would have to work with 40 new employees. I would suggest Pewlett Hackard find more ways to increase the number of mentors to help with the amount of employees retiring. 

Another helpful chart or query would be the number of employees eligible for mentorship by their job title. The query for this could look something like this:

```
    SELECT 	 COUNT(emp_no),
		     title
    FROM 	 mentorship_eligibility
    GROUP BY title
    ORDER BY COUNT(emp_no) DESC;
```

One more helpful chart or query would be the number of employees eligible for retirement by their department. The query for this could look something like this:

```
    SELECT      COUNT(ut.emp_no),
		        d.dept_name
    FROM        unique_titles AS ut
    INNER JOIN  dept_emp AS de
    ON          (ut.emp_no = de.emp_no)
    INNER JOIN  departments AS d
    ON          (de.dept_no = d.dept_no)
    GROUP BY    d.dept_name
    ORDER BY    COUNT(ut.emp_no) DESC;
```

