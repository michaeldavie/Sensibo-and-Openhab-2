# Sensibo-and-OpenHAB2

To have OpenHAB2 control a Sensibo system via the Sensibo API carry out the following steps:

- Obtain an API key from Sensibo at https://home.sensibo.com/me/api.
- Use your API key in the following URL below to get the ID's of your pods: https://home.sensibo.com/api/v2/users/me/pods?apiKey=MYAPIKEY
- This should give you a reply similar to:
```{"status": "success", "result": [{"id": "POD_ID"}]}```
- Modify the rules file to include your API key and pod ID.
- Add the items from the included items file to your system.
- Add the entries from the included sitemap file to your system.

# Notes

- The Sensibo API does not update a pod's state when it is off. As a result, I've chosen to store the user's desired state in OpenHAB items, rather than to read the current state from the Sensibo API. The desired state is then pushed to the pod when it is turned on.
- The rules seem to function correctly, but do throw timeout and null pointer exceptions.
- The rules and items can be modified / duplicated to support additional pods.
