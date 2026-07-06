# KubeVirtBMC Helm chart

[![Chart CI](https://github.com/kubevirtbmc/chart/actions/workflows/chart-ci.yml/badge.svg)](https://github.com/kubevirtbmc/chart/actions/workflows/chart-ci.yml)

This repository hosts the Helm chart for [KubeVirtBMC](https://github.com/kubevirtbmc/kubevirtbmc).

## Install

KubeVirtBMC uses cert-manager for webhook certificates, so install cert-manager in the target cluster before installing this chart.

```sh
helm repo add kubevirtbmc https://kubevirtbmc.github.io/chart
helm repo update
helm install kubevirtbmc kubevirtbmc/kubevirtbmc \
  --namespace kubevirtbmc-system \
  --create-namespace
```

## Repository layout

The chart source lives in [`charts/kubevirtbmc`](charts/kubevirtbmc). Pushes to `main` are linted and installed into a kind cluster. Pushes to `release` additionally package and publish the chart to the `gh-pages` branch by chart-releaser.
