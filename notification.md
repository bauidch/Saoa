## Notification

``` qml
import org.nemomobile.notifications 1.0
...
...
Button {
                Notification {
                    id: notification
                    category: "x-nemo.testing"
                    summary: "TestThings"
                    body: "What's Up, my friend?"
                    onClicked: console.log("Clicked")
                }
                text: "Application notification" + (notification.replacesId ? " ID:" + notification.replacesId : "")
                onClicked: notification.publish()
            }
```

https://sailfishos.org/develop/docs/nemo-qml-plugin-configuration/
