`--pretty=oneline`
	Shows each commit in one line

`--pretty=short/full/fuller`
	Determines the length of the output (verbosity)
	
`--pretty=format: ...`
	Specify output format
```git
$ git log --pretty=format:"%h - %an, %ar : %s"
6fec8fd - Eve, 25 minutes ago : added hello_world.py
65c7fa2 - Eve, 4 weeks ago : modified hello_world.c
db07392 - Eve, 4 weeks ago : commiting: README.txt, hello_world.c

```

|Specifier|Description of Output|
|---|---|
|%H|Commit hash|
|%h|Abbreviated commit hash|
|%T|Tree hash|
|%t|Abbreviated tree hash|
|%P|Parent hashes|
|%p|Abbreviated parent hashes|
|%an|Author name|
|%ae|Author email|
|%ad|Author date (format respects the --date=option)|
|%ar|Author date, relative|
|%cn|Committer name|
|%ce|Committer email|
|%cd|Committer date|
|%cr|Committer date, relative|
|%s|Subject|