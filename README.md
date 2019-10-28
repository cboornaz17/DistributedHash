# Programming Languages 
## Programming Assignment 2: Distributed Hash Table
### Corey Boornazian & JJ Stadler

Our implementation runs via the provided compile.sh and run.sh scripts. 

### Compilation
To run our program, first run the compile.sh script.

The compile.sh script contains these lines:
```bash
java -cp salsa1.1.5.jar:. salsac.SalsaCompiler pa2/*.salsa
javac -classpath salsa1.1.5.jar:. pa2/*.java
```

This will compile our salsa files, Main.salsa and Node.salsa.

### Running 
Next run the run.sh script. The run.sh script contains these lines: 
```bash
java -cp salsa1.1.5.jar:. pa2/Main $1 $2 $3
```

This will run our client application and set up the necessary Actors. With no arguments, actors will be created locally.

### Distributed Setup
If you want to run the program in a distributed fashion, you will first need to some set up to configure.

First run a nameserver and run your theaters. Next, add your configuration to a theaters file. The theaters file should be in the pa2 directory when you want to run. The theaters file should have 1 line per theater you want to use, with only the ip address of each theater on a line. Our example theaters file looks like this: 
```
127.0.0.1:4040
127.0.0.1:4041
127.0.0.1:4042
```

Once you have created the nameserver and theaters file, you can run the run.sh script with arguments as follows:

`run.sh <theatersFile> <nameServer> <isDebug>`

Where theatersFile is a path to a theatersFile configured as shown above, nameServer is the ip address of your nameserver, and isDebug is a boolean for whether or not you want to show debug output.
