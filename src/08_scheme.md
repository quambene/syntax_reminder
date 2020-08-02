# Scheme

### Prefix notation

```lisp
;;; Combination
(+ 5 64)

;;; Fundamental forms
define
lambda
set!
```

### Print

```lisp
(write-line "hello world")
```

### Variables

```lisp
(define pi 3.14159)

(define string "my string")

;;; Local state variables
(set! <name> <new-value>)
```

### Data types

```lisp
;;; List
(list 1 2 3 4)
```

### Procedure

```lisp
(define (square x) (* x x))

;;; Lambda
(lambda (x) (+ x 4))
```
