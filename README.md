Generate self-signed root certificate and client.pem/server.pem
===============================================================

```bash
# Create $HOME/CA directory
mkdir $HOME/CA

# copy the required files to there
cp openssl.cnf root.sh cert.sh $HOME/CA

# generate the root CA (root.pem and cacert.pem):
cd $HOME/CA
./root.sh
```

The root.pem and cacert.pem are valid for three years. Do not repeat this step
until the certificate expires.

To generate the client.pem key file (enter "password" and "localhost"):

```bash
./cert.sh client
```

To generate the server.pem key file (enter "password" and "localhost"):

```bash
./cert.sh server
```

The client.pem and server.pem certificates are valid for one year.

Required files in HOME/CA directory:

```
openssl.cnf
root.sh
cert.sh
```

Files generated
---------------

file            | goal
----------------|-------------------------
`cacert.pem`	| root certificate for distribution
`root.pem`	| root CA (to sign client/server key files, do not distribute)
`rootkey.pem`	| private key
`rootreq.pem`	| sign request
`root.srl`	| serial number
`client.pem`	| client key file
`clientkey.pem`	| private key
`clientreq.pem`	| sign request
`server.pem`	| server key file
`serverkey.pem`	| private key
`serverreq.pem`	| sign request
