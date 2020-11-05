Create custom coin
====================

This is an automated generator of a custom coin. Set of scripts described below downloads the Litecoin source code (currently 0.14.2) and modifies it according to parameters set in configuration file. Scrypt POW algorithm is switched for the YescryptR16 and DarkGravityWave v3 is added for the purpose of difficulty computation.

The best choice to run this script is Ubuntu 18.04 (Because of crosscompilation runs only with this version) but if you do not crosscompile, you can run also on Ubuntu 16.10 or Debian Jessie, but then you should switch the variable for DEBIAN in config.sh.

Description of files
---------------------

File                          | Description
------------------------------|------------------
config.sh                     | here you can set all desired altcoin params
dependencies.sh    | install dependencies necessary for unix build
genesis.sh            | contains script for mining the genesis block according to the last configuration in the config.sh. !!! Please NOTE that this step overwrites and removes your coin folder if it is already generated!!!
generate.sh           | contains script for downloading and customizing the litecoin code; (deletes) and creates COIN_NAME folder according to the last configuration in the config.sh

Graphics
---------------------

Graphics and icons are stored in the folder named "icons". Please change those files for your own.

File                                   | Description
---------------------------------------|------------------
icons/about.png                        | ...
icons/bitcoin.ico                      | This could be editted with icofx
icons/bitcoin.png                      | ...
icons/bitcoin_testnet.ico              | This could be editted with icofx
icons/bitcoin.icns                     | This could be editted with icofx

Coin generation process
---------------------

```bash
sudo apt-get install git  
git clone https://github.com/jagoanpilot/yescryptgenerator
cd yescryptgenerator
# Customize params in config.sh
# You can customize DNSSeedNodes domains. Place them one domain per line to the DNSSeedsMain.txt file for main net and to the DNSSeedsTest.txt for testnet.
# Also you can customize SeedNodes ips. Just place them one ip per line to the seeds/nodes_main.txt file for main net and to the seeds/nodes_test.txt for testnet
# And finally you can customize SeedNodes domains. Just place them one domain per line to the DomainSeedsMain.txt file for main net and to the DomainSeedsTest.txt for testnet
# You just place ips and domains to the above mentioned files and script automatically generate the code
# Change icons and graphics stored in icons folder for your own
# Run:
./dependencies.sh
./genesis.sh
./generate.sh
# Now you can save your code to the Github
```

USEFULL LINKS
---------------------

+ [Cli api call list](https://en.bitcoin.it/wiki/Original_Bitcoin_client/API_calls_list)
+ [Running daemon overview](https://en.bitcoin.it/wiki/Running_Bitcoin)
