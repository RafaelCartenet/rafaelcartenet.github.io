---
layout: single
title:  "Spark"
date:   2018-08-07 22:30:00 -0600
author_profile: true
excerpt_separator: "<!--more-->"
header:
  overlay_image: /images/paris.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
---

WORK IN PROGRESS

<!--more-->

<img src="/images/Apache_Spark_logo.png" alt="apache spark" class="inline"/>



This is a simple spark cheatsheet I made when I learnt to use it for some Extract-Transform-Load operations.


```py

```


```py
```
# General

### Import sql functions
```py
import pyspark.sql.functions as F
```

## Object Transformations

**Transform to Pandas dataframe**
```py
import pandas as pd

def _map_to_pandas(rdds):
    """ Needs to be here due to pickling issues """
    return [pd.DataFrame(list(rdds))]

def toPandas(df, n_partitions=None):
    """
    Returns the contents of `df` as a local `pandas.DataFrame` in a speedy fashion. The DataFrame is
    repartitioned if `n_partitions` is passed.
    :param df:              pyspark.sql.DataFrame
    :param n_partitions:    int or None
    :return:                pandas.DataFrame
    """
    if n_partitions is not None: df = df.repartition(n_partitions)
    df_pand = df.rdd.mapPartitions(_map_to_pandas).collect()
    df_pand = pd.concat(df_pand)
    df_pand.columns = df.columns
    return df_pand
```

**Transform to list**
```py
# To extract the column 'column' from the pyspark dataframe df
mylist = [row.column for row in df.collect()]
```

## Type transformations

**Types**:
- BinaryType – Binary data.
- BooleanType – Boolean values.
- ByteType – A byte value.
- DateType – A datetime value.
- DoubleType – A floating-point double value.
- IntegerType – An integer value.
- LongType – A long integer value.
- NullType – A null value.
- ShortType – A short integer value.
- StringType – A text string.
- TimestampType – A timestamp value (typically in seconds from 1/1/1970).
- UnknownType – A value of unidentified type.

How to import a type
```py
# To import integer type
from pyspark.sql.types import IntegerType
```


How to cast:
```py
# To cast to double
F.col('mycolumn').cast(DoubleType())
```

String type to date type
```py
F.to_date(F.unix_timestamp('date', 'yyyy-MM-dd').cast("timestamp"))
```

## Join

**Inner join**

```py
df_joined = df_A.join(df_B, df_A.KEY_A == df_B.KEY_B, how='inner')
```

where KEY_A is the key to join A from and KEY_B is the key to join B from.

**Left/Right join**

```py
df_joined = df_A.join(df_B, df_A.KEY_A == df_B.KEY_B, how='right')
df_joined = df_A.join(df_B, df_A.KEY_A == df_B.KEY_B, how='left')
```

# TO CLASSIFY

### MAPPING DICT
To apply a mapping to a column given a dataframe and a mapping as a dictionary
```py
from itertools import chain

mapping = {
  'old_value1': 'new_value1',
  'old_value2': 'new_value2'
}

mapping_expr = F.create_map([F.lit(x) for x in chain(*mapping.items())])

df.withColumn("mapped_valule", mapping_expr.getItem(F.col("value")))
```

## Where function

### is equal / not equal
```py
# keep rows where column 'int_column' values are equal to integer 5.
F.where(F.col('int_column') == 5)

F.where(F.col('date_column') < '2018/12/05')

# keep rows where column 'bool_column' values are equal to boolean True.
F.where(F.col('bool_column') == True)
```

### is in / not in list
```py
my_list = [5, 23, 7]

# keep rows
F.where(F.col('value').isin(my_list))

# skip rows Where
F.where(~F.col('value').isin(my_list))
```

## Window

```py
from pyspark.sql.window import Window
window = Window.partitionBy(df['category']).orderBy(df['revenue'].desc()).rangeBetween(-sys.maxsize, sys.maxsize)
```



## Rename column
df.withColumnRenamed("colName", "newColName")


## Add time to timestamp
```py
df.withColumn('new_timestamp', F.col('timestamp') + F.expr('INTERVAL 2 HOURS'))
```

### CREATE UDF FUNCTION
```py
square_udf_int = udf(lambda z: square(z), IntegerType())
```
