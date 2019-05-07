# bash-profile


added by Anaconda3 4.4.0 installer

`export PATH="/Users/asifontes/anaconda/bin:$PATH"`

added by self

#create 'chrome' command to open .html files

`alias chrome="open -a 'Google Chrome'"`

```
cram() {
  echo "let's get crammin' "
  open -a 'Google Chrome' $1
  atom $1
  echo "consider it crammed"
}
```

`alias ll='ls -FGlAhp'`                       # Preferred 'ls' implementation

`cd() { builtin cd "$@"; ls; }`               # Always list directory contents upon 'cd'

`alias ...='cd ../../'`                       # Go back 2 directory levels
`alias f='open -a Finder ./'`                 # f:            Opens current directory in MacOS Finder

#   lr:  Full Recursive Directory Listing
#   ------------------------------------------
`alias lr='ls -R | grep ":$" | sed -e '\''s/:$//'\'' -e '\''s/[^-][^\/]*\//--/g'\'' -e '\''s/^/   /'\'' -e '\''s/-/|/'\'' | less'`

#   extract:  Extract most know archives with one command
```
extract () {
    if [ -f $1 ] ; then
      case $1 in
        *.tar.bz2)   tar xjf $1     ;;
        *.tar.gz)    tar xzf $1     ;;
        *.bz2)       bunzip2 $1     ;;
        *.rar)       unrar e $1     ;;
        *.gz)        gunzip $1      ;;
        *.tar)       tar xf $1      ;;
        *.tbz2)      tar xjf $1     ;;
        *.tgz)       tar xzf $1     ;;
        *.zip)       unzip $1       ;;
        *.Z)         uncompress $1  ;;
        *.7z)        7z x $1        ;;
        *)     echo "'$1' cannot be extracted via extract()" ;;
         esac
     else
         echo "'$1' is not a valid file"
     fi
}
```
