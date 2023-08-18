# KUBERNETES MINI-PROJECT

<a href="https://www.youtube.com/watch?v=5cgpFWVD8ds&ab_channel=Alta3Research%2CInc.">
  <img src="https://static1.squarespace.com/static/5df3d8c5d2be5962e4f87890/t/5f1f16257f1289587d71c3e2/1595872810142/ckad+thumbnail.png?format=1500w" alt="Image" width="400">
</a>

> Click the image for Chad's YouTube video on passing the CKAD!


This mini-project has been written to mimic the CKAD Exam! Below are a series of tasks that you are to complete inside your assigned Alta3 machine (the same one you've been using to complete your task.). 

- tasks may be completed in any order!
- tasks are PASS/FAIL- either you meet the criteria of the task or you don't!
- it is VITALLY IMPORTANT that you run the `setup` commands at the beginning of each task, otherwise you will not be able to complete the task.
- you are absolutely allowed to use ANY resources you want to find solutions (`kubernetes.io`, the task., etc.)
- each task has a `teardown` option that will enable you to attempt that task again if need be!
- how you achieve each task **does not matter**- all that matters is that the final product matches the criteria of the task.





## Task 1: API Primitives

<details>
<summary>Click here to view this task!</summary>

### Objectives
In this task, you'll be migrating a **Pod** from one particular **Namespace** to another. This tests our understanding of basic Kubernetes objects like containers, pods, services, and namespaces within a particular namespace. In this task specifically you'll demonstrate how to search for and identify a pod and its namespace, then move it to another namespace. Permitted reference material you can use while taking the **CKAD** exam can be found [here from kubernetes.io](https://kubernetes.io/docs/reference/kubectl/cheatsheet/#viewing-and-finding-resources) -- Good luck!

### Task Setup

1. Run the following command to setup the task.    
    `student@bchd:~$` `drill api-primitives`
    
### Summary

Team Banana is taking over a webserver from Team Pineapple. No one from Pineapple is around anymore, so who knows where this webserver is. The only thing you know is that the Pod is named `apricot`. Search for the correct pod in namespace `pineapple` and migrate it in the namespace `banana`.

   > This involves knowing how to work with basic Kubernetes objects like containers, pods, services, deployments, and namespaces.
   
**Approximate Weight of Actual Exam Grade:** 4%

### Tasks

1. Identify the pod `apricot` in the namespace `pineapple`.
0. Migrate the pod `apricot` from the namespace `pineapple` to the namespace `banana`.
0. Verify the `pod` was migrated successfully.

### Task Re-Do

1. Want to run the task again?? Run the following script to teardown your work.

    `student@bchd:~$` `teardown api-primitives`
   
</details>




   
## Task 2: Pod Basics

<details>
<summary>Click here to view this task!</summary>

### Objectives

In this task. you'll be creating a **Pod** with specific parameters within a particular namespace. This task is testing your ability to, in a timely fashion, piece together a new **pod**. Luckily for us, we have the ability to grab a template pod manifest from our permitted reference materials, so there is no need to memorize everything about how to write a manifest, but it does help. Permitted reference material you can use while taking the **CKAD** exam can be found [here from kubernetes.io](https://kubernetes.io/docs/concepts/workloads/pods/#using-pods) -- Good luck!

### Task Setup

1. Run the following command to setup the task.  

    `student@bchd:~$` `drill pod-basics`

### Summary

Create a single pod in namespace `talent` with the image `nginx:1.7.9`. The pod should be named `singer` and the container should be named `opera`. 

**Approximate Weight of Actual Exam Grade:** 3%

### Tasks

1. Create a Pod manifest as specified in the summary.
0. Persist the manifest to ETCD, having it be built in the `talent` namespace.
0. Verify the Pod was created successfully.

### Task Re-Do

1. Want to run the task again?? Run the following script to teardown your work.
    `student@bchd:~$` `teardown pod-basics`
  
</details>




  
## Task 3: Deployments

<details>
<summary>Click here to view this task!</summary>

### Objectives

In this task. you'll be converting an existing **Pod** into a **Deployment** within a particular namespace. Big considerations for this type of task is knowing and understanding task.ls and selectors. Permitted reference material you can use while taking the **CKAD** exam can be found [here from kubernetes.io](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#creating-a-deployment) -- Good luck!

### Task Setup

1. Run the following command to setup the task.  
    `student@bchd:~$` `drill deploy-rolling-updates`

### Summary

In namespace `mythical-creatures` there is a single pod named `manticore`. Convert the pod into a deployment with 2 replicas with the name `manticore-prime`. Create the deployment and save the YAML manifest as manticore-deployment.yaml.

**Approximate Weight of Actual Exam Grade:** 6%


### Tasks

1. Obtain the `manticore` Pod Manifest.
0. Convert the `manticore` Pod into the `manticore-prime` Deployment in the file `manticore-deployment.yaml`.
0. Create the new Deployment, deleting the old Pod.
0. Verify the work was completed correctly.

### Task Re-Do

1. Want to run the task again?? Run the following script to teardown your work.
    `student@bchd:~$` `teardown deploy-rolling-updates`

</details>





## Task 4: Rollbacks

<details>
<summary>Click here to view this task!</summary>

### Objectives

In this task. you'll be rolling back a **Deployment** to a previously stable version. Deployments come equipped with amazing version control features which allow for rollbacks, and tracking revision history. Knowledge of the **kubectl rollout** command is what's being tested here. Permitted reference material you can use while taking the **CKAD** exam can be found [here from kubernetes.io](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#rolling-back-to-a-previous-revision) -- Good luck!

### Task Setup

1. Run the following command to setup the task.  

    `student@bchd:~$` `drill deploy-rollbacks`

### Summary

There is an existing deployment named `mufasa` in namespace `king-of-lions`. Apparently the current version is broken. Check the deployment history and rollback to a version that actually works.
> Understand Deployments and how to perform rolling rollbacks. You could be given an existing deployment that is already several revisions old. Be prepared to rollback using kubectl to a previous version.

**Approximate Weight of Actual Exam Grade:** 4%

### Tasks

1. Identify the Deployment and view its revision history.
0. Perform the rollback to a version which works.
0. Verify the rollback completed successfully.

### Task Re-Do

1. Want to run the task again?? Run the following script to teardown your work.

    `student@bchd:~$` `teardown deploy-rollbacks`

</details>




## Task 5: ConfigMaps

<details>

<summary>Click here to view this task!</summary>

### Objectives

In this task. you'll create a **ConfigMap** and mount it as a volume to a **Pod**. ConfigMaps are used to pass **Environment Variables** and **Files** to Pods, so they always have the right settings and configurations every time they are built. Permitted reference material you can use while taking the **CKAD** exam can be found [here from kubernetes.io](https://kubernetes.io/docs/concepts/configuration/configmap/) -- Good luck!

### Task Setup

1. Run the following command to setup the task.  

    `student@bchd:~$` `drill configmaps`

### Summary

Create a ConfigMap called `metal-cm` containing the file `~/mycode/yaml/metal.html`. There is an existing manifest for a **Deployment** called `enter-sandman` located at `~/mycode/yaml/enter-sandman.yaml` which you will need to edit to add the `metal-cm` configmap mounted to the path `/var/www/index.html`. Create the deployment in the `metallica` **Namespace**.
> You'll likely be asked to create ConfigMaps, with either files or environment variables inside of them. You'll almost certainly be asked to mount these ConfigMaps as volumes or variables in a container. 

### Tasks

1. Create a ConfigMap as specified in the Summary.
0. Edit the `enter-sandman` manifest to mount the **ConfigMap** as outlined in the Summary.
0. Create the **Deployment** in the `metallica` **Namespace**.
0. Verify the **Deployment** was created successfully with the file mounted correctly.

### Task Re-Do

1. Want to run the task again?? Run the following script to teardown your work.

    `student@bchd:~$` `teardown configmaps`
    
</details>
    
    
    
## Task 6: SecurityContexts

<details>
<summary>Click here to view this task!</summary>
 
## Objectives

In this task. you'll create a **Pod** with a **SecurityContext** within a particular namespace. When taking the CKAD exam, bear in mind that the requirement to create a **SecurityContext** will not be plainly spelled out. Pay attention to the wording of the **Summary** in this one, as it is very similar to what you can expect to see on the exam. Permitted reference material you can use while taking the **CKAD** exam can be found [here from kubernetes.io](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/) -- Good luck!

### Task Setup

1. Run the following command to setup the task.  

    `student@bchd:~$` `drill securitycontexts`

### Summary

Create a pod called `gold-bar` on the `fort-knox` namespace, with the image `busybox:1.34.0` which assigns the Pod Service Account with the user ID `1000` and with the group ID `2000`. Set privilege escalation to false. Name the container `bullion`. Issue the following commands for your busybox container: `sh`, `-c`, and `sleep 1h`.
> If prompted, you would need to assign user, primary group, and/or secondary group processes to a whole Pod or a single container.

**Approximate Weight of Actual Exam Grade:** 5%

### Tasks

1. Create a Pod manifest as described by the task summary.
0. Create the pod in the `fort-knox` namespace.
0. Verify the pod was created successfully, with all of the requested parameters.

### Task Re-Do

1. Want to run the task again?? Run the following script to teardown your work.

    `student@bchd:~$` `teardown securitycontexts`
    
</details>
    
    
## Task 7: Container Logging

<details>
<summary>Click here to view this task!</summary>

### Objectives

In this task. you'll pulling container logs from running pods. On the CKAD it is possible that many tasks have a portion that ask you to generate such logs and put their output in a pre-made text file elsewhere. Permitted reference material you can use while taking the **CKAD** exam can be found [here from kubernetes.io](https://kubernetes.io/docs/reference/kubectl/cheatsheet/#interacting-with-running-pods) -- Good luck!

### Task Setup

1. Run the following command to setup the task.  

    `student@bchd:~$` `drill logging`

### Summary

In namespace `lincoln` there is a single pod named `vampire-hunter`. Output the logs from this Pod but ONLY the lines that contain the word **nginx**. Put these lines inside a file named `lincoln-logs.txt`.

**Approximate Weight of Actual Exam Grade:** 4%

### Tasks

1. Locate the `vampire-hunter` pod in your cluster.
0. Retrieve the logs from the pod's container; ONLY output the lines that contain the word **nginx**.
0. Save this output to `lincoln-logs.txt`.
0. Verify the objectives were completed.

### Task Re-Do

1. Want to run the task again?? Run the following script to teardown your work.

    `student@bchd:~$` `teardown logging`
    
</details>
