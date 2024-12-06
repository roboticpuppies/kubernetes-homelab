# Example Helm Chart

An example helm chart to deploy an app. This chart will be developed according to my needs. This is also for testing ground when developing a chart.

## Debugging the chart

You can render the template without applying it to the cluster by running `helm install demo ./chart --dry-run`

## Linting the chart

```bash
helm lint ./chart
```

## Installing an app using the chart

```bash
helm install <app name> ./chart
```