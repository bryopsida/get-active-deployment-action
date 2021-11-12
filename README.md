# get-active-deployment-action
Fetches the json information of the active deployment on the provided environment.

## How to use
You can see an example here https://github.com/bryopsida/get-active-deployment-action/blob/main/.github/workflows/test.yaml 

To include in your workflow add the following step

```yaml
      - id: fetch-active-deployment
        uses: bryopsida/get-active-deployment-action@v1
        with:
          owner: '<owner-of-the-replo>'
          repo: '<repo-that-owns-env>'
          environment: '<environment-name>'
          token: ${{ secrets.GITHUB_TOKEN }} || <your custom PAT>
```

The active deployment for that environment is available with this expression `${{ steps.fetch-active-deployment.outputs.deployment }}`.

You can extract individual properties from the deployment information like so `echo '${{ steps.fetch-active-deployment.outputs.deployment }}' | jq '.sha'`
