When I was growing up, my interests spanned various, seemingly unrelated fields. I loved maths as much as I loved history. I aimed to be a Renaissance man -a polymath-, that excelled at multiple fields. This turned out to be an arduous task and suddenly I faced the danger of being a jack of all trades, master of none.

在我的成长过程中，对许多领域的知识都很有兴趣，甚至有些是风马牛不相及的。我热爱数学，却也耽于历史。我曾志在成为一个文艺复兴式的人——一个博文广记的学者，在数个领域都佼佼有成。这个理想在后来被验证为是通往一条险峻的道路。我在忽然间意识到，自己恐怕会成一个博而不精，事事浅尝辄止而未有所得的庸人。

I started thinking about specializing in certain fields so that I could at least be “a jack of all trades, master of some” man, if not a Renaissance one. How could I specialize in a field while retaining the vast knowledge required to do software development?

我开始考虑让自己能在某个具体领域有所专擅，从而使自己在无法成为一个文艺复兴式大神时，至少可以是一个“事晓大略，专务精熟”的人。我是如何在软件开发这个要求复杂知识储备的行业中进行领域的具体化的呢？

In this post, I outline the techniques and resources I used to become a good JavaScript developer, based on my experience in the last 5 years.

在这篇博文中，我将列举自己在成为一个不错的JS开发者的五年时光中所用到的资源与技术。

Most of the web developers nowadays face the same problem: They have to excel at multiple different fields, from databases to backend architecture to frontend user interfaces to polishing these UIs with good knowledge of CSS.

最近，大多数网页开发者都面临着同样的问题：他们不得不去胜任多个领域的工作，从数据库建设到后端架构开发，从后端架构开发到前端用户界面设计，从前端用户界面设计到利用CSS进行UI打磨。

Read Books

阅读

The first and foremost observation is that you have to make a dedicated effort to excel. It is true that you can get bits and pieces while doing a half hearted effort, for example by reading some blog posts from time to time, and it will seem easier because the initial time investment will be lower. Such an education will cost you more time in the long term than a dedicated and distilled learning process. The answer to this dilemma is easy: Read books.

Books are what our civilization stands on the shoulders of. Written word is how we pass knowledge from generation to generation, in a concentrated form. One problem with becoming an expert on Web technologies is that you have to learn when to stay away from the Web itself. Web itself presents a chaotic and distracting medium for learning stuff, so the first suggestion I will make is to read books on the subject matter.

For JavaScript, start with the following books: JavaScript the Good Parts is like the bible of JavaScript. It is an old one, but still the best for starting out. JavaScript: the Definitive Guide is also a must have, though you will probably keep it as a reference. jQuery’s principle author John Resig’s Secrets of the JavaScript Ninja is also notable. If you are looking for good (and freely available online) books, take a look at JavaScript Allongé, You Don’t Know JS and Eloquent JavaScript (see also its annotated version here). These can be purchased as ebooks or dead tree format. Also, not a book but Mozilla’s Developer Network has a good guide on JavaScript.

Learn, Use and Read Libraries

The next most important step is getting to know the libraries. If the books teach you how to read a language, the libraries teach you how to speak it. There are two important things you can do with libraries: use them and read their source code.

For using libraries, get acquainted with the following: jQuery, Backbone, underscore and one of React, Angular or Ember. This is not to say you have to use these libraries, but any decent JavaScript developer should at least have some experience (good or bad) with these libraries.

The second important thing for improving your JavaScript skills is to read these libraries’ source codes. Out of these, I highly suggest Backbone and underscore’s source codes, as they are written beautifully. Reading and understanding underscore will improve your functional programming skills. Another good library for reading the source code, as recommended to me by several developers is mootols (I personally don’t have any experience using mootools or reading it, just conveying the message.)

Understanding others in the list, such as React, Ember etc. might be harder, but well worth the effort. At least skim through the source code of other libraries to see how to structure your code base and try to discover some patterns. Other notable libraries for using and reading the source code include d3, highcharts, moment.js.

