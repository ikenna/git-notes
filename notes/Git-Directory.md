---
layout: page
title: "Git Directory"
description: ""
---
{% include JB/setup %}

    $cd .git
    $ ls
    HEAD            # this file points to your currently checked out branch
    branches/       # this directory is used only by old versions of Git 
    config          # this file Contains config options for your project
    description     # GitWeb reads the contents of this file for a description of the repo. You can launch GitWeb with 'git instaweb --httpd=webrick' 
    hooks/          # this directory contains Git hook scripts
    index           # File used by Git to hold your staging area information 
    info/           # Put patterns for files to ignore in here. Similar to .gitignore. 
    objects/        # directory that Stores all the objects of your git repo.
    refs/           # directory that holds pointers to commits in the objects directory


Types of git objects 
======================
Blob - holds file data. A blob is a version of a file. 
Tree Object - Represents one level a directory heiearchy. Holds the list of file names, file modes and their associated blobs in that directory level. Also holds references to other trees (i.e sub-directories ). 
Commit object - metadata about each change added to a git repository. E.g commit date/time, author, log message, and Tree.   Root commit has no parent. Merge commits have 2  parents. Commit objects form a directed acyclic graph.  
Tag - a named reference to a particular commit.   

Git Index 
==========
    - A binary file contains a list of files (and file attributes) which have been stored in the git database at a given moment in time.  
    - On checkout, git populates the index based based on the files you have checked out into your working directory. 
    - It is used to hold a snapshot of your next commit.
    - its not a tree structure, but a flat manifest or list of files. 
    - git commit creates a commit object based on the manifest 
    - you can see files in the git index with 'git ls-files'
    - you can add files to the git index with 'git add'
    - you can see files staged in the index with  'git ls-files -s' 

Xteristics of git objects
============================
- all objects are named by the sha1 hash of their contents.    
- objects are stored in individual files in the .git/objects/ directory, but may be later compressed into pack files. 


Refs are named pointers to a commit. A ref can point to another commit or to another ref.  
/ref/head/* refs to the most recent commit in each branch
/ref/tags/* tag refs
HEAD  the ref of the currently checked out branch 

