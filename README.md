# TAs Lab Slot Assignment using Logical Programming

This Prolog project implements a scheduling system to assign weekly labs of a course to the available Teaching Assistants (TAs). The assignment ensures that no TA exceeds their teaching load and adheres to the maximum number of slots per day.

## Overview

The project includes the following functionalities:
1. Assigning TAs to lab slots.
2. Ensuring no TA exceeds their teaching load.
3. Limiting the number of slots assigned to each TA per day.
4. Generating daily and weekly schedules for TAs.

### Why Prolog?

Prolog is used for this project due to its backtracking nature, which makes it well-suited for solving constraint satisfaction problems like scheduling. Prolog's built-in backtracking mechanism efficiently explores all possible assignments and ensures that the constraints are satisfied. This makes Prolog an excellent choice for implementing the scheduling system.

## Setup

To run this project, you need to have SWI-Prolog installed, or you can use an online Prolog debugger.

## Running Tests
You can run the following test in your SWI-Prolog environment to verify the functionality of the code:

### Test Week Schedule
```prolog
?- week_schedule([[1, 1, 2, 1, 0], [0, 0, 0, 0, 0],
                  [0, 0, 0, 0, 0], [0, 2, 0, 0, 0], 
                  [0, 2, 1, 1, 0], [1, 0, 1, 1, 1]],
                 [ta(kate, 8), ta(mike, 4), ta(nina, 3)],
                 3,
                 WeekSched).
% Some acceptable outcomes :
% WeekSched = [[[kate], [mike], [kate, nina], [mike], []],
%              [[], [], [], [], []],
%              [[], [], [], [], []],
%              [[], [mike, nina], [], [], []],
%              [[], [kate, mike], [kate], [nina], []],
%              [[nina], [], [kate], [kate], [mike]]].
%
% WeekSched = [[[kate], [kate], [kate, mike], [mike], []],
%              [[], [], [], [], []],
%              [[], [], [], [], []],
%              [[], [kate, mike], [], [], []],
%              [[], [kate, mike], [kate], [kate], []],
%              [[kate], [], [nina], [nina], [nina]]].
%
% WeekSched = [[[kate], [kate], [kate, mike], [mike], []],
%              [[], [], [], [], []],
%              [[], [], [], [], []],
%              [[], [kate, mike], [], [], []],
%              [[], [kate, mike], [kate], [kate], []],
%              [[nina], [], [kate], [nina], [nina]]].
%
% WeekSched = [[[kate], [kate], [kate, mike], [mike], []],
%              [[], [], [], [], []],
%              [[], [], [], [], []],
%              [[], [kate, mike], [], [], []],
%              [[], [kate, mike], [kate], [kate], []],
%              [[nina], [], [nina], [kate], [nina]]].
% WeekSched = [ ....
```


## File Structure
1. ta_slot_assignment/3: Decrements the load of a TA by 1 if the TA's name matches the given name. 
2. slot_assignment/4: Assigns TAs to lab slots.
3. slot_assignment_helper1/3: Helper predicate for slot_assignment/4. 
4. slot_assignment_helper2/3: Updates the remaining load of each TA after the assignment. 
5. max_slots_per_day/2: Checks if any TA exceeds the maximum number of slots per day.
6. max_slots_per_day_helper/2: Helper predicate for max_slots_per_day/2.
7. occ/3: Counts occurrences of a TA's name in the list.
8. my_delete/3: Deletes all occurrences of a TA's name from the list.
9. day_schedule/4: Generates a daily schedule for TAs based on the lab slots.
10. week_schedule/4: Generates a weekly schedule for TAs ensuring no TA exceeds the daily maximum slots.

## Contributing
If you'd like to contribute to this project, please fork the repository and use a feature branch. Pull requests are welcome.

## Contact
If you have any questions or suggestions, feel free to reach out to me @*georgeelswef@gmail.com*

Enjoy exploring the world of logical programming and backtracking with this demonstrative project! **Happy coding! 🚀**
