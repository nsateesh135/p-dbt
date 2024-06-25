# Steps to setup 

1. Install Python 
2. Create a virtual environment 
   ```
   python3 -m venv dbt-tutorial-bigquery
   source dbt-tutorial-bigquery/bin/activate
   pip install --upgrade pip 
   pip install -r requirements.txt

   ```
Note : 
-m flag stands for module, which means you can execute module as script. For example python3 -m http.server

3. Install following VS code extensions 
- DBT Power User 
- Better Jinja 
- Add to GIT Ignore 
- YAML 

3. Set up DBT connection to BigQuery 
- Execute dbt init (To initialise the project)
- Which database would like to use ? : choose bigquery 
- Desired authentication method option (oauth or service_account) : choose service_account 
- keyfile (/path/to/bigquery/keyfile.json): credentials.json(place this in your current directory)
- project (GCP project id): dbt-cloud-355908
- dataset (the name of your dbt dataset): dbt_data_models
- threads (1 or more): 14
- job_execution_timeout_seconds [300]: 4500
- Desired location option (enter a number): choose US
- Profile dbt_tutorial_bigquery written to /Users/nehalkumar/.dbt/profiles.yml using target's profile_template.yml 

4. Install required DBT packages 
- Create a file named packages.yml 
- Add required packages to packages.yml 
- execute ``` dbt deps ```

5. Test DBT - BigQuery Connection 
- execute dbt run --select my_first_dbt_model 
- execute dbt run --select my_second_dbt_model 
- If profile.yml file is in pwd rather than cd execute 
  dbt run --select my_first_dbt_model --profiles-dir . 
  dbt run --select my_first_dbt_model --profiles-dir ./macros

Note - 
How to set up dbt autocomplete? 

1. install bash script from [here](https://github.com/dbt-labs/dbt-completion.bash)

2. ```dbt clean``` (clean logs, target and packages)

3. ```dbt deps``` (intall dbt packages)

4. dbt compile


