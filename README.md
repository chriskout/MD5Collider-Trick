Run bonus1 with ./bonus1

Run bonus2 with ./bonus2 (dont worry, no actually malicous code was executed)

Run:
```
md5sum bonus1
md5sum bonus2
```
The hashes are the same, but the output is different. Thats because they are different files that have the same hash.
Pretty cool right.

To do this yourself from only program.c simply run the following commands:
```
gcc program.c
head -c 4160 a.out > beginning
md5collgen -p beginning -o foo1 foo2
tail -c 3560 a.out > end
tail -c -128 foo1 > foo1lastbytes
head -c 96 end > part1end
tail -c 3336 end > part2end
cat part1end foo1lastbytes part2end > finalend
cat foo1 finalend > bonus1
cat foo2 finalend > bonus2
```
The magic in here is caused by the md5collgen function, which you can read about and get here: https://www.win.tue.nl/hashclash

