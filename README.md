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

## 

## Documentation ##

Its a 2 step process to get up and running

```
ansible-playbook main.yml

```
```
vagrant up
```

* Port 80 will be mapped from the host machine to the load balancer. Load http://192.168.50.20 from the host machine to see the webpage load balanced across the webhosts (ensure its not cached in browser)

## TODO ##

* Provide an option to generate the vagrantfile automatically with provider parametrisation
* Build fpm role and ensure nginx can pass php pages to fpm
* Different host addresses need to work with named based virtualhost config
* Test playbooks on different host OS
* Neaten up documentation and add some formatting
* Ensure all services start at boot
