# grafana-ops

IaC ops repo for Grafana

## Workflow editing existing dashboard

-   Obtain grafana service account token from admin

-   Set grizzly context

    ```
    grr config create-context yral
    grr config set grafana.url https://grafana-yral.fly.dev
    grr config set grafana.token <token>
    ```

-   Start preview server

    ```
    grr serve resources
    ```

-   Edit in preview will also make changes to YAML file, make a commit

-   "Deploy dashboards" workflow will automatically run on github

## Workflow for creating new dashboard

-   Create an empty dashboard yaml file (use [this](https://grafana.github.io/grizzly/grafana/#placing-dashboards-in-folders) template)

-   Make a commit

-   Now edit the workflow using editing existing dashboard workflow

## Workflow for syncing from Grafana to repository

- Set targets using `grr config set targets Dashboard,Dashboardfolder,DataSource`

- Pull resources using `grr pull resources`

## References

-   [Grizzly CLI tool](https://www.youtube.com/watch?v=sPD5ZUeoPus&t=287s)

-   [Environment variables](https://grafana.com/docs/grafana/latest/setup-grafana/configure-grafana/)

-   [Deploy as docker container](https://grafana.com/docs/grafana/latest/setup-grafana/installation/docker/)

-   [Google oauth setup](https://grafana.com/docs/grafana/latest/setup-grafana/configure-security/configure-authentication/google/#configure-google-oauth2-authentication)

-   [Service account for big query](https://cloud.google.com/iam/docs/service-accounts-create)

    -   Custom role permissions
        ```
        bigquery.datasets.get
        bigquery.jobs.create
        bigquery.models.export
        bigquery.models.getData
        bigquery.models.getMetadata
        bigquery.models.list
        bigquery.routines.get
        bigquery.routines.list
        bigquery.tables.export
        bigquery.tables.get
        bigquery.tables.getData
        bigquery.tables.list
        resourcemanager.projects.get
        ```
