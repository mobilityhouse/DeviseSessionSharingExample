###The example shows how to configure two rails applications to share devise session and use local ssl conection.
## This is pure scaffold rails application with devise mounted on user.
The applications are using the same secret_token (and have to use same pepper
for passwords). The domain in config/initializers/session_store.rb is set to
`:all`

## Configuration
1. Clone repository: `git clone git@github.com:mobilityhouse/DeviseSessionSharingExample.git`
2. Install apache2 and mod-passenger
3. Add site-available. Sample configuration you can find: `site-available/example`
4. Generate ssl certificate inside /etc/apache2/ssl/ (configuration of this
path is in site-available/example): `sudo openssl req -x509 -nodes -days 365
-newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out
/etc/apache2/ssl/apache.crt`
5. Restart apache
6. Open browser and login going to  `https://first.example.me/users`
7. Go to https://second.example.me/users and observe that you are already
logged in
