## Solution map
Solution maps are objects that are used to track state of specific problems, and dispatch solutions to those areas based on amount of available resources, and priority of all problems.

### Objects
#### Issue
Category that describes an issue - may contain subissues. Contains a priority.

#### Resource
Category that describes amount of a specific resource that is
available. Made up of resource units.

#### Resource unit
A single unit of a specific resource type.

#### Resource pool
A set of resources and their respective units that may be allocated
to solutions in map.

#### Solution
An object that reduces priority of a specific issue - made up of solution units, a cost,
and evidence that definitively and/or probabalisticly supports solution's effectiveness.

#### Solution unit
Incremental part of a solution's implementation.

#### Priority
Measure of how important an issue is based on damage caused.

#### Cost
Amount of resource units from pool of resources that are needed to implement a specific solution and its solution units.

### Operations
    - Update    (Reads available resources, costs, and issue priorities,
                 then selects solutions and/or solution
                 units based on what reduces priorities the most)
    - Apply     (Applies a solution unit of a specific
                 solution in map, in order to implement it)
    - Remove    (Removes a solution unit of a specific
                 solution in map)

### Solution types
    - Awareness     (Increases knowledge and understanding of issue by everybody)
    - Resilience    (Enables damage to be reversed more easily
                     if it is caused)
    - Prevention    (Stops damage before it is done)
    - Progress      (Increases progress made in reduction of issue)
