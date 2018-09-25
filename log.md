# 100 Days Of Code - Log

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
