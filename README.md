# Bash Logger

Fork of Bash Logger designed to incorperate [PSR-3](http://www.php-fig.org/psr/psr-3/) compliance.

## Contributors

- Fred Palmer
- Dean Rather
- Adam Stradomski

## Using Bash Logger

**source** the *bash-logger.sh* script at the beginning of any Bash program.

``` bash

    #!/bin/bash
    source /path/to/bash-logger.sh
    LOG_LEVEL="INFO"
    INFO "This is a test info log"

```

> Function names are in CAPS as not to conflict with the `info` function and `alert` aliases.

## An Overview of Bash Logger

### Colorized Output

![Colour Screenshot](http://i.imgur.com/xnXp8VQ.png)

### Logging Levels

Bash Logger supports the logging levels described by [RFC 5424](http://tools.ietf.org/html/rfc5424). Logging levels in order of priority: 
- **DEBUG** Detailed debug information.

- **INFO** Interesting events. Examples: User logs in, SQL logs.

- **NOTICE** Normal but significant events.

- **WARNING** Exceptional occurrences that are not errors. Examples:
  Use of deprecated APIs, poor use of an API, undesirable things that are not
  necessarily wrong.

- **ERROR** Runtime errors that do not require immediate action but
  should typically be logged and monitored.

- **CRITICAL** Critical conditions. Example: Application component
  unavailable, unexpected exception.

- **ALERT** Action must be taken immediately. Example: Entire website
  down, database unavailable, etc. This should trigger the SMS alerts and wake
  you up.

- **EMERGENCY** Emergency: system is unusable.

### Log level

- Use the LOG_LEVEL variable to determine the logs to be logged. For example, LOG_LEVEL="INFO" will disable logging of debug level messages. 

## Handlers

By default:
- Logs are displayed in colour
- Logs are written to `~/bash-logger.log`
- Only logs above level DEBUG will be logged by default. Use LOG_LEVEL="DEBUG" to log all log levels. 
- **error** level logs and above `exit` with an error code

The colours, logfile, default behavior, and log-level behavior can all be overwritten, see [examples.sh](examples.sh) for examples.
