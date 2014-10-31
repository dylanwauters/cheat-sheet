# Aanpassen van Firewall settings
* lijst van zones zones en hun services, interfaces 
** systemctl list-units --type service
//http toevoegen
firewall-cmd [--permanent] [--zone=ZONE] --add-service=http
// in de main.yml --> automatisering
- name: Configure firewall 
firewalld: service=http state=enabled permanent=no 
  - name: Configure firewall (permanent)
firewalld: service=http state=enabled permanent=yes.

//Aanmaken van testcertificaat door volgende commando’s:
•	Openssl genrsa –out ca.key 2048
•	Openssl req –key ca.key –out ca.csr
•	Openssl x509 –req –days 365 –in ca.csr –signkey ca.key –out ca.crt

//De juiste plaats geven we aan in de main file met een copy. De locaties zijn:
•	/etc/pki/tls/certs  (voor de ca.crt file)
•	/etc/pki/tls/private  (voor de ca.key)
•	/etc/pki/tls/private (voor de ca.csr)


