# InteroperableKotlin

A Google CodeLab at https://codelabs.developers.google.com/codelabs/java-freindly-kotlin

## personal notes

### static

static class vs. static methods / properties
* internals for static 'object' accessed from singleton INSTANCE
* internals (methods / props) are not themselves static
* can generate static methods / props with modifier tag @JvmStatic

### extensions

conversion uses "[...]Kt" file to name java class with exts as static funcs
* resolve java class name to origin filename or
* can define java class name from origin file with tag @file:JvmName([...])
* tag must be stated before file package information

### default param vals

java does not support default param vals
* resolve by adding ctor keyword even if only single class ctor
* precede keyword with @JvmOverloads tag to generate defaults in java calls

### instance methods

conversion renames kotlin get methods to get[Kotlin method name]
* define java method name from kotlin method with JvmName
* with @JvmName tag directly before get(), or
* with @get:JvmName([...]) tag directly before encapsulating property
* latter can be applied to prop with no explicitly defined getter

the same applies for setter methods; resolve with @set

### const

properties exposed from kotlin by setters and getters, including vals
* override by annotating prop with @JvmField to access val directly
* can also use const before val on top-level or in objects

### checked exceptions

kotlin only has unchecked exceptions
* apply @Throws([Exception]::class) before method to inform Java ex checking

---

# Java Friendly Kotlin Codelab

This repository holds the source code for the "Java Friendly Kotlin" Codelab.

Work through the codelab here: [Java Friendly Kotlin][codelab]

## License

Copyright 2019 Google LLC

Licensed to the Apache Software Foundation (ASF) under one or more contridefbutor
license agreements.  See the NOTICE file distributed with this work for
additional information regarding copyright ownership.  The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License.  You may obtain a copy of
the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the
License for the specific language governing permissions and limitations under
the License.

[codelab]: https://codelabs.developers.google.com/codelabs/java-freindly-kotlin