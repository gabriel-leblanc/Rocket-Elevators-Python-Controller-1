# Rocket-Elevators-Python-Controller

The following code in Python is made to run tests on a residential elevators controller. The code includes 2 elevator cages. When a customer calls an elevator, when the elevator moves, the buttons inside of each elevator and all the logic behind each elevator behavior. Everything is shared between 5 classes. 


### Column
The columns are where the elevators move. A lot of logic happens here. 

>#### createCallButtons
The `createCallButtons` method creates the buttons that calls the elevators. So on each floor of a building, we would see two buttons, one going `up` and the other going `down`. The two exceptions on every building is the first floor where there's only an `up` button and on the last floor where there's only a `down` button.

>#### createElevators
Here we virtually generate the elevators that'll complete the tests. The elevators are compiled in a list in wich a new item is created when a user calls an elevator.

>#### requestElevator
Each time someone calls an elevator, a request is made to find an elevator. 

>#### findElevator
When a request is done, the code finds an available elevator. There are some conditions in that method that check what elevator suites best each situation. 

>#### checkIfElevatorIsBetter
The `find elevator` method return a `bestElevator` variable. That variable is compared in the `checkIfElevatorIsBetter` method to confirm or not if the best elevator has been chosen. If not, the best elevator is selected.

### Elevator
Here is the code that concerns the elevators.

>#### createFloorRequestButtons
All the buttons in each elevators are listed here. When a user press on a button, the elevator goes up or down (the list of floors goes +1 or -1) until the right floor. 

>#### requestFloor
Simply calls the elevators to move and to operates doors.

>#### move
This is where the movement is coded. So if the elevator is lower than the floor requested, the elevator goes up one floor. It does it again until it reaches the right floor. 

>#### sortFloorList
`sortFloorList` is the list of floors that "loses" one iteration at each floor. For example, if a user want to go from floor 1 to 6, the `sortFloorList` begins with [1, 2, 3, 4, 5, 6], then [2, 3, 4, 5, 6], [3, 4, 5, 6], (...), [6]. If a user goes down, it would do: [6, 5, 4, 3, 2, 1], [5, 4, 3, 2, 1], (...), [1].

>#### operateDoors
The `operateDoors` method is responsible for the opening, waiting and closing of the doors. It is set to gives 5 seconds to the users to enter or exit the elevator. 

### CallButton, FloorRequestButton and Door
These 3 classes initiate some parameters that are necessary for the rest of the code to works.
