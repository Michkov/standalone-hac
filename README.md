# Standalone HAC

This repository installs a Stone Soup backend and a HAC UX frontend on a single cluster.

# Installation Steps

You will need a stanalone cluster (clusterbot or a large CRC) with kubeadmin 


1. Pre-Install infra-deployments https://github.com/redhat-appstudio/infra-deployments and wait til completion
2. Create a fork of this repo and clone it. This is required so that the scripts can customize the installation.
3. Set the DOMAIN variable for your cluster eg `export DOMAIN=cluster-hostname`
4. Secrets and config - You will need to create a directory `hack/commit`  (copy `./hack/no-commit-templates`).
You need credentials from your quay.io account in the correct formats and place these in the `commit` directory.
4. Run `./hack/install.sh` and it will install clowder, the applications and a proxy. 

Note, the install will always install from a preview- branch.
This is because it will change the gitops repo to reference the branch and repo itself.
Keeping these changes in a separate branch makes it easier to submit pull requests back to upstream as you separate out repo names and branch names from the upstream which references its own repo and the `main` branch.






 