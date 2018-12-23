# HTTP Password

The application can be shielded with an HTTP password (basic authentication). This allows to deploy a pilot application that
is accessible only to users that are in possession of the password.

The password is enforced by Nginx and is set or cleared in /etc/nginx/conf.d/default.conf in the onboarding-web container. 
This container accepts two environment variables:
- AUTHSWITCH : This text is used to comment or uncomment the basic authentication in the conf file. So set to ' ' (or leave blank)
to enable and set to '#' to disable the password
- HTPASSWD : HTTP password / basic authentication string in the .htpasswd format. For example to set the userid/password to 
admin/admin use this string 'admin:$apr1$Jv46odcT$pQwDyrm.Y2NMQ0E045ip01'. 
**NOTE** When you specify this string in a docker compose
file the dollar signs within the string need to be duplicated to avoid docker compose viewing them as variable markers.
See this [example](https://github.com/local-motion/bootstrap/blob/master/development/docker-compose.yml "Docker compose file").

## Basic authentication string

To create a basic authentication string on a mac:
```
htpasswd -c <password file to be created> <username>
```
This will query you for the password

For example:
```
htpasswd -c .htpasswd tester
```
