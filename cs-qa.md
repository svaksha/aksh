+ [CI](#ci)
+ [DOCUMENTATION](#documentation)
+ [ERROR](#error)
+ [TDD](#tdd)

----

+ https://en.wikipedia.org/wiki/Comparison_of_continuous_integration_software
+ System architecture: http://stackoverflow.com/questions/755540/enterprise-systems-and-application-architecture-best-practise/760643#760643

----


# CI
+ https://nigelb.me/2016-12-02-test-automation-on-centos-ci-with-ansible.html

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

## GitLab
+ http://doc.gitlab.com/ce/ci/runners/README.html

## TravisCI
+ [travis-ci](https://travis-ci.org/)
+ http://www.softwaretestinghelp.com/what-is-sei-cmm-iso-ieee-ansi-will-it-help/ 

---- 

# DOCUMENTATION
+ [Don’t document your code. Code your documentation](https://dev.to/raddikx/dont-document-your-code-code-your-documentation).
+ http://asciidoctor.org/
+ https://github.com/GitbookIO/gitbook
+ Sphinx
+ Pandoc
+ http://ericholscher.com/blog/2016/mar/15/dont-use-markdown-for-technical-docs/

----

# ERROR
+ Semantic and Syntactic: https://wci.llnl.gov/codes/basis/manual/node53.html

----


# [TDD](https://en.wikipedia.org/wiki/Test-driven_development)
+ https://en.wikipedia.org/wiki/Scenario_testing
+ http://blog.trigent.com/points-to-remember-while-identifying-effective-test-scenarios-and-designing-test-cases/


## [Test_Script](https://en.wikipedia.org/wiki/Test_script)
+ http://stackoverflow.com/questions/1550157/manual-test-script-templates
+ http://softwaretestingfundamentals.com/test-script/
+ Test case: http://softwaretestingfundamentals.com/test-case/
+ http://www.cambridge.org/ve/download_file/202207/
+ http://www.tmap.net/sites/default/files/Template_Test_Script.doc
+ http://www.riceconsulting.com/home/index.php/Web-Testing/how-to-develop-test-cases-and-test-scripts-for-web-testing.html
+ http://www.softwaretestinghelp.com/test-case-template-examples/

----
