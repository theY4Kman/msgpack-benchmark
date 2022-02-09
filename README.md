# msgpack benchmarks for JavaScript

[![Build Status](https://travis-ci.org/endel/msgpack-benchmark.svg?branch=master)](https://travis-ci.org/endel/msgpack-benchmark)

This repository aims to benchmark each msgpack implementation for JavaScript.

There is four input files to encode/decode.

- [datatypes](sample-datatypes.json) - 1305 bytes
- [small](sample-small.json) - 68 bytes
- [medium](sample-medium.json) - 250 bytes
- [large](sample-large.json) - 9237 bytes
- [huge](sample-huge.json) - 139775933 bytes (139.78 MB)

MsgPack implementations:

- [msgpack](https://www.npmjs.com/package/msgpack)
- [msgpack-javascript](https://github.com/msgpack/msgpack-javascript)
- [msgpack-js-v5](https://www.npmjs.com/package/msgpack-js-v5)
- [msgpack-lite](https://www.npmjs.com/package/msgpack-lite)
- [msgpack5](https://www.npmjs.com/package/msgpack5)
- [notepack](https://www.npmjs.com/package/notepack)
- [notepack.io](https://www.npmjs.com/package/notepack.io)

Other serialization methods for comparison:

- [cbor](https://github.com/hildjj/node-cbor)
- [cbor-js](https://github.com/paroga/cbor-js)

## Benchmarks

Results are using Node v16.13.2 on Ryzen 3950X (3.8GHz)

**sample-datatypes.json:**

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|encode|@msgpack/msgpack|174,791|±0.72%|94|
|encode|msgpack-js-v5|25,558|±77.51%|96|
|encode|msgpack-lite|102,248|±1.64%|90|
|encode|msgpack5|42,269|±0.85%|95|
|encode|notepack|171,577|±0.64%|91|
|encode|notepack.io|193,885|±0.23%|99|
|encode|notepack.io (browser)|143,281|±0.28%|97|
|encode|what-the-pack|165,998|±0.90%|96|
|encode|what-the-pack (browser)|180,841|±0.96%|92|
|encode|cbor (node)|16,436|±9.28%|87|
|encode|cbor (browser)|57,386|±0.37%|96|
|encode|JSON|255,245|±0.19%|98|

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|decode|@msgpack/msgpack|152,050|±0.61%|91|
|decode|msgpack-js-v5|80,645|±0.79%|93|
|decode|msgpack-lite|55,101|±0.59%|91|
|decode|msgpack5|40,439|±0.37%|94|
|decode|notepack|98,319|±0.35%|93|
|decode|notepack.io|155,562|±0.31%|94|
|decode|notepack.io (browser)|101,453|±0.37%|95|
|decode|what-the-pack|96,280|±0.65%|96|
|decode|what-the-pack (browser)|98,164|±0.39%|95|
|decode|cbor (node)|11,685|±0.99%|88|
|decode|cbor (browser)|68,160|±0.32%|94|
|decode|JSON|332,022|±0.33%|98|

**sample-small.json:**

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|encode|@msgpack/msgpack|472,268|±2.25%|77|
|encode|msgpack-js-v5|351,161|±0.24%|98|
|encode|msgpack-lite|312,612|±2.09%|78|
|encode|msgpack5|207,986|±0.52%|96|
|encode|notepack|1,403,432|±0.39%|94|
|encode|notepack.io|1,435,511|±0.34%|95|
|encode|notepack.io (browser)|830,007|±2.18%|79|
|encode|what-the-pack|1,121,809|±0.42%|96|
|encode|what-the-pack (browser)|1,267,577|±0.33%|99|
|encode|cbor (node)|51,483|±17.52%|67|
|encode|cbor (browser)|306,793|±2.31%|78|
|encode|JSON|1,806,808|±0.31%|95|

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|decode|@msgpack/msgpack|1,083,844|±0.68%|90|
|decode|msgpack-js-v5|779,369|±0.48%|93|
|decode|msgpack-lite|440,722|±0.25%|92|
|decode|msgpack5|281,712|±0.38%|93|
|decode|notepack|1,188,419|±0.49%|92|
|decode|notepack.io|1,415,231|±0.80%|92|
|decode|notepack.io (browser)|1,196,057|±0.62%|93|
|decode|what-the-pack|999,761|±0.55%|92|
|decode|what-the-pack (browser)|997,970|±0.45%|93|
|decode|cbor (node)|59,506|±0.80%|87|
|decode|cbor (browser)|704,485|±0.46%|94|
|decode|JSON|1,631,474|±0.59%|94|

**sample-medium.json:**

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|encode|@msgpack/msgpack|385,880|±2.60%|83|
|encode|msgpack-js-v5|98,780|±0.95%|89|
|encode|msgpack-lite|202,084|±2.60%|77|
|encode|msgpack5|104,614|±0.21%|93|
|encode|notepack|373,992|±1.37%|84|
|encode|notepack.io|537,280|±0.27%|94|
|encode|notepack.io (browser)|366,514|±1.02%|81|
|encode|what-the-pack|424,124|±0.78%|95|
|encode|what-the-pack (browser)|487,037|±0.90%|95|
|encode|cbor (node)|38,783|±1.28%|86|
|encode|cbor (browser)|171,019|±1.42%|87|
|encode|JSON|936,106|±0.53%|92|

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|decode|@msgpack/msgpack|458,744|±0.42%|94|
|decode|msgpack-js-v5|225,114|±0.96%|94|
|decode|msgpack-lite|129,651|±0.76%|87|
|decode|msgpack5|102,372|±0.40%|90|
|decode|notepack|297,672|±0.99%|90|
|decode|notepack.io|536,964|±0.94%|92|
|decode|notepack.io (browser)|328,100|±0.56%|90|
|decode|what-the-pack|300,185|±0.96%|91|
|decode|what-the-pack (browser)|297,144|±0.99%|91|
|decode|cbor (node)|23,847|±1.23%|86|
|decode|cbor (browser)|244,330|±0.63%|89|
|decode|JSON|917,510|±0.68%|91|

**sample-large.json:**

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|encode|@msgpack/msgpack|22,890|±1.38%|92|
|encode|msgpack-js-v5|4,814|±1.01%|94|
|encode|msgpack-lite|14,131|±1.61%|86|
|encode|msgpack5|6,991|±0.67%|96|
|encode|notepack|17,796|±0.72%|93|
|encode|notepack.io|19,106|±0.72%|91|
|encode|notepack.io (browser)|18,455|±0.93%|95|
|encode|what-the-pack|20,498|±1.01%|97|
|encode|what-the-pack (browser)|23,014|±1.07%|96|
|encode|cbor (node)|2,926|±1.11%|90|
|encode|cbor (browser)|6,621|±0.79%|76|
|encode|JSON|38,728|±0.32%|96|

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|decode|@msgpack/msgpack|12,008|±0.84%|63|
|decode|msgpack-js-v5|10,578|±1.01%|93|
|decode|msgpack-lite|6,187|±0.70%|90|
|decode|msgpack5|5,514|±0.75%|87|
|decode|notepack|13,887|±0.79%|89|
|decode|notepack.io|20,844|±0.58%|90|
|decode|notepack.io (browser)|8,706|±0.88%|62|
|decode|what-the-pack|13,787|±1.08%|88|
|decode|what-the-pack (browser)|13,961|±0.81%|92|
|decode|cbor (node)|1,194|±2.20%|69|
|decode|cbor (browser)|7,392|±0.75%|69|
|decode|JSON|48,048|±1.00%|92|

**sample-huge.json:**

NOTE: what-the-pack and cbor are omitted, due to errors!

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|encode|@msgpack/msgpack|2.77|±25.17%|12|
|encode|msgpack-js-v5|6.72|±2.05%|22|
|encode|msgpack-lite|11.45|±4.75%|32|
|encode|msgpack5|12.87|±4.47%|26|
|encode|notepack|16.78|±0.89%|34|
|encode|notepack.io|16.89|±1.15%|32|
|encode|notepack.io (browser)|1.68|±2.24%|9|
|encode|JSON|2.21|±6.14%|10|

|type|library|ops/sec|variance|# runs|
|-|-|-:|-:|-:|
|decode|@msgpack/msgpack|6.13|±1.48%|20|
|decode|msgpack-js-v5|21.22|±9.70%|41|
|decode|msgpack-lite|22.90|±7.49%|41|
|decode|msgpack5|23.20|±8.20%|41|
|decode|notepack|20.06|±11.36%|40|
|decode|notepack.io|23.15|±7.91%|41|
|decode|notepack.io (browser)|0.06|±6.44%|5|
|decode|JSON|6.33|±0.71%|20|

## Running the benchmarks:

```
yarn install
yarn start
```

## License

MIT
