# Deploy to Rancher Cluster

### Parameters: 
Name | Type |        | Default |
---  | ---  | ---------- | ------- |
`environment` | String | Required* | `dev`
`np_kube_config_data` | Secret | Required* |
`prod_kube_config_data` | Secret | Required* |
`jf_artifactory_token` | Secret | Required* |
`labels_path`| String | *Optional* | 
`deployment_yaml_path` | String | *Optional* | `kubernetes/deployment.yml`
`namespace` | String | *Optional* | `gitactions`
`files`| String | *Optional* | `kubernetes/.`

Usage:
```yaml
      - uses: sherwin-williams-co/sw-rancher-deploy-composite-action@main
        with:
          environment: dev
          np_kube_config_data: ${{ secrets.KUBE_CONFIG_NP_RANCHER }}
          prod_kube_config_data: ${{ secrets.KUBE_CONFIG_PROD_RANCHER }}
          jf_arttifactory_token: ${{ secrets.JF_ARTIFACTORY_TOKEN }}
          # Optional
          # labels_path: 'kubernetes/labels'
          # deployment_yaml_path: 'kubernetes/deployment.yml'
          # namespace: 'gitactions'
          # files: 'kubernetes/.'
```
