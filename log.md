### Day Something-or-other: October 3, 2018

Still learning re-frame. A funny thing I noticed while fiddling with the todomvc example app was the CSS file:

```
html,
body {
	margin: 0;
	padding: 0;
}

button {
	margin: 0;
	padding: 0;
	border: 0;
	background: none;
	font-size: 100%;
	vertical-align: baseline;
	font-family: inherit;
	font-weight: inherit;
	color: inherit;
	-webkit-appearance: none;
	appearance: none;
	-webkit-font-smoothing: antialiased;
	-moz-font-smoothing: antialiased;
	font-smoothing: antialiased;
}

body {
	font: 14px 'Helvetica Neue', Helvetica, Arial, sans-serif;
	line-height: 1.4em;
	background: #f5f5f5;
	color: #4d4d4d;
	min-width: 230px;
	max-width: 550px;
	margin: 0 auto;
	-webkit-font-smoothing: antialiased;
	-moz-font-smoothing: antialiased;
	font-smoothing: antialiased;
	font-weight: 300;
}

button,
input[type="checkbox"] {
	outline: none;
}

.hidden {
	display: none;
}

#todoapp {
	background: #fff;
	margin: 130px 0 40px 0;
	position: relative;
	box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2),
	0 25px 50px 0 rgba(0, 0, 0, 0.1);
}

#todoapp input::-webkit-input-placeholder {
	font-style: italic;
	font-weight: 300;
	color: #e6e6e6;
}

#todoapp input::-moz-placeholder {
	font-style: italic;
	font-weight: 300;
	color: #e6e6e6;
}

#todoapp input::input-placeholder {
	font-style: italic;
	font-weight: 300;
	color: #e6e6e6;
}

#todoapp h1 {
	position: absolute;
	top: -155px;
	width: 100%;
	font-size: 100px;
	font-weight: 100;
	text-align: center;
	color: rgba(175, 47, 47, 0.15);
	-webkit-text-rendering: optimizeLegibility;
	-moz-text-rendering: optimizeLegibility;
	text-rendering: optimizeLegibility;
}

#new-todo,
.edit {
	position: relative;
	margin: 0;
	width: 100%;
	font-size: 24px;
	font-family: inherit;
	font-weight: inherit;
	line-height: 1.4em;
	border: 0;
	outline: none;
	color: inherit;
	padding: 6px;
	border: 1px solid #999;
	box-shadow: inset 0 -1px 5px 0 rgba(0, 0, 0, 0.2);
	box-sizing: border-box;
	-webkit-font-smoothing: antialiased;
	-moz-font-smoothing: antialiased;
	font-smoothing: antialiased;
}

#new-todo {
	padding: 16px 16px 16px 60px;
	border: none;
	background: rgba(0, 0, 0, 0.003);
	box-shadow: inset 0 -2px 1px rgba(0,0,0,0.03);
}

#main {
	position: relative;
	z-index: 2;
	border-top: 1px solid #e6e6e6;
}

label[for='toggle-all'] {
	display: none;
}

#toggle-all {
	position: absolute;
	top: -55px;
	left: -12px;
	width: 60px;
	height: 34px;
	text-align: center;
	border: none; /* Mobile Safari */
}

#toggle-all:before {
	content: '❯';
	font-size: 22px;
	color: #e6e6e6;
	padding: 10px 27px 10px 27px;
}

#toggle-all:checked:before {
	color: #737373;
}

#todo-list {
	margin: 0;
	padding: 0;
	list-style: none;
}

#todo-list li {
	position: relative;
	font-size: 24px;
	border-bottom: 1px solid #ededed;
}

#todo-list li:last-child {
	border-bottom: none;
}

#todo-list li.editing {
	border-bottom: none;
	padding: 0;
}

#todo-list li.editing .edit {
	display: block;
	width: 506px;
	padding: 13px 17px 12px 17px;
	margin: 0 0 0 43px;
}

#todo-list li.editing .view {
	display: none;
}

#todo-list li .toggle {
	text-align: center;
	width: 40px;
	/* auto, since non-WebKit browsers doesn't support input styling */
	height: auto;
	position: absolute;
	top: 0;
	bottom: 0;
	margin: auto 0;
	border: none; /* Mobile Safari */
	-webkit-appearance: none;
	appearance: none;
}

#todo-list li .toggle:after {
	content: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="-10 -18 100 135"><circle cx="50" cy="50" r="50" fill="none" stroke="#ededed" stroke-width="3"/></svg>');
}

#todo-list li .toggle:checked:after {
	content: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="-10 -18 100 135"><circle cx="50" cy="50" r="50" fill="none" stroke="#bddad5" stroke-width="3"/><path fill="#5dc2af" d="M72 25L42 71 27 56l-4 4 20 20 34-52z"/></svg>');
}

#todo-list li label {
	white-space: pre-line;
	word-break: break-all;
	padding: 15px 60px 15px 15px;
	margin-left: 45px;
	display: block;
	line-height: 1.2;
	transition: color 0.4s;
}

#todo-list li.completed label {
	color: #d9d9d9;
	text-decoration: line-through;
}

#todo-list li .destroy {
	display: none;
	position: absolute;
	top: 0;
	right: 10px;
	bottom: 0;
	width: 40px;
	height: 40px;
	margin: auto 0;
	font-size: 30px;
	color: #cc9a9a;
	margin-bottom: 11px;
	transition: color 0.2s ease-out;
}

#todo-list li .destroy:hover {
	color: #af5b5e;
}

#todo-list li .destroy:after {
	content: '×';
}

#todo-list li:hover .destroy {
	display: block;
}

#todo-list li .edit {
	display: none;
}

#todo-list li.editing:last-child {
	margin-bottom: -1px;
}

#footer {
	color: #777;
	padding: 10px 15px;
	height: 20px;
	text-align: center;
	border-top: 1px solid #e6e6e6;
}

#footer:before {
	content: '';
	position: absolute;
	right: 0;
	bottom: 0;
	left: 0;
	height: 50px;
	overflow: hidden;
	box-shadow: 0 1px 1px rgba(0, 0, 0, 0.2),
	0 8px 0 -3px #f6f6f6,
	0 9px 1px -3px rgba(0, 0, 0, 0.2),
	0 16px 0 -6px #f6f6f6,
	0 17px 2px -6px rgba(0, 0, 0, 0.2);
}

#todo-count {
	float: left;
	text-align: left;
}

#todo-count strong {
	font-weight: 300;
}

#filters {
	margin: 0;
	padding: 0;
	list-style: none;
	position: absolute;
	right: 0;
	left: 0;
}

#filters li {
	display: inline;
}

#filters li a {
	color: inherit;
	margin: 3px;
	padding: 3px 7px;
	text-decoration: none;
	border: 1px solid transparent;
	border-radius: 3px;
}

#filters li a.selected,
#filters li a:hover {
	border-color: rgba(175, 47, 47, 0.1);
}

#filters li a.selected {
	border-color: rgba(175, 47, 47, 0.2);
}

#clear-completed,
html #clear-completed:active {
	float: right;
	position: relative;
	line-height: 20px;
	text-decoration: none;
	cursor: pointer;
	position: relative;
}

#clear-completed:hover {
	text-decoration: underline;
}

#info {
	margin: 65px auto 0;
	color: #bfbfbf;
	font-size: 10px;
	text-shadow: 0 1px 0 rgba(255, 255, 255, 0.5);
	text-align: center;
}

#info p {
	line-height: 1;
}

#info a {
	color: inherit;
	text-decoration: none;
	font-weight: 400;
}

#info a:hover {
	text-decoration: underline;
}

/*
	Hack to remove background from Mobile Safari.
	Can't use it globally since it destroys checkboxes in Firefox
*/
@media screen and (-webkit-min-device-pixel-ratio:0) {
	#toggle-all,
	#todo-list li .toggle {
		background: none;
	}

	#todo-list li .toggle {
		height: 40px;
	}

	#toggle-all {
		-webkit-transform: rotate(90deg);
		transform: rotate(90deg);
		-webkit-appearance: none;
		appearance: none;
	}
}

@media (max-width: 430px) {
	#footer {
		height: 50px;
	}

	#filters {
		bottom: 10px;
	}
}
```

