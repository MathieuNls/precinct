
-	Tung Thanh Nguyen, Hoan Anh Nguyen, Nam H. Pham, Jafar M. Al-Kofahi, and Tien N. Nguyen. 2009. Clone-Aware Configuration Management. In Proceedings of the 2009 IEEE/ACM International Conference on Automated Software Engineering (ASE '09). IEEE Computer Society, Washington, DC, USA, 123-134.

Tung _et al_ proposed an advanced clone aware SCM (Source code Management) system named Clever. Their approach uses abstract syntax trees to detect, update and manage clones.
While efficient, their approach does not prevent the introduction of clones and is not incrementable. 
Consequently, developers have to purposely run a project-wide detection for each commit (i.e. version of the program).

The same team [Hoan Anh Nguyen; Tung Thanh Nguyen; Pham, N.H.; Al-Kofahi, J.; Nguyen, T.N., "Clone Management for Evolving Software," in Software Engineering, IEEE Transactions on , vol.38, no.5, pp.1008-1026, Sept.-Oct. 2012] then refined the detection, management and edition via a new tool called JSync.
JSync is an incremental clone detector, meaning that it will only perform the detection of clones on the new changes. 
Incremental clone detector based on AST can be challenging to implement, however, they obtained precision and efficiency with their implementation. 
While the new version of their work is incremental, precinct is different in a sense that it automatically prevents the insertion of clones while they rely on developers to run their approach manually.


-	Yuki Yamanaka, Eunjong Choi, Norihiro Yoshida, Katsuro Inoue, Tateki Sano: "Applying Clone Change Notification System into an Industrial Development Process", Proceedings of the 21st IEEE International Conference on Program Comprehension (ICPC 2013).

Yuki _et al_ conducted one of the few study on the how clone management can be applied to industrial system.
They implemented a tool named Clone Notifier at NEC with the help of experienced practitioners.
They specifically focus on clone insertion notification, very much like PRECINCT.
Differently to PRECINCT, however, they use an offline approach in which the changes are commited (i.e, they reach the central repository and anyone can pull them into they machines) and a central server analyzes the changes. 
If the commited changes contain newly inserted clone, then, an email notification is sent.
We first argue that detecting clones in an offline fashion can be damaging for the project as clone can be syncronized by other team members which can lead to challenging merges when the clones will be removed.
Secondly, they did not report any performances measurements and the longer it takes for the notification to be sent to the developer, the harder it can be for him to reconstruct the mind-map required for clone removal.
Unfortunately, we cannot assess this point for Clone Notifier.
PRECINCT, however, is able to perform an incremental online detection in a few seconds. 

-	Gode, N.; Koschke, R., "Incremental Clone Detection," in Software Maintenance and Reengineering, 2009. CSMR '09. 13th European Conference on , vol., no., pp.219-228, 24-27 March 2009
Hummel, Benjamin, et al. "Index-based code clone detection: incremental, distributed, scalable." Software Maintenance (ICSM), 2010 IEEE International Conference on. IEEE, 2010.


Gode and Koschke proposed an incremental clone detector that rely on the results of analysis from past version of the software to only analyzed what changed. 
Their clone detector takes the form of an IDE plugin that alerts developers as soon as a clone gets inserted in the program. 
We argue that alerting developer of clone insertion on-the-fly via IDE warning does more harm than good.
Indeed, Latoza _et al_ found that it exists six different reasons to duplicate code  ((a) separate developers implement same functionality, (b) copy and paste of example code, (c) design decision distributed over multiple methods, (d) copy of other team’s code base, (e) branch maintained separately, (f) reimplementation by same developer in different language) and developers are aware that they are creating clones in five out of the six situations (b, c, d, e, and f) [@LaToza2006].
Consequently, it only reach its purpose in the unlikely case of two developers re-implementing the same functionality.
In the other cases, it interrupts the developers can make them loose track of the task at hand hindering their productivity [@Ko2006d].