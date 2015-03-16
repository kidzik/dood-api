# Location requests #

Content:
  * [Location Get](RequestsLocation#Location_Get.md)

## Location Get ##

| request URL | **(HTTPS)** `/location/get/` |
|:------------|:-----------------------------|
| method | **POST** |
| description | request for [Location object](DatatypesLocation.md). |

<font color='red'>
<b>Warning:</b> Currently we support GET and HTTP in this request<br>
</font>

**Prameters:**
| **parameter** | **type** | **description** | **default** |
|:--------------|:---------|:----------------|:------------|
| `longitude` | `Double` | Longitude |
| `latitude` | `Double` | Latitude |
| `default_city` | String |  | Warszawa |

**Returns data:**

One [Location](DatatypesLocation.md) object.

**Error codes:**

| **API CODE** | **meaning** |
|:-------------|:------------|