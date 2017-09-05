# Sensibo-and-OpenHAB2

To have OpenHAB2 control a Sensibo system via the Sensibo API carry out the following steps:

- Obtain an API key from Sensibo at https://home.sensibo.com/me/api.
- Modify `sensibo-interface.rules` to include your API key and add it to your system.
- Add the items from `sensibo.items` to your system.
- Add the entries from `sensibo.sitemap` to your system.

# Notes

- The Sensibo API does not push updates to a pod while the pod is off. As a result, I've chosen to store the user's desired state in OpenHAB items, rather than to read the current state from the Sensibo API. The desired state will then be pushed to the pod when it is turned on.
- The rules and items can be modified / duplicated to support additional pods.
- The "Switchable" tag allows the on/off switch to be made available to HomeKit/Siri and Alexa via their respective bindings, allowing for voice control.
