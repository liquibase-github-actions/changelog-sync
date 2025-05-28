# Liquibase Changelog Sync Action
Official GitHub Action to run Liquibase Changelog Sync in your GitHub Action Workflow. For more information on how changelog sync works visit the [Official Liquibase Documentation](https://docs.liquibase.com/commands/home.html).
## Changelog Sync
Marks all changes as executed in the database
## Usage
```yaml
steps:
- uses: actions/checkout@v3
- uses: liquibase-github-actions/changelog-sync@v4.32.0
  with:
    # The root changelog file
    # string
    # Required
    changelogFile: ""

    # The JDBC database connection URL
    # string
    # Required
    url: ""

    # Context string to use for filtering
    # string
    # Optional
    contextFilter: ""

    # The default catalog name to use for the database connection
    # string
    # Optional
    defaultCatalogName: ""

    # The default schema name to use for the database connection
    # string
    # Optional
    defaultSchemaName: ""

    # The JDBC driver class
    # string
    # Optional
    driver: ""

    # The JDBC driver properties file
    # string
    # Optional
    driverPropertiesFile: ""

    # Label expression to use for filtering
    # string
    # Optional
    labelFilter: ""

    # Password to use to connect to the database
    # string
    # Optional
    password: ""

    # Username to use to connect to the database
    # string
    # Optional
    username: ""

```

### Secrets
It is a good practice to protect your database credentials with [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Optional Liquibase Global Inputs
The liquibase changelog sync action accepts all valid liquibase global options as optional parameters. A full list is available in the official [Liquibase Documentation](https://docs.liquibase.com/parameters/command-parameters.html).

### Example
```yaml
steps:
  - uses: actions/checkout@v3
  - uses: liquibase-github-actions/changelog-sync@v4.32.0
    with:
      changelogFile: ""
      url: ""
      headless: true
      licenseKey: ${{ secrets.LIQUIBASE_LICENSE_KEY }}
      logLevel: INFO
```

## Feedback and Issues
This action is automatically generated. Please submit all feedback and issues with the [generator repository](https://github.com/liquibase/github-action-generator/issues).
