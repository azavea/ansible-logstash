# ansible-logstash

An Ansible role for installing Logstash.

## Role Variables

- `logstash_version` - Logstash version
- `logstash_short_version` - Logstash short version

## Example Playbook

It is important to note that this role does not include any templates for Logstash configuration. Because Logstash supports `conf.d` style configuration, users of the role are encouraged to write separate Ansible tasks and templates to configure Logstash for their needs.

There is an example template in the [examples](./examples/) directory that reads `/var/log/syslog` and pretty prints a dump of that to `stdout`. Because Logstash is running as a daemon, `stdout` ends up being captured in `/var/log/logstash/logstash.stdout`.

Running the following command should allow you to confirm that the Logstash `file` input and `stdout` output are working:

```bash
$ cat /var/log/logstash/logstash.stdout
```
