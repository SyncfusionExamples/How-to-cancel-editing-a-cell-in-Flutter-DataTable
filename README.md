# How to cancel editing a cell in Flutter DataTable (SfDataGrid)?

In this article, we will show how to cancel editing a cell in [Flutter DataTable](https://www.syncfusion.com/flutter-widgets/flutter-datagrid).

Initialize the [SfDataGrid](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/SfDataGrid-class.html) widget with the necessary properties. The [DataGridSource.onCellBeginEdit](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/DataGridSource/onCellBeginEdit.html) method is called when a cell enters edit mode. This method provides the row, rowColumnIndex, and column as parameters. You can use these parameter values to determine whether editing should proceed. Return false if you want to prevent specific cells from entering edit mode

```dart
@override
  bool onCellBeginEdit(
    DataGridRow dataGridRow,
    RowColumnIndex rowColumnIndex,
    GridColumn column,
  ) {
    if (column.columnName == 'ID') {
      if (rowColumnIndex.columnIndex == 0 && rowColumnIndex.rowIndex == 2) {
        return false;
      }
    }
    return true;
  }
```

You can download this example on [GitHub](https://github.com/SyncfusionExamples/How-to-cancel-editing-a-cell-in-Flutter-DataTable).