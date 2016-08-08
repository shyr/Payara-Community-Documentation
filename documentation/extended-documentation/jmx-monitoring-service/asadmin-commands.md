# Using the asadmin commands
_Payara Server and Micro 163 (4.1.1.163) onwards_

The JMX Monitoring Service provides two asadmin commands: `set-monitoring-configuration` and `get-monitoring-configuration`. This page documents the options available to the commands and how they should be used.

## `set-monitoring-configuration`

Usage: `asadmin> set-monitoring-configuration --dynamic true|false --enabled true|false --amx true|false --logfrequency <long.value> --logfrequencyunit MICROSECONDS|MILLISECONDS|SECONDS|MINUTES|HOURS|DAYS --addproperty 'name=AttributeName value=MBeanObjectName description=Option_Description' --delproperty AttributeName`

Aim: Sets the monitoring service configuration and can dynamically reload the configuration.

| Option | Type | Description | Default | Mandatory |
|--------|------|-------------|---------|-----------|
| `--target` | String | The instance or cluster to get the monitoring service configuration of | server | no |
| `--dynamic` | Boolean | Whether or not to dynamically reload the configuration | false | no |
| `--enabled` | Boolean | The enabled state of the service | N/A | yes |
| `--amx` | Boolean | Whether or not to boot AMX on startup | N/A | no |
| `--logfrequency` | Long | The numerical value for the rate at which messages are logged | N/A | no |
| `--logfrequencyunit` | TimeUnit | The unit for of rate at which messages are logged | N/A | no |
| `--addproperty` | String | MBean attribute to monitor. Takes a string of the format `'name=AttributeName value=MBeanObjectName description="Description"'`, where name and value are required and the string must be enclosed in ' ' | N/A | no |
| `--delproperty` | String | MBean attribute to stop monitoring. Takes a `name` value of and removes the property corresponding to it. | N/A | no |

## `get-monitoring-configuration`

Usage: `asadmin> get-monitoring-configuration --pretty false|true`

Aim: Retrieves the monitoring service configuration and outputs it.

| Option | Type | Description | Default | Mandatory |
|--------|------|-------------|---------|-----------|
| `--target` | String | The instance or cluster to get the monitoring service configuration of | server | no |
| `--pretty` | Boolean | Displays Boolean configuration options as a tick or cross | N/A | no |