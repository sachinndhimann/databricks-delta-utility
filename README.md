
![GitHub](https://img.shields.io/github/license/sachinndhimann/databricks-delta-utility/)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/sachinndhimann/databricks-delta-utility/)

## Overview

This Python package designed to simplify Delta table management on Databricks. It provides functionalities to create, read, update, and delete Delta tables, with parameterization for table names, prefix, and suffix. The package also auto-detects the Databricks workspace and current user.

## Features

- Create Delta tables with customizable names.
- Delete Delta tables with error checking and exception handling.
- List existing Delta tables.
- Auto-detect Databricks workspace and current user.
- Parameterization for table names, prefix, and suffix.
- Use of a `config.json` file to store transactions and metadata.

## Installation

```bash
pip install my-databricks-package

#Usage
from my_databricks.my_databricks.dbdelta_manager import DatabricksDeltaTableManager
from pyspark.sql import SparkSession

# Create a Spark session
spark = SparkSession.builder.appName("MyDatabricksApp").getOrCreate()

# Create an instance of DatabricksDeltaTableManager
manager = DatabricksDeltaTableManager(spark_session=spark, mount_path="/mnt/delta_tables")

# Example usage:
manager.create_delta_table("example_table", suffix="v1", prefix="prod")
manager.delete_delta_table("prod_example_table_v1")
tables = manager.list_delta_tables()
print(tables)

#Configuration
The package uses a config.json file to store transactions and metadata. The file is stored in the specified mount path.

#Contributing
Contributions are welcome! Please follow the contribution guidelines when submitting pull requests.

#License
This project is licensed under the MIT License - see the LICENSE file for details.
