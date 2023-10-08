# tryit

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

'Try it' is a simple puzzle game based around PC building.

1.The left block with orange border shows a build with unknown specs but known power rating;
2.On the left pane,complete the form with the specs and hit submit:
	2.1.Each spec has a power value used to calculate the power rating of the build;
3.On the right block with orange border,you'll see your build and its power rating and
in the center you'll see your score,your current result and the 'Next' button.Click it to move on;
4.The point of the game is to create a build that matches the power rating of the proposed build:
	4.1.You can create any build you want and,as long as it matches the requested power rating,
	you get the win;
	4.2.There are 4 power rating categories:
		4.2.1.Office laptop - power rating 1-2;
		4.2.2.Office desktop - power rating 3-4;
		4.2.3.High end build - power rating 5-6;
		4.2.4.Battlestation - power rating 7-8;
	4.3.If you match the power rating category,you get 5 points and,if you match the exact power rating,you get an extra 5 points;
5.The ranking system is pretty straight forward:
	5.1.There are 6 ranks and each rank takes more and more points to complete:
		5.1.1.Computer illiterate:0-100 points;
		5.1.2.Basic user:100-250 points;
		5.1.3.Average user:250-500 points;
		5.1.4.Experienced user:500-1000 points;
		5.1.5.Computer enthusiast1000-2000 points;
		5.1.6.Computer expert:2000+ points
	5.2.If you reach the last rank,you finish the game (well,you can still play and increase your score but no more rank ups)
