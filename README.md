# troubleshooting
Some notes for encountered technical troubles

*The environment I am using is Ubuntu 18.04, the problem descriptions vary with devices.*

## Unable to link to Github

### Error message: 

`fatal: unable to access 'https://github.com/<repo>.git/': Problem with the SSL CA cert (path? access rights?)`

### Resolutions:

1. (Optional) Create a directory for installing a certificate file. My choice was `mkdir ~/<cacert_dir>`.

2. Install the certificate into that directory and name it as `cacert.pem` by running this command `curl http://curl.haxx.se/ca/cacert.pem -o ~/<cacert_dir>/cacert.pem`.

3. Run command `git config --global http.sslCAinfo "$HOME/<cacert_dir>/cacert.pem"`.

4. Try to access Github again.


## A certificate error when using `urllib` related packages

### Error message: 

(Forgot to record it)

### Resolutions:

1. Run `sudo update-ca-certificates --fresh`.

2. Run `export SSL_CERT_DIR=/etc/ssl/certs` (the directory path may be different from yours).
