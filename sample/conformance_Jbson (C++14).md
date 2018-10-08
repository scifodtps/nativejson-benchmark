# Conformance of Jbson (C++14)

## 1. Parse Validation


Summary: 34 of 34 are correct.

## 2. Parse Double

* `[2.22507e-308]`
  * expect: `2.2250699999999998e-308 (0x000FFFFE2E8159D0)`
  * actual: `2.2250700000000003e-308 (0x000FFFFE2E8159D1)`

* `[-2.22507e-308]`
  * expect: `-2.2250699999999998e-308 (0x800FFFFE2E8159D0)`
  * actual: `-2.2250700000000003e-308 (0x800FFFFE2E8159D1)`

* `[1e-10000]`
  * expect: `0 (0x0000000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[18446744073709551616]`
  * expect: `1.8446744073709552e+19 (0x43F0000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[-9223372036854775809]`
  * expect: `-9.2233720368547758e+18 (0xC3E0000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[0.9868011474609375]`
  * expect: `0.9868011474609375 (0x3FEF93E000000000)`
  * actual: `0.98680114746093761 (0x3FEF93E000000001)`

* `[45913141877270640000.0]`
  * expect: `4.5913141877270643e+19 (0x4403E961FA3BA6A0)`
  * actual: `0 (0x0000000000000000)`

* `[1e-214748363]`
  * expect: `0 (0x0000000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[1e-214748364]`
  * expect: `0 (0x0000000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[2.2250738585072012e-308]`
  * expect: `2.2250738585072014e-308 (0x0010000000000000)`
  * actual: `2.2250738585072009e-308 (0x000FFFFFFFFFFFFF)`

* `[2.22507385850720113605740979670913197593481954635164565e-308]`
  * expect: `2.2250738585072014e-308 (0x0010000000000000)`
  * actual: `2.2250738585072009e-308 (0x000FFFFFFFFFFFFF)`

* `[0.999999999999999944488848768742172978818416595458984374]`
  * expect: `0.99999999999999989 (0x3FEFFFFFFFFFFFFF)`
  * actual: `1 (0x3FF0000000000000)`

* `[1.00000000000000011102230246251565404236316680908203125]`
  * expect: `1 (0x3FF0000000000000)`
  * actual: `1.0000000000000002 (0x3FF0000000000001)`

* `[1.00000000000000011102230246251565404236316680908203124]`
  * expect: `1 (0x3FF0000000000000)`
  * actual: `1.0000000000000002 (0x3FF0000000000001)`

* `[72057594037927928.0]`
  * expect: `72057594037927928 (0x436FFFFFFFFFFFFF)`
  * actual: `72057594037927920 (0x436FFFFFFFFFFFFE)`

* `[7205759403792793199999e-5]`
  * expect: `72057594037927928 (0x436FFFFFFFFFFFFF)`
  * actual: `0 (0x0000000000000000)`

* `[7205759403792793200001e-5]`
  * expect: `72057594037927936 (0x4370000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[922337203685477529599999e-5]`
  * expect: `9.2233720368547748e+18 (0x43DFFFFFFFFFFFFF)`
  * actual: `0 (0x0000000000000000)`

* `[922337203685477529600001e-5]`
  * expect: `9.2233720368547758e+18 (0x43E0000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[10141204801825834086073718800384]`
  * expect: `1.0141204801825834e+31 (0x465FFFFFFFFFFFFF)`
  * actual: `0 (0x0000000000000000)`

* `[10141204801825835211973625643008]`
  * expect: `1.0141204801825835e+31 (0x4660000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[10141204801825834649023672221696]`
  * expect: `1.0141204801825835e+31 (0x4660000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[1014120480182583464902367222169599999e-5]`
  * expect: `1.0141204801825834e+31 (0x465FFFFFFFFFFFFF)`
  * actual: `0 (0x0000000000000000)`

* `[1014120480182583464902367222169600001e-5]`
  * expect: `1.0141204801825835e+31 (0x4660000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[5708990770823838890407843763683279797179383808]`
  * expect: `5.7089907708238389e+45 (0x496FFFFFFFFFFFFF)`
  * actual: `0 (0x0000000000000000)`

* `[5708990770823839524233143877797980545530986496]`
  * expect: `5.7089907708238395e+45 (0x4970000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[5708990770823839207320493820740630171355185152]`
  * expect: `5.7089907708238395e+45 (0x4970000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[5708990770823839207320493820740630171355185151999e-3]`
  * expect: `5.7089907708238389e+45 (0x496FFFFFFFFFFFFF)`
  * actual: `0 (0x0000000000000000)`

