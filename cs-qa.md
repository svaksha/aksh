

+ https://en.wikipedia.org/wiki/Comparison_of_continuous_integration_software
+ System architecture: http://stackoverflow.com/questions/755540/enterprise-systems-and-application-architecture-best-practise/760643#760643

----

# DOCUMENTATION
+ https://github.com/GitbookIO/gitbook
+ Sphinx
+ Pandoc


----

## GitLab
+ http://doc.gitlab.com/ce/ci/runners/README.html

## TravisCI
+ [travis-ci](https://travis-ci.org/)
+ http://www.softwaretestinghelp.com/what-is-sei-cmm-iso-ieee-ansi-will-it-help/ 

---- 

# CI HowTo
1. In the BugTicket system, start listing known problems.
2. Prioritize what needs to be fixed
3. Make a fix, test the fix.
   + Unit tests are functional tests.
       + Unit tests are stand alone test.
       + Performs a single cohesive function.
       + Compiled separately
       + Is a single task under a larger work heading
   + Need to add smoke test - what absolutely must pass before it goes to production?
   + Need to add regression test - did the new code break something already out there?
4. User Experience is above all.

## Advice
+ https://www.quora.com/What-is-the-difference-between-Bamboo-CircleCI-CIsimple-Ship-io-Codeship-Jenkins-Hudson-Semaphoreapp-Shippable-Solano-CI-TravisCI-and-Wercker
    + You should be able to run lion share of your CI tasks on your development machine. 
    + Test all your CI scripts locally. This also helps if you are working on CI a lot and want to test changes before running them on production CI server, kind of debugging process.


----
