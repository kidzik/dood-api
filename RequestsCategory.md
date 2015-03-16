# Category requests #

Content:

  * [Category Get](RequestsCategory#Category_Get.md)

## Category Get ##
| request URL | **(HTTP)** `/category/get/` |
|:------------|:----------------------------|
| method | **GET** |
| description | Get children of category with given `parent_id`,whole list all together or specific (listed) objects |

**Prameters:**

| **parameter** | **type** | **description** |
|:--------------|:---------|:----------------|
| `session_key` | String | User's current session key |
| `parent_id`  | `Long` | Get children of category with given `parent_id` |
| `get_all` | Boolean | If `true` give all category objects |
| `get_top` | Boolean | If `true` give all category objects from the top level (not implemented yet) |

<a href='Hidden comment: 
has-version - <font color="red"> NOT SUPPORTED YET. 

Unknown end tag for &lt;/font&gt;

 Client admits having category tree of given version. Server will update client"s tree and try to limit the transfer. All retrieved objects should overwrite existing ones
'></a>

_**Note:**_
  * `parent_id=NULL` means children of `root` category element

**Returns:**

[Category](DatatypesCategory.md) structures.