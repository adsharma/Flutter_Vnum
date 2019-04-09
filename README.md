# Vnum

A library that enables value based enum  behaviour using classes in flutter

## Usage


New Vnums:
```dart
import 'package:vnum/vnum.dart';
```

Sample definition:
```dart
@EnumReflectable
class CarType extends VNum<String> {
  static final CarType sedan = CarType.define("sedan-value");
  static final CarType suv = CarType.define("suv-value");
  static final CarType truck = CarType.define("truck-value");
  static final CarType none = CarType.define("value-none");
  CarType.define(String fromValue) : super.define(fromValue);
  factory CarType(String value) => VNum.fromValue(value,CarType);
}
```

Instantiate:

```dart
var car = CarType.sedan;
var carValue = car.value;
var carFromValue = CarType('suv-value');
```

Comparison:
```dart
var sedan = CarType.sedan;
var truck = CarType.truck
print(sedan == truck);
```



### For implementation:

* Json Serialization