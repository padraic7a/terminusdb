# Build From Source

The following directions should work on debian or ubuntu.

#### SWIPL 

To use Terminus Server, you will need the SWIPL installation of
prolog. To install this in Debian variants simply use the apt package
manager:

```
apt install swi-prolog
```
Once installed, you will have to install two library dependencies from SWIPL. 

This can be done by typing: 

```
$ swipl
Welcome to SWI-Prolog (threaded, 64 bits, version 8.1.10-28-g8a26a53c1)
SWI-Prolog comes with ABSOLUTELY NO WARRANTY. This is free software.
Please run ?- license. for legal details.

For online help and background, visit http://www.swi-prolog.org
For built-in help, use ?- help(Topic). or ?- apropos(Word).

1 ?- pack_install('https://github.com/GavinMendelGleason/hdt.git').
% Contacting server ....
2 ?- pack_install(mavis). 
% Contacting server ....
```

#### HDT Library 

You will also need to install `hdt-cpp`. You can git clone the source tree from this repository: 

```
git clone https://github.com/rdfhdt/hdt-cpp
```

... and follow the directions contained in the repostiory for the
pre-requisites and building the code.

#### Terminus Server

The Terminus Server source tree should then be cloned from GitHub: 

```
git clone https://github.com/terminusdb/terminus-server
cd terminus-server
git submodule init
git submodule update
```

You need to set the admin user password which is used as a
super-user API key for access. This can be done with the
`initialize_database` script. The script should also be used to
configure the server name, as shown in the example.

```
utils/initialize_database -k "my_password_here" -s "my_server_name_here"
```

At this point you can enter the terminusDB directory and start the server: 

```
./start.pl
```

Now you are ready to interact with the HTTP server. 
