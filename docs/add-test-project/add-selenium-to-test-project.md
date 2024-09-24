# Add Selenium

## Adding Selenium via the documentation

 I look into [Install a Selenium library](https://www.selenium.dev/documentation/webdriver/getting_started/install_library/) and find instructions to install it via maven:

>Specify the dependencies in the project’s pom.xml file:
>```xml
>        <dependency>
>            <groupId>org.seleniumhq.selenium</groupId>
>            <artifactId>selenium-java</artifactId>
>            <version>${selenium.version}</version>
>        </dependency>
>```

I see I need to specify a version via the `properties` tag in pom.xml. That is, I must add `<selenium.version>4.25.0</selenium.version>` in there.

Is 4.25.0 the latest available version? I check https://www.selenium.dev/downloads/ and see it is the latest version. However, I'm using maven. The latest available on https://mvnrepository.com/artifact/org.seleniumhq.selenium/selenium-java is 4.24.0.

## Test the adding of selenium

I stick to 4.25.0 and run `mvn test-compile`.

It does download. It downloads from https://repo.maven.apache.org!
>Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-java/4.25.0/selenium-java-4.25.0.pom.

This `selenium-java-4.25.0.pom` has these dependencies
> ```xml
>   <dependencies>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-api</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-chrome-driver</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-devtools-v127</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-devtools-v128</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-devtools-v129</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-devtools-v85</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-edge-driver</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-firefox-driver</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-ie-driver</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-remote-driver</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-safari-driver</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>         <dependency>
>             <groupId>org.seleniumhq.selenium</groupId>
>             <artifactId>selenium-support</artifactId>
>             <version>4.25.0</version>
>         </dependency>
>   </dependencies>
> ```

The pom includes drivers for chrome, edge, firefox, internet explorer and firefox as maven artifacts. As well as other artifacts I don't know.


`mvn test-compile` produced output. Lots of it. Seel the below

> ```log
> [INFO] Scanning for projects...
> [INFO]
> [INFO] ---------------< com.sintutu.fakeapitests:fakeapitests >----------------
> [INFO] Building fakeapitests 1.0-SNAPSHOT
> [INFO]   from pom.xml
> [INFO] --------------------------------[ jar ]---------------------------------
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-java/4.25.0/selenium-java-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-java/4.25.0/selenium-java-4.25.0.pom (4.4 kB at 6.7 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-api/4.25.0/selenium-api-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-api/4.25.0/selenium-api-4.25.0.pom (2.2 kB at 52 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/jspecify/jspecify/1.0.0/jspecify-1.0.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/jspecify/jspecify/1.0.0/jspecify-1.0.0.pom (1.5 kB at 27 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-chrome-driver/4.25.0/selenium-chrome-driver-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-chrome-driver/4.25.0/selenium-chrome-driver-4.25.0.pom (3.3 kB at 11 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/auto/service/auto-service-annotations/1.1.1/auto-service-annotations-1.1.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/auto/service/auto-service-annotations/1.1.1/auto-service-annotations-1.1.1.pom (2.3 kB at 56 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/auto/service/auto-service-aggregator/1.1.1/auto-service-aggregator-1.1.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/auto/service/auto-service-aggregator/1.1.1/auto-service-aggregator-1.1.1.pom (4.3 kB at 106 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/sonatype/oss/oss-parent/7/oss-parent-7.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/sonatype/oss/oss-parent/7/oss-parent-7.pom (4.8 kB at 146 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-chromium-driver/4.25.0/selenium-chromium-driver-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-chromium-driver/4.25.0/selenium-chromium-driver-4.25.0.pom (2.7 kB at 5.9 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-json/4.25.0/selenium-json-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-json/4.25.0/selenium-json-4.25.0.pom (2.3 kB at 8.4 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-remote-driver/4.25.0/selenium-remote-driver-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-remote-driver/4.25.0/selenium-remote-driver-4.25.0.pom (5.3 kB at 152 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/guava/guava/33.3.0-jre/guava-33.3.0-jre.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/guava/guava/33.3.0-jre/guava-33.3.0-jre.pom (9.3 kB at 153 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/guava/guava-parent/33.3.0-jre/guava-parent-33.3.0-jre.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/guava/guava-parent/33.3.0-jre/guava-parent-33.3.0-jre.pom (20 kB at 240 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/guava/failureaccess/1.0.2/failureaccess-1.0.2.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/guava/failureaccess/1.0.2/failureaccess-1.0.2.pom (3.3 kB at 93 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/guava/guava-parent/26.0-android/guava-parent-26.0-android.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/guava/guava-parent/26.0-android/guava-parent-26.0-android.pom (10 kB at 275 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/guava/listenablefuture/9999.0-empty-to-avoid-conflict-with-guava/listenablefuture-9999.0-empty-to-avoid-conflict-with-guava.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/guava/listenablefuture/9999.0-empty-to-avoid-conflict-with-guava/listenablefuture-9999.0-empty-to-avoid-conflict-with-guava.pom (2.3 kB at 47 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/code/findbugs/jsr305/3.0.2/jsr305-3.0.2.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/code/findbugs/jsr305/3.0.2/jsr305-3.0.2.pom (4.3 kB at 93 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/checkerframework/checker-qual/3.43.0/checker-qual-3.43.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/checkerframework/checker-qual/3.43.0/checker-qual-3.43.0.pom (2.1 kB at 54 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/errorprone/error_prone_annotations/2.28.0/error_prone_annotations-2.28.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/errorprone/error_prone_annotations/2.28.0/error_prone_annotations-2.28.0.pom (4.3 kB at 92 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/errorprone/error_prone_parent/2.28.0/error_prone_parent-2.28.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/errorprone/error_prone_parent/2.28.0/error_prone_parent-2.28.0.pom (13 kB at 320 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/j2objc/j2objc-annotations/3.0.0/j2objc-annotations-3.0.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/j2objc/j2objc-annotations/3.0.0/j2objc-annotations-3.0.0.pom (5.1 kB at 163 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/semconv/opentelemetry-semconv/1.25.0-alpha/opentelemetry-semconv-1.25.0-alpha.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/semconv/opentelemetry-semconv/1.25.0-alpha/opentelemetry-semconv-1.25.0-alpha.pom (1.7 kB at 45 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-api/1.42.1/opentelemetry-api-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-api/1.42.1/opentelemetry-api-1.42.1.pom (1.8 kB at 6.4 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-context/1.42.1/opentelemetry-context-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-context/1.42.1/opentelemetry-context-1.42.1.pom (1.6 kB at 36 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-exporter-logging/1.42.1/opentelemetry-exporter-logging-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-exporter-logging/1.42.1/opentelemetry-exporter-logging-1.42.1.pom (2.0 kB at 32 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk/1.42.1/opentelemetry-sdk-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk/1.42.1/opentelemetry-sdk-1.42.1.pom (2.5 kB at 64 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-common/1.42.1/opentelemetry-sdk-common-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-common/1.42.1/opentelemetry-sdk-common-1.42.1.pom (1.8 kB at 6.9 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-trace/1.42.1/opentelemetry-sdk-trace-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-trace/1.42.1/opentelemetry-sdk-trace-1.42.1.pom (2.2 kB at 7.8 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-api-incubator/1.42.1-alpha/opentelemetry-api-incubator-1.42.1-alpha.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-api-incubator/1.42.1-alpha/opentelemetry-api-incubator-1.42.1-alpha.pom (1.8 kB at 6.1 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-metrics/1.42.1/opentelemetry-sdk-metrics-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-metrics/1.42.1/opentelemetry-sdk-metrics-1.42.1.pom (2.2 kB at 6.6 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-logs/1.42.1/opentelemetry-sdk-logs-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-logs/1.42.1/opentelemetry-sdk-logs-1.42.1.pom (2.2 kB at 7.5 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure-spi/1.42.1/opentelemetry-sdk-extension-autoconfigure-spi-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure-spi/1.42.1/opentelemetry-sdk-extension-autoconfigure-spi-1.42.1.pom (1.8 kB at 6.2 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure/1.42.1/opentelemetry-sdk-extension-autoconfigure-1.42.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure/1.42.1/opentelemetry-sdk-extension-autoconfigure-1.42.1.pom (2.2 kB at 8.0 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/net/bytebuddy/byte-buddy/1.15.1/byte-buddy-1.15.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/net/bytebuddy/byte-buddy/1.15.1/byte-buddy-1.15.1.pom (16 kB at 196 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/net/bytebuddy/byte-buddy-parent/1.15.1/byte-buddy-parent-1.15.1.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/net/bytebuddy/byte-buddy-parent/1.15.1/byte-buddy-parent-1.15.1.pom (63 kB at 292 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-http/4.25.0/selenium-http-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-http/4.25.0/selenium-http-4.25.0.pom (2.8 kB at 10 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/dev/failsafe/failsafe/3.3.2/failsafe-3.3.2.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/dev/failsafe/failsafe/3.3.2/failsafe-3.3.2.pom (1.0 kB at 28 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/dev/failsafe/failsafe-parent/3.3.2/failsafe-parent-3.3.2.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/dev/failsafe/failsafe-parent/3.3.2/failsafe-parent-3.3.2.pom (9.2 kB at 241 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-manager/4.25.0/selenium-manager-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-manager/4.25.0/selenium-manager-4.25.0.pom (2.6 kB at 9.6 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-os/4.25.0/selenium-os-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-os/4.25.0/selenium-os-4.25.0.pom (2.4 kB at 9.3 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/apache/commons/commons-exec/1.4.0/commons-exec-1.4.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/apache/commons/commons-exec/1.4.0/commons-exec-1.4.0.pom (9.5 kB at 307 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/apache/commons/commons-parent/65/commons-parent-65.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/apache/commons/commons-parent/65/commons-parent-65.pom (78 kB at 1.4 MB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v127/4.25.0/selenium-devtools-v127-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v127/4.25.0/selenium-devtools-v127-4.25.0.pom (2.9 kB at 10 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v128/4.25.0/selenium-devtools-v128-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v128/4.25.0/selenium-devtools-v128-4.25.0.pom (2.9 kB at 10 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v129/4.25.0/selenium-devtools-v129-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v129/4.25.0/selenium-devtools-v129-4.25.0.pom (2.9 kB at 10 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v85/4.25.0/selenium-devtools-v85-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v85/4.25.0/selenium-devtools-v85-4.25.0.pom (2.9 kB at 11 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-edge-driver/4.25.0/selenium-edge-driver-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-edge-driver/4.25.0/selenium-edge-driver-4.25.0.pom (3.1 kB at 10 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-firefox-driver/4.25.0/selenium-firefox-driver-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-firefox-driver/4.25.0/selenium-firefox-driver-4.25.0.pom (3.4 kB at 13 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-ie-driver/4.25.0/selenium-ie-driver-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-ie-driver/4.25.0/selenium-ie-driver-4.25.0.pom (2.9 kB at 5.8 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-safari-driver/4.25.0/selenium-safari-driver-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-safari-driver/4.25.0/selenium-safari-driver-4.25.0.pom (2.7 kB at 9.9 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-support/4.25.0/selenium-support-4.25.0.pom
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-support/4.25.0/selenium-support-4.25.0.pom (3.2 kB at 91 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-java/4.25.0/selenium-java-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-java/4.25.0/selenium-java-4.25.0.jar (545 B at 1.9 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-api/4.25.0/selenium-api-4.25.0.jar
> Downloading from central: https://repo.maven.apache.org/maven2/org/jspecify/jspecify/1.0.0/jspecify-1.0.0.jar
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-chrome-driver/4.25.0/selenium-chrome-driver-4.25.0.jar
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/auto/service/auto-service-annotations/1.1.1/auto-service-annotations-1.1.1.jar
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-chromium-driver/4.25.0/selenium-chromium-driver-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/jspecify/jspecify/1.0.0/jspecify-1.0.0.jar (3.8 kB at 95 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-json/4.25.0/selenium-json-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/auto/service/auto-service-annotations/1.1.1/auto-service-annotations-1.1.1.jar (3.2 kB at 33 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-manager/4.25.0/selenium-manager-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-json/4.25.0/selenium-json-4.25.0.jar (71 kB at 222 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v127/4.25.0/selenium-devtools-v127-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-chrome-driver/4.25.0/selenium-chrome-driver-4.25.0.jar (15 kB at 41 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v128/4.25.0/selenium-devtools-v128-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-chromium-driver/4.25.0/selenium-chromium-driver-4.25.0.jar (37 kB at 101 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v129/4.25.0/selenium-devtools-v129-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-api/4.25.0/selenium-api-4.25.0.jar (233 kB at 506 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v85/4.25.0/selenium-devtools-v85-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v85/4.25.0/selenium-devtools-v85-4.25.0.jar (1.0 MB at 859 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-edge-driver/4.25.0/selenium-edge-driver-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v127/4.25.0/selenium-devtools-v127-4.25.0.jar (1.5 MB at 1.3 MB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-firefox-driver/4.25.0/selenium-firefox-driver-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v129/4.25.0/selenium-devtools-v129-4.25.0.jar (1.6 MB at 1.3 MB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-http/4.25.0/selenium-http-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-devtools-v128/4.25.0/selenium-devtools-v128-4.25.0.jar (1.6 MB at 1.2 MB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/dev/failsafe/failsafe/3.3.2/failsafe-3.3.2.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/dev/failsafe/failsafe/3.3.2/failsafe-3.3.2.jar (144 kB at 105 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-ie-driver/4.25.0/selenium-ie-driver-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-edge-driver/4.25.0/selenium-edge-driver-4.25.0.jar (15 kB at 10 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-remote-driver/4.25.0/selenium-remote-driver-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-firefox-driver/4.25.0/selenium-firefox-driver-4.25.0.jar (83 kB at 57 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/guava/guava/33.3.0-jre/guava-33.3.0-jre.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-http/4.25.0/selenium-http-4.25.0.jar (83 kB at 53 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/guava/failureaccess/1.0.2/failureaccess-1.0.2.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/guava/failureaccess/1.0.2/failureaccess-1.0.2.jar (4.7 kB at 2.9 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/guava/listenablefuture/9999.0-empty-to-avoid-conflict-with-guava/listenablefuture-9999.0-empty-to-avoid-conflict-with-guava.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-ie-driver/4.25.0/selenium-ie-driver-4.25.0.jar (17 kB at 10 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/code/findbugs/jsr305/3.0.2/jsr305-3.0.2.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/guava/listenablefuture/9999.0-empty-to-avoid-conflict-with-guava/listenablefuture-9999.0-empty-to-avoid-conflict-with-guava.jar (2.2 kB at 1.3 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/checkerframework/checker-qual/3.43.0/checker-qual-3.43.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/code/findbugs/jsr305/3.0.2/jsr305-3.0.2.jar (20 kB at 11 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/errorprone/error_prone_annotations/2.28.0/error_prone_annotations-2.28.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/checkerframework/checker-qual/3.43.0/checker-qual-3.43.0.jar (232 kB at 127 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/com/google/j2objc/j2objc-annotations/3.0.0/j2objc-annotations-3.0.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/errorprone/error_prone_annotations/2.28.0/error_prone_annotations-2.28.0.jar (19 kB at 10 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/semconv/opentelemetry-semconv/1.25.0-alpha/opentelemetry-semconv-1.25.0-alpha.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/j2objc/j2objc-annotations/3.0.0/j2objc-annotations-3.0.0.jar (12 kB at 6.4 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-api/1.42.1/opentelemetry-api-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-remote-driver/4.25.0/selenium-remote-driver-4.25.0.jar (538 kB at 270 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-context/1.42.1/opentelemetry-context-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/semconv/opentelemetry-semconv/1.25.0-alpha/opentelemetry-semconv-1.25.0-alpha.jar (75 kB at 36 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-exporter-logging/1.42.1/opentelemetry-exporter-logging-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-context/1.42.1/opentelemetry-context-1.42.1.jar (47 kB at 22 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-common/1.42.1/opentelemetry-sdk-common-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-api/1.42.1/opentelemetry-api-1.42.1.jar (157 kB at 67 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure-spi/1.42.1/opentelemetry-sdk-extension-autoconfigure-spi-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-exporter-logging/1.42.1/opentelemetry-exporter-logging-1.42.1.jar (16 kB at 6.9 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure/1.42.1/opentelemetry-sdk-extension-autoconfigure-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/com/google/guava/guava/33.3.0-jre/guava-33.3.0-jre.jar (3.1 MB at 1.3 MB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-api-incubator/1.42.1-alpha/opentelemetry-api-incubator-1.42.1-alpha.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-common/1.42.1/opentelemetry-sdk-common-1.42.1.jar (55 kB at 23 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-trace/1.42.1/opentelemetry-sdk-trace-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure-spi/1.42.1/opentelemetry-sdk-extension-autoconfigure-spi-1.42.1.jar (19 kB at 7.4 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk/1.42.1/opentelemetry-sdk-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure/1.42.1/opentelemetry-sdk-extension-autoconfigure-1.42.1.jar (47 kB at 18 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-metrics/1.42.1/opentelemetry-sdk-metrics-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-api-incubator/1.42.1-alpha/opentelemetry-api-incubator-1.42.1-alpha.jar (64 kB at 24 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-logs/1.42.1/opentelemetry-sdk-logs-1.42.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-trace/1.42.1/opentelemetry-sdk-trace-1.42.1.jar (130 kB at 48 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/net/bytebuddy/byte-buddy/1.15.1/byte-buddy-1.15.1.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk/1.42.1/opentelemetry-sdk-1.42.1.jar (6.8 kB at 2.3 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-os/4.25.0/selenium-os-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-metrics/1.42.1/opentelemetry-sdk-metrics-1.42.1.jar (310 kB at 104 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/apache/commons/commons-exec/1.4.0/commons-exec-1.4.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-logs/1.42.1/opentelemetry-sdk-logs-1.42.1.jar (54 kB at 18 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-safari-driver/4.25.0/selenium-safari-driver-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/apache/commons/commons-exec/1.4.0/commons-exec-1.4.0.jar (66 kB at 21 kB/s)
> Downloading from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-support/4.25.0/selenium-support-4.25.0.jar
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-manager/4.25.0/selenium-manager-4.25.0.jar (8.6 MB at 2.8 MB/s)
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-os/4.25.0/selenium-os-4.25.0.jar (29 kB at 9.2 kB/s)
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-safari-driver/4.25.0/selenium-safari-driver-4.25.0.jar (27 kB at 8.1 kB/s)
> Downloaded from central: https://repo.maven.apache.org/maven2/org/seleniumhq/selenium/selenium-support/4.25.0/selenium-support-4.25.0.jar (174 kB at 51 kB/s)
> Downloaded from central: https://repo.maven.apache.org/maven2/net/bytebuddy/byte-buddy/1.15.1/byte-buddy-1.15.1.jar (4.2 MB at 1.2 MB/s)
> [INFO]
> [INFO] --- resources:3.3.1:resources (default-resources) @ fakeapitests ---
> [INFO] skip non existing resourceDirectory C:\Users\DELL\dev\fake-rest-api-java\fakeapitests\src\main\resources
> [INFO]
> [INFO] --- compiler:3.13.0:compile (default-compile) @ fakeapitests ---
> [INFO] No sources to compile
> [INFO]
> [INFO] --- resources:3.3.1:testResources (default-testResources) @ fakeapitests ---
> [INFO] skip non existing resourceDirectory C:\Users\DELL\dev\fake-rest-api-java\fakeapitests\src\test\resources
> [INFO]
> [INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ fakeapitests ---
> [INFO] Recompiling the module because of changed dependency.
> [INFO] Compiling 1 source file with javac [debug release 17] to target\test-classes
> [INFO] ------------------------------------------------------------------------
> [INFO] BUILD SUCCESS
> [INFO] ------------------------------------------------------------------------
> [INFO] Total time:  15.017 s
> [INFO] Finished at: 2024-09-20T21:55:25+02:00
> [INFO] ------------------------------------------------------------------------
>```

So when did I ask for https://repo.maven.apache.org/maven2/io/opentelemetry/opentelemetry-sdk-extension-autoconfigure/1.42.1/opentelemetry-sdk-extension-autoconfigure-1.42.1.pom? I didn't. I suspect one of the artifacts had reference to it. So by transitivity, my project pulls it in. [Transitive dependencies](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html#transitive-dependencies) seem to be at play here. For a fuller overview of how dependencies are managed, see [Introduction to the Dependency Mechanism](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html). It's sufficient for now to note that everything needed to use selenium (i.e. the [bill of materials](https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html)) is now included.

## Use Selenium in a unit test