The reason I pasted all that was to make a point. And that I don't know how to include the expandable-code-snippet-thingy. Maybe I'll figure that out tomorrow.

The funny part, I thought, was how responsible this is for the look and feel of the app. I don't think it is even mentioned in the docs, because it really has nothing to do with how re-frame works, and it probably came from somewhere else anyway. Here it is with and without it:

![Todomvc Screenshot](/2018-10-03-175127_1366x768_scrot.png)

![no css](/2018-10-03-175549_1366x768_scrot.png)

So where to learn how to do good CSS? I suppose the docs on MDN would be a good start. Looking for any recommendations here. My new career is in UI design, so I want to build a solid foundation.

Another thing I've been doing lately is setting up spacemacs. Anyone know a good guide on that? Just kidding, I'm using [jr0cket's](https://practicalli.github.io/spacemacs/)!

### Day 15: September 29, 2018

Finished up the script for the rest of the re-frame example application tutorial video, but I've gotta move straight on to the [todomvc](https://github.com/Day8/re-frame/tree/master/examples/todomvc) app.

Bring it on.

### Day 14: September 28, 2018

So now that I know what I'll be doing for work, I can refocus my learning trajectory to more UI design type stuff. And learning re-frame! Since my first video left off at the 3rd "domino", the second will cover the next 2. I've already prepared the script and done the audio. 

### Day 13: September 27, 2018

Today I've been in a state of utter shock because I had an interview this morning and...

I got the job... and it's in England! Doing re-frame and Datomic!

So soon I'll be having some *serious* Clojure work to do...

In the meantime, here's a [juxt](https://porkostomus.gitlab.io/posts-output/2018-09-27-Just-Juxt-44/).

### Day 12: September 26, 2018

Working on my [minesweeper game](https://porkostomus.gitlab.io/posts-output/2018-08-27-minesweeper/) in Reagent, rewriting the mine-detector that I had in [tsweep](https://github.com/porkostomus/tsweep) which is really funny because that was my very first Clojure project.

Here's my new mine-detector. It's just a set of predicates for whether there's a mine in any of the 8 surrounding squares: 

```
(defn mine? [x y]
  (= 1 (get (:matrix @app-state) [x y])))
(defn left? [x y]
  (mine? (dec x) y))
(defn right? [x y]
  (mine? (inc x) y))
(defn top? [x y]
  (mine? x (inc y)))
(defn bottom? [x y]
  (mine? x (dec y)))
(defn top-left? [x y]
  (mine? (dec x) (inc y)))
(defn top-right? [x y]
  (mine? (inc x) (dec y)))
(defn bottom-left? [x y]
  (mine? (dec x) (dec y)))
(defn bottom-right? [x y]
  (mine? (inc x) (dec y)))
```

Compared to the old one, which was represented with a single vector (shown here just for the lulz):

```
(defn left [coll]
  (loop [board coll square (dec (count coll))]
    (if (> 0 square)
         board
        (if (not= 0 (rem square rows))
            (recur (assoc board square
			         (conj (get board square)
					       (dec square)))
		    (dec square))
        (recur board (dec square))))))

(defn right [coll]
  (loop [board coll square (dec (count coll))]
    (if (> 0 square)
         board
        (if (not= 0 (rem (inc square) rows))
            (recur (assoc board square
                     (conj (get board square)
                       (inc square)))
            (dec square))
        (recur board (dec square))))))

(defn top [coll]
  (loop [board coll square (dec (count coll))]
    (if (> 0 square)
         board
        (if (< rows (inc square))
            (recur (assoc board square
              (conj (get board square)
                (- square rows)))
            (dec square))
        (recur board (dec square))))))

(defn bottom [coll]
  (loop [board coll square (dec (count coll))]
    (if (> 0 square)
         board
        (if (> (- (* rows rows) rows) square)
          (recur (assoc board square
                   (conj (get board square)
                         (+ rows square)))
          (dec square))
        (recur board (dec square))))))

(defn top-left [coll]
  (loop [board coll square (dec (count coll))]
    (if (> 0 square)
         board
        (if (and (< rows (inc square))
                 (not= 0 (rem square rows)))
            (recur (assoc board square
                     (conj (get board square)
                       (dec (- square rows))))
            (dec square))
    (recur board (dec square))))))

(defn top-right [coll]
  (loop [board coll square (dec (count coll))]
    (if (> 0 square)
         board
        (if (and (< rows (inc square))
                 (not= 0 (rem (inc square) rows)))
            (recur (assoc board square
              (conj (get board square)
                (inc (- square rows))))
            (dec square))
    (recur board (dec square))))))

(defn bottom-left [coll]
  (loop [board coll square (dec (count coll))]
    (if (> 0 square)
         board
        (if (and (> (- (* rows rows) rows) square)
                 (not= 0 (rem square rows)))
            (recur (assoc board square
                     (conj (get board square)
                       (dec (+ rows square))))
            (dec square))
        (recur board (dec square))))))

(defn bottom-right [coll]
  (loop [board coll square (dec (count coll))]
    (if (> 0 square)
         board
        (if (and (> (- (* rows rows) rows) square)
                 (not= 0 (rem (inc square) rows)))
            (recur (assoc board square
                     (conj (get board square)
                       (inc (+ rows square))))
            (dec square))
        (recur board (dec square))))))
  ```

I find it quite hilarious, personally. But at the time, it seemed a miracle that I pulled it off at all.

Bonus: It will also come in handy for a Sudoku board.

### Day 11: September 25, 2018

Getting started with [Datomic Ions](https://docs.datomic.com/cloud/ions/ions-tutorial.html). And I *really* mean getting started, with a fresh Linux install. The [AWS CLI tool](https://docs.aws.amazon.com/cli/latest/userguide/installing.html) uses Python, and I haven't even installed `pip` yet, so that's where I'm at:

```
$ sudo apt install python-pip
```

```
$ pip install awscli --upgrade --user
```

```
$ aws --version
aws-cli/1.16.20 Python/2.7.15rc1 Linux/4.15.0-34-generic botocore/1.12.10
```

So far so good.

### Day 10: September 24, 2018

Mentored a whole bunch of exercisms. Mostly easy ones like Armstrong Numbers and Two-Fer. Could definitely use more active mentors because they tend to pile up if I start slacking, and I feel bad because no one should have to wait several days just to have their solution looked at.

Today's [Just Juxt](https://porkostomus.gitlab.io/posts-output/2018-09-24-Just-Juxt-41/) was a fun one too.

### Day 9: September 23, 2018

**Link to work:**

* [re-frame tutorial Part 1](https://www.youtube.com/watch?v=Xo6W300s1Xs&t=183s)

### Day 8: September 22, 2018

**Today's Progress**: Making a video tutorial out of the re-frame [simple example app](https://github.com/Day8/re-frame/blob/master/docs/CodeWalkthrough.md). Using [soundoftext](https://soundoftext.com/) for the narration,
and paraphrasing the readme to say just enough to explain what's going on. I began right with installing Java and Leiningen,
cloning the repo and starting the app, recording my screen in OBS. Once I get enough video footage and audio samples I'll start editing them down in Kdenlive.

When I'm done the finished video will likely be something along the lines of [these](https://www.youtube.com/playlist?list=PLU4xPIn8mcE69QF41HoFaHxw2Whk3h7PQ).

### Day 7: September 21, 2018

**Today's Progress**: A big reason I'm doing this challenge is to prepare myself for a job using Clojure. During a recent interview, I was asked if I had ever used [re-frame](https://github.com/Day8/re-frame). On my resume I have several small projects using [Reagent](http://reagent-project.github.io/), but nothing larger.

I explained myself based on the common advice I've heard regarding the Reagent vs. re-frame debate, which I'll simplify as something like:

>Use re-frame if your app is complicated enough to need it, otherwise use Reagent.

So for my personal stuff, the answer was easy. Nothing that I made had enough complexity to require anything but the most basic UI elements.

And that's what we're about to change.

I currently have an [app](https://porkostomus.github.io/elements/) for learning the periodic table of elements. I want to build it up into something that demonstrates different chemical compounds and how they are composed.

The best part is how well documented the framework is, and how many people I've heard express how nice the code is and how worthwhile it will be to learn it. So I'm gonna take my time, and do some screencasts along the way. That way others will be able to learn as well, but my selfish reason is that I've found that I learn best by going through the process of presenting the material as if I were to teach it.

For some inspiration... here is the *entire* example re-frame app:

```
(ns simple.core
  (:require [reagent.core :as reagent]
            [re-frame.core :as rf]
            [clojure.string :as str]))

(defn dispatch-timer-event []
  (let [now (js/Date.)]
    (rf/dispatch [:timer now])))

(defonce do-timer (js/setInterval dispatch-timer-event 1000))

(rf/reg-event-db
  :initialize
  (fn [_ _]
    {:time (js/Date.)
     :time-color "#f88"}))

(rf/reg-event-db
  :time-color-change
  (fn [db [_ new-color-value]]
    (assoc db :time-color new-color-value)))

(rf/reg-event-db
  :timer
  (fn [db [_ new-time]]
    (assoc db :time new-time)))

(rf/reg-sub
  :time
  (fn [db _]
    (:time db)))

(rf/reg-sub
  :time-color
  (fn [db _]
    (:time-color db)))

(defn clock []
  [:div.example-clock
   {:style {:color @(rf/subscribe [:time-color])}}
   (-> @(rf/subscribe [:time])
       .toTimeString
       (str/split " ")
       first)])

(defn color-input []
  [:div.color-input
   "Time color: "
   [:input {:type "text"
            :value @(rf/subscribe [:time-color])
            :on-change #(rf/dispatch [:time-color-change (-> % .-target .-value)])}]])

(defn ui []
  [:div
   [:h1 "Yo dawg, it is now"]
   [clock]
   [color-input]])

(defn ^:export run []
  (rf/dispatch-sync [:initialize])
  (reagent/render [ui]
                  (js/document.getElementById "app")))
```

It shows the time on the screen, updating every second, with an input field letting you pick the color.

See the docs for the version with all the comments, which someone did such a great job on only for me to edit them back out so that I can show how tiny the code is. This is a complete framework!


### Day 6: September 20, 2018

**Today's Progress**: Just Juxt #37: Re-implement map (4clojure #118), Make a Lisp Part 2

**Thoughts:** I wanted to cut to the chase and get right into the interpreter, using self-hosted Clojurescript and none of that low-level readline business. More along the lines of the one in SICP. Eric Normand shared one of the most basic ones I've seen on the [Apropos show](https://youtu.be/WFWZlbpZ4Qg), so I figured that would be a good place to start.

**Link to work:**

* [Just Juxt #37](https://porkostomus.gitlab.io/posts-output/2018-09-20-Just-Juxt-37/)
* [Make a Lisp Part 2](https://porkostomus.gitlab.io/posts-output/2018-09-20-day-6/)

### Day 5: September 19, 2018

**Today's Progress**: Just Juxt #36: The Balance of N (4clojure #115), Make a Lisp in Clojure

**Thoughts:** For awhile I've been looking at the [Make a Lisp](https://github.com/kanaka/mal) project and fiddled around with various implementations, particularly C and Bash, but for this challenge decided to do it in Clojure.

**Link to work:**

* [Just Juxt #36](https://porkostomus.gitlab.io/posts-output/2018-09-19-Just-Juxt-36/)
* [Make a Lisp in Clojure](https://porkostomus.gitlab.io/posts-output/2018-09-19-day-5/)

### Day 4: September 18, 2018

**Today's Progress**: Just Juxt #35: Game of Life (4clojure #94)

**Thoughts:** Today while working on ctrain (adding more problems to it) I started getting some very perplexing behavior, when I edited a file that was `slurp`ed in it was still printing the same wrong file. I renamed it, and still no change. I tried to `slurp` the new name, and got an error. It truly made no sense.

Eventually I realized that my terminal was still SSH'd into my other machine.

I mentored numerous [Exercism](https://exercism.io/) solutions today, because one of the most active mentors is on vacation so I've had to up my game considerably. Lots of new folks doing the first exercises! I learn a lot from reading them and picking them apart, and try to give very careful feedback, because I realize that I've taken the responsibility of assisting people in their first exposure to Clojure!

And today's Just Just was a fun one too, Conway's Game of Life!

**Link to work:**

* [Just Juxt #35](https://porkostomus.gitlab.io/posts-output/2018-09-18-Just-Juxt-35/)
* [ctrain](https://github.com/porkostomus/ctrain)
* [Exercism](https://exercism.io/)

### Day 3: September 17, 2018

**Today's Progress**: Just Juxt #34: Read Roman numerals (4clojure #92)

**Thoughts:** Fun fact: [Subtractive notation](https://en.wikipedia.org/wiki/Subtractive_notation) was not the original pattern for Roman numerals. I wonder how much this change had to do with making clock faces appear more balanced.

Today was very exciting for me because yesterday's challenge was completed... by a fellow participant! I received a [pull request](https://github.com/porkostomus/ctrain/commit/5fadbea52f3da219fbfd81fe70d92b1b6501439c) from [kazesberger](https://github.com/kazesberger) addressing the issue that I spoke of yesterday. Now that the app functions properly, I can work on expanding it. The dataset only included the first 87 problems, the rest I believe were submitted over time, which I plan to do as well, and then maybe add problems from other sources for my own big custom learning app. 

I also did some work on [Cryogen Now!](https://gitlab.com/cryogenweb/cryogenweb.gitlab.io), a forkable template I made so that people can get a Clojure static site running on Gitlab Pages in just a few clicks. It took me way too long to get the configuration right, and don't want anyone to ever have to go through that. Github has [Jekyll Now](https://github.com/barryclark/jekyll-now) which uses Ruby, and now we've got one too!

**Link to work:**

* [Just Juxt #34](https://porkostomus.gitlab.io/posts-output/2018-09-17-Just-Juxt-34/)
* [ctrain](https://github.com/porkostomus/ctrain)
* [Cryogen Now!](https://gitlab.com/cryogenweb/cryogenweb.gitlab.io)

### Day 2: September 16, 2018

**Today's Progress**: Published Just Juxt #33: Graph Connectivity (4clojure #91)

**Thoughts:** I wrote a [blog post](https://porkostomus.gitlab.io/posts-output/2018-09-16-day-2/) about my ctrain app that I started awhile back and got stuck. I did this in the spirit of public struggling - I spend so much time looking at other people's solutions that I end up spending proportionally less on figuring them out myself - and found myself trying to do it again with this challenge. So I wanted to do something that I knew I didn't know how to solve. Sure, it feels like a bit of a copout using something that I started 9 months ago, but hey, there are still 98 more days left of this challenge! I could spend a day revisiting each one of my projects, and still have most of the days left for trying new things. I feel like it's utilizing the challenge for a good purpose.

Though I couldn't figure out how to fix a certain bug, the program I made does work! In fact, I made [several Clojure tutorial videos](https://www.youtube.com/watch?v=fdB5dhPXiXc&list=PLU4xPIn8mcE69QF41HoFaHxw2Whk3h7PQ) with it.

**Link to work:**

* [Just Juxt #33](https://porkostomus.gitlab.io/posts-output/2018-09-16-Just-Juxt-33/)
* [ctrain](https://github.com/porkostomus/ctrain)

### Day 1: September 15, 2018

**Today's Progress**: Published Just Juxt #32: Cartesian Product (4clojure #90)

**Thoughts:** I decided to merge my existing project into the challenge, since I've been doing the 4clojure problems for the past month for Just Juxt. However, in the spirit of 100 Days Of Code, I will be extending the amount of time I spend on them. The format I've been using is a Cryogen blog with KLIPSE snippets, which I find to be very effective for both working on the exercises as well as presenting them. Each article includes a cljs.test framework for the problem, and having the code actually running in the browser is the best way to know that it works!

I also enjoy producing Clojure tutorials and stuff on my [YouTube channel](https://www.youtube.com/bobbytowers), so if something seems particularly inspiring during the challenge, I'll post a video on it!

**Link to work:** [Just Juxt #32](https://porkostomus.gitlab.io/posts-output/2018-09-15-Just-Juxt-32/)
