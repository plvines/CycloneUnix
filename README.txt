Basic Call:
./Cyclone TABLE_FILE [-edges] [-traj TRAJFILE] [-c #] [-v] [-f OUTFILE]

TABLE_FILE: the name of the file containing the model's tables,
include extension. See below for formatting rules

-c #: runs the program as # subprocesses, optimally should be equal to
 the number of available processors on the computer. Ignored when
 generating edges or trajectories

-v: verbose, outputs the output to the commandline through standard
 out

-f OUTFILE: outputs the output to the file/path designated by OUTFILE

-edges: generates the list of edges formatted as two columns, the
 first being the source, the second being the destination, ordered by
 source node number.

-traj TRAJFILE: computers the trajectory starting from the trajectory
 listed in TRAJFILE and ending it whatever limit cycle it ends in. The
 output it split into two pieces: the nonrepeating trajectory portion,
 and the ending limit cycle portion.

*** FILE FORMAT: ****

TABLE_FILE:
the table file must be formatted as follows (variations may work, but
are not guaranteed):
MODEL_NAME
RUN_NAME
# (of tables)
# # # ... # (of states for each variable, in order)

x# x# ... x# (inputs to the table, with the last one being the output
of the table)
#
#
#
.
.
.
# (output column of the table)
	
(next table)


for an example of a simple model of 5 variables, see Sim1.txt

TRAJFILE:
MODEL_NAME
RUN_NAME
[ # # # . . . #] 
(starting state for each variable listed in order with a tab or space
between them)
