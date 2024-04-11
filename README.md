# gitops

harness connector --file oms-modernized/harnesscd-pipeline/github-connector.yml apply --git-user fbesnard-dvt --project-id OMS_Modernization
harness connector --file oms-modernized/harnesscd-pipeline/kubernetes-connector.yml apply --delegate-name scaleway-helm-delegate --project-id OMS_Modernization
harness service --file oms-modernized/harnesscd-pipeline/service.yml apply --project-id OMS_Modernization
harness environment --file oms-modernized/harnesscd-pipeline/environment.yml apply --project-id OMS_Modernization
harness infrastructure  --file oms-modernized/harnesscd-pipeline/infrastructure-definition.yml apply --project-id OMS_Modernization
harness pipeline --file oms-modernized/harnesscd-pipeline/canary-pipeline.yml apply --project-id OMS_Modernization
