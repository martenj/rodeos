.. _use_case_admin:

=======================
Administrator Use Cases
=======================

This section describes the use cases for the administrator.

.. _use_case_team_setup:

-----------------
Create a new Unit
-----------------

In this use case the RODEOS (iRODS) administrator creates a new data generation unit.
The steps are as follows:

1. Create a new group in the underlying unix user/group management system and add all users to it.
2. Create a user for the sequencers in the unit's home organization user directory and make them known in the HPC system as well.
3. Setup the landing zones on the storage system and assign appropriate Unix ownership and permissions.
4. Setup the ingest users in the unit's home organization user directory.
5. Setup the ingest server with ingest jobs.

Steps 1-5 can be automated with the RODEOS installation Ansible playbooks.

6. Create a group for the unit members in iRODS and add them to the group.
7. For the group members that should be able to manage groups for the customers, adjust the meta data attribute ``rodeos::sudo::group-prefix`` and inform users about the prefix to use.
