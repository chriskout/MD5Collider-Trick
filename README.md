#How to work
Run bonus1 with ./bonus1
Run bonus2 with ./bonus2 (dont worry, no actually malicous code was executed)
Run:
```
md5sum bonus1
md5sum bonus2
```
Pretty cool right.

To do this yourself form only program.c simply run the following commands:
```
head -c 4160 a.out > beginning
md5collgen -p beginning -o foo1 foo2
gcc program.c
tail -c 3560 a.out > end
tail -c -128 foo1 > foo1lastbytes
head -c 96 end > part1end
tail -c 3336 end > part2end
cat part1end foo1lastbytes part2end > finalend
cat foo1 finalend > bonus1
cat foo2 finalend > bonus2
```
The magic in here is caused by the md5collgen function, which you can read about and get here: https://www.win.tue.nl/hashclash

