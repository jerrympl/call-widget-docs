# Call Widget API

This document goes through how to setup your widget on your page.

## Embedd API code options

Place this code on the bottom of your HTML structure. The best option is to put this code before `</body>`

```javascript
<script type="text/javascript">
    (function() {
        var s = document.createElement('script');
        s.setAttribute('src', 'http://call.interfeo.com/widgetEmbedd.js');
        document.body.appendChild(s);
    })();
</script>
```

If you would like to get an access to widget API you can call API actions in this listener:

```javascript
window.addEventListener('interfeo:ready', function(event) {
    // call widget API action in here
})
```

Overriding config params:

```javascript
InterfeoWidget.config({
    param1: 'value',
    ...
});
```

Overriding single config option:

```javascript
InterfeoWidget.param(optionName, optionValue);
```

Full list of available config properties:

| Param | Description |
| --- | --- |
| minimizedStateTooltip | Copy for tooltip presented when user hovers on call widget icon |
| minimizedStateIcon | Icon presented in Call Widget minimized state. Default is phone |
| minimizedStateIconSize | Icon's size in minimized state |
| dialogTitle | Title of dialog that pops up in maximized state (when user clicks on widget icon) |
| dialogTitleSuccess | Title of dialog when form is submitted |
| dialogCopy | Copy for dialog. This copy is placed under the dialog title |
| dialogPhoneFieldPlaceholder | Placeholder copy for phone input field |
| dialogConfirmButton | Copy for submit button |
| dialogDismissButton | Copy for cancel button |
| allowScheduleOtherDay | Determines whether user is able to schedule a call on different date and time. If this option is set to true, user will see switcher.|
| gdprCheckboxCopy | Copy located next to checkbox. This should be a statement that user gives a consent regarding GDPR |
| scheduleOtherDayOptionsSwitcherLabel | Copy for switcher presented when "allowScheduleOtherDay" is set to true. |
| scheduleOtherDayOptionsAvailableHours | List of available hours presented when "allowScheduleOtherDay" is set to true.  |
| scheduleOtherDayOptionsAvailableDates | List of available dates presented when "allowScheduleOtherDay" is set to true.  |
| scheduleOtherDayOptionsDayLabel | Label for "scheduleOtherDayOptionsAvailableDates"  presented when "allowScheduleOtherDay" is set to true.  |
| scheduleOtherDayOptionsTimeLabel | Label for "scheduleOtherDayOptionsAvailableHours"  presented when "allowScheduleOtherDay" is set to true.  |
| messagesError | Error alert copy  |
| messagesSuccess | Success alert copy  |
| messagesSending | Sending in progress copy presented in submit button |

### Example usage of passing many config params

```javascript
InterfeoWidget.config({
    minimizedStateTooltip: 'Click me here!',
    dialogTitle: 'Wanna order a call?',
    dialogConfirmButton: 'Yes, call me back!'
});
```


Resizing widget iframe:

```javascript
InterfeoWidget.resize(width, height);
```

Listening widget events
```javascript
InterfeoWidget.on(eventName, function(e) {
    // do the stuff
});
```