Do Exercises and Ask Questions to Yourself

The next step for becoming a good JavaScript developer is to do a lot of exercises. Ideally, these exercises will be focusing not on DOM, but the language, so make sure to have a test harness that can run in node.js. Do small, but plenty exercises in node.js. Do katas and go through different ways of using JavaScript: closures, prototypes, array-extras (map, filter) etc. While doing the exercises, always have a list of fundamental ideas in JavaScript in your mind.

A friend of mine, Armagan, who is an excellent JavaScript programmer and teacher uses the book Pro JavaScript Design Patterns in his lectures, so this book is worth checking out.

Try to answer questions such as: How does prototypal inheritance work? What defines a closure? How does the meaning of this keyword change? How does one use apply/bind/map/filter/call? Gather a list of common source points JavaScript developers face and try to explain it in your own words. Explaining these concepts to another person in written or verbal form will help improve your skills immensely. While doing the exercises, try to go over those where you discover “What if?” scenarios. For example, “What is the meaning of “this” if I use bind twice? How does jQuery make sure that the this keyword refers to the jQuery object and not the global object? How does this library achieve a certain feature?” are some common questions you should be asking yourself.

Learn the standards

The next step is getting to know more about the EcmaScript standards. Grab a copy of the latest EcmaScript standard and try reading it. Doing this, also try to learn more about the upcoming features in JavaScript, as brought in ES6 and ES7. There have recently been a flux of new features like promises, modules, generators, comprehensions and again, reading the standard, along with a dedicated book such as Nicholas Zakas’ (Understanding EcmaScript 6) or Dr. Axel Rauschmayer’s ES6 books (Exploring JS) will help. The road to expertise is through learning the standard from the principal source and discovering the new additions to the language.

Use Resources on the Web

I mentioned earlier the dangers of using the Web to learn about the Web, so my final recommendations will entail how to get the best out of resources on the Web. Hacker News is a good source, however tracking it constantly will usually cost more time than needed, as the signal to noise ratio will be low. Instead, aim for weekly digests such as JavaScript Weekly. Over time, you will see which libraries or techniques are getting traction. On Twitter, try to find influential JavaScript developers. This list of 33 JavaScript developers to follow by Tutsplus is a good start. Other resources on the web include some blogs such as Toptal Blogs, Rebecca Murphey’s blog (see also A Baseline for Front-End [JS] Developers: 2015 if you are interested in this blog post), Nicholas Zakas’ blog. (Email me if you have pointers to other good blogs and I’ll include it in this list.)

Another important resource on the Web is conference videos and educational videos. For conferences, JSConf series are high quality. For educational videos, I strongly suggest Pluralsight, as they have an army of experienced developers preparing high quality courses. (no affiliation with Pluralsgiht)

TL;DR Version

Start with reading books as they give you distilled information.
Learn fundamental libraries such as jQuery, underscore, Backbone; but also read their source codes.
Do exercises and try to explain common JavaScript concepts such as inheritance in your own words. Give lectures and talks on these subjects.
Read through the new versions of the standard, and start using the latest additions to the language.
Follow the web resources in batch, through digests or blogs which you frequent once a week or conference and educational videos.
Conclusion

Constantly repeating these and making lots of projects will improve your JavaScript skills immensely. Always keep in mind to make a dedicated effort and you can hopefully become an expert after a few years. I consider myself a good JavaScript programmer, and I still have a long way to expertise and these are the techniques I’m following in my journey. Feel free to reach out to me for feedback and corrections at ustun@ustunozgur.com

And finally, as Ustun Ozgur Software, we are looking for talented JavaScript developers in Istanbul, Turkey. See our company website for job openings.

Happy learning,

Ustun

If you have read so far, consider following me on Twitter at @ustunozgur

Interested in React.js and Advanced JS Training? See my training/workshop site

Thanks to Engin Arslan for initiating this discussion with me.

Discuss this on HackerNews