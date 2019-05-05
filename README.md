# vsCodeSetup
Readme file containing custom task setup for test with coverlet

1) Get extensions: <b>coverlet</b> and <b>coverage gutters</b>
```
dotnet tool install --global coverlet.console
```
2) Modify tasks.json with the following
```
  {
      "label": "test_coverlet",
      "command": "dotnet",
      "type": "process",
      "args": [
          "test",
          "/p:CollectCoverage=true",
          "/p:CoverletOutputFormat=lcov",
          "/p:CoverletOutput=./lcov.info",
          "${workspaceFolder}/<PATH TO TEST PROJECT>/<NAME OF TESTPROJECT *.csproj FILE>"
      ],
      "problemMatcher": "$msCompile",
      "group": {
          "kind": "test",
          "isDefault": true
      }
  }
```
3) Possibly modify keyboard shortcut *Tasks: Run Test Task*
