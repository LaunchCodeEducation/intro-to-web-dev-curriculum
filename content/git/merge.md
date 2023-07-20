# Merging in Git

::: index
! merge, ! merge conflict, ! stash
:::

## How to Merge

A **merge** in Git occurs when two branches are combined in the
repository.

::: admonition
Example

Let\'s say a programmer wants to merge a branch called `test` into
`main`. To accomplish this:

1.  The programmer switches to the branch they want to merge into. In
    this case:

    ``` bash
    $ git checkout main
    ```

2.  The programmer then runs the merge command:

    ``` bash
    $ git merge test
    ```

When successful, the code in the `test` branch is pulled into `main`.
:::

## Merge Conflicts

This process is often seamless. In the example in the previous section,
a programmer created a branch to change the HTML and the other
programmer did the same to change the CSS. Because the two programmers
changed different files, the merge of the updated HTML and updated CSS
won\'t create a conflict.

A **merge conflict** occurs when a change was made to the same line of
code on both branches. Git doesn\'t know which change to accept, so it
is up to the programmers to resolve it. Merge conflicts are minor on
small applications, but can cause issues with large enterprise
applications.

Even though the thought of ruining software can be scary, every
programmer deals with a merge conflict during their career. The best way
to deal with a merge conflict is to face it head on and rely on
teammates for support!

### Ways to Avoid Merge Conflicts

Even though merge conflicts are normal in Git, it is also normal for
programmers to want to do everything they can to avoid them. Here are
some tips on how to avoid a merge conflict:

1.  Git has a dry-run option for many commands. When a programmer uses
    that option, Git outputs what WILL happen, but doesn\'t DO it. With
    merging in Git, the command to perform a dry-run and make sure there
    aren\'t any conflicts is `git merge --no-commit --no-ff <branch>`.
    The `--no-commit` and `--no-ff` syntax tells Git to run the merge
    without committing the result to the repository.
2.  Before merging in a branch, any uncommitted work that would cause a
    conflict needs to be dealt with. A programmer can opt to not commit
    that work and instead **stash** it. By using the `git stash`
    command, the uncommitted work is saved in the stash, and the
    repository is returned to the state at the last commit. If the
    programmer wants to retrieve stashed work later, they can do so with
    the command `git stash pop`.

## Check Your Understanding

::: admonition
Question

If a programmer is on the branch `test` and wants to merge a branch
called `feature` into `main`, what steps should they take?
:::
