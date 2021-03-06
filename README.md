# builder.isbpl

A simple build script processor for Java applications written in [ISBPL](https://github.com/TudbuT/ISBPL).

## Add dependencies

You have multiple options:
- Download: `"https://url.to/the/jar/file" download`
- Local file: `"/path/to/file.jar" file`
- Custom processor: Define a function that takes whatever you want, adds the desired jarfile to lib/, and returns its name.

All dependencies are added to the completed jarfile.

## Run your application

- With rebuild: `isbpl build.isbpl build run`
- Without rebuild: either `bash run.sh` or `isbpl build.isbpl run`, depending on the situation.

## Make a jar

- With rebuild: `isbpl build.isbpl build jar`
- Without rebuild: `isbpl build.isbpl jar`

To autogenerate a manifest, add `makeManifest` in front of the `jar`.

## Default tasks

- clean
- build
- makeManifest
- jar
- javadoc
- run

## Use a custom buildscript

```isbpl
"builder.isbpl" include

"MainClassName" =mainClass
"myCoolProject" =name

func dependencies {
    "Define your dependencies here" #
}

func myCoolTask {
    "\n> Doing the cool thing..." puts
}
"myCoolTask" task
```
