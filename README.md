# app-protect

This runs NGINX as Reverse Proxy and enables App Protect

Listens on Port 80 and proxies the request to the back-end application on port 9090
Change the endpoints as required

Note:
Load the NGINX App Protect module on the main context in `nginx.conf` file:

      load_module modules/ngx_http_app_protect_module.so;


## default_server.conf - This runs a default server on port 9090
  Accessible only from 127.0.0.1 and denied for all other IPs. 

## app_protect.conf - This runs an APP Protect enabled endpoint on port 80.
  Default Security policy has been enabled
  Note the location of the default policy and edit as required
  Note the location of the logs and review them as required


## Testing:

On the Virtual Machine:
1. `curl "localhost"`

Welcome to nginx!

  
2. `curl "localhost/?</script>"`
<html><head><title>Request Rejected</title></head><body>The requested URL was rejected. Please consult with your administrator.<br><br>Your support ID is: 18381064594571692234<br><br><a href='javascript:history.back();'>[Go Back]</a></body></html>
