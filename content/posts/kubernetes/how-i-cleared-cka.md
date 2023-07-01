---
title: "Kubernetes: How I cleared CKA exam?"
date: 2023-06-30T12:13:32+05:30
description: "Certified Kubernetes Administrator"
tags: [kubernetes]
---

## Exam Details

CKA (Certified Kubernetes Administrator) exam is a problem-based exam, and you'll solve those problems right in command line or by writing manifesto files. It is a 2 hours exam, and You will get around 17 questions. 

A passing score is 66%. As per the latest update from CNCF (as of June, 2023), Kubernetes cluster with version v1.27 is used for all clusters in the exam environment.

You can buy exam from [Linux Foundation](https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/) and the best time to buy will be around Black Friday as you get some serious discounts. 

| Topics         |  % Weightage 
|----------------|-----------------------------|
|Troubleshooting cluster, nodes, deployments  |`30%`                        |
|Cluster Architecture, Installation & Configuration|`25%` |         
|Services & Networking        |`20%`|
|Workloads & Scheduling | `15%`|
|Storage | `10%`|

## Exam Terminal Setup

During exam, you will get Linux desktop using remote VDI. You have to work mostly with CLI terminal inside that Linux box. If you're from Linux background, you will find is easy and not much difficult for non Linux users either. 

You are allowed use only 2 reference docs [Kubernetes Docs](https://kubernetes.io/docs) and [Kubernetes Blog](https://kubernetes.io/blog). Please be aware that you can technically access google or other internet sites, but it violates exam code of conduct and then your exam session will be automatically be closed.

## Topics to be focused
  1. Troubleshooting (30%) - covers cluster components/services/deployments/pods failure scenarios.
      - Cluster component failure 
          - pods in kube-system namespace failed/errors out etc
          - API server is down/failed
      - Service endpoint failure or connection errors
      - Understand how to monitor applications
      - Manage container stdout & stderr logs
      - Troubleshoot application failure
      - Troubleshoot cluster component failure
      - Troubleshoot networking

  2. Cluster Architecture, Installation & Configuration (25%) - includes cluster install/setup, join nodes, backup/restore etcd scenarios.
      - Manage role based access control (RBAC)
      - Use Kubeadm to install a basic cluster
      - Manage a highly-available Kubernetes cluster
      - Provision underlying infrastructure to deploy a Kubernetes cluster
      - Perform a version upgrade on a Kubernetes cluster using Kubeadm
      - Implement etcd backup and restore

  3. How to manipulate `kubectl get` command output data using:
      - filtering using `jsonpath`
      - sorting using `--sort-by`
      - custom columns using `--custom-columns`


## Must Read Books 

  1. [Certified Kubernetes Administrator (CKA) Study Guide](https://learning.oreilly.com/library/view/certified-kubernetes-administrator/9781098107215/) from O'Reilly.
  2. [Kubernetes Up and Running](https://learning.oreilly.com/library/view/kubernetes-up-and/9781098110192/) from O’Reilly.


## Lab/Simulator Practices

  1. [CKA Exam Simulator from killer.sh](https://killer.sh/cka) 
      * Must take practice as it provides near real experience of CKA exam and its terminal.  
      * More set of questions with difficulty level equal or higher than the actual exam.
      * Can attempt 2 times and the simulator environment available for 36 hours which is very for getting hands dirty.
      * Solutions for all questions will be available.

  2. [CKA Exam Simulator from killercode.com](https://killercoda.com/killer-shell-cka)
      * Good to practice multiple times and its free.
      * Few sets of questions but good to have. 
   

## Useful Shell Aliases and Environment variables

You will be given a base CLI terminal in your exam and set below aliases, environment variables for faster command execution. Time management is crucial so these shortcuts help a lot. 

```console
$ alias k=kubectl                                               # will already be pre-configured
$ alias kn='kubectl config set-context --current --namespace '  # kn mynamespace
$ alias kp='kubectl get pods'                                   # kp / kp my-pod-name
$ alias kd='kubectl get deploy'                                 # kd / kd my-deploy-name
$ alias ks='kubectl get svc'                                    # ks / kp my-service-name
$ alias ka='kubectl get all'                                    # ka / ka -A
```

```console
$ export dr="--dry-run=client -o yaml"     # k create deploy nginx --image=nginx $dr
$ export now="--force --grace-period 0"    # k delete pod x $now
```

## Tips/Hints for exam

  1. Each question is given a kubernetes context. Please ensure to first set the context before even going through the question.
  2. Each question is given a % mark weightage (i.e ranges between 2% - 13% etc).  So, spend more time on higher weightage questions (i.e mostly troubleshooting, cluster install/setup related questions)
  3. Do not get stuck or spend too much time on a single question. If you start to feel like stuck on a question for more than 5 minutes without any progress, flag (using button at the bottom) that question and move on. 
  4. Tackle the flagged (i.e unsolved) questions at the end.

