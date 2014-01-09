## git diff-blame

Annotates each line in a diff hunk with author and commit information like blame.

## Example:

    $ git diff-blame HEAD^
    diff --git c/git-diff-blame w/git-diff-blame
    --- c/git-diff-blame
    +++ w/git-diff-blame
    ed3dc1d5 (Desmond Brand 2014-01-09 12:08:57 -0800 52)           my $n_end = $n_ofs + $n_cnt - 1;
    ^275a5e3 (Desmond Brand 2014-01-09 12:04:26 -0800 53)           if (!$create) {
    ^275a5e3 (Desmond Brand 2014-01-09 12:04:26 -0800 54)               open($pre, '-|', 'git', 'blame', '-M', "-L$o_ofs,$o_end",
    ed3dc1d5 (Desmond Brand 2014-01-09 12:08:57 -0800 55)   -                "-l",
    ^275a5e3 (Desmond Brand 2014-01-09 12:04:26 -0800 56)                    $oldrev, '--', $prefilename) or die;
    ^275a5e3 (Desmond Brand 2014-01-09 12:04:26 -0800 57)           }
    ^275a5e3 (Desmond Brand 2014-01-09 12:04:26 -0800 58)           if (!$delete) {
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 59)               if ($newrev) {
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 60)                   open($post, '-|', 'git', 'blame', '-M', "-L$n_ofs,$n_end",
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 61)   -                    "-l",
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 62)                        $newrev, '--', $postfilename) or die;
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 63)               } else {
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 64)                   open($post, '-|', 'git', 'blame', '-M', "-L$n_ofs,$n_end",
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 65)   -                    "-l",
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 66)                        '--', $postfilename) or die;
    15f5a1f9 (Desmond Brand 2014-01-09 12:46:50 -0800 67)               }
    ^275a5e3 (Desmond Brand 2014-01-09 12:04:26 -0800 68)           }

Original version by @toddlipcon taken [from here](https://github.com/toddlipcon/tlipcon-bin/blob/master/git-diff-blame).
