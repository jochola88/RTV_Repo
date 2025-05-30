# RTV_Repo
This is a project to the create a data pipeline that enables RTV to track
poverty related household progress metrics overtime
In this pipeline we are using a local setup of postgresql

This pipeline will be composed of 5 schemas in the database namely:
1. external
2. staging
2. base
3. derived
4. final

Below is a description of the different schemas.
1. external schema
This is where all external source data files are are loaded into tables.

2. staging schema 
    In this schema, we prepare and clean the data to make it ready to move down the pipeline.

3. base schema
    This schema contains the base facts and dimensions with data from staging schema.
    Data in this schema is meant to be a reflection of what is in the sources.

4. derived schema
    Data for this schema comes from the tables in the base schema.
    This is where we create the derived facts and dimensions which will be used in our analysis.
    This is where we derive required new facts and carryout all required computations on the data.

5. final schema
    This is where we put store the data that will be visualized.
    It picks it's data from the derived schema.
    In case, all the data from the derived schema is not required for analysis, we just load a slice of it into the
    final schema.

