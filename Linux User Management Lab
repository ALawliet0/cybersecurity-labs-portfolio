Project Description

This project demonstrates how to manage users and groups in a Linux environment using Bash commands.

As part of a cybersecurity training scenario, the objective was to ensure that new employees are properly added to the system, assigned to the correct primary and secondary groups, given ownership of project files, and removed when they leave the organization.

Through this exercise, I practiced using useradd, usermod, chown, userdel, and groupdel commands to manage authentication and access control in Linux systems.

Explanations of Commands
Command	Description
sudo useradd username	Adds a new user to the system.
sudo usermod -g group username	Sets the primary group of an existing user.
sudo chown username filename	Changes the ownership of a file to the specified user.
sudo usermod -a -G group username	Adds the user to a supplementary group while keeping their existing group memberships.
sudo userdel username	Deletes a user from the system.
sudo groupdel group	Deletes a group from the system.
Task 1: Add a New User

Step 1: Add the new employee researcher9 to the system:

sudo useradd researcher9


Step 2: Assign researcher9 to the research_team as their primary group:

sudo usermod -g research_team researcher9


Alternative: Combine both steps when creating the user:

sudo useradd researcher9 -g research_team

Task 2: Assign File Ownership

Assign ownership of project_r.txt to researcher9:

sudo chown researcher9 /home/researcher2/projects/project_r.txt


Ensures researcher9 has control over the file related to their project.

Task 3: Add the User to a Secondary Group

Add researcher9 to the sales_team as a secondary group:

sudo usermod -a -G sales_team researcher9


-a → append (do not remove existing group memberships)

-G → specify the secondary group

This allows researcher9 to work in multiple departments without losing primary group access.

Task 4: Delete a User

Remove researcher9 from the system:

sudo userdel researcher9


Output may include:

Userdel: Group researcher9 not removed because it is not the primary group of user researcher9


This is expected.

Remove the leftover group if no longer needed:

sudo groupdel researcher9

Summary

In this lab, I learned to:

Add new users to Linux systems.

Assign users to primary and secondary groups.

Change file ownership to ensure proper access control.

Delete users and clean up unused groups.

These skills are essential for managing authentication and access control in Linux, which is a core responsibility for cybersecurity analysts.
