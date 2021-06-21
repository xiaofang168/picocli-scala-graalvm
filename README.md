Scala Picocli with GraalVM
========

## Install GraalVM

1. Download GraalVM Community Edition from https://github.com/graalvm/graalvm-ce-builds/releases.
2. Add `bin` directory to `PATH`
3. Install `native-image` command
  ```
  $ gu install native-image
  ```

## Build

1. Build the project
  ```
  $ sbt graalvm-native-image:packageBin
  ```
2. Run the command
  ```
  $ ./target/graalvm-native-image/picocli-scala-graalvm
  Missing required parameter: <file>
  Usage: checksum [-hV] [-a=<algorithm>] <file>
  Prints the checksum (MD5 by default) of a file to STDOUT.
        <file>      The file whose checksum to calculate.
    -a, --algorithm=<algorithm>
                    MD5, SHA-1, SHA-256, ...
    -h, --help      Show this help message and exit.
    -V, --version   Print version information and exit.
  ```
3. 编译耗时和所需要的内存
```
[info] [picocli-scala-graalvm:15335]    classlist:   7,756.17 ms,  1.55 GB
[info] [picocli-scala-graalvm:15335]        (cap):  10,182.90 ms,  1.55 GB
[info] [picocli-scala-graalvm:15335]        setup:  13,431.99 ms,  1.55 GB
[info] [picocli-scala-graalvm:15335]     (clinit):     777.52 ms,  1.78 GB
[info] [picocli-scala-graalvm:15335]   (typeflow):  20,729.26 ms,  1.78 GB
[info] [picocli-scala-graalvm:15335]    (objects):  11,491.61 ms,  1.78 GB
[info] [picocli-scala-graalvm:15335]   (features):     665.82 ms,  1.78 GB
[info] [picocli-scala-graalvm:15335]     analysis:  34,281.94 ms,  1.78 GB
[info] [picocli-scala-graalvm:15335]     universe:   1,463.65 ms,  1.78 GB
[info] [picocli-scala-graalvm:15335]      (parse):   7,639.76 ms,  1.92 GB
[info] [picocli-scala-graalvm:15335]     (inline):   4,865.91 ms,  1.96 GB
[info] [picocli-scala-graalvm:15335]    (compile):  39,751.17 ms,  3.49 GB
[info] [picocli-scala-graalvm:15335]      compile:  53,961.21 ms,  3.49 GB
[info] [picocli-scala-graalvm:15335]        image:   2,570.84 ms,  3.49 GB
[info] [picocli-scala-graalvm:15335]        write:     993.74 ms,  3.49 GB
[info] [picocli-scala-graalvm:15335]      [total]: 114,821.71 ms,  3.49 GB
```