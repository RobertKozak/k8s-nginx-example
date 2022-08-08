# Kubernetes NGINX Example

A simple NGINX deployment example

in containers folder you will find the two custom containers used for this example:

* nginx - special nginx build as non root
* trivy - used to scan images for CVEs

## Pipeline

The Pipeline is created with 3 bash files:

* build - build custom container images
* deploy - deploy images to kubernetes if no CRITICAL CVEs found. use --force to skip this test
* pipeline

pipeline will call build and then deploy.

### arguments to pipeline and deploy
Use:

--force to skip trivy CVE scan
--show-sbom to display SBOM
--show-all to display the results of deployment

## SBOM

SBOM named sbom-spdx.json can be found in the /tmp folder in spdx-json format.

> **NOTE:**  This example assumes you have jq installed and docker configured and running. It also assumes you have a valid KUBECONFIG file for a kubernetes cluster and kubectl installed.

