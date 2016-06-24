# Continuous development
Definition: It is an umbrella term hat describes several aspects of iterative software application development, including continuous integration, continuous delivery, continuous testing and continuous deployment.


# Continuous integration
Continuous integration refers specifically to the process of steadily adding new code commits to source code, a concept that has evolved over the years. Originally, a daily build was the standard for continuous integration. Today, the usual rule is for each team member to submit work as soon as it is finished and for a build to be conducted with each significant change. Usually, a certain baseline of automated unit and integration testing is performed to ensure that new code does not break the build. This way developers know as soon as they're done if their code will meet minimum standards and they can fix problems while the code is still fresh in their minds. An important advantage of continuous integration is that it provides developers with immediate feedback and status updates for the software they are working on.

Continuous Integration is the practice of integrating changes from different developers in the team into a mainline as early as possible, in best cases several times a day. This makes sure the code individual developers work on doesn’t divert too much. When you combine the process with automated testing, continuous integration can enable your code to be dependable.


# Continuous delivery
Continuous delivery builds on continuous integration and as with continuous integration, each code commit is automatically tested at the time it is added. In addition to the automated unit and integration testing, a continuous delivery system will include functional tests, regression tests and possibly other tests, such as pre-generated acceptance tests. After passing the automated tests, the code changes are sent to a staging environment for deployment.

Continuous Delivery
is the practice of keeping your codebase deployable at any point. Beyond making sure your application passes automated tests it has to have all the configuration necessary to push it into production. Many teams then do push changes that pass the automated tests into a test or production environment immediately to ensure a fast development loop.


# Continuous deployment

Definition: 
It’s a process whereby all code that is written for an application is immediately deployed into production. The result is a dramatic lowering of cycle time and freeing up of individual initiative. It has enabled companies I’ve worked with to deploy new code to production as often as fifty times every day.

continuous deployment requires tremendous discipline and can greatly enhance software quality, by applying a rigorous set of standards to every change to prevent regressions, outages, or harm to key business metrics.

By making a few simple investments and process changes, any development team can be on their way to continuous deployment. It’s the journey, not the destination, that counts. Here’s the why and how, in five steps

# Continuous deployment

is closely related to Continuous Integration and refers to keeping your application deployable at any point or even automatically releasing to a test or production environment if the latest version passes all automated tests.



1. Continuous integration server:

This is the backbone of continuous deployment. We need a centralized place where all automated tests (unit tests, functional tests, integration tests, everything) can be run and monitored upon every commit.
At the beginning, do not be afraid. It is easy while following a simple rule: we’ll add a new automated test every time we fix a bug. Following that rule will start to immediately get testing where it’s needed most: in the parts of your code that have the most bugs and, therefore, drive the most waste for your developers. 

2. Source control commit check
The next piece of infrastructure we need is a source control server with a commit-check script. I’ve seen this implemented with CVS, subversion or Perforce and have no reason to believe it isn’t possible in any source control system. The most important thing is that you have the opportunity to run custom code at the moment a new commit is submitted but before it is accepted by the server. Your script should have the power to reject a change and report a message back to the person attempting to check in. This is a very handy place to enforce coding standards, especially those of the mechanical variety.

But its role in continuous deployment is much more important. This is the place you can control what I like to call “the production line” to borrow a metaphor from manufacturing. When something is going wrong with our systems at any place along the line, this script should halt new commits. So if the CI server runs a build and even one test breaks, the commit script should prohibit new code from being added to the repository. In subsequent steps, we’ll add additional rules that also “stop the line,” and therefore halt new commits.

3. 

# Continous Delivery vs. Continous Deployment

While continuous deployment implies continuous delivery the converse is not true. Continuous delivery is about putting the release schedule in the hands of the business, not in the hands of IT. Implementing continuous delivery means making sure your software is always production ready throughout its entire lifecycle - that any build could potentially be released to users at the touch of a button using a fully automated process in a matter of seconds or minutes.

This in turn relies on comprehensive automation of the build, test and deployment process, and excellent collaboration between everyone involved in delivery - developers, testers, DBAs, systems administrators, users, and the business.

In the world of continuous delivery, developers aren't done with a feature when they hand some code over to testers, or when the feature is "QA passed". They are done when it is working in production. That means no more testing or deployment phases, even within a sprint (if you're using Scrum). If you're using Kanban and you want to do continuous delivery, you can't bring a new story into play until the one you're working on is released to users.

However it doesn't always make sense to release every good build to users. In particular, this is usually impossible for embedded products when there is coupling between a software change and a hardware change. In the world of COTS, there are good marketing and support reasons why you'd not want to have more than a few "released" versions of your software in play at any given time (although you could still do regular "developer" or "early access" builds as Eclipse and the Omni Group do). There are probably other good reasons too - the important point is that they must be business reasons.

So when can you say you're doing continuous delivery? I'd say it's when you could flip a switch to go to continuous deployment if you decided that was the best way to deliver value to your customers. In particular, if you can't release every good build to users, what does it mean to be "done" with a story? I think at least the following conditions must apply:

    You have run your entire test suite against the build containing the story. This validates that the story is delivering the expected business value, and that no regressions have been introduced in the process of developing it. In order to be efficient, that means having comprehensive automated tests at the unit, component and acceptance level.
    The story has been demonstrated to customers from a production-like environment. Production-like means identical with production, within the bounds of reason. Even if you're deploying to an enormous cluster, you can use a technique like blue-green deployments to run a different version of your app in parallel on the production environment without affecting users.
    There are no obstacles to deploying to production. In other words, you could deploy the build to users using a fully automated process at the push of a button if you decided to. In particular, that means you've also tested it fulfills its cross-functional characteristics such as capacity, availability and security. If you're using an SOA or you have dependencies between your application and other systems, it means ensuring there are no integration problems.


