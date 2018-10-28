# akkroo
Akkroo automated server build task

## Requirements

*	Use Vagrant stand up three Linux virtual machines using a recognized orchestration tool to automate the steps (preferably you will use ansible, but chef or puppet are acceptable also).
*	Two machines will run a “hello world” web application of your own devising using any language, tools and framework you see fit. Ideally to you make use of an off the shelf framework for this application.
*	The third machine with run a load balancer of your choice.
*	Use parametrisation where appropriate.
*	Test and demonstrate that load balancing works and include evidence.
*	During the development process, check your project into git and push commits “little and often” so we can follow your development process.
*	You should provide suitable documentation in your git repo to allow others to recreate your solution and tests.
*	You should make use of markdown formatting to enhance your documentation.
*	You should consider that others might not use the same Vagrant providers and hardware as you.
*	Reference and credit any external resources you used whilst preparing this task.
*	Provide us with a link to your git repository so we can review the results

## References ##

[ https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#headers ] - Markdown cheatsheet
[ https://docs.ansible.com/ansible/2.5/scenario_guides/guide_vagrant.html ] - Vagrant and ansible docs
[ https://www.howtoforge.com/tutorial/how-to-setup-haproxy-as-load-balancer-for-nginx-on-centos-7/ ] - Haproxy reference

## Prerequisites

* Install pip and then the latest ansible version (2.7)
* Ensure you have a suitable provider installed
* Install ansible
* Install vagrant

## Documentation ##

*Its a 2 step process to get up and running*

```
1. ansible-playbook main.yml
2. vagrant up

```

* Once the servers are built and provisioned, you can view static pages load balanced via URL: http://192.168.50.20
* You can also view php pages, add domain www.helloworld.com to your host file pointing at 192.168.50.20 and then browser URL: http://www.helloworld.com/akkroo.php


## Features ##

* Added support for any number of web servers
* Haproxy dynamically writes its config file based on how many hosts exist and discovers them using an ansible group
* Added parametrisation for any provider
* Role based tasks for easy re-use

## Issues ##

* Whilst learning how to use vagrant I was unaware of the .vagrant directory and I accidently commited changes to this directory. Once realized I added an ignore file for this and removed it from github.
* I wanted to use ansible groups but I wasn't sure how to get vagrant to place any number of hosts into the same group. I decided to solve this by generating the inventory file and not using vagrants built in inventory generation.
