# Deploy to Rancher Cluster

**Inputs**
```yaml
inputs:    
   labels_path:
    description: 'Location of kubernetes labels'
    required: false
    default: 'kubernetes/labels'
   deployment_yaml_path:
     description: 'Location of the deployment.yml file'
     required: false
     default: 'kubernetes/deployment.yml'
   namespace:
     description: 'Rancher namespace'
     required: true
     default: 'gitactions'
   files:
     description: 'Kubernetes files to apply'
     required: false
     default: 'kubernetes/.'
   environment:
     descripton: 'dev, prod'
     required: true
   kube_config_data:
     description: 'Kube config for rancher cluster'
     required: true
```

Usage:
```yaml
jobs:
  deploy:
    runs-on: sw-ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Deploy Action
        uses: sherwin-williams-co/sw-rancher-deploy-composite-action@main
        with:
          environment: dev
          kube_config_data: ${{ secrets.KUBE_CONFIG_NP_RANCHER }}
```
