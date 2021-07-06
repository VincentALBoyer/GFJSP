# GFJSP
Data set of GFJSP used in the paper "The Generalized Flexible Job Shop Scheduling Problem" by by 
Vincent Boyer, Jobish Vallikavungal Devassia, Xavier Cantú-Rodríguez, M. Angélica Salazar-Aguilar submitted for revision to the Computers & Industrial Engineering.


Parameters:
- nop: number of operations
- nmach: number of machines
- t(m): type of machine m (0: Cutting; 1: Pressing; 2: Forging; 3: Furnace)
- p(m,i): processing time of operation i on machine m (+inf as default value)
- w(m,i): weight of operation i on machine m (+inf as default value)
- lmin(i,j): minimum lag between operation i and j (-inf as default value)
- lmax(i,j): maximum lag between operation i and j (+inf as default value)
- nm(i): number of machines that can process operation i
- no(i): number of operation that must be process after operation i
- d(i): due date of operation i (not used)
- a(i): starting time of time window of operation i (not used)
- b(i): ending time of time window of operation i (not used)
- C(m): capacity of machine m
- SetUp(m,i,j): setup time from i to j on machine m (+inf as default value)
- nsu(m): number of setups (different than +inf) on machine m
- MaxHoldTime(m): maximum holding time of machine m (=20 for the furnaces, 0 for Cutting, Pressing, and Forging)
- delta(m): loading and unloading time of machine m (=1 for all machines)

In the sequel, [data_1 data_2 ... data_n]xk denote k consecutive block of data with the same structure

Instance file structure:

#Number of operations and machines
nop nmach

#Operation Data
d(0) a(0) b(0) nm(0) [m_id p(m_id,0) w(m_id,0)]xnm(0) no(0) [op_id lmin(0,op_id) lmax(0,op_id)]xno(0)
...             
d(nop-1) a(nop-1) b(nop-1) nm(nop-1) [m_id p(m_id,nop-1) w(m_id,nop-1)]xnm(nop-1) no(nop-1) [op_id lmin(nop-1,op_id) lmax(nop-1,op_id)]xno(nop-1)

#Machines Data
C(0) t(0)  nsu(0) [op_i op_j SetUp(0,op_i, op_j)]xnsu(0)
...
C(nmach-1) t(nmach-1)  nsu(nmach-1) [op_i op_j SetUp(nmach-1,op_i, op_j)]xnsu(nmach-1nmach-1)


