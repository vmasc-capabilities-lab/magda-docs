# Creating Docker Images and deploying

```{toctree}
```

As shown in [https://github.com/magda-io/magda/blob/master/deploy/helm/internal-charts/web-server/README.md](Web-Server Helm chart config), if you want to change the image of a particular Magda component you need to reference the root repository/organization. When the helm chart is built, it appends the Magda name to the component then retrieve the image.
