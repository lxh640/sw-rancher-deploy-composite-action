# Deploy to Rancher Cluster

### Parameters: 
Name | Type |            | Default |
---  | ---  | ---------- | ------- |
`environment`| String | Required | `dev`
`kube_config_data` | Secret | Required

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
