# HA Proxy Example

## Tomcat
- based on tomcat:9.0 Docker image
- restores manager apps to use as example
- adds GUI user in tomcat-users.xml

## HAProxy
- based on haproxy:2.4 Docker image
- adds very basic, and commented haproxy.conf file
- starts haproxy with -dD (diagnostic mode)
- uses private root CA and localhost certificate (in /certs)
    - note for haproxy you need cert and private key in one file
- includes sample redirect rule for http -> https

## docker-compose.yaml
- starts tomcat first, then haproxy
- exposes all ports to outside world for testing
    - in practice you wouldn't expose Tomcat ports at all

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
NOTE THIS DOESN'T WORK ON FIREFOX as the localhost private CA certs are not allowed
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
