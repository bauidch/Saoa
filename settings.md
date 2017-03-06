# Make Settings in QML and Python

## QML

Settings Dialog
```
```

##Python

Create settings file
```python
def creat_dir:()
  homeDir = os.path.expanduser("~")
  os.chdir(homeDir + "/.config/")
  
  if not os.path.exists("your-app/"):
    os.makedirs("your-app/")
    
  if not os.path.isfile("your-app/settings.json"):
    File = open("your-app/settings.json", "w")
    data = {
      'id': '',
      'username': '',
      'passowrd': '',
      'location': ''
            
     }
    data = json.dumps(data)
    File.write(data)
    File.close()  
```

Read Settings
```python
def read_settings():
    homeDir = os.path.expanduser("~")
    os.chdir(homeDir + "/.config/your-app")
    with open('settings.json') as settings_data:
        settings = json.load(settings_data)
    pyotherside.send('settings', settings)
```

Save Settings
```python
def save_settings(id, username, password, location):
    homeDir = os.path.expanduser("~")
    os.chdir(homeDir + "/.config/your-app")
    File = open("settings.json", "w")
    data = {
        'id': id,
        'username': username,
        'passowrd': password,
        'location': location
            
     }
    data = json.dumps(data)
    File.write(data)
    File.close()

```
