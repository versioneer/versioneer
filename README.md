# Versioneer

**Versioneer** is a tool that was developed to save time when bumping versions in decentralized code bases that have lots of independent modules and chained dependencies. The code is still in early development & planning, but will soon be available for open-source contribution in early-2022.

**Versioneer** itself is a CLI to be written in Go and SQLite that will be compatible with both Windows & Linux/Unix systems. In its completion, **Versioneer** will keep an up-to-date index of modules by way of configuration files and be able to help maintain absolute dependency integrity by keeping your code updated with the lastest internal dependency releases.

## Quick Start Guide
1. You will need to have Go installed. If you don't have it installed already, please follow this [installation guide here](https://golang.org/doc/install).


2. To install Versioneer using Go, simply run the following installation command:

`go install github.com/versioneer/versioneer/cmds@latest`

  > To get a complete version history with features, you can view our [release history here](RELEASE.md).


3. Check for installation success by checking the version:

`versioneer -v` or `vsnr -v`


4. Generate an SSH key for Git (works for Bash and PowerShell).

`ssh-keygen -t ed25519 -C "<YOUR_GIT_EMAIL_ADDRESS_HERE>"`

This will prompt the following message: _Generating public/private ed25519 key pair._
_Enter file in which to save the key (/Users/####/.ssh/id_ed25519):_

The file name you enter should be `ed25519_vsnr`.

You will then be prompted to enter a passphrase. This is optional.

You will then see the SSH key fingerprint generated, which should look something like this:
`SHA256:FHsTyFHNmvNpw407+rp+M1yqMyBF8vXSBRkZtkQ0RKY youremail@yourdomain.com`


5. Add the SSH key to your Git account.

[To add the SSH key to your **GitHub** account](https://github.com/)

[To add the SSH key to your **GitLab** account](https://gitlab.com/)

[To add the SSH key to your **Gerrit** account](https://gerrit.com/)
  

6. Register your DPMS (Dependency Package Management System) paths.
  #### Add Custom DMS Paths via CLI

  `versioneer --dependency --add --type=<DPMS_TYPE> --path=<PATH/TO/YOUR/DMS/BIN>`

> The following DPMS types will be supported in order of priority:
> - Maven (Java) = maven
> - Gradle (Java) = gradle
> - NPM (Node.js) = npm
> - YARN (Node.js) = yarn
> - Cargo (Rust) = cargo
> - Go (Golang) = go
> - Composer (PHP) = composer
> - Gems (Ruby) = gems
> - Pipenv (Python) = pipenv
> - Pyenv (Python) = pyenv
> - Poetry (Python) = poetry
> - Docker (Python) = docker-python
    
  #### Add Dependency Paths via Default Configuration File
  To auto-install ***all*** default dependency paths:
  
  `versioneer --dependency --add --defaults`
  
  To auto-install ***some*** default dependency paths:

_Here is an example that installs Maven, NPM, and Go..._

  `versioneer --dependency --add --defaults=some --types=[maven, npm, go]`

[To view the default configuration file for MacOS/Linux](/config/dpms/macos-linux/default.config.json)

[To view the default configuration file for Windows](/config/dmps/windows/default.config.json)
  
 #### Add Dependency Paths via Custom Configuration File
 The easiest way to list custom installation paths is to copy and edit the default configuration file. You can also look at this [***example.config.json***](/config/dpms/vsnr-example.config.json). 

To install dependencies via custom paths:

 `versioneer --dependency --add --path=<PATH/TO/YOUR/config.json>`


7. Register your Modules via batch or one by one.
  #### Register Modules via Local Configuration File (Batch method)
  This is the best method if you're trying out Versioneer individually.

You can create a `versioneer.config.json` (or whatever you would like to name it).

[To view the example module registry template click here](/config/module/example-batch.config.json)
  
  #### Register Modules via Repository Configuration Files (One-by-one method)
  This is the best method if you're trying out Versioneer as a team or organization. Each module will need its own configuration file. 
  
[To view the example module configuration template click here](/config/module/example-repo.config.json)
  
  ***For MacOS/Linux Users***
  ``` bash
  touch /path/to/your/repo/versioneer.config.json
  ```
  
  ***For Windows Users***
  ``` PowerShell
  New-Item -Path /path/to/your/repo -Name "versioneer.config.json"  -ItemType "file"
  ```
  
  
8. Check dependencies.
Since steps update frequently and this README is not maintained, it's best to run `versioneer --help` or `vsnr -h` to learn how to check dependencies, automatically update them, and cascade changes.


## Using the Reporting Tool
Coming soon to Versioneer is a React Front-end Application that will show historical and current revisions. Just run `versioneer --run-report --output=GUI`. Running `--output=CLI` or omitting the `--output` parameter will output the same information in the command line.

## Requirements
- Go 1.13+
That's all. 

## Support
Versioneer is currently being developed on both MacOS, Windows. It is also to be tested on Oracle 8 Linux; which runs on Red Hat Enterprise Linux (RHEL)

## Contributions
### Requirements
- make 
- Node.js v12+
Versioneer will include a `Makefile` that aids in building locally.

## Testing
- For everything run `make test`.  
- For front-end only, run `npm test`.
- Versioneer assumes that files that end in `_test.go` and `.test.(js|ts)` are test files.
- JavaScript and TypeScript files are tested in Jest. 

## Development
### UI
`make ui`
### Server
`make server`
### CLI
`make cli`

## Sandboxing
- If you are having an issue or are developing a new feature. Please refer to the configuration files in the `sandbox` branch in order to generate your own sandbox setup.

## Get in Touch
Created at [Liquidware](https://www.liquidware.com) by:
- [Omie Walls](mailto:omie.walls@Liquidware.com)
<!--
**versioneer/versioneer** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
