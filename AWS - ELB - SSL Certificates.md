## ELB - SSL Certificates
![image](https://github.com/nhvu95/aws-handbook/assets/26276890/8cc633c3-5acd-47cb-8c7b-7546902f846c)
### OVERVIEW ABOUT SSL/TLS
* An SSL certificate allows traffic between your clients and your load balancer to be encrypted in transit ( in-flight encryption)

* SSL refer to the secure sockets layer used to encrypt connections
* TLS refers to Transport Layer Security, which is a new version
* Nowadays, TLS certificates are mainly used, but people still refer as SSL

* Public SSL Certificates are issued by Certificate Authorities (CA)
* Comodo, Symantec, GoDaddy, GlobalSign, DigiCert, LetsEncrypt, etc
* SSL Certificates have an expiration date (you set) and must be renewed

### HOW AWS SSL WORKS?
* The load balancer uses an X.509 certificate ( SSL/TLS server certificated)
* You can manage certificates using ACM ( AWS Certificate Manager)
* You can create and upload your own certificates alternatively
* HTTPS listener:
           * You must specify a default certificate
           * You can add an optional list of certs to support multiple domains
           * Clients can use SNI (Server Name Indication) to specify the hostname they reach
           * Ability to specify a security policy to support older versions of SSL/TLS (legacy clients)

### SNI - Server name indication
* SNI Solves the problem of loading multiple SSL certificates onto one web server (to serve multiple websites)
* It's a newer protocol that requires the client to indicate the hostname of the target server in the initial SSL Handshake
* The server will then find the correct certificate or return the default one

Note: 
* Only works for ALB & NLB (newer generation), CloudFront
* Does not work for CLB (Older gen)


### CLB (v1)
* Support only one SSL certificate
* Must use multiple CLB for multiple hostname with multiple SSL certificates

### ALB (v2) & NLB (v2)
* Supports multiple listeners with multiple SSL certificates
* Uses server name indication (SNI) to make it work

