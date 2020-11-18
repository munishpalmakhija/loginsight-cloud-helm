# loginsight-cloud-helm

This repo contains helm charts to push Kubernetes Logs to vRealize Log Insight Cloud by default fluentd daemonset. 

# Pre-requisities 

You need to have following pre-requisties 

1.	vRealize LogInsight Cloud API Token 
2.	Helm Version = '3.x'
3.  Admin access to the Kubernetes Cluster

# Installing the Chart - Procedure 1 

## Add Chart Repo 

| helm repo add loginsight-cloud https://munishpalmakhija.github.io/loginsight-cloud-helm/ |


## Get Values file in your working directory 

| helm show values loginsight-cloud/loginsight-cloud-helm  > values.yaml |

## Update Values file with API Token and other relevant details.  

| cat values.yaml |

## Install Chart.  

| helm install test-vrlic loginsight-cloud/loginsight-cloud-helm -f values.yaml |

## Verify Kubernetes Pods  

| kubectl get pods -A | grep test-vrlic |

## Verify Helm Release 

| helm list |


# Installing the Chart - Procedure 2

## Add Chart Repo 

| helm repo add loginsight-cloud https://munishpalmakhija.github.io/loginsight-cloud-helm/ |


## Install Chart by setting values during run time.  

| helm install test-vrlic loginsight-cloud/loginsight-cloud-helm --set vrlic.apiKey=SETME --set tag.environment=DEMO |

## Verify Kubernetes Pods  

| kubectl get pods -A | grep test-vrlic |

## Verify Helm Release 

| helm list |