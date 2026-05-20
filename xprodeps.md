# rapidjson dependencies

|project|license [^_l]|description [dependencies]|version|source|diff [^_d]|
|-------|-------------|--------------------------|-------|------|----------|
|<a id='rapidjson' />[rapidjson](http://Tencent.github.io/rapidjson/)|[MIT](https://raw.githubusercontent.com/Tencent/rapidjson/master/license.txt 'MIT License')|A fast JSON parser/generator for C++ with both SAX/DOM style API [pvt deps: _googletest_]| |[upstream](https://github.com/Tencent/rapidjson 'github.com/Tencent/rapidjson')|  [patch]|
|<a id='googletest' />[googletest](https://google.github.io/googletest/)|[BSD-3-Clause](https://github.com/google/googletest/blob/master/LICENSE 'BSD 3-Clause New or Revised License')|GoogleTest - Google Testing and Mocking Framework [deps: _Threads_]|[xpv1.16.0.6](https://github.com/externpro/googletest/releases/tag/xpv1.16.0.6 'release')|[repo](https://github.com/externpro/googletest 'github.com/externpro/googletest') [upstream](https://github.com/google/googletest 'github.com/google/googletest')|[diff](https://github.com/externpro/googletest/compare/v1.16.0...xpv1.16.0.6 'github.com/externpro/googletest/compare/v1.16.0...xpv1.16.0.6') [patch]|
|<a id='Threads' />[Threads](https://cmake.org/cmake/help/latest/module/FindThreads.html)|[LGPL-2.1-or-later](https://spdx.org/licenses/LGPL-2.1-or-later.html 'GNU Lesser General Public License v2.1 or later')|Finds and determines the thread library of the system for multithreading support|[xpv1.0.4](https://github.com/externpro/Threads/releases/tag/xpv1.0.4 'release')|[repo](https://github.com/externpro/Threads 'github.com/externpro/Threads')|[diff](https://github.com/externpro/Threads/compare/v0...xpv1.0.4 'github.com/externpro/Threads/compare/v0...xpv1.0.4') [bin]|

![deps](xprodeps.svg 'dependencies')

Dependency version check: all 2 parent-manifest versions match pinned versions.

|diff  |description|
|------|-----------|
|patch |diff modifies/patches existing cmake|
|intro |diff introduces cmake|
|auto  |diff adds cmake to replace autotools/configure/make|
|native|diff adds cmake but uses existing build system|
|bin   |diff adds cmake to repackage binaries built elsewhere|
|fetch |diff adds cmake and utilizes FetchContent|

[^_l]: see [SPDX License List](https://spdx.org/licenses/ '') for a list of commonly found licenses
[^_d]: see table above with description of diff
