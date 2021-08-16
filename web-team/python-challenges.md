# Python Take Home Challenge

We use [Python](https://www.python.org/) as the primary language for our codebase with [FastAPI](https://fastapi.tiangolo.com/) and [Django REST framework](https://www.django-rest-framework.org/).

We don't want to ask you abstract technical questions during the interview, so we have a small challenge for you.

## MFA workflow challenge

Multi-factor authentication (MFA) is a mode of authentication where a user is granted access to the secured asset only after presenting multiple pieces of evidence to the authentication method. The most common MFA evidence pieces include passwords, TOTP tokens, SMS tokens and one time login links or passwords.

For this challenge, you are to architect and build a Python + FastAPI application for performing the following MFA workflows

### Workflows to Support

* **ACCOUNT CREATION**: User is allowed to create an account with their email address and password. After these credentials are supplied, the user is emailed a one-time use url that they must visit and again supply password. Upon confirmation of the password, the user is presented with a success message and also given a TOTP key that they will need to use when logging into the platform in the future. Accounts are not valid until all steps have been completed

* **LOGIN**: User is asked for their email address. Upon receipt of their email address, they are emailed a one-time use url which they must visit. When visiting the link, the user has to supply their password and their TOTP code. Once verified, the user is presented with a success message showing them the last previous time they logged. Login is not successful until after all steps are completed

* **DELETE ACCOUNT**: User is allowed to delete their account by supplying their email address and password. After these credentials are received, the user is emailed a one-time use url and upon visiting this link, the deletion is effected and user is presented with a success message


### Build setup
This coding challenge is not in place to evaluate how you set up your deployment setup, but to give you a chance to build something small so we can see how you approach it.
In order to simplify the deployment process, we *highly* recommend that you use [Docker](https://www.docker.com) + [Docker Compose](https://docs.docker.com/compose/).


### Requirements
- Use [Python 3.8+](https://www.python.org/) + [FastAPI](https://fastapi.tiangolo.com/)
- Application code should have [type hints](https://docs.python.org/3/library/typing.html) and expose [OpenAPI](https://www.openapis.org/) documentation.
- Application code should have some test coverage.
- Provide a `README` file and add information on how to build and/or run the project locally. This file can also include your thought process and any explanation.
- Push the application to a public github repo and provide us with a link.

### Implementation
- Email sending can be done via the [SendGrid API](https://sendgrid.com/) or also mocked. If mocked, then the one-time url can be returned to the user as the result of the previous action.
- The one-time url must be only usable only once.
- Making the one-time url be only valid for 30 mins is a nice to have.
- User password should not be saved in cleartext.
- Application state can be saved in a database (SQLite, Dockerized PostGres, etc).
- No UI is needed although one can be created (ie. a simple HTML based form for the different workflows).
- Do not cheat. There are lots of MFA workflow projects out there, we're not interested in those. We want to see **how you think**.
- If you want to go above and beyond, by adding additional functionality, feel free to, **as long as you still satisfy the original requirements**.

### What we're evaluating
- Does `README.md` contain sufficient information to run the project?
- Does it work?
- How is the code structured?
- How clean is the code?
- What is the code test coverage?
- Is the end result easily deployable?

### Tips
- DRY code is not the only thing that matters, we also care about things getting too complex. Finding the line between writing simple and DRY code is part of the challenge.

### Timeframe
Take as much time as you need. We're expecting this will take you one or two evenings.

### More Questions?
Please reach out to us at recruiting **AT** dizzbo **dot** com, we're happy to help!
