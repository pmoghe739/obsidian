Planning your code is much more important than actually coding.

As a matter of habit as soon as a task is given to me , i start coding by creating classes and methods into it , for example given a task to show a user some data from the database, what i will do is create a model class, a controller and a view and go home thinking job done. 

The problem with this approach is what if requirements change some day ( and they will !! ) i did not think of scalability of the API , i did not check if some other model is already present in the code base that could be re-used this leads to clunky code base and bunch of if-else conditions which make the code very difficult to navigate, instead the correct approach is :

Take a step back and think about the problem statement as a whole in the mind, what problem are we trying to solve, how will it affect our business .
Then think is there already a solution available for it, jot down all the solutions that have a partial match with this problem .

Now that we have a hawk eye view of the problem we should be able to figure out the best case solution for our problem and given constraints and timelines.
This will help reduce bugs and regression issues in production and ship quality code and best **Solve big complex problems.**


