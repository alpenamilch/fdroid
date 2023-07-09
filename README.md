# fdroid
=========

Repo URL  https://alpenamilch.github.io/fdroid/repo

## Installer

sudo apt-get install fdroidserver

- Create a directory called fdroid, then run fdroid init in that directory to generate the signing key that uniquely identifies your repo.
- Optionally edit the config.yml file to your liking, detailed examples are in examples/config.yml
- Within fdroid, make a directory called repo and put APK files in it.
- Run fdroid update.
- If it reports that any metadata files are missing, you can create them in the metadata directory and run it again.
- To ease creation of metadata files, run fdroid update with the -c option. It will create ‘skeleton’ metadata files that are missing, and you can then just edit them and fill in the details.
- Then, if you’ve changed things, run fdroid update again.
- Running fdroid update adds an icons directory into the repo directory, and also creates the repository index files (index.xml, index.jar, etc)

NOTE: To make this process secure, read Real World Setup below!
Publish the resulting contents of the repo directory to your web server (or set serverwebroot in your config.yml then use fdroid deploy)

## Quick info


mkdir ~/fdroid
cd ~/fdroid
fdroid init
cp /path/to/\*.apk ~/fdroid/repo/
fdroid update --create-metadata
emacs config.yml # add the serverwebroot, etc.
fdroid deploy -v
