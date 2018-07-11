docker run --rm -i -v $(pwd):/docfx_project  tsgkadot/docker-docfx:latest docfx init
cd src/Confluent.Kafka
dotnet build
cd src/Confluent.Kafka.Avro
dotnet build
cd src/Confluent.SchemaRegistry
dotnet build
dotnet run --rm -i -v $(pwd):/docfx_project sgkadot/docker-docfx:lates docfx /docfx_project/docfx.json build

Note: 
when generate docfx.json, the defaul generated file cannot generate file because taget version is not specified.

```
      "properties": { "TargetFramework": "netstandard2.0" }
```
The full metadata is here

```
"metadata": [
    {
      "src": [
        {
          "files": [
            "src/**.csproj"
          ]
        }
      ],
      "dest": "api",
      "disableGitFeatures": false,
      "properties": { "TargetFramework": "netstandard2.0" }
    }
  ],
```