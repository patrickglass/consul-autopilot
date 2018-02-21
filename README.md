# consul-autopilot

consul-autopilot will ensure your consul cluster is always in a healthy and recoverable state

## Features

- Consul snapshot on interval
- Native support for uploading backups to S3
- Automatic restore from backup if consul has a leader but has no known backup. This allows cluster restore for disaster recovery with minimal human intervention

## Usage

Configuration of the service is done with environment variables.

Consul Lifeguard Agent:

- `CONSUL_BACKUP_INTERVAL`: Number of seconds to wait between backups. Default '3600'
- `CONSUL_BACKUP_DEST`: File/URI prefix for destination snapshot. Timestamp will be appended for each backup. Default '/tmp/consul-lifeguard-backup'

Consul Agent:

- `CONSUL_ADDR`: Specify the consul service http address. Default '127.0.0.1:8500'
- `CONSUL_HTTP_TOKEN`: Specify the consul API access token when ACL is enabled. ACL is not supported by default

