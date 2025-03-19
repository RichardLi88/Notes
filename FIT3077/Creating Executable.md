
1. Compile to *.class file with:
	- `javac Main.java`
2. Create *.jar file with:
	- `jar --create --file <name>.jar --main-class=<ClassName> -C . .`
3. move *.jar file to a subdirectory (e.g. `build/`)
	- `mkdir build && mv *.jar build`
4. use `jpackage` to create executable:
	- `jpackage --type app-image --name <AppName> --input build --main-jar <jarFileName>`
	- on Windows, replace `app-image` with `exe`
	- on Mac, replace `app-image` with `dmg`
	- on Linux, use either `app-image`, `rpm`, or `deb`