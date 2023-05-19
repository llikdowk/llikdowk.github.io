# UPROPERTY attributes

## Meta attributes

### RowType
This limites the scope of the possible selectable rows for a `FDataTableRowHandle` type.

Example: 
```
UPROPERTY(EditDefaultsOnly, meta=(RowType = "/Script/CommonUI.CommonInputActionDataBase"))
FDataTableRowHandle ApplyInputActionData;
```
