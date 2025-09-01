# Fun With (Native Image) Flags 🏁

## Overview 🐰
* Intro
* General approach to the flags
* Development
* Performance
* Sonitoring
* Security
* GraalVM for JDK 25

## Development Flags: Must have 🛠️
*  `-Ob`: Optimize for build time
*  `-Os`: Optimize for executable size
*  `-o`: file output: name and location
*  `--emit-build-report`: extensive report about the build & executable
*  Linking: dynamic (default), mostly static: `--static-nolibc`, static: `--static --libc=musl`

## Development Flags: Advanced 🛠️
* `-g`: generate debugging information
*  `--parallelism`: specify the maximum number of threads to use concurrently during native executable generation
*  `--dry-run`: output the command line that would be used for the build

## Performance Flags 🚀
*  `-O3`: Optimize for best performance
*  `-pgo`: profile-guided optimizations
*  `--gc=G1`: use the G1 GC for high throughput
*  `-march=native`: specialize for the given hardware

## Montitoring 📈
* `--enable-monitoring=jfr`
* `--enable-monitoring=jvmstat`
* `--enable-monitoring=heapdump`
* OpenTelemetry, Micrometer
* Spring Boot Actuator / Micronaut Management
* Vendor and cloud solutions — check your deployment environment
* OS-level: `perf stat`, `vmmap`, etc

## Security 🛡️
* `--enable-sbom=embed`
* `--enable-sbom=classpath` (for programmatic access and external tooling)
* `--enable-sbom=export`
* Vulnerability scanning: `native-image-inspect --sbom ./target/demo-sbom | grype -v`
* `--enable-sbom=class-level (specific classses, fields, methods, etc)`

## New 25.0 flags 🔮
* `-H:Preserve=all`: include _everything_
  * or a module/package/cp entry
* `-H:+RelativeCodePointers`: extra security at high performance with PIE
* `-H:+ReportDynamicAccess`: a visual report of reflection and other dynamic access config
More performance and security :)
