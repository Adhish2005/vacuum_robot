# Cleaning Robot Algorithms

This is simple cleaning robot algorithm written in Python. It assumes the following:

- Map can be interpreted as 2-d grid, with obstacles as obstructed points in the map.
- Obstacles can be arbitrary, both in quantity and position.
- The algorithm knows nothing about the surrounding environment.
- The robot only provides 3 API: turn_left, turn_right (rotate the looking direction) and move (move ahead 1 point)

The goal of the algorithm is to make the robot travel around room, with any point in the room visited at least one.

# how does it work

The algorithm (sweeper.py) works as follow:

1. Initialize the observed map to empty, current position to (0, 0)
2. Find the nearest unvisited point in observed map using Breadth-First Search
3. If cannot find, algorithm stops, and the accessible part of the room has been cleaned. Otherwise go to step 4
4. Move the robot to the position found in step 2, with each step updating the current position.
5. If it cannot move to the desired position, mark the position as obstructed in observed map, otherwise mark it as visited.
5. Go back to step 2


# demo

A demonstration can be found in https://adhish2005.github.io/vacuum_robot/

The code for the demonstration is placed under `showdown/` folder. It will compare the efficiency of different algorithms in randomly generated matrices.
