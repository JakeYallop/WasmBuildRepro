## Build repro
Delete the bin/ and obj/ folders between each step - otehrwise an additional publish or an additional build will not regenerate the bundle as the inputs are the same.

```
dotnet build
```
You should see
```
Running WriteMyFile target after WasmBuildApp. WasmAppDir = <repo path>\bin\Debug\net8.0\browser-wasm\AppBundle. This message appears when doing either a build or a publish.
```


```
dotnet publish -c Release
```

```
MSBuild version 17.8.0+6cdef4241 for .NET
  Determining projects to restore...
  All projects are up-to-date for restore.
C:\Program Files\dotnet\sdk\8.0.100-rc.2.23502.2\Sdks\Microsoft.NET.Sdk\targets\Microsoft.NET.RuntimeIdentifierInference.targets(311,5): message NETSDK1057: You are using a p
review version of .NET. See: https://aka.ms/dotnet-support-policy [<repo path>\WasmBuildRepro.csproj]
  WasmBuildRepro -> <repo path>\bin\Release\net8.0\browser-wasm\WasmBuildRepro.dll
  Running WriteMyFile target after WasmBuildApp. WasmAppDir = <repo path>\bin\Release\net8.0\browser-wasm\AppBundle. This message appears when doing either a
   build or a publish.
  Optimizing assemblies for size. This process might take a while.
  WasmBuildRepro -> <repo path>\bin\Release\net8.0\browser-wasm\publish\
  WasmBuildRepro -> <repo path>\bin\Release\net8.0\browser-wasm\WasmBuildRepro.dll
  Running WriteMyFile target after WasmBuildApp. WasmAppDir = <repo path>\bin\Release\net8.0\browser-wasm\AppBundle. This message appears when doing either a
   build or a publish.
  WasmBuildRepro -> <repo path>\bin\Release\net8.0\browser-wasm\publish\
  <build output truncated>
  Stripping symbols from dotnet.native.wasm ...
  Generated app bundle at <repo path>\bin\Release\net8.0\browser-wasm\AppBundle\
  Message from publish!! This message does not appear when doing a build.
  testfile.txt does not exist.
```