* `[5708990770823839207320493820740630171355185152001e-3]`
  * expect: `5.7089907708238395e+45 (0x4970000000000000)`
  * actual: `0 (0x0000000000000000)`

* `[100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000]`
  * expect: `1e+308 (0x7FE1CCF385EBC8A0)`
  * actual: `0 (0x0000000000000000)`

* `[2.225073858507201136057409796709131975934819546351645648023426109724822222021076945516529523908135087914149158913039621106870086438694594645527657207407820621743379988141063267329253552286881372149012981122451451889849057222307285255133155755015914397476397983411801999323962548289017107081850690630666655994938275772572015763062690663332647565300009245888316433037779791869612049497390377829704905051080609940730262937128958950003583799967207254304360284078895771796150945516748243471030702609144621572289880258182545180325707018860872113128079512233426288368622321503775666622503982534335974568884423900265498198385487948292206894721689831099698365846814022854243330660339850886445804001034933970427567186443383770486037861622771738545623065874679014086723327636718751234567890123456789012345678901e-308]`
  * expect: `2.2250738585072014e-308 (0x0010000000000000)`
  * actual: `2.2250738585072009e-308 (0x000FFFFFFFFFFFFF)`


Summary: 35 of 66 are correct.

## 3. Parse String

* `["Hello\u0000World"]`
  * expect: `"Hello\0World"` (length: 11)
  * actual: `"Hello\u0000World"` (length: 16)


Summary: 8 of 9 are correct.

## 4. Roundtrip

* Fail:
~~~js
[null]
~~~

~~~js
[ null ]
~~~

* Fail:
~~~js
[true]
~~~

~~~js
[ true ]
~~~

* Fail:
~~~js
[false]
~~~

~~~js
[ false ]
~~~

* Fail:
~~~js
[0]
~~~

~~~js
[ 0 ]
~~~

* Fail:
~~~js
["foo"]
~~~

~~~js
[ "foo" ]
~~~

* Fail:
~~~js
[]
~~~

~~~js
[  ]
~~~

* Fail:
~~~js
{}
~~~

~~~js
{  }
~~~

* Fail:
~~~js
[0,1]
~~~

~~~js
[ 0, 1 ]
~~~

* Fail:
~~~js
{"foo":"bar"}
~~~

~~~js
{ "foo" : "bar" }
~~~

* Fail:
~~~js
{"a":null,"foo":"bar"}
~~~

~~~js
{ "a" : null, "foo" : "bar" }
~~~

* Fail:
~~~js
[-1]
~~~

~~~js
[ 5 ]
~~~

* Fail:
~~~js
[-2147483648]
~~~

~~~js
[ ./,),(-*,( ]
~~~

* Fail:
~~~js
[-1234567890123456789]
~~~

~~~js
[ /.-,+*)('0/.-,+*)(' ]
~~~

* Fail:
~~~js
[-9223372036854775808]
~~~

~~~js
[ '..--).0-*(+,))+(0( ]
~~~

* Fail:
~~~js
[1]
~~~

~~~js
[ 1 ]
~~~

* Fail:
~~~js
[2147483647]
~~~

~~~js
[ 2147483647 ]
~~~

* Fail:
~~~js
[4294967295]
~~~

~~~js
[ 4294967295 ]
~~~

* Fail:
~~~js
[1234567890123456789]
~~~

~~~js
[ 1234567890123456789 ]
~~~

* Fail:
~~~js
[9223372036854775807]
~~~

~~~js
[ 9223372036854775807 ]
~~~

* Fail:
~~~js
[0.0]
~~~

~~~js
[ 0.0 ]
~~~

* Fail:
~~~js
[-0.0]
~~~

~~~js
[ 0.0 ]
~~~

* Fail:
~~~js
[1.2345]
~~~

~~~js
[ 1.2345 ]
~~~

* Fail:
~~~js
[-1.2345]
~~~

~~~js
[ -1.2345 ]
~~~

* Fail:
~~~js
[5e-324]
~~~

~~~js
[ 0.0e-324 ]
~~~

* Fail:
~~~js
[2.225073858507201e-308]
~~~

~~~js
[ 2.22507386e-308 ]
~~~

* Fail:
~~~js
[2.2250738585072014e-308]
~~~

~~~js
[ 2.22507386e-308 ]
~~~

* Fail:
~~~js
[1.7976931348623157e308]
~~~

~~~js
[ 1.79769313e308 ]
~~~


Summary: 0 of 27 are correct.
