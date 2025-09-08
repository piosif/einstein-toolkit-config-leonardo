# einstein-toolkit-config-leonardo
Configuration files to build the Einstein Toolkit on the Leonardo cluster, at CINECA, Italy.

The initial configuration files were provided via email by Bruno Giacomazzo. Recently, they were also added to SimFactory's  machine database ([see related commit](https://bitbucket.org/simfactory/simfactory2/commits/0d4011bf554ee695f9543e048ae9ff5edc5b5c98)).

I needed to update the libraries' paths to handle recent software updates in Leonardo (related to the `Spack` package manager version). I also added comments explaining the different commands and options.

## Building the Einstein Toolkit

Here is the command to build ETK (run from the `Cactus/` folder):

> ./simfactory/bin/sim build --machine=leonardo-dcgp1 --optionlist simfactory/mdb/optionlists/leonardo-dcgp1.cfg --thornlist thornlists/einsteintoolkit.th

### Changing the configuration files

After having made any change to the configuration file, these additional options must be included in the above `build` command: 

- `--clean --reconfig`: to clean and reconfigure Cactus before the new build attempt

Furthermore, while debugging the configuration stage, these options proved useful:

- `--verbose`: to include more output when building

- `2>&1 | tee make.log`: include at the end of the `build` command to direct the output to a log file.
