
# How to push a directory in git repo


Git commands

1. First create repo on remote or git hub.
2. come to local folder
3. do git init
4. git status
5. git add
6. git commit -m "message"
7. git remote add origin git@github.com:FRK65/myproject.git
8. git push origin master
9. git push origin master --force



**terminal- Notes % git branch**

fatal: Not a git repository (or any of the parent directories): .git

**terminal- Notes % git init**

Initialized empty Git repository in /Users/khan/Downloads/Notes/.git/

**terminal- Notes % git status**

On branch master, No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)

        .gitignore
        .idea/
        Java_Notes.iml
        src/

nothing added to commit but untracked files present (use "git add" to track)
**terminal- Notes % git add src**
**terminal- Notes % git status** 
On branch master, No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to unstage)

        new file:   src/Resume/MyResume.md
        new file:   src/Routine.md
        new file:   src/Topics.md
        new file:   src/main/About_Collection.md
        new file:   src/main/About_Collection_Difference.md
        new file:   src/main/About_Java.md
        new file:   src/main/Class-Object-and-keywords.md
        new file:   src/main/Exception_Handling.md
        new file:   src/main/Garbage_Collection.md
        new file:   src/main/JDK_JRE_JVM.md
        new file:   src/main/Memory_management.md
        new file:   src/main/OOPs_Concepts.md
        new file:   src/main/Serialization_and_Deserialization.md
        new file:   src/main/String_in_java.md
        new file:   src/main/Threads_MultiThreading.md
        new file:   src/main/test.md
        new file:   src/work/company.md

Untracked files:
(use "git add <file>..." to include in what will be committed)

        .gitignore
        .idea/
        Java_Notes.iml

**terminal- Notes % git branch**    
**terminal- Notes % git status**
On branch master

No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to unstage)

        new file:   src/Resume/MyResume.md
        new file:   src/Routine.md
        new file:   src/Topics.md
        new file:   src/main/About_Collection.md
        new file:   src/main/About_Collection_Difference.md
        new file:   src/main/About_Java.md
        new file:   src/main/Class-Object-and-keywords.md
        new file:   src/main/Exception_Handling.md
        new file:   src/main/Garbage_Collection.md
        new file:   src/main/JDK_JRE_JVM.md
        new file:   src/main/Memory_management.md
        new file:   src/main/OOPs_Concepts.md
        new file:   src/main/Serialization_and_Deserialization.md
        new file:   src/main/String_in_java.md
        new file:   src/main/Threads_MultiThreading.md
        new file:   src/main/test.md
        new file:   src/work/company.md

Untracked files:
(use "git add <file>..." to include in what will be committed)

        .gitignore
        .idea/
        Java_Notes.iml

**terminal- Notes % git commit -m "my notes 1"**

[master (root-commit) 69c23fe] my notes 1
17 files changed, 5523 insertions(+)
create mode 100644 src/Resume/MyResume.md
create mode 100644 src/Routine.md
create mode 100644 src/Topics.md
create mode 100644 src/main/About_Collection.md
create mode 100644 src/main/About_Collection_Difference.md
create mode 100644 src/main/About_Java.md
create mode 100644 src/main/Class-Object-and-keywords.md
create mode 100644 src/main/Exception_Handling.md
create mode 100644 src/main/Garbage_Collection.md
create mode 100644 src/main/JDK_JRE_JVM.md
create mode 100644 src/main/Memory_management.md
create mode 100644 src/main/OOPs_Concepts.md
create mode 100644 src/main/Serialization_and_Deserialization.md
create mode 100644 src/main/String_in_java.md
create mode 100644 src/main/Threads_MultiThreading.md
create mode 100644 src/main/test.md
create mode 100644 src/work/company.md

**terminal- Notes %  git remote add origin https://github.com//FRK65/notes.git**  
**terminal- Notes % git push origin master**

Counting objects: 23, done.
Delta compression using up to 12 threads.
Compressing objects: 100% (19/19), done.
Writing objects: 100% (23/23), 69.87 KiB | 6.35 MiB/s, done.
Total 23 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/FRK65/notes/pull/new/master
remote:
To https://github.com//FRK65/notes.git
[new branch]      master -> master

 **terminal- Notes %** 
