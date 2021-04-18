create a Google Cloud Function running this command in the same line:
```
gcloud functions deploy telegram_bot --set-env-vars "TELEGRAM_TOKEN=<TELEGRAM_TOKEN>" --runtime python38 --trigger-http --project=<project_name>
```

Some details:

* Here webhook is the name of the function in the `main.py` file
* You need to specify your Telegram token with the `--set-env-vars` option
* `--runtime python38` describe the environment used by our function, Python 3.8 in this case
* `--trigger-http` is the type of trigger associated to this function, you can find here the complete list of triggers
The above command will return something like this:
  
Step three, you need to set up your Webhook URL using this API call:
```
curl "https://api.telegram.org/bot<TELEGRAM_TOKEN>/setWebhook?url=<URL>"
```