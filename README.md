# Guía de Instalación de CSP-Config-Management en Google Kubernetes Engine

## Paso 1 - Instalar Nomos.

Referencias:
https://cloud.google.com/anthos-config-management/docs/how-to/nomos-command#installing
https://cloud.google.com/anthos-config-management/downloads

WINDOWS:

```
gsutil cp gs://config-management-release/released/latest/windows_amd64/nomos.exe nomos.exe
```

LINUX:

```
gsutil cp gs://config-management-release/released/latest/linux_amd64/nomos nomos
```

MAC:

```
gsutil cp gs://config-management-release/released/latest/darwin_amd64/nomos nomos
```

```
chmod +x ./nomos
```

## Paso 2 - Instalar el Operador de CSP Config Management en el cluster de Kubernetes mediante el comando kubectl.

Referencias:
https://cloud.google.com/anthos-config-management/docs/how-to/installing#installing

```
gsutil cp gs://config-management-release/released/latest/config-management-operator.yaml config-management-operator.yaml
```

```
kubectl apply -f config-management-operator.yaml
```

## Paso 3 - Configurar el Operador.

Referencias:
https://cloud.google.com/anthos-config-management/docs/how-to/installing#configuring-config-management-operator

Ejemplo ambiente de desarrollo:

Configración del Operador: https://github.com/gdgcloudsantiagoapp/csp-config-management/blob/master/dev-config-management-operator.yaml

```
kubectl apply -f dev-config-management-operator.yaml
```

Ejemplo ambiente productivo:

Configración del Operador: https://github.com/gdgcloudsantiagoapp/csp-config-management/blob/master/prod-config-management-operator.yaml

```
kubectl apply -f prod-config-management-operator.yaml
```

## Paso 4 - Verificar instalación y configuración del operador.

```
./nomos status
```
