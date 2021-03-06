# snapshotanalyzer-30000
Demo project to manage AWS E2 instances snapshot

## About

This project uses boto3 to connect to AWS and list ec2 instances.

## Configure

Load the profile name shotty ,use the keys generated by aws cli

aws configure --profile=shotty

## Running (shotty.py)

pipenv run python shotty/shotty.py


## Running (shotty_cmds.py)

pipenv run python shotty/shotty.py <command> --project=PROJECT

*command* is list, stop, start
*project* is optional , one of the tag can be given  as argument


Eg:
pipenv run python shotty/shotty_cmds.py list  --project=Valkyrle
pipenv run python shotty/shotty_cmds.py start  --project=Valkyrle
pipenv run python shotty/shotty_cmds.py stop  --project=Valkyrle
pipenv run python shotty/shotty_cmds.py --help


# Running (shotty_cli.py)

#groups implemented within click commands.
*Command* is instances , volumes, snapshots
*subcommand* depends on command , list ,snapshot etc.

pipenv run python shotty/shotty_cli.py --help
pipenv run python shotty/shotty_cli.py  instances --help
pipenv run python shotty/shotty_cli.py  volumes --help
pipenv run python shotty/shotty_cli.py instances list --help


# Running (shotty_volumes.py)

pipenv run python shotty/shotty_volumes.py volumes list   

# Running (shotty_snapshots.py)
lists Snapshots
pipenv run python shotty/shotty_snapshots.py snapshots list

# creates snapshots
pipenv run python shotty/shotty_snapshots.py instances snapshot
pipenv run python shotty/shotty_snapshots.py --help
pipenv run python shotty/shotty_snapshots.py instances --help
