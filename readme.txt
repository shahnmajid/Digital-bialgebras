R version required 4.0.0 or newer, to download R check: https://www.r-project.org/

**********

1. How to display the coalgebra solutions?
 
For each algebra load the corresponding .RData file in R. Then type:

coalgebra.solutions

This will display all possible solutions (in rows) for all 64 coefficients C^\mu_{\nu\rho} from equation (2.3). 

To display only one solution at the time, e.g. the first one type:

coalgebra.solutions[1,]

For example for algebra C, coalgebra.solutions[1,] will give:

> coalgebra.solutions[1,]
C111 C112 C113 C114 C121 C122 C123 C124 C131 C132 C133 C134 C141 C142 C143 C144 C211 C212 C213 C214 C221 C222 C223 C224 C231 C232 C233 C234 C241 C242 C243 C244 C311 C312 C313 C314 C321 C322 C323 
   1    0    0    0    0    0    0    0    0    0    0    0    0    0    0    0    0    0    0    0    0    1    0    0    0    0    0    0    0    0    0    0    0    0    0    0    0    0    1 
C324 C331 C332 C333 C334 C341 C342 C343 C344 C411 C412 C413 C414 C421 C422 C423 C424 C431 C432 C433 C434 C441 C442 C443 C444 
   0    0    1    0    0    0    0    0    0    0    0    0    0    0    0    0    1    0    0    0    0    0    1    0    0 

from where all the coefficients C^\mu_{\nu\rho} can be read - the format is C^\mu_{\nu\rho}=C\mu\nu\rho and {\mu,\nu,\rho}=1,2,3,4

********


2. What is the type of the coalgebra solutions?

First open the folder '25algebras_in4D' and read the 'readme.25algebras.txt' file.

To recognise what is the type (i.e. among A*-P*,NA*-NF*) of the given solution from the coalgebra.solutions table, type:

coalg.dual

This will display the numered list (of the lists) for all coalgebra.solutions and to each of them there will be assigned a list of the ALGEBRA versions from the package 25algebras_in4D.RData as explained in readme.25algebras.txt.

Here the numbers in double square brackets ([[x]]) refer to the number of the given COALGEBRA solution in the coalgebra.solutions table.

The numbers in the list refer to the numbers of the given solution in the ALGEBRA solutions (see 25algebras_in4D folder) and they DO NOT refer to the coalgebra.solutions numbers.


For example for the case of algebra C:

coalg.dual[[1]] 

will give the following list:
>coalg.dual[[1]]
[[1]]
  [1]    2    4    6    8   53   60   75   86  111  114  138  140  233  235  237  239  283  298
 [19]  306  318  341  352  369  372  392  394  396  398  443  450  465  476  501  504  528  530
 [37]  713  715  717  719  763  778  786  798  821  832  849  852  914  916  918  920  947  954
 [55]  960  980 1005 1007 1024 1034 1145 1147 1149 1151 1177 1185 1198 1212 1235 1245 1255 1266
 [73] 1304 1306 1308 1310 1337 1344 1350 1370 1395 1397 1414 1424 1565 1567 1569 1571 1597 1605
 [91] 1618 1632 1655 1665 1675 1686 2271 2296 2322 2340 2355 2361 2396 2439 2465 2490 2496 2551
....
which means that the first coalgebra solution (i.e. C.1) is dual to the algebra solution 2 - and this according to the FULL LIST in readme.25algebras.txt corresponds to algebra C.

Similarly, coalg.dual[[2]] 

will give the following list:

> coalg.dual[[2]]
[[1]]
  [1]   61   63   69   74   76   84  115  117  123  130  135  137  292  299  301  305  307  315
 [19]  346  353  355  361  366  368  451  453  459  464  466  474  505  507  513  520  525  527
 [37]  772  779  781  785  787  795  826  833  835  841  846  848  953  955  961  963  969  976
 [55] 1008 1010 1015 1021 1023 1030 1184 1186 1192 1199 1201 1207 1238 1246 1248 1252 1254 1261
 [73] 1343 1345 1351 1353 1359 1366 1398 1400 1405 1411 1413 1420 1604 1606 1612 1619 1621 1627
 ....
which means that the second coalgebra solution (i.e. C.2) is dual to the algebra solution 61 - and this according to the FULL LIST in readme.25algebras.txt corresponds to algebra K.

We proceed like this to recognise the types (i.e. duals) for all the coalgebra.solutions.

*******

3. Groups of coalgebras of the given type (i.e. lists from Sections 4.1, 4.2).

To display the coalgebra orbits (i.e. the coalgebras grouped by the given type, coalgebras grouped as isomorphic to each other (but not necessarily as bialgebra isomorphisms)) type

orbits

This will give the numbered list, where each number refers to the given coalgebra solution (i.e. the row in the coalgebra.solutions table).

So here the numbers in double square brackets ([[x]]) refer to the number of the given solution in the coalgebra.solutions table 
(hence the list will be as long as the number of total coalgebra.solutions there are).

Also the numbers in the list refer to the number of the given solution in the coalgebra.solutions table.

To know which type X* the given coalgebra is (i.e. (H,X*)), see above for step number 2. 

For example for algebra C, the first 3 orbits are:

> orbits
[[1]]
[[1]][[1]]
[1] 1
[[2]]
[[2]][[1]]
 [1]  2  5  9 12 14 18 19 20 22 27 30 31 36 41 42 49 64 68 77 79 80 83 88 90
[[3]]
[[3]][[1]]
[1]  3  6 16 52 55 58

We ignore the second lines of square brackets (e.g.[[1]][[1]], [[2]][[1]]) here. 

From these lists we can read that the solution [[1]] (i.e. C.1) is the only one of the given type, as we have 

[[1]]
[1] 1


Solution [[2]] (i.e. C.2) is isomorphic (as coalgebra isomorphism) to solutions 2  5  9 12 14 18 19 20 22 27 30 31 36 41 42 49 64 68 77 79 80 83 88 90 (i.e. C.2, C.5, C.9 etc.)
[[2]]
 [1]  2  5  9 12 14 18 19 20 22 27 30 31 36 41 42 49 64 68 77 79 80 83 88 90
and so on.

In total algebra C will have 90 orbits, as there are 90 coalgebra solutions, but there will be many identical orbits (as the whole lists will repeat for all the isomorphic coalgebras).

4. Distinct orbits (how to get the distinct bialgebras/Hopf algebras) from Sec. 4.3 shown in Figure 1.

To display the distinct orbits (i.e. the bialgebras grouped with their isomorphic ones), type

distinct.orbits

this will give the numbered list, where each number refers to the given coalgebra solution (i.e. the row in the coalgebra.solutions table) 
of the coalgebras which are isomorphic under the algebra automorphisms, i.e. providing bialgebra isomorphisms. i.e. this will give different distinct orbits of non isomorphic bialgebras. 

Here the numbers in double square brackets ([[Y]]) DO NOT refer to the number of the given solution in the coalgebra.solutions table, they only number the distinct orbits.

Only the numbers is the list refer to the number of the given solution in the coalgebra.solutions table.

For example in the case C, distinct.orbits will give the list of 20 distinct ones, the first few are:
[[1]] 
[1] 1
[[2]]
[1]  2  5 14 22 30 49  this tells us that solution 2 is isomorphic (as a bialgebra) to 5 14 etc.
[[3]]
[1]  3  6 16 52 55 58  this tells us that solution 3 is isomorphic (as a bialgebra) to 6 16 etc.

In total for algebra C we have 20 distinct orbits, which are shown on the Figure 1.

