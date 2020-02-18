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
