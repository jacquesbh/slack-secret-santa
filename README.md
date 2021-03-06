# Slack Secret Santa app

Just go to https://slack-secret-santa.herokuapp.com/ and have fun.

Code source is under MIT License.

- This application is powered by Symfony 3 and its Micro Kernel;
- Hosting is provided by Heroku;
- Session are stored in Heroku Redis servers;
- Built with ♥ by [@pyrech](https://github.com/pyrech) and [@damienalexandre](https://github.com/damienalexandre).

## Install, run and deploy

- Download and install the Heroku Toolbelt 
- If you haven't already, log in to your Heroku account and follow the prompts to create a new SSH public key.
- Give your heroku details to Damien to be able to deploy

```
$ heroku login
$ heroku git:remote -a slack-secret-santa
$ heroku plugins:install heroku-redis
$ git push heroku master
```

The app requires:

- a Redis server
- PHP 5.6+

As we rely on env variables, we cannot use `server:run`. Run:

    cd web/
    SLACK_CLIENT_SECRET=TOTO SLACK_CLIENT_ID=TOTO php -d variables_order=EGPCS -S 127.0.0.1:8000 ../etc/router.php
    open http://127.0.0.1:8000/
    
Variables are:

- `SLACK_CLIENT_SECRET`: Application secret from Slack;
- `SLACK_CLIENT_ID`: Application id from Slack;
- `REDIS_URL`: The full redis connexion url (default `redis://localhost:6379`)
