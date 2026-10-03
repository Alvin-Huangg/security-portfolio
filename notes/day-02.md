Write notes/day-02.md: explain CIDR to someone non-technical using a warehouse
analogy (aisles, bays, locations).

Day 2: CIDR

CIDR is a short way of pointing at a whole group of network addresses at once, without listing them one by one. Think of a warehouse location label, which reads from broad to specific: aisle, then bay, then shelf, then the exact spot. If I tell a picker "aisle 12," I mean every location in that aisle, which is thousands of spots. If I say "aisle 12, bay 04, shelf C," I've narrowed it to a handful, and if I give the full label, I mean exactly one. A network address works the same way: it has four numbers that go from broad to specific, and the slash number at the end says how much of the address is pinned down. So 10.0.0.0/8 pins only the first number, like naming just the aisle, and covers about 16.7 million addresses, while 10.5.9.37/32 pins all four and means one single machine. That is why a bigger slash number means a smaller group: the more of the label you fix, the fewer locations are left. The one to remember is 0.0.0.0/0, where nothing is pinned down at all, which is the whole building, or in network terms, the entire internet.
