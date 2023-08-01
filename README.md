# Media Access Function API Unity3D package

This repository provides a Unity3D package implementing media pipeline API specified by in ISOIEC 23090-14.


## Downloading 

The package can be added to a Unity3D project using the package manager UI, by using ["Add package from git URL"](https://docs.unity3d.com/Manual/upm-ui-giturl.html) to download and add it to the project's `Packages` directory.

Alternatively, it is possible to simply clone the repository to a local directory `git clone https://github.com/5G-MAG/rt-xr-maf-plugin.git rt.xr.maf`,
then chose to [Add package from disk](https://docs.unity3d.com/Manual/upm-ui-local.html).


## Building

The repository is meant to be compiled as part of a unity project.
The core MAF & media pipeline factory library source is currently being developped and tested on windows.


## Package content

**Do not edit source code in these directories directly:**
- `Lib/maf` directory contains SWIG generated C# bindings.
- `Lib/bin` directory contains precompiled SWIG generated wrapper.
- `Plugins` directory contains precompiled media pipelines.

These are artifacts generated from the [libmaf repository](https://github.com/5G-MAG/rt-xr-maf-native).

### Dependencies

`Dependencies` directory contains system dependencies for pre-compiled plugins


#### ffmpeg libraries

The `avpipeline` plugin makes use of ffmpeg libraries.

The pre-compiled ffmpeg libraries are [compiled to comply with LGPL](https://ffmpeg.org/legal.html), with only a subset of all codecs available.
To use additional codec libraries (such as libx264 or libx265), make sure to link against your own ffmpeg libraries when building your project.


## Tests

Tests run in Unity3D's test runner.


## Implementation notes

During initial development of this package, the C# bindings have been provided a clear separation between the media pipeline implementation in native code, and Unity3D managed code.

However this approach has limitations, and it should be emphasized that a Unity native plugin can use the MAF API directly in native code.

## License

Licensed under the License terms and conditions for use, reproduction,
and distribution of 5GMAG software (the “License”).

You may not use this file except in compliance with [the License](/LICENSE.md).
You may obtain a copy of the License at https://www.5g-mag.com/license .

Unless required by applicable law or agreed to in writing, software distributed under the License is
distributed on an “AS IS” BASIS,

WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and limitations under the License.
