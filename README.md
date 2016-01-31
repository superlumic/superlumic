# Superlumic

Superlumic is a light utility wrapper around Ansible to ease the automated install of OSX 10.10 and higher. It uses several roles distilled over years of use in the Chef based predecessor, Kitchenplan.

Since moving to Ansible for my server deploys, I wanted to bring the same experience I created with Kitchenplan to OSX via Ansible. Existing solutions like Battleschool didn't offer the user experience I had in mind, so I started fresh.

While the Kitchenplan wrapper uses a Ruby gem and quite some code, I kept Superlumic a pure Bash script and use as much of the Ansible ecosystem and built in Ansible features as possible. This will help in extensability and maintenance.

## Configuration

Start by forking [superlumic-config](https://github.com/superlumic/superlumic-config). This is the default configuration "role" for Superlumic and will serve as a starting point for your own configuration.

You will need at least a "default.yml" playbook. Use the roles folder to create "profiles" and add extra dependencies in the "requirements.yml" as needed.

How you organise your config files is entirely up to you, but this is how I do it. The "profile-all" role are the apps and settings that everyone in my company needs. Then I have a group file per type of installation (developers, designers, etc). You can then create a "username.yml" playbook to add all the specific things for a specific user.

## Running Superlumic

```bash
curl -s https://raw.githubusercontent.com/superlumic/superlumic/master/superlumic | bash -s <your repo clone url here>
```

Or if you have an adversion to piping scripts over the internet into bash, download the [Superlumic script](https://raw.githubusercontent.com/superlumic/superlumic/master/superlumic) and run it.

**Note:** Superlumic takes in an additional, optional, argument that determines the name of the playbook to use. When no argument is supplied, "default.yml" will be used. However, if you ran the script thusly:

```bash
curl -s https://raw.githubusercontent.com/superlumic/superlumic/master/superlumic | bash -s <your repo clone url here> roderik
```

Then "roderik.yml" will be used.

## Out of the box result?

Starting from "default.yml" this will get you:

* All my favorite GUI apps installed via Homebrew Cask
* All my favorite commandline apps installed via Homebrew
* A fully operational PHP 5.5 installation with composer, optimised for running Symfony
* A MySQL and Postgresql database
* A configured Sublime Text 3
* NodeJS and several frontend oriented tools like bower, gulp and grunt
* A bash 4 CLI environment, with a nice prompt, and terminal theme
* A VIM environment with Janus installed
* A whole host of "osx default" settings including computername, dock size and position, etc

and, since it's almost pure Ansible, a very easy way to adjust, tune and extend this configuration to match your needs exactly.
