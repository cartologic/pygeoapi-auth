## Generate SSL certificates for the Nginx

```bash
cd ./nginx/certs
```

### Generate a private key

```bash
openssl genpkey -algorithm RSA -out pygeoapi.key
```

### Generate a certificate signing request (CSR)

```bash
openssl req -new -key pygeoapi.key -out pygeoapi.csr -subj "/C=EG/ST=Cairo/L=Cairo/O=Pygeoapi/OU=IT Department/CN=\*.pygeoapi.local"
```

### Generate the self-signed certificate

```bash
openssl x509 -req -days 365 -in pygeoapi.csr -signkey pygeoapi.key -out pygeoapi.crt
```
