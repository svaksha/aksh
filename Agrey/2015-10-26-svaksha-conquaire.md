# Objectives
+ Infrastructure to support continuous research data quality monitoring.
+ Infrastructure to host data and implement corresponding workflows.
+ OpenData - Make the data publicly available to allow reproduction of the computational analysis.
+ Ensure research data quality and reproducibility along the whole research lifecycle. 

Other useful tips to keep in mind: 
+ https://github.com/swcarpentry/good-enough-practices-in-scientific-computing/blob/gh-pages/index.md is an ongoing paper being written about best practices in scientific computing with many useful tips like normalizing data, automation, writing small funtions, etc.. 
+ The standardization of research methodologies and processes will help the data quality monitoring process, create reusable datasets and reproducable research.

----

# Technology

### Docker containers
+ VM's are memory-intensive and harder to setup besides varying across distros. Hence, docker containers are a safer method to ensure easy reproducability without massive system or data changes.
+ Use [Docker](https://docker.com) to containerize the research data that is syntactically well-formed, has __meta tags__, is __cleaned up__ and __ready for reuse__ or for __testing and revalidating__ already published research. 
+ By creating __docker instances__ for the pockets of research that a scientist wishes to share, one can easily __reproduce the same environment instance in which the original computation was carried out__.
+ Write simple scripts to simplify the deployment of local code which will ease my worktable (see https://github.com/svaksha/yaksha)

### Reprozip
+ https://vida-nyu.github.io/reprozip/, states that computational reproducibility can be very painful to achieve due to the tedious scientific paper reviewing process which requires authors to generate a compendium that encapsulates all the inputs needed to correctly reproduce their experiments: the data, a complete specification of the experiment and its steps, and information about the originating computational environment (OS, hardware architecture, and library dependencies). Given the various OS in the market the dependency hell makes this an impossible task to get right across all distros even if they use similar tools.

+ Reprozip is almost like a virtual machine, but maybe smaller than a VM and most importantly it uses vagrant and docker and runs on anaconda (2.x), all of which gives you an isolated sandbox to test your research while allowing others to use the tools used by you to reproduce the analytic procedures (e.g. scripts, spreadsheets, etc.) that were used to process or analyse the research data. I tried to install it for Python-3.x within anaconda but there was a package conflict, so I filed a BR: https://github.com/ViDA-NYU/reprozip/issues/157

### Other tools
+ Configuration management software : Saltstack, Puppet, Ansible, Chef
+ Servers:: Self-hosted server farms.
+ DVCS:: Git (on Gitlab - Foss stack)
+ MessagingLib:: RabbitMQ, ZeroMQ
+ DB:: Depending on the researcher data, support for RDBMS (Postgres, MariaDB), NoSQL (Mongo, Redis) or Array-based DB (SciDB).


### Data Quality Framework
+ Quality checks on data for range and errors.

### Git-GitLab
+ Git is the DVCS running the backend system to store data running a web-application to upload scripts etc so they can see how far they are from data. 
+ Use Gitlab, a Free and open source DVCS that uses GIT for version control.
+ For advanced features of git, non-CS researchers would need to be provided with help and documentation to enable them to use the tools smoothly. 

