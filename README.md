# Fun With (Native Image) Flags 🏁

* Build time and run time flags
* Rule of thumb: follow the JVM DX

## Development flag
* `-Ob` (Maven `dev` profile)
* `-Os`
* -g: generate debugging information
* -o: name of the output file to be generated
* `--emit=build-report`
* --dry-run: output the command line that would be used for building
* --parallelism: specify the maximum number of threads to use concurrently during native executable generation?
* Linking

## Performance / Optimization level flags
* 👩‍💻 PGO
  * ML-enabled PGO
* G1 GC
* `-march=native`
* `-Xmx`
* Memory management (`xmx`)

## Security
* SBOM flags (default)
* Obfuscation

## Montitoring
* `--enable-monitoring`
* 👩‍💻 Micrometer Micronaut
* `jvmstat`  
* JFR, JMX, `jcmd`
* `perf stat <process>`

## New 25.0 flags
* `-H=Preserve`
* FFM, Vector API?
* Crema?
* Layers?
