# Git Branching

###  1. На локальном репозитории сделать ветки для:

    Postman
    Jmeter
    CheckLists
    Bug_Report
    SQL
    Charles
    Mobile_testing
    
Ветка создается командой ``git branch "название ветки"``

    $ git branch Postman
   
###  2. Запушить все ветки на внешний репозиторий

Командой ``git push -u origin "название ветки"`` загружается на внешний репозиторий

    $ git push -u origin Postman
    Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
    remote:
    remote: Create a pull request for 'Postman' on GitHub by visiting:
    remote:      https://github.com/DrakenJager/Git_branching/pull/new/Postman
    remote:
    To https://github.com/DrakenJager/Git_branching.git
    * [new branch]      Postman -> Postman
    branch 'Postman' set up to track 'origin/Postman'.

Аналогично для каждой последующей ветки

###  3. В ветке Bug_Reports сделать текстовый документ со структурой баг репорта

Переходим в ветку Bug_Reports, командой ``git checkout Bug_Reports``

    $ git checkout Bag_Reports
    Switched to branch 'Bug_Reports'
    Your branch is up to date with 'origin/Bug_Reports'.

Создаем текстовый документ через команду ``cat > bug_report.txt``

    cat > bug_report.txt
    1) id
    2) severity
    3) environment
    4) title
    5) steps to reproduce
    6) expected result
    7) actual result
    8) attachments
    9) bug started
    10) bug comments


### 4. Запушить структуру багрепорта на внешний репозиторий

Сначала выполняем ``git add .`` и далее команду ``git commit -m "комментарий"``

    $ git commit -m "add Bug_report"
    [Bug_Reports 734dd15] add Bug_report
    1 file changed, 10 insertions(+)
    create mode 100644 Bug_report.txt

Чтобы запушить на внешний репозиторий используем команду ``git push``

    $ git push
    Enumerating objects: 4, done.
    Counting objects: 100% (4/4), done.
    Delta compression using up to 12 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 396 bytes | 396.00 KiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    To https://github.com/DrakenJager/Git_branching.git
    465d632..734dd15  Bug_Reports -> Bug_Reports

### 5. Вмержить ветку Bug_Reports в Main

Для того чтобы вмержить ветку ``Bag Reports``, нужно сначала перейти в ту ветку, куда мы хотим ее вмержить

Для этого используем сначала команду ``git checkout main``

    $ git checkout main
    Switched to branch 'main'
    Your branch is up to date with 'origin/main'.
    
А после уже используем команду ``git merge Bug_Reports``

    $ git merge Bug_Reports
    Updating 465d632..734dd15
    Fast-forward
    Bug_report.txt | 10 ++++++++++
    1 file changed, 10 insertions(+)
    create mode 100644 Bug_report.txt

### 6. Запушить main на внешний репозиторий

Используем команду ``git push``

    $ git push
    Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
    To https://github.com/DrakenJager/Git_branching.git
    465d632..734dd15  main -> main

### 7. В ветке CheckLists набросать структуру чек листа

Для начала переходим в ветку CheckList, командой ``git checkout "название ветки"``

    $ git checkout CheckLists
    Switched to branch 'CheckLists'
    Your branch is up to date with 'origin/CheckLists'.

Создаем текстовый документ через команду ``cat > checklist.txt``

    $ cat > checklist.txt
    1) id
    2) title
    3) precondition
    4) steps to reproduce
    5) expected result


    
### 8. Запушить структуру на внешний репозиторий 

Используем команды ``git add .``, ``git commit -m "add checklist.txt"`` и ``git push``
    
### 9. На внешнем репозитории сделать Pull Request ветки CheckLists в main

### 10. Синхронизировать Внешнюю и Локальную ветки Main

Используем команду ``git pull``

    $ git pull
    remote: Enumerating objects: 4, done.
    remote: Counting objects: 100% (4/4), done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 2 (delta 0), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (2/2), 752 bytes | 19.00 KiB/s, done.
    From https://github.com/DrakenJager/Git_branching
    734dd15..06f768e  main       -> origin/main
    Updating 734dd15..06f768e
    Fast-forward
    checklist.txt | 5 +++++
    1 file changed, 5 insertions(+)
    create mode 100644 checklist.txt

 
   
