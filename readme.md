# Deploying Dockerized App on AWS EKS Cluster using ArgoCD and GitOps methodology with CircleCI

✨This repository contains the code of the kubernetes manifest files.

## Architecture
 <img width="659" alt="image" src="https://github.com/satyam19arya/K8s_EKS_yaml_manifest/assets/77580311/97f426b1-92c1-4554-b5d4-c60c8105d999">


## Execution steps
When CircleCI notices any changes in the application code, it starts executing the jobs that we have set up. There are a total of four jobs.

### Test
- This job tests the code. After the test job is completed, CircleCI proceeds to the next job. 

### Build
- In the build job, CircleCI pulls the base Docker images and packages our application code inside the image.

### Push
- The push job pushes the newly generated image to DockerHub with a new tag.

### Update Manifest
- After the successful completion of the push job,now the last job is executed which updates the Kubernetes manifest repository with the new tag. This enables ArgoCD to detect the change and apply it to the cluster.

By following this pipeline, we ensure that our application code is thoroughly tested, built into Docker images, and deployed with the updated manifest using the GitOps approach.
