# Bull SQLite
Simple Helper Package for using SQLite3 in Python

## Example usage
```python
import bull

# connect(db_name) returns an instance of the Database class
db = bull.Database.connect('example_database_name')
```

### One way of creating a table using `bull.Database.execute()`
```python
create_cats_table_query = 'CREATE TABLE cats(catId INTEGER PRIMARY KEY, catName TEXT NOT NULL);'
db.execute(create_cats_table_query)
```

### Another way of creating the same table using `bull.Database.create_table()`

```python
db.create_table(table_name='cats',
                fields=[
                    bull.Field('catId', bull.Type.INTEGER, bull.ColumnConstraint.PRIMARY_KEY),
                    bull.Field('catName', bull.Type.TEXT, bull.ColumnConstraint.NOT_NULL)
                ])
```
