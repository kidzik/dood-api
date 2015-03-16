# Category #

| **Field** | **Type** | **Description** |
|:----------|:---------|:----------------|
| name | `String` | category name |
| parent\_id | `Long` | parent ID |
| _photo_ | `String` | URL of file with category icon |

<font color='red'>
<b>Warning:</b> category object doesn't have version field (from header). See <a href='Datatypes#API_Session.md'>API Session</a>.<br>
</font>

**Note:**
  * Categories are organized in a tree structure.
  * There is separate _root_ element for category tree with id=0. Children of `root` will all have `0` object in `parent` field. `root` has parent `null`.
  * `photo` can be either full URL or just location of file in [Photo server](Datatypes#API_Session.md)