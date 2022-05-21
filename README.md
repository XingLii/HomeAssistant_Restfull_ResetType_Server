# HomeAssistant Restfull-ResetType-Server
Controll Via Restfull API from Homeassistant a Dell Server with Redfish API


1. Add this to configuration.yaml
``` yaml
rest_command:
  restapi_control_resettype_dell_server:
    url: "https://<<IP>>/redfish/v1/Systems/System.Embedded.1/Actions/ComputerSystem.Reset"
    method: POST
    username: "XY"
    password: "XY"
    content_type: "application/json;charset=utf-8"
    payload: '{"ResetType": "{{ ResetType }}"}'
    verify_ssl: false
```  
2. Change IP in the URL
3. Set User and Password from IDRAC

The ResetTypes are from [Supported Action — Reset Description](https://www.dell.com/support/manuals/de-de/idrac9-lifecycle-controller-v4.x-series/idrac9_4.00.00.00_redfishapiguide_pub/supported-action-—-reset?guid=guid-3444cf02-da8d-422a-9400-6ce5ba71d9bd&lang=en-us)
  
With this set you cant test it via Services
  
![image](https://user-images.githubusercontent.com/20464134/169671301-83dedcd0-b85c-4acf-a181-1b81ba9b97e8.png)

The Dell Server should now react to the Data Block with the ResetType in it.

It works in Automations aswell.
