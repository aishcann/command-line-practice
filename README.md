# Command Line Practice

Here's a possible solution to command line practice.

Know that there are many ways to get a problem done, and if yours doesn't look the exact same as mine, but you still came to the same conclusion, all is well!

## Setup
```
mkdir star_wars
```
## Part 1: Set the Scene
1.
```shell
cd star_wars
mkdir death_star
touch death_star/darth_vader.txt death_star/princess_leia.txt death_star/storm_trooper.txt
```
***Note**: instead of `cd`-ing into `death_star` to `touch` the files, I can `touch` the files from outside the folder using the correct relative path*


2.
```shell
mkdir galaxy_far_far_away
```

3.
```shell
cd galaxy_far_far_away
mkdir tatooine && cd tatooine
touch luke.txt ben_kenobi.txt
```
***Note:** here, I `cd`'ed into tatooine before `touch`-ing the files. There is no relative path needed if you `cd` directly into the folder you want to `touch` files into.*

*Also notice that I can group multiple different commands together with `&&`*

4.
```shell
mkdir millenium_falcon
touch millenium_falcon/han_solo.txt millenium_falcon/chewbacca.txt
```

***Note:** here's another example of using a relative path to touch the files*

## Part 2: `mv` - rename
1..

```shell
mv ben_kenobi.txt obi_wan.txt    
```

***Note:** since I am already in the tatooine folder, renaming is simple. I can just use the old file name and the new file name - I don't have to write any paths to find the files*

## Part 3: `cp` - copy

*if you used `man cp` to find more information, you can exit that detail window with `\q`*

1.
```shell
cp ../../death_star/storm_trooper.txt .
```
***Note:** `..` refers to the parent directory, and `.` refers to the current directory. Here I used the relative path of `storm_trooper.txt` to make a copy of it into the `tatooine` directory.

## Part Four: `mv` - move

*all the following commands were done from inside the `tatooine` directory*

1.
```shell
mv luke.txt ./millenium_falcon
mv obi_wan.txt ./millenium_falcon
```
2.
```shell
mv millenium_falcon .. 
```
3.
```shell
mv ../millenium_falcon ../../death_star 
```
4.
```shell
mv ../../death_star/princess_leia.txt ../../death_star/millenium_falcon 
```

## Part V: `rm` - remove

*moving out of `tatooine` and going to the `death_star` directory with `cd ../../death_star`*

1.
```shell
rm millenium_falcon/obi_wan.txt
```

## Part VI: All together

*moving out of `death_star` and going to the `star_wars` directory with `cd ..`*

1.
```shell
cd galaxy_far_far_away
mkdir yavin_4
```
2.
```shell
mv ../death_star/millenium_falcon yavin_4
```
3.
```shell
cd yavin_4
mkdir x_wing
```
4.
```shell
mv millenium_falcon/princess_leia.txt .
mv millenium_falcon/luke.txt x_wing
```
5.
```shell
mv millenium_falcon ..
mv x_wing ..
```
6.
```shell
cd ../../death_star
mkdir tie_fighter_1 tie_fighter_2 tie_fighter_3
```
***Note:** mulitple directories can be created at the same time by adding them to the same line*

7.
```shell
mv darth_vader.txt tie_fighter_1
```
8.
```shell
cp storm_trooper.txt tie_fighter_2
cp storm_trooper.txt tie_fighter_3
```
9.
```shell
mv tie_fighter_1 ../galaxy_far_far_away
mv tie_fighter_2 ../galaxy_far_far_away
mv tie_fighter_3 ../galaxy_far_far_away
```

## Part VII: `rm -r`: Remove directories and everything they contain

*moving into the `star_wars` directory from `death_star` with `cd ..`

1.

```shell
rm -r galaxy_far_far_away/tie_fighter_2 galaxy_far_far_away/tie_fighter_3 
```

***Note:** Just like multiple directories can be created at the same time, multiple items can be deleted at once by adding them to the same line.* 

## Part VIII: May the Force Be With You..

1. 
```shell
 touch galaxy_far_far_away/x_wing/the_force.txt
```
2.
```shell
rm -r death_star
```
3.
```shell
mv galaxy_far_far_away/x_wing galaxy_far_far_away/yavin_4 
mv galaxy_far_far_away/millenium_falcon/ galaxy_far_far_away/yavin_4 
```

## Final File Structure

```
- star_wars
    - galaxy_far_far_away
        - tatooine
            - storm_trooper.txt
        - tie_fighter_1
            - darth_vader.txt
        - yavin_4
            - millenium_falcon
                - chewbacca.txt
                - han_solo.txt
            - x_wing
                - luke.txt
                - the_force.txt
            - princess_leia.txt
```