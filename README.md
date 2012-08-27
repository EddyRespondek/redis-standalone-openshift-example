Redis on OpenShift
==================

This git repository helps you get up and running quickly with Redis on OpenShift.


Quickstart
----------------------------

Create an account at http://openshift.redhat.com/

Create a Openshift application with a cartridge of your choice.

    rhc app create -a redis -t diy-0.1

Add this upstream repo

    cd redis
    git remote add upstream -m master git://github.com/EddyRespondek/redis-standalone-openshift-example.git
    git pull -s recursive -X theirs upstream master
    
Then push the repo upstream

    git push

That's it, you can now checkout your application at:

    http://redis-$yournamespace.rhcloud.com


Command Line Tools
----------------------------

SSH into you application and run command

    export PATH=${OPENSHIFT_RUNTIME_DIR}bin/:$PATH

the following command line tools are now available

    redis-cli
    redis-server
    redis-benchmark
    redis-check-aof
    redis-check-dump

Running redis-cli will fail on it's default host and port, instead use sockets

    redis-cli -s ${OPENSHIFT_GEAR_DIR}tmp/redis.sock


Log File
----------------------------

To view the redis.log file use command

    rhc app tail -a $APPNAME