# Ringworm-infection

The goal of this project was to simulate the process of ringworm infection spreading over an area of skin of size N x N cells (N - odd number). The initial infected skin cell is in the center. At each time interval, an infected cell can infect any of the neighboring healthy cells with a probability of 50%. After six units of time, the infected cell becomes immune to infection, the resulting immunity lasts for the next four units of time, and then the cell becomes healthy again. During the simulation of the described process, give the current state of the simulated skin area at each time interval, noting infected, immune and healthy cells. 

Implementation.
Classes:
- cell (base class): sets a certain location of a cell on the skin area, has getters for location of a cell (row and column numbers), status() and print() methods which have a certain way of identifying the class (status is 0, prints it out as a "." symbol)
- healthy (child class, parent - cell): has overwritten status() method (status is 1), print() method represents a healthy cell as "-" 
- immune (child class, parent - cell): status() method returns 2, has its own constructor for setting up the amount of time it stays immune and pointer to the next immune cell, methods for counting down units of time, making a cell healthy, getter and setter for pointers to the next cell in the list of immune cells. Prints out as "#"
- infected (child class, parent - immune): inherits from the immune class, status is 3, has methods for making cells ummine after being infected, infect() method for neighboring cells, prints out as "*". Manages time through parent class
- list: queue for keeping track of infected and immune cells, friend class for skin
- skin (area N x N cells): initializes skin area with cells, infects the central one, takes care of each cell state on every step of the process, prints out the skin area after every unit of time. 

Process of the infection spread varies every time the program in run thanks to the rand() function which is used on every step to define whether neighboring cells will be infected or not.
