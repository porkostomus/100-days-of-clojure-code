Great! It works, let's just make this the new log now.

And I'll upload the new .spacemacs too. Done.

```clojure
(+ 1 4)
```

```clojure
[ 1 2 3 4]
```

```clojure
(def small-map {:a 2 :b 4 :c 8})
(:b small-map)
```

```clojure
(use '(incanter core charts pdf))
;;; Create the x and y data:
(def x-data [0.0 1.0 2.0 3.0 4.0 5.0])
(def y-data [2.3 9.0 2.6 3.1 8.1 4.5])
(def xy-line (xy-plot x-data y-data))
(view xy-line)
(save-pdf xy-line "incanter-xy-line.pdf")
(save xy-line "incanter-xy-line.png")
```

![chart](incanter-xy-line.pdf)
