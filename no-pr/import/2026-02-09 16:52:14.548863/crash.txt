Traceback (most recent call last):
  File "/app/iambic/plugins/v0_1_0/github/github.py", line 558, in wrapped_workflow_func
    template_changes = workflow_func(repo_url, default_branch)
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/plugins/v0_1_0/github/github.py", line 723, in _handle_import
    raise e
  File "/app/iambic/plugins/v0_1_0/github/github.py", line 710, in _handle_import
    repo = prepare_local_repo_for_new_commits(repo_url, repo_dir, "import")
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/plugins/v0_1_0/github/github.py", line 130, in prepare_local_repo_for_new_commits
    cloned_repo = clone_git_repo(repo_url, repo_path, None)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/core/git.py", line 60, in clone_git_repo
    repo = Repo.clone_from(repo_url, repo_path, branch=remote_branch_name)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/git/repo/base.py", line 1325, in clone_from
    return cls._clone(
           ^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/git/repo/base.py", line 1234, in _clone
    finalize_process(proc, stderr=stderr)
  File "/usr/local/lib/python3.11/site-packages/git/util.py", line 419, in finalize_process
    proc.wait(**kwargs)
  File "/usr/local/lib/python3.11/site-packages/git/cmd.py", line 604, in wait
    raise GitCommandError(remove_password_if_present(self.args), status, errstr)
git.exc.GitCommandError: Cmd('git') failed due to: exit code(128)
  cmdline: git clone -v -- https://*****:*****@github.com/smoy/iambic-templates-tutorial.git /tmp/lambda442_0n9i/.iambic/repos/
  stderr: 'Cloning into '/tmp/lambda442_0n9i/.iambic/repos'...
remote: Internal Server Error
fatal: unable to access 'https://github.com/smoy/iambic-templates-tutorial.git/': The requested URL returned error: 500
'
