## Installing dbt

1. Activate your venv and run `pip3 install dbt`
1. Copy `airbyte-normalization/sample_files/profiles.yml` over to `~/.dbt/profiles.yml`
1. Edit to configure your profiles accordingly

## Running dbt

1. `cd airbyte-normalization`
1. You can now run dbt commands, to check the setup is fine: `dbt debug`
1. To build the dbt tables in your warehouse: `dbt run`

## Running dbt from Airbyte generated config

1. You can also change directory (`cd /tmp/dev_root/workspace/1/0/normalize` for example) to one of the workspace generated by Airbyte within one of the `normalize` folder.
1. You should find `profiles.yml` and a bunch of other dbt files/folders created there.
1. To check everything is setup properly: `dbt debug --profiles-dir=$(pwd) --project-dir=$(pwd)`
1. You can modify the `.sql` files and run `dbt run --profiles-dir=$(pwd) --project-dir=$(pwd)` too
1. You can inspect compiled dbt `.sql` files before they are run in the destination engine in `normalize/build/compiled` or `normalize/build/run` folders# airbyte-poc
