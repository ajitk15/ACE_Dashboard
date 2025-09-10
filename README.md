# ACE_Dashboard

$ curl -s -k https://<url>/apiv2/servers/IS1?depth=3 |  jq '{jvmDebugPort: .properties.jvmDebugPort, httpConnectorPort: (.children.resourceManagers.children[] | select(.name=="http-connector") | .properties.ListenerPort), httpsConnectorPort: (.children.resourceManagers.children[] | select(.name=="https-connector") | .properties.ListenerPort)}'


{
  "jvmDebugPort": 0,
  "httpConnectorPort": 7800,
  "httpsConnectorPort": 7843
}
