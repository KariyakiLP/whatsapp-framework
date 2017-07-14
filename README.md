# mac (Whatsapp framework) 
![Version](https://img.shields.io/badge/version-0.0.9-brightgreen.svg?style=flat-square)
![Version](https://img.shields.io/badge/release-alpha-yellow.svg?style=flat-square)

Mac is a whatsapp bot/framework I made as a weekend project. The project itself has all you need to make your own custom functions easily.

_This needs **Python 3.5**_

## Setup:
1. Clone this repository (with submodules since it uses tgalal's yowsup library)
```sh
> git clone --recursive https://github.com/danielcardeenas/whatsapp-framework.git
```
2. Run setup.sh (Most likely on sudo since its going to install some libraries)
```sh
> sudo ./setup.sh
```

3. Register your phone and get a password with yowsup-cli: [_Documentation_](https://github.com/tgalal/yowsup/wiki/yowsup-cli-2.0)


4. Open **config.py** and add set your credentials

5. Ready to go! (Now you can add your own whatsapp modules)
```sh
> ./start.sh
```

## Quickstart
Create your own module inside [`modules/`](https://github.com/danielcardeenas/whatsapp-framework/tree/master/modules) directory
```python
# modules/hi_module.py

from app.mac import mac, signals

@signals.message_received.connect
def handle(message):
    if message.command == "hi":
        mac.send_message("Hello", message.conversation)
```
Now you should only add it into [`modules/__init__.py`](https://github.com/danielcardeenas/whatsapp-framework/blob/master/modules/__init__.py) to enable the module
```python
# modules/__init__.py
...
from modules import hi_module
...
```
And that's it! You are ready to go.

###### _You can take [hihelp module](https://github.com/danielcardeenas/whatsapp-framework/blob/master/modules/hihelp/hihelp.py) as an example._


## Modules screenshots:
![alt text](http://i.imgur.com/ZRlk5Uj.png)
![alt text](http://i.imgur.com/JmPbPXB.png)
![alt text](http://i.imgur.com/L4ebZql.png)

## Contributing
Adding your own funcitons to Mac is very easy. Check the [**wiki**](https://github.com/danielcardeenas/MacBot/wiki) for more info.
