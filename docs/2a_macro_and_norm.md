## Use macros combined with :norm

Macros are quite a powerful concept in vim.
You can basically save a sequence of commands and then play it again multiple times.
You can automate a lot of sequences using them.
For example imagine you have the following list:
```
hello, world
foo, bar
foo1, bar1
foo2, bar2
```
and you want to rewrite it to:
```python
hello = "world"
foo = "bar"
foo1 = "bar1"
foo2 = "bar2"
```
Then if you go to the first line and type `qw` you will start recording a sequence of commands to the register `w`.
Then you can type something like `0wxi =<Esc>wi"<Esc>A"<Esc>` and press `q` again, you saved the sequence of commands in the `w` register.
To replay it, you can run `5@w` and it will run the sequence 5 times!
But if you want to apply it to the next lines, you can also visually select the next lines and type `:norm@w` and it will apply the sequence to each line.
Imagine that you file is life 1000 lines long... reformatting is now a Kinderspiel.
