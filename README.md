# 🥪 The Jaffle Shop 🦘

## Clone

```shell
git clone https://github.com/dbeatty10/jaffle-sl-template.git
cd jaffle-sl-template
```

## Install

Install metricflow, et al within a virtual environment:
```shell
python3 -m venv .env
source .env/bin/activate
python3 -m pip install --upgrade pip
python3 -m pip install --upgrade metricflow~=0.200.0.dev0
python3 -m pip install --upgrade dbt-snowflake~=1.6.0dev0
source .env/bin/activate
dbt --version
mf --version
```

## Test the connection

Either:
1. Update the `profile` within `dbt_project.yml` to refer to one of your pre-existing Snowflake profiles, or
2. Create a profile named `snowflake` in your `profiles.yml`.

```shell
dbt debug
```

## Load data

```shell
dbt deps
dbt seed
```

## Run

```shell
dbt build --exclude path:jaffle-data
mf validate-configs
mf query --metrics large_orders
```
