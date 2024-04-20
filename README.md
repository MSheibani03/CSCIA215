# CSCIA215 Final Project
openssl genrsa -out private_key_michael.pem 3072
nano certificate_extensions.ext
openssl req -new -sha384 -key private_key_michael.pem -out michael.csr -subj "/CN=usca.edu"
openssl x509 -req -sha384 -days 365 -in michael.csr -signkey private_key_michael.pem -out public_cert.pem -extfile certificate_extensions.ext 
