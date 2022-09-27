ohm-editor appears to go into an infinite loop:
to repeat:

this grammar:
```
SSL {
Main = Def+

Def = name "=" number ";"

name = letter alnum*
number =
  | "-" digit+ -- negative
  |     digit+ -- positive
  
comment =
  | "{" dontcareChar* "}" -- nested
  | dontcareChar*         -- base
  
dontcareChar = ~"}" ~"{" any
space += comment
}
```
this input:
```
x
```

(The above grammar is under development and is probably buggy, but, Ohm-Editor shows red "no match" and no parse).
