 # Work with Python in a SailfishOS App

### Requirements

- Add in the file 'YourApp/rpm/yourapp.yaml' under Requrements  ```pyotherside-qml-plugin-python3-qt5```
- On A QML Page add ```import io.thp.pyotherside 1.3```

### In QML
```
Python {
            id: python

            Component.onCompleted: {
                addImportPath(Qt.resolvedUrl('.'));

                setHandler('loadingCircle', function(newvalue) {
                    oneLocation.loadingCircle = newvalue;

                });

                importModule('getdata', function () {});
                // Import the main module and load the data
                                importModule('getdata', function () {
                                    python.call('getdata.allFood', [oneLocation.locationTitle], function(result) {
                                        // Load the received data into the list model
                                        if (result.length <= 0) {
                                            oneLocation.noData = "True";
                                        }

                                        for (var i=0; i<result.length; i++) {
                                            listModel.append(result[i]);
                                        }
                                    });
                                })
            }


            onError: {
                console.log('python error: ' + traceback);
            }


        } 
``` 
### In Python

Send data to one of your Pages ```python pyotherside.send('lblText',var)``` 
