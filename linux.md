# Linux notes

## Ubuntu
Setting up SSH: needed to install SSH daemon `sudo apt-get install ssh`.

## Fedora

sshd already installed, needed to start it up

* `systemctl status sshd`
* `systemctl start sshd`

Enable it permanently: `systemctl enable sshd`

### OSQuery install
Official yum/RPM instructions:
```bash
curl -L https://pkg.osquery.io/rpm/GPG | sudo tee /etc/pki/rpm-gpg/RPM-GPG-KEY-osquery
sudo yum-config-manager --add-repo https://pkg.osquery.io/rpm/osquery-s3-rpm.repo
sudo yum-config-manager --enable osquery-s3-rpm
sudo yum install osquery
```

Needed to tweak that slightly - Fedora now uses `dnf` instead of `yum`.

```
curl -L https://pkg.osquery.io/rpm/GPG | sudo tee /etc/pki/rpm-gpg/RPM-GPG-KEY-osquery
sudo dnf config-manager --add-repo https://pkg.osquery.io/rpm/osquery-s3-rpm.repo
sudo dnf install osquery
```


### Fish shell

Installed Fish and made it my default shell. `chsh` is the usual command to change shells but it's not installed by default, argh.

```bash
# Install chsh
sudo dnf install util-linux-user
# Use Fish by default
chsh -s /usr/bin/fish
```

### Permissions

By default, can’t read /var/lib/pgsql directory with my regular account - that’s a giant pain.

Fix: add myself (the “parallels” account) to the postgres group and grant group read+execute permissions on everything in the folder. Can’t give write access to the group, Postgres doesn't allow that.

```bash
# Add parallels user to postgres group
usermod -aG postgres parallels
# Grant group permissions to everything in the Postgres folder
chmod -R g+rx /var/lib/pgsql
```
Then login/logout.
