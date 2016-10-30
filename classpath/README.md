# Features Example
Shows support for classpath protocol.

`org.lesscss:lesscss-maven-plugin:compile` does not support compilation of sources located in classpath

# file.jar content:
* /file.less

    @import (less) "abc/1.less";
    span {
        content: 'this style is defined in file.jar';
    }

* /abc/1.less

    @import (less) "2.less";
    span {
        content: "file.jar/abc/1.less"
    }

* /abc/2.less

    span {
        content: "file.jar/abc/2.less"
    }

# Usage
How to use example:

1. open `pom.xml`
2. add configuration
3. run Maven command `mvn -e biz.gabrys.maven.plugins:lesscss-maven-plugin:compile`