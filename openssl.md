 # Create a CSR for name.com:
 `openssl req -new -newkey rsa:2048 -nodes -keyout name.com.key -out name.com.csr --config name.com.conf`
 
 # Example conf file:
 ```bash
 [ req ]
default_bits       = 2048
distinguished_name = req_distinguished_name
req_extensions     = req_ext
prompt             = no
[ req_distinguished_name ]
countryName             = SG
stateOrProvinceName     = Pinata
localityName            = Pinata
organizationName        = Awesome works PLC
organizationalUnitName  = Engineering division
commonName              = awesome.works.com
[ req_ext ]
subjectAltName = @alt_names
[alt_names]
DNS.1 = {req_distinguished_name::commonName}
DNS.2 = superawesome.works.com
 ```
 
 # Verify the CSR:
  `openssl req -text -noout -verify -in name.com.csr`
  
 # Read a certificate chain p7b:
 `openssl pkcs7 -inform DER -outform PEM -in <certificateBundle.p7b> -print_certs`
