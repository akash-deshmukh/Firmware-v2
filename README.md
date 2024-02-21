jgit-cookbook
Build Status Gradle Status Tag

Provides examples and code snippets for the JGit Java Git implementation.

The JGit framework is rich and diverse, it has two layers, a low-level api and a higher-level set of porcelain commands. This can be a bit intimidating at first as there are lots of classes, some of which are not relevant for most tasks.

This project tries to provide a collection of ready-to-run snippets which provide a quick start for building functionality using JGit.

Please make sure to take a look at the nicely written introduction and also use the existing JavaDoc and the User Guide as well, as they are well done and provide detailed information and a general overview of JGit respectively.

Note: Please use sites such as http://stackoverflow.com for general questions about JGit usage, not issues in this project. Issues should be used for problems with snippets and suggestions of missing snippets. Snippets from good answers on stackoverflow can then be included here, naturally.

Getting started
Grab it
git clone https://github.com/centic9/jgit-cookbook.git
Build it and create Eclipse project files
When using Maven
mvn dependency:sources eclipse:eclipse package
When using Gradle
./gradlew eclipse check
Run it
Each snippet is a small standalone Java application, so you can simply  
import the project into your favourite IDE and execute the snippets there.
Currently the following snippets are available
General Repository handling
Open an existing repository
Create a new repository
Porcelain commands
Initialize a new repository
Add a new file to the index
Commit a file to an existing repository
Commit all changes
List commits (i.e. Log)
List all tags in a repository
List all branches in a repository
List all commits in a repository
List uncommitted changes of a repository
Create and delete branches
Create and delete tags
List all tags applied on a branch
Revert a modified tracked file back to its original state in most recent commit
Return diff between two branches
Show diff of changes to a file between two revs
Show diff of changes to all files between two commits
Show diff of changes to a file between two commits when the file has been renamed
Show Status
Store contents of branch into a compressed file
Write contents of branch into a compressed file using a custom archive format
Blame, i.e. find out which commit changed specific lines in a file
Add and list Notes attached to commits
List available Notes
Clean all untracked files
Create, list, apply and drop stashes
Run garbage collection
Blame, i.e. retrieve information who last changed which line in a file
Merge changes from a branch
List changed files between two commits
List changed files in index
List changed files in checkout
Commands working with remote repositories
Clone a remote repository into a new local directory
Clone a remote repository via Apache SSHD
Iterate remote references in a repository
List remote heads/tags without a local clone
Fetch from remote repositories
Fetch from remote repositories and use 'prune' to remove outdated remote branches/tags
Fetch from remote repositories via SSH protocol
Clone a remote repository via SSH protocol and username/password credentials
Rebase onto an upstream branch
Using InMemoryRepository to clone a Git repo in-memory and work from there
Checkout a PR from GitHub
Push to a remote repository
Set remote tracking branch
Low-level API
Get the SHA-1 ref from a name, e.g. refs/heads/master
Get the commit-object from a name or a SHA-1
Get the commit-message
Get the tree-object from a commit-object, name or SHA-1
Read the contents of a file/blob
Get the tag-object from a name or a SHA-1
Resolve complex references, e.g. HEAD^^ to a SHA-1
Iterate over the commits on a branch
Iterate over a range of commits
Read contents of a specific file from a specific commit
List remotes configured for the current repository
Print out user information from Git
Read file attributes, e.g. executable state, file or directory, size, ...
Use class BranchTrackingStatus to retrieve number of commits ahead/behind compared to remote branches
Check if commits on other branches are merged into a given branch
List files in a directory as-of a specific commit or a tag
Iterate over files of a commit recursively
Iterate over files of a commit non-recursively
Find all commits that are reachable via tags, branches, remotes, HEADs, ...
GitServlet
There is a standalone sub-project in directory httpserver which starts up a simple HTTP Git server based on the JGit GitServlet.
Just import the project in your IDE and start up the Main application, see the Comments in the code for more details.

Another simple way to start the sample-server is to run ./gradlew run in the httpserver-directory.

