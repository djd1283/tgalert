# tgalert
Repository containing simple module to allow easy Telegram messages for code updates. Original intention is to notify programmer when long process finishing, such as training a model or building a dataset.

How to setup with pip:
```
pip install tgalert
nano ~/.tg-config  # add auth token for your Telegram bot (use @BotFather, can be shared), followed by your client id (use @get_id bot)
```

Then in your code:

```from tg_alert import TelegramAlert

alert = TelegramAlert()
alert.write('Training complete')
```

Extra features:

- if .tg-config does not exist, write() performs no action. so it can be used in code without checks
- if program crashes on exception it will notify on Telegram (except KeyboardInterupt and SyntaxError)
