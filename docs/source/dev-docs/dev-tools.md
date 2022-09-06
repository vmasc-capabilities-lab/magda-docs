# Magda Development Tools

```{toctree}
```

Magda works using API's and Data61 has created multiple command line tools to assist in using Magda. Using these tools requires some setup before and that is the purpose of this document.


1. Be connected to the Magda Kubernetes instance via kubectl. 
    - You can find how to do this [here](http://a4301cbac87c8425588cfd11c344c83d-898319321.us-east-2.elb.amazonaws.com/api/v0/apidocs/index.html#api-Authentication_API)
2. Open a separate terminal and run the command:

    `kubectl port-forward combined-db-0 5432`

Now you are connected to the combined database hosted in AWS EKS and able to use Magda's Tools.


## @magda/org-tree

A set of tools for managing Magda organizational hierarchy.

[NPM Package](https://www.npmjs.com/package/@magda/org-tree)

## @magda/acs-cmd

A set of tools for managing Magda user accounts.

[NPM Package](https://www.npmjs.com/package/@magda/acs-cmd)
