# Ocean

The "Ocean" simulation system. A closed ecological system is modeled according to the predator-prey principle. 

** Simulation ** modeling in this case assumes that we do not use mathematical models, formulas, but we obtain simulation results based on the random interaction of objects in the ocean. 

### Entities:

- **Ocean** - two-dimensional matrix of cells. 
- **Cell** - an ocean cell that can either be empty or contain an object. 
- **Object** - an object that can occupy an ocean cell. 
- **Stone** - a stationary ocean object simply occupying a cell.
- **Prey** - prey fish. It moves randomly across the ocean, multiplies and dies at specified intervals. 
- **Predator** - predator fish. Moves across the ocean, eats prey fish, reproduces. May starve to death. 

### Stages 

At the initial stage, it is necessary to develop classes for the main entities. The ocean acts as a container for cells, a cell is a container for objects. All objects are combined into a collection and the ocean manages all objects through a loop. The ocean sends a **live ()** message to all objects, and each object behaves according to the given algorithm.  

As a result of the "vital activity" of objects in the ocean, the following events occur: 

- living objects randomly move to neighboring cells;
- living objects reproduce, feed and die; 

The simulation continues until:

- the user interrupts the process;
- food is running out in the ocean - **Prey** objects;
- there are no predators in the ocean - **Predators** objects; 

#### Prey

The lowest link in the food chain. Lives a given number of iterations. Performs free movement across the ocean in 1 cell step. It multiplies over a period of time. 

#### Predator

The predator is the highest link in the food chain. Inherits **Prey** behavior, but can starve and hunt prey. It can reproduce only when fed. 

### Результаты моделирования

At the beginning, the parameters of all objects are loaded into the ocean and objects are randomly placed (the number is specified in the parameters). After that, the main cycle turns on and then three outcomes are possible:

- Death of predators. Production fills all the available ocean space.
- Death of prey. Predators breed, but then inevitably die of hunger. The ocean is empty.
- Fluctuations in numbers. The number of predators and prey fluctuates according to a harmonious law. This is the preferred option. 


### Console version

Each object in the ocean is displayed on the screen with a specific symbol. Modeling assumes a random distribution of a given number of stones, prey and predators in the ocean (initial state) and a stepwise change in the state of the ocean. All objects make their move during a step. After that, a map of the ocean is displayed on the screen and the process loops.