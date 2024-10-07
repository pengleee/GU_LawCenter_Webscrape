# GU_Webscrape

This is a naive webscrape script for GU law center directory.

AI regulation is a hot topic right now, and many times it's lawyers who are leading the discussions and influencing policymakers. One of the aspects of our project is aimed at understanding how lawyers and policy professionals think about new technologies like AI, especially when they haven't taken formal coursework in CS or machine learning. To get at this question, I'm running an IRB-approved survey at Georgetown with help from the law school.

For starters, it would be very helpful if you could help me scrape the Georgetown directory and filter by law student status. So basically output would be a `.csv` file with 3-5 columns:

1. Affiliation (confirm law school, or finer detail if available)
    - The Georgetown University Law Center is the law school of Georgetown University, a private research university in Washington, D.C., United States. It was established in 1870 and is the largest law school in the United States by enrollment, with over 2,000 students.
2. Status (student, staff, faculty, etc --- if you can collect the meta, I'll filter these on my own, since there may be duplicate roles)
3. Georgetown .edu email address
4. Year in program and major (only if available)

That's it. No need to include anyone's names etc. We don't want to collect anyone's personal info from the directory so please leave that out.