Useful code elsewhere
cf-ops-automation-broker
Implementation of a simple git server serving anynymous git: protocol: https://github.com/orange-cloudfoundry/cf-ops-automation-broker/blob/8bcb286652fae2b8fe2ccc9f67c53cb0272bcbd0/cf-ops-automation-broker-core/src/main/java/com/orange/oss/cloudfoundry/broker/opsautomation/ondemandbroker/git/GitServer.java
Usage in tests: https://github.com/orange-cloudfoundry/cf-ops-automation-broker/blob/8bcb286652fae2b8fe2ccc9f67c53cb0272bcbd0/cf-ops-automation-bosh-broker/src/test/java/com/orange/oss/cloudfoundry/broker/opsautomation/ondemandbroker/sample/BoshServiceProvisionningTest.java#L134
Missing snippets
Iterate all commits of a repository: https://gerrit.googlesource.com/plugins/branch-network/+log/refs/heads/master/src/main/java/com/googlesource/gerrit/plugins/branchnetwork/data/JGitFacade.java
Take some of the unit tests as example: https://github.com/eclipse/jgit/tree/master/org.eclipse.jgit.test/tst/org/eclipse/jgit/api
SubModules: http://stackoverflow.com/questions/13426798/jgit-read-gitmodules http://www.codeaffine.com/2014/04/16/how-to-manage-git-submodules-with-jgit/ https://stackoverflow.com/questions/26090139/jgit-reading-commits-from-a-submodule https://download.eclipse.org/jgit/site/6.7.0.202309050840-r/apidocs/org/eclipse/jgit/submodule/package-frame.html
Diffing: http://stackoverflow.com/questions/12987364/how-to-diff-with-two-files-by-jgit-without-creating-repo
Amend a previous commit: http://stackoverflow.com/questions/4772142/jgit-unstaging-files-removing-files-from-the-index-and-ammending-a-commit
Remove a file from the index: http://stackoverflow.com/questions/4803462/jgit-java-git-library-unstaging-files
Git repo on Amazon S3: http://stackoverflow.com/questions/8744611/git-repository-on-s3-as-origin-not-as-backup http://stackoverflow.com/questions/7031729/publish-to-s3-using-git http://www.fancybeans.com/blog/2012/08/24/how-to-use-s3-as-a-private-git-repository/
CherryPick: http://download.eclipse.org/jgit/site/6.7.0.202309050840-r/apidocs/org/eclipse/jgit/api/CherryPickCommand.html http://stackoverflow.com/questions/18300898/how-to-cherry-pick-a-commit-that-has-more-than-one-parent
More authentication: http://www.lordofthejars.com/2016/09/authenticating-with-jgit.html
How to do a shallow clone (i.e. --depth 1) as soon as https://bugs.eclipse.org/bugs/show_bug.cgi?id=475615 is implemented
Support this project
If you find these snippets useful and would like to support it, you can Sponsor the author

Sources
The following sources were used to build the snippets:

JGit JavaDoc
JGit User Guide
JGit related questions on stackoverflow
AlBlue's Blog: Embedding JGit
JGit main page
What’s the Difference? Creating Diffs with JGit
Other applications using JGit
EGit - Git plugin for Eclipse - https://www.eclipse.org/egit/
Gerrit - A web-based team code collaboration tool - https://www.gerritcodereview.com
Gitiles - A simple Git repository browser - http://code.google.com/p/gitiles/ and https://android.googlesource.com
JGitFS - A userfs implementation which allows to browse branches, tags, committs as a directory structure - https://github.com/centic9/JGitFS
jgitstats - displays repository stats - https://github.com/selesse/jgitstats
git-to-solr - Index git history into a Solr repository - https://github.com/arafalov/git-to-solr
Elegit - GUI client for people who want to learn Git - https://github.com/dmusican/Elegit
Grgit - A wrapper over JGit that provides a fluent API for interacting with Git repositories in Groovy-based tooling - https://github.com/ajoberstar/grgit
jgitver A library to calculate a project semver compatible version from a git repository and its content - https://github.com/jgitver/jgitver
gitective - Investigate Git repositories via filters - https://github.com/kevinsawicki/gitective
RJGit - A JRuby wrapper around the JGit library - https://github.com/repotag/rjgit
KGit - A Kotlin Wrapper of JGit - https://github.com/sya-ri/KGit
Jabylon - A web based translation tool - https://github.com/jutzig/jabylon/ - GitTeamProvider.java
Ruby Build

Contribute
Please note that the list of snippets is not yet complete, probably never will. If you are missing things or have suggestions how to improve or add snippets, please either send pull requests or create issues.

Licensing
Copyright 2013-2023 Dominik Stadler

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
