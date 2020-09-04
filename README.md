# csp-config-management
Anthos Configuration Management Directory

Installation

STEP 1 - INSTALL NOMOS:

References:
https://cloud.google.com/anthos-config-management/docs/how-to/nomos-command#installing
https://cloud.google.com/anthos-config-management/downloads

WINDOWS:

gsutil cp gs://config-management-release/released/latest/windows_amd64/nomos.exe nomos.exe

LINUX:

gsutil cp gs://config-management-release/released/latest/linux_amd64/nomos nomos

MAC:

gsutil cp gs://config-management-release/released/latest/darwin_amd64/nomos nomos

chmod +x ./nomos

STEP 2 - INSTALL OPERATOR:

References:
https://cloud.google.com/anthos-config-management/docs/how-to/installing#installing

gsutil cp gs://config-management-release/released/latest/config-management-operator.yaml config-management-operator.yaml

kubectl apply -f config-management-operator.yaml


STEP 3 - CONFIGURATE OPERATOR:

References:
https://cloud.google.com/anthos-config-management/docs/how-to/installing#configuring-config-management-operator

FOR DEV ENV:
kubectl apply -f dev-config-management-operator.yaml

FOR PROD ENV:
kubectl apply -f prod-config-management-operator.yaml

STEP 3 - VERIFY INSTALLATION

./nomos status
