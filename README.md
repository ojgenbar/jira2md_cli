# jira2md CLI Tool

Based on these repos:
* https://github.com/FokkeZB/J2M
* https://github.com/kylefarris/J2M

### Usage
```
$ j2m [--toM|--toJ] [--stdin] $filename 

Options: 
--toM, -m:    Treat input as jira text and convert it to Markdown 
--toJ, -j:    Treat input as markdown text and convert it to Jira 
--stdin:      Read input from stdin. In this case the give filename is ignored 
```

#### Usage Example
```bash
# convert notes to jira markup and copy it to the clipboard (mac)
j2m --toJ notes.md | pbcopy

# retrieve some file in jira markup and save it as markdown
curl http://someserver.com/jira.txt | j2m --toM --stdin > notee.md
```

Works with lists and other (not ideal):
```
$ cat test.md | j2m --toJ --stdin
h1. First
h2. Second

bq. Citation

{code:python}
h1. Code

import antigravity

antigravity.enable()
{code}

# Complicated list
## adsfdasf
## adsfdasf
**** sadfasd
**** 345
          {code:bash}
          sudo -i
          {code}
# asdasdasdasf
** sadas
# dqwrfqwrf
```