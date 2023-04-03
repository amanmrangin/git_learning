#### Add a new file (never exist in git)
1. Navigate to existing directory: `cd exercise-1`
   -   Verify the output by running `git status -sb` ![img_5.png](img_5.png)
2. Create a new file (file1.txt) with any editor your choice or command (e.g nano file1.txt):
   `nano file1.txt`
   - Add a new line: "_This is line 1 of file1.txt_" and close the file1.txt 
   - Verify the output by running `git status -sb` ![img_6.png](img_6.png)
   - Notice that **_??_** before _file1.txt_ indicates that _file1.txt_ is a new file and untracked by Git
3. Add a new (untracked/unversioned by Git) 'file1.txt' from Working Directory (Working Tree) to local git Stage(Index)
   `git add file1.txt`
   
   The above command has added a **new** untracked/unversioned file (file1.txt) from local _exercise-1_ directory to local git repo stage directory (/.git/index)
   Verify the output by running `git status -sb` ![img_4.png](img_4.png)
4. Remove a newly added file 'file1.txt' from local git Stage(Index), (/.git/index)
    