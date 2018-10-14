- [100 Days of Clojure Code](#sec-1)
  - [Day 29: October 13, 2018](#sec-1-1)
    - [More minesweeper business](#sec-1-1-1)
    - [Hey wait, let's check out Incanter some more!](#sec-1-1-2)
  - [Day 28: October 12, 2018](#sec-1-2)

# 100 Days of Clojure Code<a id="sec-1"></a>

## Day 29: October 13, 2018<a id="sec-1-1"></a>

### More minesweeper business<a id="sec-1-1-1"></a>

Ah&#x2026; so now that we've got this sweet live-coding journal set up, we can get back to the thing I was trying to do in the first place. What was it?

Yes, my Minesweeper board:

```clojure
(def board-width 6)
(def board-height 6)

(for [x (range board-width)
      y (range board-height)]
      [x y])
```

([0 0] [0 1] [0 2] [0 3] [0 4] [0 5] [1 0] [1 1] [1 2] [1 3] [1 4] [1 5] [2 0] [2 1] [2 2] [2 3] [2 4] [2 5] [3 0] [3 1] [3 2] [3 3] [3 4] [3 5] [4 0] [4 1] [4 2] [4 3] [4 4] [4 5] [5 0] [5 1] [5 2] [5 3] [5 4] [5 5])

It totally works! You just have to have a REPL going. Cider-jack-in.

### Hey wait, let's check out Incanter some more!<a id="sec-1-1-2"></a>

I was watching a talk recently about this library and how it's still working great. Who was that? I need to find that again.

Anyway, now that I've stepped into such a tank I might as well kick the tires and see what kind of stuff it can do.

So what is [Incanter](https://github.com/incanter/incanter) anyway? A Clojure-based, R-like statistical computing and graphics environment for the JVM.

That sounds great. Especially all that smartypants statistical computing stuff.

If I were the type of person who dabbled in the likes of whatnot stuff, what would I do?

## Day 28: October 12, 2018<a id="sec-1-2"></a>

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

This code will demonstrate the creation of a basic x-y line plot using the Incanter xy-plot function.

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

![img](./incanter-xy-line.png "A basic x-y line plot")

Try an example: sample 1,000 values from a standard-normal distribution and view a histogram:

```clojure
(use '(incanter core stats charts))
(view (histogram (sample-normal 1000)))
```

Try another simple example, a plot of the sine function over the range -10 to 10:

```clojure
(view (function-plot sin -10 10))
```
![Screenshot](/2018-10-12-193431_1366x768_scrot.png)
![Histogram](/2018-10-13-175035_1366x768_scrot.png)
![Sine Wave](/2018-10-13-175838_1366x768_scrot.png)
