# flink-metrics-signalfx

A metrics reporter implementation for the SignalFX - https://www.signalfx.com/

Flink metrics variables will send to SFX as dimensions - https://docs.signalfx.com/en/latest/metrics-metadata/metrics-metadata.html#dimensions

## Build

```
./mvn clean package
```

## Install

In order to use this reporter you must copy `flink-metrics-signalfx-{{version}}.jar` into the `/lib` folder
of your Flink distribution. Metrics will be filtered out if metrics name contains the filter from
metrics.reporter.signalfx.filters.

## Parameters:

- token - the SignalFX token.
- filters - the metrics will be filtered out from reporter. 

## Example configuration:

```
metrics.reporter.signalfx.class: com.github.lukess.flink.metrics.signalfx.SignalFXReporterFactory
metrics.reporter.signalfx.interval: 60 SECONDS
metrics.reporter.signalfx.token: xxx
metrics.reporter.signalfx.filters: KafkaConsumer,KafkaProducer
```