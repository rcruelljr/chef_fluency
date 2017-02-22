# Resources

Resources are statements that describe the desired configuration
for a node.
Resources are included in recipes.

*Resource components*
Resource Type
Resource Name
Resource Properties
Actions

*Package actions*
:install -- default action -- installs a packagae
:nothing -- does nothing until notified if used with notifier
:purge -- remove configuration files and packages
:reconfig -- reconfig packages
:remove -- removes a package
:upgrade -- install package -- if already installed, make sure it is up-to-date

*Source actions*
Actions that are available to the service resource type


## Idempotency/Convergence - Test & Repair model

*Convergence*
The action of testing the state of a resource to determine
if that resource is already in the desired state.

*Pre-convergence*
The phase prior to the node undergoing configuration. Linting
tests usually take place at this point.

*Post-convergence*
Execute unit tests to verify that the node has reached the
desired state of configuration.

*Idempotency*
If the node in question is already in the desired state, no
changes to the configuration of the node are made.

*Test & Repair*
The above items collectively define the test and repair model:
- If the node is not in the desired state take action.
- Determine if the node has reached convergence.
- On follow up attempts, determine the idempotency of the node.
If no changes need to be made, do nothing.

## Common resources and their actions

