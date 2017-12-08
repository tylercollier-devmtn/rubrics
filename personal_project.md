# DevMountain Phoenix Personal Project Rubric

> This is a work in progress and will change before your personal project begins.

The intent of a personal projects is to build something using technologies you have been taught, as well as to learn new technologies on your own.

This rubric serves to guide students and mentors in the requirements. Wherever there is ambiguity on what the requirements are, focus on the goal of learning.

## Requirements

Always required:

* Full stack CRUD site
    * Create/POST
    * Read/GET
    * Update/PATCH
    * Delete/DELETE
    * Each of the above must manipulate the database.
* 1 foreign key and a JOIN statement
    * Yes, you need a JOIN. Usually this means you'd be displaying a list somewhere. Some sites, with the small scope of intended functionality, don't lend themselves to such a list with the database's data. A simple workaround for this is to create an admin page which displays the data. Such a page can even be public if it doesn't contain sensitive information; perhaps don't have a link to the admin page on the site itself but tell users in the README or a private email how to view it (e.g. by visiting #/admin). An example of such a list might be, for a store, all orders for all users. Or what about users without an order (use an outer join)?

| Category            | Name                           | Points | Description               |
|---------------------|--------------------------------|--------|---------------------------|
| Testing             |                                |        |                           |
|                     | Unit Tests                     | 30     | There will be a link here |
|                     | Endpoint Tests                 | 20     |                           |
|                     | E2E Tests                      | 40     |                           |
| Modules/Build tools |                                |        |                           |
|                     | 3rd Party Api                  | 20 per |                           |
|                     | Sass/Less                      | 10     |                           |
|                     | Webpack/Browserify             | 20     |                           |
| Frameworks          |                                |        |                           |
|                     | Redux/Thunks                   | 10     |                           |
|                     | Angular 2                      | 40     |                           |
|                     | Angular 1.5 Components         | 30     |                           |
|                     | React Native                   | 30     |                           |
|                     | Electron                       | 20     |                           |
| Planning/Design     |                                |        |                           |
|                     | Domain Registration            | 10     |                           |
|                     | Defined MVP/API                | 10     |                           |
|                     | Responsive                     | 20     |                           |
| Hosting             |                                |        |                           |
|                     | Zeit, Heroku (easy solutions)  | 0      |                           |
|                     | Digital Ocean                  | 10     |                           |
| Custom              |                                |        |                           |
|                     | Instructor approves early on   | ?      |                           |
| Techs               |                                |        |                           |
|                     | Stripe                         | 20     |                           |
|                     | s3                             | 10     |                           |
|                     | Sockets                        | 20     |                           |
|                     | ChartJs                        | 10     |                           |
|                     | D3                             | 20     |                           |
|                     | Other? (approved early on)     | 10-30  |                           |
|                     | Custom/Styled Auth0 login form | 10     |                           |
| Presentation        |                                |        |                           |
|                     | Mentions Tech                  | 10     |                           |
|                     | Uses Time Effectively          | 10     |                           |

Total points required: 70

* 3rd party API
* CSS-in-JS: 10 points
* Emailers: 10 points
     * Sendgrid
     * Nodemailer

### Definitions

#### Hosting

Note: hosting, in general, is tough. You should therefore not wait until the last moment to give it a try. It's tempting to do so, since it's sometimes thought of as the final step, but shouldn't be thought of in this matter because there are considerations to take into account. Depending on your technology choices, you might not be able to host with one solution vs others. See further consideration in the sections below.

##### Zeit

Gotchas:

Zeit normally takes about 1 or 2 minutes to deploy. During one cohort's personal projects, some students were seeing times of 15-30 minutes. Sometimes random failures happened. This was later acknowledged and addressed by Zeit, but be advised.

##### Digital Ocean

A note on how Digital Ocean servers (and others like it) are structured. Your app will run on some port number above 1024, like 3000, 3030, or whatever you choose. However, the normal http port is 80 and https is 443, which require root/admin access. Therefore, the pattern is to run a "reverse proxy" tool, such as Nginx or Apache, which will accept web requests on those ports, and forward the traffic to your node server. When setting up your Digital Ocean droplet, ensure you choose to have Nginx, and follow steps to forward the web traffic between ports.

Gotchas:

While many students receive instant access to Digital Ocean, some students were told to wait while their account access request was reviewed. Ultimately some students are denied for reasons not explained by Digital Ocean's communications with those students.

#### 3rd party API

API is a broad term, but we mean web requests using axios or similar. The simplest definition is axios is needed to obtain data.

**What counts:**

Examples include

* The Star Wars API https://swapi.co/
* The Pokemon API https://pokeapi.co/
* A weather API, e.g. https://openweathermap.org/api

**What doesn't count:**

* you find a library that does most of the raw API calls for you. E.g. the Stripe client side library wouldn't count because it makes the web requests for you and hides you from this complexity. Note that Stripe is a library that DOES count for points as a "Tech" (see elsewhere in this document).

Examples:
* FillMurray - http://www.fillmurray.com/: (A student did try to use this site.) it's an image placeholder (aka filler images) site. No axios calls needed.

#### Mail

Be advised that there are many challenges with email. Worse still is that email behaves in a not fully predictable way, e.g. sometimes mail will go to spam, and sometimes that same email content, sent later, won't. This is not to discourage you from trying. The reality is that you'll almost certainly send automated email at some point in your career, so learning now still helps, but just to set your expecations.

**Email receiving servers**: each email server is allowed to operate as it sees fit. The biggest issue is that your email will be flagged as spam by one provider and not another. The reasons messages are marked as spam are rarely given (as this knowledge would aid spammers).
**Email clients**: each email client (the software that displays the email) about format. If you only need very simple email messages, you'll be fine. Be advised that all styling must be inline (no external stylesheets; you must use the style attribute), and some styles are ignored and thus don't work, such as flexbox. The rules change over time.

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

## To add:
* Goal is learning.
* Can earn partial points sometimes, like on "responsive". If you have a little bit that's responsive, but not the whole site, this isn't worth full points. On the other hand, if e.g. a student tries to use Digital Ocean but it doesn't work, then it should probably be 0 points (although the student is allowed to come back after they've fixed it).