### There is only one way to scale this system, go to cloud and add auto scaling!
- I love when I hear this kind of thing, nowadays, some developers talk and write about auto scaling as a "Silver bullet", and I think: "Yes, it is, but, why would you buy a gun, a silver bullet, a course to learn how to shoot, train for six monthes and then you kill a ant with your "Silver Bullet"?"
- Every decision you make in software development should be directly related with the money you (or your company) can spend! 
- Ok, but my system is slow, what should I do?
	- Find the problem, use pareto principle and eisenhower matrix to find out which part of the system should you start optimizing and then start with the basics:
		- Fix database optimization problems? **(Low Cost / High benefit)**
			- Are the indices correctly created?
			- Are Fill Factor correctly used?
			- Are the query correctly created?
			- The query filter is correctly used? (where in int, biging when possible, avoid concat)
			- Did you analyze the query plan (execution plan)?
			- Is yours primary keys ordered?
			- Ask DBA for help
		- Fix ORM problems?  **(Low Cost / High benefit)**
			- Search for N + 1 problems and solve them
			- Use Eager Loading when possible
			- Are the ORM configurations correctly created?
		

I'll continue later :)
