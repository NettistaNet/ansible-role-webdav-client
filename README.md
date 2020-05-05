# Basic ansible webdav-client role

Simple role to mount a webdav-url on debian based linux distributions. 

I am using this role mount a hetzner-storage box as backup-location. 

The role does the following makes sure:

* [davfs2](https://savannah.nongnu.org/projects/davfs2) is installed
* locking is disabled (*use_locks 0*)
* _/etc/davfs2/secrets_ exists
* mount-point exists
* webdav-url is mounted 

## Role Variables

All the variables have defaults just for documentation. While dest is a resonable mount-point. You need to provide a _src_-url, a _username_ and a _password_ of your webdav-server. 

You should set 
```yaml
davfs2_mounts:
  - src: https://some.url/some/resource
    dest: /backup
    user: user
    password: password
```