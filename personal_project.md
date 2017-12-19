# DevMountain Phoenix Personal Project Rubric

> This is a work in progress and will change before your personal project begins.

The intent of a personal project is to build something using technologies you have been taught, as well as to learn new ones on your own.

This rubric serves to guide students and mentors in the requirements. Wherever there is ambiguity on what the requirements are, focus on the goal of learning and preparing for the real world.

## Requirements

Always required:

* Full stack CRUD site
    * Create/POST
    * Read/GET
    * Update/PATCH
    * Delete/DELETE
    * Each of the above must manipulate the database (except GET).
* 1 foreign key and a JOIN statement
    * Yes, you need a JOIN. Usually this means you'd be displaying a list somewhere. Some sites, with the small scope of intended functionality, don't lend themselves to such a list with the database's data. A simple workaround for this is to create an admin page which displays the data. Such a page can even be public if it doesn't contain sensitive information; perhaps don't have a link to the admin page on the site itself but tell users in the README or a private email how to view it (e.g. by visiting #/admin). An example of such a list might be, for a store, all orders for all users. Or what about users without an order (use an outer join)?

You also must use technologies to gain points. The technologies and their associated points are listed here, with descriptions farther below.

| Category                                    | Name                           | Points        |
|---------------------------------------------|--------------------------------|---------------|
| [Testing](#testing)                         |                                |               |
|                                             | Unit Tests                     | 30            |
|                                             | Endpoint Tests                 | 20            |
|                                             | E2E Tests                      | 40            |
| [Build tools](#build-tools)                 |                                |               |
|                                             | Sass/Less                      | 10            |
|                                             | Webpack/Browserify             | 20            |
| [Planning and Design](#planning-and-design) |                                |               |
|                                             | Domain Registration            | 10            |
|                                             | Defined MVP/API                | 10            |
|                                             | Responsive                     | 20            |
| [Hosting](#hosting)                         |                                |               |
|                                             | Zeit, Heroku (easy solutions)  | 0             |
|                                             | Digital Ocean                  | 10            |
| [Custom](#custom)                           |                                |               |
|                                             | Instructor approves early on   | ?             |
| [Techs](#techs)                             |                                |               |
|                                             | 3rd Party API                  | 10 per/20 max |
|                                             | Redux                          | 10            |
|                                             | Stripe                         | 20            |
|                                             | s3                             | 10            |
|                                             | Sockets                        | 20            |
|                                             | ChartJs                        | 10            |
|                                             | D3                             | 20            |
|                                             | Other? (approved early on)     | 10-30         |
|                                             | Custom/Styled Auth0 login form | 10            |
|                                             | NodeMailer/Sendgrid            | 10            |
|                                             | Twilio                         | 10            |
|                                             | CSS in JS                      | 10            |
| [Presentation](#presentation)               |                                |               |
|                                             | Mentions Tech                  | 10            |
|                                             | Uses Time Effectively          | 10            |
| **Total points required**                   |                                | **70**        |

## Definitions
### Testing
#### Unit Tests
(Daniel)
#### Endpoint Tests
(Daniel)
#### E2E Tests
(Daniel)
### Build Tools
#### Less or Sass

Sass and Less are both CSS preprocessors, meaning they extend the CSS language, adding features that allow variables, mixins, functions, and many other techniques. They are a way to simplify your CSS workflow, making development and maintenance tasks easier. Though they are both essentially doing the same job, Sass is used far more in the industry and it is the recommended one if you choose to use a CSS preprocessor.

Gotchas: 
* You might hear the term Sass/SCSS, that’s because they are (for the most part) the same thing.
* Sass/Less are tools that you can become very reliant on because of the simplicity that they bring to your development. Though it is something that you can simply implement in every project you create moving forward, it is important that you don’t forget/neglect the rules of basic CSS.
* Getting a preprocessor up and running might be a headache your first time around. Here is a great guide that will make set up a breeze. https://github.com/missyjeanbeutler/sass-demo

#### Webpack or Browserify
Webpack is the build tool that powers `create-react-app`. Behind the scenes, `create-react-app` uses Webpack to perform build steps that eventually results in the `bundle.js` file your website uses. There is also the `webpack-dev-server` that is used to run the site in development mode, which allows for file watching and auto-refreshing.
### Planning and Design
(Be sure to explain project-plan.pdf)
#### Domain Registration

Domain Registration is the process for registering a domain name, which identifies one or more IP addresses with a name that is easier to remember and use in URLs to identify particular web pages. There are many domain registrars out there and not every choice will be the perfect fit in every way, so do your own research. That being said some of the more popular registrars are: namecheap, bluehost, HostGator and GoDaddy.

Gotchas:
* Be aware that registering for a domain name isn’t free. There are many sites that will offer a hosting package that will then give you a free domain name. Take “free” with a grain of salt. It is often cheaper to host elsewhere then wait for a promotion (they happen very often on GoDaddy) where you can register a domain name for $0.99/year.
* Speaking of hosting, that is something you must do before you start the process of hooking up to a domain name.
* It is highly recommended that get the domain privacy package when registering for a domain name. That will protect against identity theft, prevents domain-related spam, and deters hijackers.
* If you are hosting with Zeit, you must upgrade your Zeit account to the paid version to use a custom domain name.


#### Defined MVP and API
(Aaron)
#### Responsive
Responsive design means that your application looks good regardless of the size of the screen.  Whether the user is using your site from their laptop or phone it should keep an effective layout and proper functionality.  This is done using response CSS, media queries, inline-styling, and various other strategies.  One main strategy is mobile-first design, meaning design your site for a phone sized screen first and build it out for larger screen sizes.

Gotchas: Layout and Design take alot of time.  Making your site look good in multiple different layouts will take even more time. BUT if there's a chance a employer may visit your site on their mobile device, this could be valueable time spent!

### Hosting

Note: hosting, in general, is tough. You should therefore not wait until the last moment to give it a try. It's tempting to do so, since it's sometimes thought of as the final step, but shouldn't be thought of in this matter because there are considerations to take into account. Depending on your technology choices, you might not be able to host with one solution vs others. See further consideration in the sections below.

#### Zeit

Gotchas:

Zeit normally takes about 1 or 2 minutes to deploy. During one cohort's personal projects, some students were seeing times of 15-30 minutes. Sometimes random failures happened. This was later acknowledged and addressed by Zeit, but be advised.

#### Digital Ocean

A note on how Digital Ocean servers (and others like it) are structured. Your app will run on some port number above 1024, like 3000, 3030, or whatever you choose. However, the normal http port is 80 and https is 443, which require root/admin access. Therefore, the pattern is to run a "reverse proxy" tool, such as Nginx or Apache, which will accept web requests on those ports, and forward the traffic to your node server. When setting up your Digital Ocean droplet, ensure you choose to have Nginx, and follow steps to forward the web traffic between ports.

Gotchas:

While many students receive instant access to Digital Ocean, some students were told to wait while their account access request was reviewed. Ultimately some students are denied for reasons not explained by Digital Ocean's communications with those students.

### Custom

### Techs
#### 3rd party API

API is a broad term, but we mean web requests using axios or similar. The simplest definition is axios is needed to obtain data. You earn 10 points for each separate API you use, with a max of 20. For our definition, we mean each different domain. For example, if you make 1 API call to swapi.co, 2 to pokeapi.co, and 1 more to OpenWeather, you'll earn a total of 20 points: 10 for swapi.co, 10 for the 2nd API to pokeapi.co, and 0 more for OpenWeather, since you're already at the total of 20.

**What counts:**

Examples include

* The Star Wars API https://swapi.co/
* The Pokemon API https://pokeapi.co/
* A weather API, e.g. https://openweathermap.org/api

**What doesn't count:**

* you find a library that does most of the raw API calls for you. E.g. the Stripe client side library wouldn't count because it makes the web requests for you and hides you from this complexity. Note that Stripe is a library that DOES count for points as a "Tech" (see elsewhere in this document).

Examples:
* FillMurray - http://www.fillmurray.com/: (A student did try to use this site.) it's an image placeholder (aka filler images) site. No axios calls needed.

#### Redux
(Tyler)
#### Stripe
(Tyler)
#### S3
(Tyler)
#### Socket.io

Socket.io enables real-time bidirectional event-based communication. It is a great tool to show real-time analytics, instant messengers, push notifications, or do document collaboration. Socket.io works very well with and is simple to integrate into ExpressJS. The format of sockets in your server is similar to creating endpoints. The socket.io docs are not only great they also have a quick tutorial on how to set up a chat application - https://socket.io/get-started/chat/

Gotchas: 
* There are many ways to decide who is the recipient of a particular “emit”. Be advised that one way may work in a certain situation but may not in another. The docs have a great emit cheatsheet that will be valuable along the way.
* There are two important parts to Socket.io (server and client) and they both come with the ‘socket.io’ npm package.

#### ChartJS
In the world of data – visualization plays a keen role in portraying the data.  Being able to effectively display that data is made a little easier with chartJS.  ChartJS is a open source HTML library, available as a react-exstension that makes displaying data in the form of a graph or chart fairly simple.  The documentation is pretty straightforward, and integration with React is very doable. 

Gotchas: ChartJS has certain limitations that other libraries, like D3 do not.  While it is easier to use, it has less options and customizations you have x amount of graph/chart options you can use and while interativity is being added, it is not as updated as D3.

#### D3
D3 is more of a libary for creating and manipulating HTML than it is a charting libary like ChartJS.  The possibilites with D3 are pretty endless, D3 can go way beyond graphs/charts and into other sort of graphics you may need.  Like this: https://bl.ocks.org/mbostock/1353700 the many many ways that you can visualize data with D3 make it pretty awesome.

Gotchas: D3's main drawback is its difficult to incorporate, there is a steep learning curve.
The syntaxes are more complex than Chart.js because it involves creating each element of the chart. Sifting through the documentation can take awhile.  Also, some high-level stuff, D3 directly manipulates the DOM while react is built around manipulating the virtual DOM.  Get React and D3 to play nicely together takes some fiddling. Here's a good article for this: 
https://medium.com/@tibotiber/react-d3-js-balancing-performance-developer-experience-4da35f912484 Don't let these gotchas scare you, D3 is a valuable libary to have knowledge of to impress potential employers.

#### Custom Styled Auth0 login form

#### NodeMailer

Nodemailer is a module for Node.js applications to make sending emails very simple. There are only three simple steps from setting up to sending a Nodemail. Step one is setting up a transport service that Nodemailer can use to send the emails (it can be any email that you have, or you can create a new one just for the project). Step two is setting up the message options. Message options is a fancy way to say “who sends what to whom”. The last step is just using the sendMail() method on your previously created transporter.

Be advised that there are many challenges with email. Worse still is that email behaves in a not fully predictable way, e.g. sometimes mail will go to spam, and sometimes that same email content, sent later, won't. This is not to discourage you from trying. The reality is that you'll almost certainly send automated email at some point in your career, so learning now still helps, but just to set your expecations.

Gotchas: 
* Each email server is allowed to operate as it sees fit. The biggest issue is that your email might be flagged as spam by one provider and not another. The reasons messages are marked as spam are rarely given (as this knowledge would aid spammers). 
* Email clients (the software that displays the email) can be picky about format. If you only need very simple email messages, you'll be fine. Be advised that all styling must be inline (no external stylesheets; you must use the style attribute), and some styles are ignored and thus don't work, such as flexbox. The rules change over time.
* Just to make sure that you are aware: all styling is in line styling. Styling will be a time sink if you choose to make a complicated email.

#### Twilio

Twilio has a wide range of servies that can be used. They vary from sending SMS messages, phone calls, real-time video, as well as programmable chats all from your Node.js server. For the sake of this project, it would be recommended that you limit your Twilio experience to just the SMS service. Twilio’s SMS service is very easy to use after you go through the extensive set up it requires. 

Gotchas:
* Twilio does not require a traditional “API key”. To set up your Twilio SMS service you must request an account SID and a Twilio Authentication token. You must then apply for a phone number that will be handling all of the message sending.
* There is a free account type (yay!) as well as paid accounts. With the free account, you are limited to sending messages to a single phone number that you choose during creation and only that number while using the free account. A free Twilio account can be great if you just want to be the sole receiver or the information. If you want to have your users receive messages, you’ll have to fork over some moneys per message sent.

#### CSS-in-JS

CSS-in-JS is a way to keep styling scoped to a component, without letting styles affect the rest of the site. You can read more about it [here](http://blog.vjeux.com/2014/javascript/react-css-in-js-nationjs.html).

Examples of CSS-in-JS libraries:

* [Styles components](https://github.com/styled-components/styled-components)
* [Aphrodite](https://github.com/Khan/aphrodite)
* [Emotion](https://github.com/emotion-js/emotion)
* [Glamor](https://github.com/threepointone/glamor)
* [Glamorous](https://github.com/paypal/glamorous)
* [JSS](https://github.com/cssinjs/jss)
* [Radium](https://github.com/FormidableLabs/radium)

### Presentation
#### Mentions Tech
(Tyler)
#### Uses Time Effectively
(Tyler)
(We need to finalize what time frame we need to give them)

## To add:
* Goal is learning.
* Can earn partial points sometimes, like on "responsive". If you have a little bit that's responsive, but not the whole site, this isn't worth full points. On the other hand, if e.g. a student tries to use Digital Ocean but it doesn't work, then it should probably be 0 points (although the student is allowed to come back after they've fixed it).
