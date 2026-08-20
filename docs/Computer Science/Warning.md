1. STL data structures are slow (use custom [forward star link list](/home/albert/Imacder/cpp_training/basic_ds/forward_star_link_list.cpp), [heap](/home/albert/Imacder/cpp_training/basic_ds/bin_heap.cpp))
2. add EXPLICIT guard rails
3. write what you think is something to be kept in mind down
4. C++ division rounds towards 0, use custom ceil div / floor div
5. when doing floating point ops, **DO NOT** add up then substract back when doing sweep line, the smaller value will get absorbed into the larger one
6. use `1ll * ` when doing modular multiplication! 
7. `unordered_map` is only fast when you have enough element, and element hashing is fast. for smaller access use `map`.
8. If the problem has double edges, **OPEN DOUBLE THE SIZE!!!**
9. Use `fflush` in interactive problems!!!
10. `swap` arrays will copy the items, not transfer the pointers
11. **DO NOT USE `cin >> (s + 1);` ON CHAR ARRAY!!!**
12. When using backward for loops, check if the first element exceeds `int`.
