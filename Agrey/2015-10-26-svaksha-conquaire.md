+ [OBJECTIVES](#objectives)
+ [TECHNOLOGY](#technology)
   + [Continuous Integration](#continuous-integration)        
        + [Configuration Management](#configuration-management)
        + [TDD](#tdd)
   + [Computational Reproducibility - Docker](#computational-reproducibility-docker)
   + [Computational Reproducibility - Reprozip](#computational-reproducibility-reprozip)
   + [Database](#database)
   + [DVCS - Git GitLab](#dvcs-git-gitlab)
   + [Framework - Data Quality Assesment](#framework-data-quality-assesment)
        + [Bubbles](#bubbles)
   + [Framework - Web](#framework-web)
   + [Infrastructure - Server](#infrastructure-server)
   + [Messaging Lib](#messaging-lib)
   + [Visualization](#visualization)
   
====

# OBJECTIVES
+ Infrastructure to support continuous research data quality monitoring.
+ Infrastructure to host data and implement corresponding workflows.
+ OpenData - Make the data publicly available to allow reproduction of the computational analysis.
+ Ensure research data quality and reproducibility along the whole research lifecycle. 

Other useful tips to keep in mind: 

+ https://github.com/swcarpentry/good-enough-practices-in-scientific-computing/blob/gh-pages/index.md is an ongoing paper being written about best practices in scientific computing with many useful tips like normalizing data, automation, writing small funtions, etc.. 
+ The standardization of research methodologies and processes will help the data quality monitoring process, create reusable datasets and reproducable research.


Development related tips:

+ Choose the stack whose programming language is popular across domains (web-dev, TDD and scientific development) with good library support for all the different domains.
+ Mixing programming languages is inevitable for certain tasks but more than 2 or 3 will become a maintenance nightmare over time - Dependency hell and future maintenance issues, if any.
+ Must be easy to learn - in terms of future development and maintenance issues.
+ Existing cross-lang API wrappers must be maintained in future too.
+ Good community support - essential for help-related issues.
+ Good documentation.

====

# TECHNOLOGY

Leverage existing FOSS tools for the similarity in features and other specifications and their reuse potential as per the Licenses they are released under. The web framework, CI, messaging libs, and other backendtack options available are : 

## [Continuous Integration](https://en.wikipedia.org/wiki/Continuous_integration)

+ [GitLab Continuous Integration](https://about.gitlab.com/gitlab-ci/): Integrated CI to test, build and deploy your code on GitLab.
+ [BuildBot](https://en.wikipedia.org/wiki/Buildbot), is written in Python on top of the Twisted libraries.
+ [Dockunit.io](https://dockunit.io/) is a GPL licensed, cross-platform experiment in Docker based integration tests [CI platform](https://github.com/dockunit/platform) that integrates with github.
+ [Tox](http://tox.readthedocs.org/en/latest/), an automation tool providing packaging, testing and deployment of Python software.
+ [Rake](https://en.wikipedia.org/wiki/Rake_%28software%29), a Ruby tool for software task management and build automation.
+ [Capistrano](https://en.wikipedia.org/wiki/Capistrano_%28software%29), an open source Ruby tool for running scripts on multiple servers to deploy web applications.
+ _NON-FOSS_:
   + [Travis-CI](https://travis-ci.org/), free only for open source projects - integrates with github, gitlab status is not known.

### Configuration Management
+ Ansible (.py)
+ Saltstack (.py)
+ Puppet (.rb)
+ Chef (.rb)

### TDD
+ Julia: https://github.com/svaksha/Julia.jl/blob/master/QA.md
+ Python: https://github.com/svaksha/pythonidae/blob/master/QA.md
+ Ruby: 
   * https://github.com/sdogruyol/awesome-ruby#testing
   * https://github.com/markets/awesome-ruby#testing



## Database
Depending on the researcher data types, support which of the following DB's(?): 

+ RDBMS (Postgres, MariaDB, ..)
+ NoSQL : Is it document/ graph/ array based?
   - MongoDB
   - [Redis](http://redis.io/), is an open source (BSD licensed), in-memory data structure store, used as database, cache and message broker.
+ Array-based DB (SciDB).
+ HDF5


## DVCS - Git GitLab
+ Git is the DVCS running the backend system to store data running a web-application to upload scripts, etc..
+ Use Gitlab, a Free and open source DVCS that uses GIT for version control.
+ For advanced features of git, non-CS researchers would need to be provided with help and documentation to enable them to use the tools smoothly. 


## Computational Reproducibility - [Docker](https://docker.com)
VM's are memory-intensive and harder to setup besides varying across distros. Hence, docker containers are a safer method to ensure easy reproducability without massive system or data changes.
+ Containerize the research data that is syntactically well-formed, has __meta tags__, is __cleaned up__ and __ready for reuse__ or for __testing and revalidating__ already published research. 
+ By creating __docker instances__ for the pockets of research that a scientist wishes to share, one can easily __reproduce the same environment instance in which the original computation was carried out__.
+ Write simple scripts to simplify the deployment of local code which will ease the worktable. (see, https://github.com/svaksha/yaksha)



## Computational Reproducibility - [Reprozip](https://vida-nyu.github.io/reprozip/)
+ Computational reproducibility is hard to achieve due to the tedious scientific paper reviewing process which requires authors to generate a compendium that encapsulates all the inputs needed to correctly reproduce their experiments: the data, a complete specification of the experiment and its steps, and information about the originating computational environment (OS, hardware architecture, and library dependencies). 
+ Various OS introduce a dependency hell making it an impossible task to get the same computational environment across all distros even if they use similar tools.
+ Reprozip is almost like a virtual machine, but maybe smaller than a VM and most importantly it uses vagrant and docker and runs on anaconda (2.x).
+ Gives the user an isolated sandbox to test their research while allowing others to use the tools used by the scientist to reproduce the analytic procedures (e.g. scripts, spreadsheets, etc.) that were used to process or analyse the research data. 
+ There was a package conflict bug for Python-3.x within anaconda, now fixed : https://github.com/ViDA-NYU/reprozip/issues/157

   
## Framework - Data Quality Assesment
+ Quality checks on data for range and errors.
+ Domain-independent tests check syntactic wellformedness.
+ Validate data according to schemas. _Task_: Integrate validation scripts into platform.
+ Provision of metadata and consistent use of vocabulary.
+ Open availability of scripts for automation tasks.
+ Domain-specific quality checks will be implemented and integrated into the framework as services in a plug-in framework. 

The Foss tools available are : 

### [Bubbles](http://bubbles.databrewery.org/index.html)
+ A Python framework for data processing and data quality measurement.
+ Implements basic concepts like abstract data objects, operations and dynamic operation dispatch. 
+ Repo: https://github.com/Stiivi/bubbles
+ License: MIT.

###### NOTES
+ _Pros_:
   * A Python framework makes it easier to maintain the dependency hell of various scientific libs if researchers also use Python for their analyical work.
   * The scientific library ecosystem has excellent support for [Astronomy & GIS](https://github.com/svaksha/pythonidae/blob/master/Earth-Science.md), [Biology](https://github.com/svaksha/pythonidae/blob/master/Biology.md), [Chemistry](https://github.com/svaksha/pythonidae/blob/master/Chemistry.md), [Physics](https://github.com/svaksha/pythonidae/blob/master/Physics.md), [Math](https://github.com/svaksha/pythonidae/blob/master/Mathematics.md), [Statistics](https://github.com/svaksha/pythonidae/blob/master/Statistics.md), and other scientific disciplines.
+ _Cons_:
   * The packaging ecosystem can be hard for a newbie to navigate. Automating this is easier.



## Framework - Web
The most popular web frameworks to consider are:

+ Django (.py)
   - Django is better suited to CMS-like tasks.
   - Strong and popular with many django-libs.
   - Good community support, project wont vanish or cease development.
   - More explicit than Ruby/RoR.
+ RoR (.rb)
   - Rails is more general-purpose.
   - Good community support and a popular web tool.
   - Fast prototyping and easy to get webapps up and running in a very quick time BUT has too much inbuilt magic.
   - Many high quality gems (libs) out there that would serve many common requirements for web development.
+ [Volt](http://voltframework.com/) (.rb), https://github.com/voltrb/volt
   - New ruby framework.
   - Not sure about the level of community support, libs and documentation.



## Infrastructure - Server
+ Self-hosted server farms.


## Messaging Lib
+ RabbitMQ
+ ZeroMQ

## Visualization
Tools for visualization are available in Python, Julia, Javascript, etc..

+ 

