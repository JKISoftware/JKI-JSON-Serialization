![JKI JSON](https://github.com/JKISoftware/JKI-JSON-Serialization/raw/master/img/json.png)
# JKI JSON

JKI JSON is a library for flattening LabVIEW data to JSON strings and for unflattening JSON strings back to LabVIEW data.
This library extends LabVIEW's native JSON serialization with powerful features such as ability to unflatten JSON strings directly
to LabVIEW variants, a feature that is useful when building reusable software components. Furthermore JKI JSON serialization
library allows unflattening the same JSON string into different LabVIEW data structures allowing for example unflattening
of a fixed length JSON array into a LabVIEW cluster.

## Installation

You can download and install JKI JSON with VI Package Manager.

[Get JKI JSON Serialization](http://vipm.jki.net/#!/package/jki_lib_json_serialization)

## Usage
JKI JSON is a LabVIEW toolkit providing a library of VIs for flattening LabVIEW data type
into JSON strings and unflattening JSON strings into LabVIEW data types.

### Palette
To use unit JKI JSON, you need to drop the corresponding JKI JSON toolkit
VIs to the block diagrams. The JKI JSON toolkit VIs are located under the JKI Tools functions
palette menu.

![Functions palette](https://github.com/JKISoftware/JKI-JSON-Serialization/raw/master/img/JSON-Palette.png "Functions palette")

### Basic Workflow
The toolkit provides a VI for flattening LabVIEW data to JSON strings and another VI for unflattening
JSON strings back to LabVIEW data. The basic workflow is presented in the image below.

![Basic workflow](https://github.com/JKISoftware/JKI-JSON-Serialization/raw/master/img/Flatten-Unflatten-JSON-String.png "Basic workflow")

### Flatten to JSON String
Flatten to JSON String VI is used to flatten a LabVIEW data to a JSON string.

![Flatten to JSON String](https://github.com/JKISoftware/JKI-JSON-Serialization/raw/master/img/Flatten-To-JSON-String.png "Flatten to JSON String")

The VI provides multiple arguments for defining how to flatten the LabVIEW data to JSON string.

**Numeric Extensions** when true will treat positive and negative infinity as well as non-a-number as symbols. This is not compatible with JSON standard but is supported with many JSON implementations.

**Multiline** when true will generate a human readable multi-line JSON string. When false the JSON document will be in a compact form and fitted to a single line. This is recommended for over-the-network interfaces as well as applications that require single line JSON documents.

**Covert Timestamps** when true allow converting LabVIEW timestamps into ISO 8601 compatible timestamp strings.

**Covert Timestamps** when true set the UTC timezone to be used for timestamp conversions instead of local time. In both cases timestamp is unique and can be unflattened properly in a different timezone.

**Enums As Strings** when true will flatten LabVIEW enums to JSON strings. When false enums will be flattened to numbers.

### Unflatten from JSON String
Unflatten from JSON String VI is used to unflatten JSON string to LabVIEW data.

![Unflatten from JSON String](https://github.com/JKISoftware/JKI-JSON-Serialization/raw/master/img/Unflatten-From-JSON-String.png "Unflatten from JSON String")

The VI provides few arguments for defining how to flatten the LabVIEW data to JSON string.

**Type and Defaults** when set will provide LabVIEW a hint of the data type to be used for unflattening the data from a JSON string. If not provided, LabVIEW will use default data type mapping. Many JSON types support multiple LabVIEW representations. The default value of cluster elements will be used if not found in the JSON object.

_Numbers_: JSON numbers can be unflattened to all numeric LabVIEW types.

_Enums_: JSON strings and numbers can be unflattened to LabVIEW enum values.

_Paths_: JSON strings can be unflattened to LabVIEW paths.

_Timestamps_: JSON strings can be unflattened to LabVIEW timestamps.

_Arrays_: JSON arrays and clusters can be unflattened to LabVIEW arrays.

_Clusters_: JSON clusters and arrays can be unflattened to LabVIEW clusters.

**Nulls as Defaults** when true will replace null values with default values as defined using the Type and Defaults input. When false will unflatten null values to the values for each data type that best correspond to JSON null values.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

To contribute to JKI JSON, you will need 32-bit LabVIEW 2013 f2 professional development environment.

## Credits

JKI JSON is an open source project maintained by [JKI](http://jki.net).

## License

JKI JSON is distributed under the open source three clause BSD license providing everyone right to use and distribute both souce code
and compiled versions of JKI JSON. See LICENSE.md file for details.
