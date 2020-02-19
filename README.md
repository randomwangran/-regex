* Thompson NFA is so fast!

https://swtch.com/~rsc/regexp/regexp1.html


* https://emacs-china.org/t/topic/11860/4

  
		("f\\(['\"]\\{1,3\\}\\)\\([^\\1]+?\\)\\1"
		(
		 ;; "f\\(['\"]\\{1,3\\}\\)\\([^\\1]+?\\)\\1"
		 "f\\(['\"]\\{1,3\\}\\)\\(.+?\\)\\1"
     
     
     
     Could you please clarify what you want to do past.

What this new regexp improve the previous version?

Thanks for you inspiration.


> The previous version would not match an f-string like f'some {Arg} \n {arg2}'. It was also not doing what I thought. I thought [^\1] would be any character not matching the first group, but in fact it means do not match a \ or 1. The new regexp works like it should to fontify {arg}s inside f-strings.


I am sorry, I am new to regexp. [And I am learning this with my friends
who speed chinese.](https://emacs-china.org/t/topic/11860/9)

I can not understand it right away.

I use this to understand it:

`(re-search-forward "f\(['"]\{1,3\}\)\([^\1]+?\)\1" nil t)`

I am guessing you are try to find this string

`lkjciidsofwopvqi-something`

in this string long string

`flkjciidsofwopvqi-something`

But I got:

```lisp
Debugger entered--Lisp error: (invalid-read-syntax ") or . in a vector")
  read(#<buffer *scratch*>)
  elisp--preceding-sexp()
  elisp--eval-last-sexp(nil)
  eval-last-sexp(nil)
  funcall-interactively(eval-last-sexp nil)
  call-interactively(eval-last-sexp nil nil)
  command-execute(eval-last-sexp)
```

Looks like I am missing some context here.




- matches two or more blank lines in sequence.

` (re-search-forward "^\n\\{2,\\}")`


- match TODO

`(re-search-forward "\\[TODO\\](\\([^\\)]+\\))" nil t)`

- match UUID

`(re-search-forward "PDFNAME::\\([a-zA-Z0-9 \.\_\,\-]+\\)\.pdf - " nil t)`

- match page number

`(re-search-forward "PAGENUM::\\([0-9]+\\)::END" nil t)`

- match secrete

`(re-search-forward (concat arg "::\\(.*\\)"))`

- match @dfn{xxx}

`(re-search-forward "@dfn{\\([^}]+\\)}" nil t)`

- match end sentence

`(re-search-forward "[\.,;:!\?]" end t)`


* python
** white space
https://gitlab.kwant-project.org/kwant/kwant/blob/master/check_whitespace
