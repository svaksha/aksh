+ [AMQP](#amqp)
+ [AWS](#aws)
+ [CONFIG](#config)
+ [DEVOPS](#devops)
   + [Automation](#automation)
   + [Batch Jobs](#batch-jobs)
   + [CI](#ci)
   + [LibCloud](#libcloud)
   + [OCP](#ocp)
   + [Open SDN](#open-sdn)
+ [DELL](#dell)
+ [DOCKER](#docker)
+ [Monitoring](#monitoring)
+ [OpenStack](#openstack)
+ [Rackspace](#rackspace)
+ [HEROKU](#heroku)
+ [NEWS](#news)
+ [OpenShift](#openshift)
+ [SECURITY](#security)
+ [Vagrant](#vagrant)
+ [VM](#vm)
+ [Yaksha ToDo](#yaksha-todo)
   + [Automation](#automation)

----

+ http://en.wikipedia.org/wiki/Category:Cloud_infrastructure
+ http://en.wikipedia.org/wiki/Category:Cloud_computing_providers
+ http://en.wikipedia.org/wiki/Comparison_of_open-source_configuration_management_software
+ http://docs.python-guide.org/en/latest/scenarios/admin/

----

# AMQP
+ http://www.amqp.org/
+ Disque, https://github.com/antirez/disque

## Celery
+ Celery, https://github.com/celery/celery
+ http://docs.celeryproject.org/en/latest/getting-started/first-steps-with-celery.html#rabbitmq


## ZeroMQ
+ ZeroMQ, https://github.com/zeromq/pyzmq
+ http://zeromq.org/intro:get-the-software
+ zguide, http://zguide.zeromq.org/page:all
+ guide, http://zguide.zeromq.org/py:all
   + Julia, https://github.com/imatix/zguide/tree/master/examples/Julia
   + Python, https://github.com/imatix/zguide/tree/master/examples/Python

## RabbitMQ
+ RabbitMQ, https://www.rabbitmq.com       # Erlang AMQP lib
   + https://www.rabbitmq.com/tutorials/tutorial-two-python.html
   + http://www.rabbitmq.com/configure.html#config-items
   + http://www.rabbitmq.com/memory.html#diskfreesup
+ Pika, https://github.com/pika/pika       # a Pure Python RabbitMQ/AMQP 0-9-1 client library.
   + http://pika.readthedocs.org/en/0.9.14/intro.html

----

# AWS
+ http://aws.amazon.com 
+ http://en.wikipedia.org/wiki/Amazon_Web_Services
+ http://en.wikipedia.org/wiki/Amazon_Elastic_Compute_Cloud

## HELP
+ REF : http://docs.aws.amazon.com/general/latest/gr/Welcome.html
+ http://docs.aws.amazon.com/general/latest/gr/rande.html
+ https://aws.amazon.com/documentation/
+ CLI tools : http://docs.aws.amazon.com/general/latest/gr/GetTheTools.html

### SO
+ http://stackoverflow.com/questions/10526345/ec2-command-line-tools   

----

# CONFIG
### how to create a config file
+ http://stackoverflow.com/questions/18700295/standard-way-of-creating-config-file-suitable-for-python-and-java-together
+ https://wiki.python.org/moin/ConfigParserExamples
+ https://docs.python.org/3.5/library/configparser.html

----

# DEVOPS
+ https://github.com/devopsbookmarks/devopsbookmarks.com

## Automation
+ https://github.com/NARKOZ/hacker-scripts :: git clone git@github.com:NARKOZ/hacker-scripts.git

## Batch Jobs
+ [Luigi](https://github.com/spotify/luigi) :: A Python module that helps you build complex pipelines of batch jobs. It handles dependency resolution, workflow management, visualization etc. It also comes with Hadoop support built in.

## CI
+ An introduction to containers for continuous integration : https://github.com/fredhutchio/containers-ci

## [LibCloud](https://libcloud.apache.org/)
+ A Python library for interacting with many of the popular cloud service providers using a unified API - can handle files on AWS, Dropbox, GoogleDrive. 
+ List of supported providers : https://libcloud.readthedocs.org/en/latest/supported_providers.html

# [OCP](http://www.opencompute.org)
+ http://www.opencompute.org :: The Open Compute Project (OCP) is reimagining 
hardware, making it more efficient, flexible, and scalable.

# Open SDN 
__An open platform for network services across a spectrum of hardware 
in multivendor environments.__
+ https://www.opendaylight.org/

----

# DOCKER
+ Install docker on debian, https://docs.docker.com/engine/installation/linux/debian/
+ https://docs.docker.com/v1.5/faq/
+ http://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-normal-virtual-machine
+ https://github.com/ddboline/docker_scripts :: Scripts to use with Docker, along with example Dockerfile's
+ Various Dockerfiles : https://github.com/jfrazelle/dockerfiles and a blog post: https://blog.jessfraz.com/post/docker-containers-on-the-desktop/
+ https://www.digitalocean.com/community/tutorials/docker-explained-how-to-containerize-python-web-applications
+ https://books.google.co.in/books?id=oAkZBQAAQBAJ&pg=PA116&lpg=PA116&dq=python+code+to+spin+up+docker+containers&source=bl&ots=dSp_ddqppk&sig=BfOcQ7hY1oBndYT3DtVbgaT8dis&hl=en&sa=X&ei=Q9EcVeroFI-0uATYvoKYBg&ved=0CEcQ6AEwBw#v=onepage&q=python%20code%20to%20spin%20up%20docker%20containers&f=true
+ http://phusion.github.io/baseimage-docker/
+ https://pypi.python.org/pypi/docker-compose/1.2.0rc3
+ https://coreos.com/os/docs/latest/getting-started-with-docker.html
+ https://docs.docker.com/installation/ubuntulinux/
+ https://docs.docker.com/articles/basics/
+ http://www.liquidweb.com/kb/how-to-install-docker-on-ubuntu-14-04-lts/
+ [dockerspawner](https://github.com/jupyter/dockerspawner) :: Spawns JupyterHub user servers in Docker containers. 
+ https://www.stgraber.org/2013/12/20/lxc-1-0-blog-post-series/

## docker-gitlab
+ http://doc.gitlab.com/omnibus/docker/
+ https://github.com/sameersbn/docker-gitlab-ci

## DockerCloud
+ https://docs.docker.com/docker-cloud/getting-started/
+ https://forums.docker.com/c/docker-cloud

## dockerboxer
+ https://docker.io , https://docker.com
+ https://quay.io/user/svaksha

## docker-persistent-Storage
+ http://www.computerweekly.com/feature/Docker-storage-101-How-storage-works-in-Docker
+ http://stackoverflow.com/questions/18496940/how-to-deal-with-persistent-storage-e-g-databases-in-docker

#### Docker Demo
+ https://github.com/bizmate/docker_lemp_php7_mysql


#### Press
+ http://www.zdnet.com/article/red-hat-ubuntu-and-docker-container-virtualization-goes-mainstream/
+ http://www.infoworld.com/article/2609888/virtualization/docker-challenges-virtualization-market-with-containers.html
+ http://www.techrepublic.com/article/containers-replacements-or-alternatives-to-virtual-machines/
+ http://www.zdnet.com/article/docker-an-open-source-startup-you-need-to-know-about/


----

# DELL
+ https://support.enstratius.com/home
 
## mixcoatl
#### Wiki
+ Wiki :: https://github.com/enStratus/mixcoatl/wiki/Mixcoatl-0.10.32

#### Bugs 
+ https://github.com/enStratus/mixcoatl/issues/207
   + https://github.com/enStratus/mixcoatl/search?utf8=%E2%9C%93&q=customerId
   + https://github.com/enStratus/mixcoatl/blob/fa6dad007a3e2c07763660e21cca19b81fd73723/tests/data/region.py
+ https://github.com/irvingpop/enstratius-api-tools
+ https://github.com/zomGreg/riak-cli-tool

----

# Monitoring
+ https://en.wikipedia.org/wiki/Comparison_of_network_monitoring_systems
+ Blog on incron, http://www.splitbrain.org/blog/2011-01/07-watcher_a_recursive_incron_alternative
+ [Watcher](https://github.com/splitbrain/Watcher) :: A daemon that watches specified files/folders for changes and fires commands in response to those changes. It is similar to incron, however, configuration uses a simpler to read ini file instead of a plain text file. Unlike incron it can also recursively monitor directories. It's also written in Python, making it easier to hack.

### System Disk Monitoring tools

+ https://pypi.python.org/pypi/psutil
+ https://github.com/nicolargo/glances
+ https://github.com/google/grr
+ https://github.com/python-diamond/Diamond
+ https://github.com/Jahaja/psdash
+ https://github.com/prometheus
+ http://www.zenoss.com
+ https://en.wikipedia.org/wiki/Ganglia_%28software%29
+ https://en.wikipedia.org/wiki/Icinga
+ https://en.wikipedia.org/wiki/Nagios

## Chef 
(.rb)
+ https://github.com/chef/chef
+ http://stackful-dev.com/cuisine-the-lightweight-chefpuppet-alternative

## Puppet 
(.rb)
+ http://en.wikipedia.org/wiki/Puppet_%28software%29

## Vagrant 
(.rb)
+ https://en.wikipedia.org/wiki/Vagrant_%28software%29

## Cobbler 
(.py)
+ https://en.wikipedia.org/wiki/Cobbler_%28software%29
+ https://github.com/cobbler/cobbler

----

# [OpenStack](http://openstack.org)
+ Nova, https://github.com/openstack/nova
+ http://www.openstack.org/software/
+ [OpenStack drivers](http://www.openstack.org/marketplace/drivers/)
+ http://www.ibm.com/developerworks/cloud/library/cl-openstack-pythonapis/

###### UserExample
+ https://www.mediawiki.org/wiki/Wikimedia_Labs

----

# Rackspace
+ https://github.com/rackerlabs

----

# HEROKU
+ https://addons.heroku.com/
+ https://devcenter.heroku.com/articles/getting-started-with-python
+ https://devcenter.heroku.com/articles/procfile
+ https://devcenter.heroku.com/categories/heroku-architecture
+ https://id.heroku.com/login

----

# NEWS
+ http://www.networkworld.com/article/2160016/cloud-computing/who-makes-up-openstack-.html
+ https://training.linuxfoundation.org/sysadmin-evolution
+ http://www.networkworld.com/article/2160163/cloud-computing/12-free-cloud-storage-options.html
+ http://probably.co.uk/puppet-vs-chef-vs-ansible.html

## Random Papers
+ [Large-scale cluster management at Google with Borg](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43438.pdf).

----

# OpenShift
+ http://help.openshift.com
+ https://blog.openshift.com/run-your-nodejs-projects-on-openshift-in-two-simple-steps/
+ https://wiki.python.org/moin/FreeHosts

----

# SECURITY

+ credential leaks : https://github.com/ChALkeR/notes/blob/master/Do-not-underestimate-credentials-leaks.md
+ https://en.wikipedia.org/wiki/Operations_security
+ Use [OTR](https://otr.cypherpunks.ca/) for chatting, GnuPG for encrypted & verified data sharing, with EnigMail for emails and [TrueCrypt](https://truecrypt.ch/) for storage.


## Firewalls

Each line should start with $ipt (which is your variable that points to the iptables binary with complete path).  This shows your second line starting with "ESTABLISHED" & third line with "$WAN_IFACE".

Did you check your linefeeds and command formatting?

Alternately flush your tables and load each command manually to see where/if you have script errors! Just cut/copy/paste each line into your
tables, then display the full recipe with "iptables_save" and/or pipe via STOUT to a text file to compare or import at startup.  Depending on your distro, iptables startup config and version, your templates might conflict.  Many stock firewalls, VPN solutions and Virtualized servers use bridging, TUN or null devices with DNAT/SNAT and or EBTABLES.

Just pulling partial iptables out of your scripts tool bin for use, while replacing the complete startup UFW config firewall, might be a quick
solution, however security threats today demand that you use a complete solution or build upon modern tools, like SHOREWALL: http://shorewall.net/bridge-Shorewall-perl.html

Other appliance based SOHO firewalls include: SMOOTHWALL: http://www.smoothwall.org
IPCOP: http://www.ipcop.org

+ Firewalld, OpenWall, IPWire, MonoWall, & Untangle are compared here: https://en.m.wikipedia.org/wiki/Comparison_of_firewalls
+ Block and limit known attacks: http://www.cyberciti.biz/tips/linux-iptables-10-how-to-block-common-attack.html

Also don't forget to check your kernel values!  In order to support iptables in bridging mode (which you are not doing but might consider),
your Linux kernel needs to be compiled with CONFIG_BRIDGE_NETFILTER=1, and your /etc/sysctl.conf file either needs to not contain any entries for the following settings or have them set to “1”:

net.bridge.bridge-nf-call-arptables=0 net.bridge.bridge-nf-call-ip6tables=0
net.bridge.bridge-nf-call-iptables=0

Traditionally, Ubuntu and other Debian derivatives store network interface configurations in the file /etc/network/interfaces. However, GNOME's Network Manager system automatically configures any interface not explicitly described in that file.

In theory, this should mean that if you specify interface and bridge configurations in `/etc/network/interfaces`, you shouldn't have to worry
about Network Manager overriding or otherwise conflicting with those settings. But in practice, most Admins agree, you're better off
*disabling* Network Manager altogether in the `System→Preferences→Startup Applications` applet, if you want to set up a bridged iptable configuration in `/etc/network/interfaces`.

To *completely* disable Network Manager, you also need to open the `System→Preferences→Network Connections` control panel and delete all
connection profiles under the Wired tab. Even if Network Manager is disabled as a startup service, Ubuntu will read network configuration
information set by this control panel, resulting in strange interactions with `/etc/network/interfaces`.

Even after disabling the Network Manager service, setting up `/etc/network/interfaces` and stopping and restarting `/etc/init.d/networking`,
ethernet devices can show up in the routing table with the *same IP address* as the bridge (which is why we asked you what your route was showing). You must kill all processes and restart the Daemon.

Since most of us really need something "bigger" than say as SOHO router (even something running a ddwrt /openwrt solution), I would suggest adding a nice appliance instead?

This is a pretty tight solution:  REDWALL, http://redwall.sourceforge.net/features.html

#### Web, basic port firewalling

+ https://www.owasp.org/index.php/Main_Page, is a good place to start for Web, aimed more towards the Development side (applications).
+ Linux server hardening, http://www.tecmint.com/linux-server-hardening-security-tips/
Keep in mind those tips are for  PRODUCTION SERVERS rather than Development machines or Workstations.  For example, it is best practices NOT to have GUI desktops on most Production Linux Servers (there are some exceptions), but for Workstations, most Developers would prefer to have a GUI development environment.

----

# Vagrant
+ If you mess-up the VM, blow it away with vagrant, https://www.vagrantup.com/docs/

----

# VM
+ setting up a Debian VM step by step instructions: https://jtreminio.com/2012/07/setting-up-a-debian-vm-step-by-step/

----

# [Yaksha](http://svaksha.github.io/yaksha) ToDo
+ Papertrail, CopperEgg, Skeddly, Monit, Jenkins.

### Cleanup my bash programs 
+ [BASH best practices](https://github.com/progrium/bashstyle).

### Automation
__Dotbot__
+ https://github.com/webpro/awesome-dotfiles
+ https://github.com/cypher/dotfiles
+ https://github.com/TheLocehiliosan/yadm
+ http://dotfiles.github.io/
+ Blog post on [managing dotfiles](http://www.anishathalye.com/2014/08/03/managing-your-dotfiles/) and [dotbot](https://github.com/anishathalye/dotbot) with the dotfiles [template](https://github.com/anishathalye/dotfiles_template).
+ Shell script to initialize your dotfiles with `dotbot`: https://github.com/Vaelatern/init-dotfiles
+ https://github.com/szaghi/dotfiles
+ https://bitbucket.org/patrickdoane/dotfiles
__homeshick__
+ [homeshick](https://github.com/andsens/homeshick) : git dotfiles synchronizer written in bash.
+ https://github.com/andsens/rc-files : homesick compatible bashrc and zshrc files.
+ @[holman](http://zachholman.com/2010/08/dotfiles-are-meant-to-be-forked/) talks about keeping dotfiles lean. Learn how they do it: [rtomayko](https://github.com/rtomayko/dotfiles), [holman](https://github.com/holman/dotfiles), [mathiasbynens](https://github.com/mathiasbynens/dotfiles), ..
__zsh__
+ Reconsider if [zsh](https://github.com/robbyrussell/oh-my-zsh) is more useful than bash? on all machines?
+ https://github.com/jbernard/dotfiles :: Dotfile management made easy. http://pypi.python.org/pypi/dotfiles/
+ https://github.com/alebcay/awesome-shell
__AWS__
+ https://github.com/colinbjohnson/aws-missing-tools :: tools for managing AWS resources including EC2, EBS, RDS, IAM, CloudFormation and Route53.
+ https://github.com/colinbjohnson/snippets
+ https://github.com/colinbjohnson/awstraining
__basher__
+ [basher](https://github.com/basherpm/basher) :: A package manager for shell scripts. 

### Auto-Alias
+ [HuffShell](https://github.com/paulmars/huffshell) :: A gem for suggesting and optimizing your shell aliases, programtically. 

### Backup
+ https://github.com/tsileo/dirtools :: Exclude/ignore files in a directory (using .gitignore like syntax), compute hash, search projects for an entire directory tree, gzip compression and track changes in a directory over time.
+ https://github.com/tsileo/incremental-backups-tools :: Storage agnostic incremental backups tools, building blocks for creating incremental backups utilities. 
+ https://github.com/lra/mackup :: Keep your application settings in sync (OS X/Linux).
+ https://pypi.python.org/pypi/backalaika/0.2.1
+ https://www.zufallsheld.de/2014/01/25/python-backup-script-revisited/
+ https://github.com/aliceh75/dufl

### Docker
+ https://github.com/ContinuumIO/docker-images : Repository of Docker images created by Continuum Analytics. 
    + See the Docker site:  https://registry.hub.docker.com/repos/continuumio/



