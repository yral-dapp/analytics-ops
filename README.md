# grafana-ops

IaC ops repo for Grafana

## Grizzly dashboard editing workflow

-   Set grizzly context
-   Use grizzly serve
-   Use grizzly apply (if creating a new dashboard, make sure to have no other uncommitted changes)
-   Edit in preview and make commit

## References

-   [Grizzly CLI tool](https://grafana.github.io/grizzly/workflows/)

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
