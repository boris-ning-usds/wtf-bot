# wtf-bot

A Flask application that powers the /wtf Slack command. Inspired by a [previous incarnation](https://github.com/paultag/wtf) of similar functionality. Configured for deployment on [Cloud Foundry](https://www.cloudfoundry.org/). Relies on the VA [acronym list](https://github.com/department-of-veterans-affairs/acronyms).

## Local development

Clone this repo.

```
$ git clone https://github.com/department-of-veterans-affairs/wtf-bot.git
$ cd /path/to/wtf-bot/
```

### Create and configure virtual environment.

***nix**

 ```
  $ make python-install
  $ source ENV/bin/activate
 ```

**Windows**

 ```
> python3 -m venv ENV
> ENV\Scripts\activate
> pip3 install -r requirements.txt dev-requirements.txt
 ```

**Run tests.**

```
$ make test
```

## Run the server locally

### Set up environment variables

***nix**

```
$ export FLASK_APP=/path/to/wtf-bot/wtf.py
$ export FLASK_DEBUG=1
$ export SLACK_TOKENS={comma separated tokens to be defined by you}
$ export DATA_URL=https://raw.githubusercontent.com/department-of-veterans-affairs/acronyms/master/acronyms.csv
```

**Windows**

```
> set FLASK_APP=/path/to/wtf-bot/wtf.py
> set FLASK_DEBUG=1
> set SLACK_TOKENS={comma separated tokens to be defined by you}
> set DATA_URL=https://raw.githubusercontent.com/department-of-veterans-affairs/acronyms/master/acronyms.csv
```

### Start the local server

```
$ flask run
```

**Query the `/slack` endpoint.**

```
$ curl -X POST http://127.0.0.1:5000/slack -d "text=aaa&token={to be defined by you}"
```

## Bugs, feature requests, or contributions

Open an [Issue](https://github.com/department-of-veterans-affairs/wtf-bot/issues). Pull requests welcome.
