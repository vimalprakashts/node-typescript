### Pre Request 

1. VS Code

2. Node js https://nodejs.org/en/

3. NPM https://nodejs.org/en/

4. Typescript https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html

5. Mongo DB


##### Verify the installation 

> node -v
> npm -v
> tsc -v

### Configure the workspace

1. Create node js project

> npm init -y


2. Enable the typescript

create `tsconfig.json` file 

and add the below content

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "noImplicitAny": true,
    "target": "es6",
    "declaration": true,
    "outDir": "./dist",
    "sourceMap": true,
    "strict": true,
    "lib": [
      "es2017"
    ],
    "noImplicitThis": false
  },
  "exclude": [
    "node_modules",
    "typings",
    "dist"
  ]
}
```

3. Add the vs code lanch.json and task.json 

> create director with the name `.vscode`

> add the launch.json 

```json
{
    // Use IntelliSense to learn about possible Node.js debug attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Launch",
            "type": "node",
            "request": "launch",
            "program": "${workspaceRoot}/dist/index.js",
            "stopOnEntry": false,
            "args": [],
            "cwd": "${workspaceRoot}",
            "preLaunchTask": "tsc",
            "runtimeExecutable": null,
            "runtimeArgs": [
                "--nolazy"
            ],
            "outFiles": [
                "${workspaceRoot}/dist"
            ],
            "sourceMaps": true
        },
        {
            "name": "Attach",
            "type": "node",
            "request": "attach",
            "port": 5858,
            "address": "localhost",
            "restart": false,
            "sourceMaps": false,
            "localRoot": "${workspaceRoot}",
            "remoteRoot": null
        }
    ]
}
```

> add the tasks.json

```json
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "command": "tsc",
    "isShellCommand": true,
    "args": [
        "-p",
        "."
    ],
    "showOutput": "silent",
    "problemMatcher": "$tsc"
}
```


4. Create folder structure 

> create `src` at root of the directory

> Create Controllers, Helpers, Models, Routers , Server, Services 

> mkdir -p src/Controllers src/Helpers src/Models src/Routers src/Server src/Services

> touch src/index.ts



