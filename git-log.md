# git-log - Show commit logs

help information can be found in `git log --help`


## git log

show commit logs

```
commit 96aa81e8ff691d644b5fd1c7a10b8726c476f5f1 (HEAD -> devel, origin/devel, origin/HEAD)
Author: Rick Elrod <rick@elrod.me>
Date:   Sat Aug 1 15:34:35 2020 -0500

    Remove incidental_azure_rm_mariadbserver tests (#71037)

    Change:
    - Remove incidental test which has no remaining incidental coverage.

    Test Plan:
    - CI

    Signed-off-by: Rick Elrod <rick@elrod.me>

commit 54bee7152b70409f751aefb4affafdd3867df87b
Author: Sandra McCann <samccann@redhat.com>
Date:   Fri Jul 31 16:57:57 2020 -0400

    Update network platform guides with FQCN (#70699)

    * fqcn all the docs things!
```

## git log --oneline

display each commit in one line (only has the SHA1, commit log headline) 

```
96aa81e (HEAD -> devel, origin/devel, origin/HEAD) Remove incidental_azure_rm_mariadbserver tests (#71037)
54bee71 Update network platform guides with FQCN (#70699)
61b36c6 Porting guides for ansible-base 2.10 and ansible 2.10 (#70891)
698efb8 'Foreport' changes to 2.10 porting guide from stable-2.10 to devel. (#71024)
5019335 Document how to upgrade to ansible with pip (#70768)
75e8da0 hacking: fix announce script version parsing (#71008)
f99f96c Fix unstable unarchive test (#71004)
58145df document how to migrate between collections (#70243)
9879da8 DOCS: add 2.10 collections roadmap (#70975)
bf7276a Emit proper error for `x in y` when y is undefined (#70990)
d62dffa Add latest rc from ansible-base (#70974)
8c48366 Document to_json will convert to ASCII strings by default (#70954)
e28b20d remove github link from plugins (#70951)
ac5f3f8 unarchive - Check 'fut_gid' against 'run_gid' in addition to supplemental groups (#65666)
e139739 iptables: Add a note about ipv6-icmp (#70915)
54e2ae7 fix downloading collections in git repos and tar.gz artifacts (#70524)
e6bf202 linux facts - return proper broadcast address (#64528)
c4f442e facts - fix incorrect time for some date_time_facts (#70665)
```

## git log --graph

show commit with graph information, like commit parents information

we can add --oneline have a better view just like:

```
* 9a8101d (HEAD -> master, origin/master, origin/HEAD) update file4.txt
*   ce87351 (origin/feature-1, feature-1) Merge branch 'master' of https://github.com/git2022/git-demo
|\
| * 633068a Create file3.txt
* | c24b2b9 add file4
|/
* 26db882 Update README.md
* 3cd71e7 Update README.md
* b32548c Update file1.txt
* c0ef1d4 test my origin
* 1535546 update README.md
* 4b08db0 add readme
* 897fb06 3rd commit
* 2e4624f 2nd commit
* d0bde7c 1st commit
```

## git log --stat

display commit changes (add and delete)

```
commit 96aa81e8ff691d644b5fd1c7a10b8726c476f5f1 (HEAD -> devel, origin/devel, origin/HEAD)
Author: Rick Elrod <rick@elrod.me>
Date:   Sat Aug 1 15:34:35 2020 -0500

    Remove incidental_azure_rm_mariadbserver tests (#71037)

    Change:
    - Remove incidental test which has no remaining incidental coverage.

    Test Plan:
    - CI

    Signed-off-by: Rick Elrod <rick@elrod.me>

 test/integration/targets/incidental_azure_rm_mariadbserver/aliases        |   3 -
 test/integration/targets/incidental_azure_rm_mariadbserver/tasks/main.yml | 640 --------------------------------------------------------------------
 test/support/integration/plugins/modules/azure_rm_mariadbserver.py        | 388 -----------------------------------------
 3 files changed, 1031 deletions(-)

commit 54bee7152b70409f751aefb4affafdd3867df87b
Author: Sandra McCann <samccann@redhat.com>
Date:   Fri Jul 31 16:57:57 2020 -0400

    Update network platform guides with FQCN (#70699)

    * fqcn all the docs things!

 docs/docsite/rst/network/user_guide/platform_ce.rst         | 192 +++++++++++++++++++++++++++++++++++++++++-----------------------------------------
 docs/docsite/rst/network/user_guide/platform_cnos.rst       |  21 ++++-----
 docs/docsite/rst/network/user_guide/platform_dellos10.rst   |  22 +++++-----
 docs/docsite/rst/network/user_guide/platform_dellos6.rst    |  21 ++++-----
 docs/docsite/rst/network/user_guide/platform_dellos9.rst    |  21 ++++-----
 docs/docsite/rst/network/user_guide/platform_enos.rst       |  21 ++++-----
 docs/docsite/rst/network/user_guide/platform_eric_eccli.rst |  21 ++++-----
 docs/docsite/rst/network/user_guide/platform_exos.rst       |  32 +++++++-------
 docs/docsite/rst/network/user_guide/platform_icx.rst        |  19 +++++----
 docs/docsite/rst/network/user_guide/platform_ironware.rst   |  21 ++++-----
 docs/docsite/rst/network/user_guide/platform_meraki.rst     |  11 ++---
 docs/docsite/rst/network/user_guide/platform_netvisor.rst   |  23 +++++-----
```

## git shortlog

Summarize 'git log' output, by default, it summarize by author

```
Git 2022 (1):
      update file4.txt

Peng Xiao (8):
      1st commit
      2nd commit
      3rd commit
      add readme
      update README.md
      test my origin
      add file4
      Merge branch 'master' of https://github.com/git2022/git-demo

git2022 (4):
      Update file1.txt
      Update README.md
      Update README.md
      Create file3.txt
```

we can order by the number of commits for each author

```
git shortlog -n
```

```
Peng Xiao (8):
      1st commit
      2nd commit
      3rd commit
      add readme
      update README.md
      test my origin
      add file4
      Merge branch 'master' of https://github.com/git2022/git-demo

git2022 (4):
      Update file1.txt
      Update README.md
      Update README.md
      Create file3.txt

Git 2022 (1):
      update file4.txt
```


