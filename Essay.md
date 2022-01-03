## Intro
In Douglas Hubbard's book "How to Measure Anything", he specifies three reasons why measurements matter; they 'informs key decisions', they have their 'own market value [...] and could be sold to other parties for profit', and a measurement can simply 'entertain or satisfy a curiosity'. He goes on to note that “anything that is important and is observable is measurable with some work."
There is a lack of a standardised metric and technique of processing metrics in the software engineering world to monitor the performance of a team and thus a wide range of metrics are used from individual developers to tech giants. 
## Metrics
Before getting into the details of metrics used in software engineering, we first must examine some of the common issues with these metrics.
#### Defining value in Software Engineering
Metrics are the gold dust of the business world. In many fields a metric can be easily defined, for example, in the world of marketing a quota might be used to measure productivity or value. 
The measurement of software engineering can be a deceiving task. There are many metrics that are easy to measure and call productivity however they often don’t factor in value. Software engineering is often compared to the creation of art. The value of a piece of art is not defined by the amount of medium used or its size. 
#### Gamification
A common drawback of these metrics is their potential for gamification. Gamification is the application of a strategy to “play” a system for a specific outcome. As Goldratt said: “Tell me how you measure me, and I will tell you how I will behave.”
From the perspective of a company, who wishes to boost their profits, software engineers being distracted from creating high quality code in favour of fulfilling a metric to boost their performance in the eyes of their supervisors, is clearly not favourable.
#### Complexity
There is limiting factor in the complexity of the metric put in place. It needs to be well-balanced (represent quality and functionality and collaboration within a team) and also be understandable by superiors (managers, executives, etc.) who may be less technologically literate, or be managing a wide range of teams. These two things which can be incredibly time-consuming to balance to the point of a truly “fair” metric not being feasible.
### Metrics
There are quite a large number of metrics that are in use today. I will try to detail the most interesting or most commonly used.
#### Lines of Code
The most obvious metric in software engineering is measuring productivity by lines of code, also known as source lines of code (https://en.wikipedia.org/wiki/Source_lines_of_code). It is easy to compute and easy to understand by people with limited knowledge of software engineering. 
It has a major drawback in that it, like many other metrics, is relatively easily gamified. It is often easy to draw out a single line of code into many, e.g., a for loop has the instantiation of the counter (int i = 0), the loop condition (i < 3), and the incrementor/decrementor (i++/i--) on the same line. This can be easily drawn out to multiple lines of code by using a while loop instead. 
##### Source versus Logical
The above metric can more specifically be described as physical source lines of code where simply the number of lines is counted, and comments are excluded from this count. The above example of gamification in physical SLOC can be partially remedied by using logical lines of code (LLOC) as a metric. LLOC counts some form of executable “statements” (Note: this varies between languages). For example, in the line of code for(i=1;i<3;i++) LLOC would count this as 3 lines. However, LLOC doesn’t prevent a software engineer from inserting useless/redundant lines of code, e.g., code duplication (which is discouraged due to it increasing the potential for bugs).
Additionally, many of these metrics should not be used to compare code written in different coding languages as these languages may have inherent differences in their verbosity. A software engineer may opt for a more verbose language to increase their performance over choosing a more suitable language for a task. 
This metric was more appropriate and popular when languages such as assembly and FORTRAN were popular, as these are line-oriented languages that don’t have the scope for formatting like modern languages do. Further reading (https://www.ifpug.org/content/documents/Jones-LinesofCodeMetricV6.pdf)
#### Number of Commits
The use of number of commits as a metric encourages software engineers to commit more regularly. This can be beneficial as it increases transparency within a team. Additionally, bugs or misinterpretations of tasks can be caught quicker if these commits are monitored regularly.
However, this metric also suffers from being easily gamified. It can be partially remedied by also tracking the number of lines of code added/deleted/modified and using this to attempt to weight the value of commits. However, low quality code can still be used to game this system.
#### Bugs per KLOC
Bugs per KLOC (1000 LOC) can help to give a quality metric. The constraints of this metric would be defined ahead of time (is a bug simply 1 line or many? Does the point of production in which the bug is caught matter? Etc.)
It is important that code generated is as bug-free as possible as the maintenance and debugging of code can be expensive ((https://web.archive.org/web/20090610052743/http://www.nist.gov/public_affairs/releases/n02-10.htm). 
Additionally, some code needs to be bug free (NASA, self-driving cars), and thus huge amounts of money are poured into ensuring this which may make this inappropriate in some industries.
Furthermore, the cons of using LOC as a metric also apply here.
#### Velocity
Agile Velocity is frequently used in industry as a productivity metric (e.g., https://gitlab.com/gitlab-com/www-gitlab-com/-/issues/3906). Agile Velocity is generated by calculating the sum of the weighted number of tasks or stories completed in a regular interval or sprint. The tasks and their weights are selected and assigned during the planning phase of a project. The purpose of velocity is as a delivery forecasting tool by giving an estimation as to the amount of work a team can complete in a time period and using this to estimate the amount of time it would take to reach other project milestones.
Unfortunately, this is a planning tool that has been co-opted into a performance metric which results in a number of shortcomings. 
The weight of a task is assigned before the completion of a task and therefore might not be an accurate reflection of the task’s completion in reality.
Its use as a performance metric may also undermine its use as a forecasting tool. In a scenario where management, using velocity as a metric of team performance, ask for productivity to increase by 100% a team can gamify this system by doubling the weight assigned to each task, thus increasing their apparent productivity without any impact on the actual productivity. I’ll discuss the misuse of metrics in software engineering by less technologically literate supervisors in the fourth section.
#### ”Impact”
Impact is a newer metric. It has it’s basis in LOC but it uses a combination of other measurable factors such as number of files modified, bugs per KLOC, etc.. This allows team collaboration (through a tool such as team messages and mentoring) and elements of code quality to be factored in as required.
While this can be made as broad as necessary, it can be very time consuming to try implement in a balanced fashion to the point of infeasibility. Furthermore, its complexity can increase it being misinterpreted, and even diminish the trust of software engineers in the system that is used to track their productivity.

---

As can be seen, many of these metrics fall apart when used to compare the productivity of code written in different languages or for different tasks. It could be argued that 
At what point do the metrics generated between two projects become like “comparing apples to oranges” and simply not feasible to do so to a degree that honours the quality of the code appropriately?
Referring back to Hubbard’s book, Hubbard calls out the haste to measure for the sake of measuring without thoroughly defining what the data will be used for once collected. Metrics that are easy to measure or that are already generated due to the nature of how code is generated (e.g., LOC) are sometimes used out of ‘laziness’ in my opinion.
 
## Tools for Gathering Data
### GitPrime
### Velocity 2.0 
## Computation on Data Collected
### AI/ML 
## Ethical, Moral and Legal Concerns
Before getting into this topic, it is worth noting how vast an area this is. It seems as though technology companies are finding new and exciting ways to act unethically is a constant news item.  
Innovation is the bread and butter of tech companies. At this point in time the state of technology can be summed up by the Jurassic Park quote, “your scientists were so preoccupied with whether or not they could, they didn't stop to think if they should”.
While this may seem a little removed from the topic of “Measuring Software Engineering”, the ways in which Big Tech traverses legality and ethics applies to its employees, its customers and beyond.
### Legal
#### Size of Tech Companies
We have gotten to the point in time where technological access and literacy is vital to exist in many parts of the world. As a result, tech companies are raking in astronomical amounts of money. This phenomenon is referred to by economists as the “network effect”. Which begs the question, what can this money buy?
#### What money can buy
Technology is the biggest lobby sector in the EU in terms of spending. Something else of note is that these companies are not lobbying as individuals but rather have a business association that lobbies on their behalf with a budget that “far surpasses that of the bottom 75 per cent of the companies in the digital industry”. Furthermore, despite the EU leading the way on the regulation of tech (https://www.cnbc.com/2021/03/25/big-tech-how-europe-became-the-worlds-top-regulator.html) the EU Commission is in bed with Big Tech. “[The EU] Commission high-level officials held 271 meetings, 75 percent of them with industry lobbyists. Google and Facebook led the pack.” (https://corporateeurope.org/en/2021/08/lobby-network-big-techs-web-influence-eu).
#### Legislation always behind the Curve
#### Lack of expertise by Legislators
It is well-documented that the ethical impact and legislation of technology in general hasn’t been taken a seriously as it should have been in the past. As a result, the power of technology remained underestimated and now legislative catch-up is happening. And it is a joke. Specifically looking at the US, searching “congressional hearing technology” will present you with countless examples of the very people in charge of regulating technology asking painfully uninformed questions. Such poor questions, in fact, that even after the stock hit of Cambridge Analytica scandal, Mark Zuckerberg made $3 billion dollars during his questioning by US congress (https://money.cnn.com/2018/04/12/investing/facebook-stock-mark-zuckerberg-congress/index.html). 
Sticking with the US Congress and Senate, “[t]oday, the average age of a Representative is 57 and the average of a Senator is 61” (https://www.quorum.us/data-driven-insights/the-115th-congress-is-among-the-oldest-in-history/) and it’s no surprise it’s having an impact (https://www.washingtonpost.com/powerpost/how-the-oldest-senate-ever-is-taking-a-toll-on-the-operations-of-washington/2017/12/16/349f27b8-e1b3-11e7-89e8-edec16379010_story.html?utm_term=.f4e7f5e6c58e). @turkmmtz on Twitter summed it up well: “How 70-80 year olds are generally regarded as unemployable due to mental decline/skill mismatch - yet they're exclusively running the country” (https://mobile.twitter.com/turkmmtz/status/1424746756118548485) 
### Ethical
For the question of ethics I’m going to focus in on the interactions between a technology company and its software engineers.
#### Is any data collection ethical?
The data collected in the code generated by a software engineer for a company is inherent in the code and has no ethical implications in my eyes.
However, employers are tracking their employees more and more for the purpose of increasing productivity (https://www.npr.org/2021/10/02/1042667303/companies-are-using-a-growing-number-of-tracking-services-as-employees-work-from?t=1641246770527).  
#### Lack of knowledge regarding the Interpretation of Metrics
#### Automated Systems/Lazy Superiors
#### Selling of Data
### Security of Data

-

Because of the relative lack of consequences on Tech Giants for acting unethical, they will continue to be unethical, either for profit or out of laziness.
	
