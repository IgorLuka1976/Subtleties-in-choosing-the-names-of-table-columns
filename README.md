# Subtleties-in-choosing-the-names-of-table-columns
Subtleties in choosing the names of table columns

Not so long ago I had a problem. A well-functioning procedure stopped working for a long time and began to report errors of a non-existent column.

The reason was the creation of a new table in the same database with the same name, but in a different schema(ex. Not dbo.MyTable  , but Schema2.Mytable).
My procedure was also created in a Schema2.Procedure1, but worked with the table of the dbo.MyTable(schema dbo) . And when a new table(Schema2.Mytable) appeared in the same scheme as my procedure(Schema2.Procedure1)
,and now the procedure(Schema2.Procedure1) was already looking for data in the Schema2.Mytable, Instead of dbo.MyTable .
Here is such a confusion
