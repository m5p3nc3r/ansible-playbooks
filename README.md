```bash
# install roles and collections
ansible-galaxy install -r requirements.yml

# Install the playbook
ansible-playbook -i inventory frontend.yaml

# Check the cron jobs
crontab -u matt -l
```

TODO: Update the pre/post scripts at /etc/letsencrypt/renewal-hooks to stop/start docker reverse_proxy
TODO: Update cron to run certbot as root

If the above is done, I'm not sure the blow is needed...
TODO: Ensure /var/log/letsencrypt, /var/lib/letsencryprt and maybe /etc/letsencrypt are writable as the ansible user.
Something like

```bash
chgrp adm /var/log/letsencrypt
chmod g+rwx /var/log/letsencrypt
chgrp -R adm /etc/letsencrypt/
chmod -R g+rwx /etc/letsencrypt/
chgrp adm /var/lib/letsencrypt
chmod g+rwx /var/lib/letsencrypt
```
