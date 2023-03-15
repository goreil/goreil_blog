---
layout: post
title: "Common Problems and Solutions"
date: 2023-03-15
categories: general
---
This is a cheatsheet for general common Problems that I had that don't fit anywhere else.
## VMWare
* Enable Shared folder `sudo vmhgfs-fuse .host:/ /mnt/hgfs/ -o allow_other -o uid=1000`

## Linux Bash
* Get only first word of line `awk '{print $1;}'`
### Script usage
{% highlight bash %}
if [ "$#" -ne 1 ]
then
    echo "Usage: $0 arg1"
    exit 1
fi
{% endhighlight %}

### Remove first word of each line
**Problem:** You copy pasted code from a pdf and need to remove the incices

**Solution:**
- Run bash
- Enter: `cut -f 2- -d ' ' file.txt > new_file.txt`
### grep
* Grep without: `grep -v`
* Grep next 20 lines `grep -A20`
* Grep any char `grep .`


## Windows Powershell
- MD5 Checksum: `CertUtil -hashfile %name of file% MD5`. 
- SHA-256 Checksum: `Get-fileHash %Filename`

## Latex

### Figure
Example:

```latex
\begin{figure}
    \includegraphics[width = \linewidth]{Path to graphic}
    \label{fig:label}
    \caption{Caption}
\end{figure}
```

## Python

### Decorators
**Problem:** Some of my functions should always run something else first (e.g. check if key is in ID)

**Solution:**
Use decorators:
```
def pretty_sumab(func):                                                                                     
    def inner(a,b):                                                                                         
        print(str(a) + " + " + str(b) + " is ", end="")                                                     
        return func(a,b)                                                                                    
                                                                                                            
    return inner                                                                                            
@pretty_sumab                                                                                               
def sumab(a,b):                                                                                             
    summed = a + b                                                                                          
    print(summed)                                                                                      
                                                                                                            
if __name__ == "__main__":                                                                                  
    sumab(5,3)   
```
### I need to mock the input and output for unittesting
**Solution:**
In Progress. 

https://code-maven.com/mocking-input-and-output-for-python-testing#:~:text=That%20means%20every%20time%20input%20is%20called%20inside,collects%20any%20text%20typed%20in%20on%20the%20keyboard.

## R

### Comment out selection
Use `CTRL + SHIFT + C`

### Prettify Code
Use `CTRL + I`

### Get name of Variable as string
`deparse(substitute(x))` will return "x"

### Tmux

* Show all sessions `Ctrl+B + S`
* 
eturn to main `Ctrl+B + D`
* Kill all sessions `tmux kill-server`
