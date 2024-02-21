### Git Flow Branching Stratagy

Main points :

1 . Name
2 . Long lived Short lived

* Master{podoction code} and Devolop{it infornt of master} branch are long lived  branches we cant delete

* feature release hotfix are short lived

* * * { Pull before push} it a concept of git rule means every devopler wants code from git then he need to push the code to git then he get pull request also called as merge 

3 . Source and destinatiin
4 . Merge and how to promote PROD

* {PR}


5 . Conflicts

* Git flow the conflict when the different changes on 1 line then both party where come to an understand and and they push some code to devolop branch after  tested

* * When a devoper push the code to feature branch then feature branch test the code weather code is correct are not if they find out any bugs then they send back the code to devolop branch or then debug there mistake in testing branch .

Feature Branch like :
                      QA
                      PRE PROD
                      MASTER....ETC

* After debug/test then they merge the code to Master branch . using pull request it goes to production branch after that they test the code and they push to code in to git and devolp brach pull the code using pull request {PR} 

* Coming to hotfix it is used rarely .

* CI/CD is most use only feature branch because devops/devoloper can esaily store the data they can esaily pull the data for years...



