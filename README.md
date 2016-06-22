# Hamcrest Optional

[![release](http://github-release-version.herokuapp.com/github/baev/hamcrest-optional/release.svg?style=flat)](https://github.com/baev/hamcrest-optional/releases/latest)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.baev/hamcrest-optional/badge.svg?style=flat)](https://maven-badges.herokuapp.com/maven-central/com.github.baev/hamcrest-optional)
[![build](https://img.shields.io/jenkins/s/http/ci.qatools.ru/hamcrest-optional_master-deploy.svg?style=flat)](http://ci.qatools.ru/job/hamcrest-optional_master-deploy/lastBuild/)
[![covarage](https://img.shields.io/sonar/http/sonar.qatools.ru/com.github.baev:hamcrest-optional/coverage.svg?style=flat)](http://sonar.qatools.ru/dashboard/index/com.github.baev:hamcrest-optional)

An extension to [Java Hamcrest](https://github.com/hamcrest/JavaHamcrest) which provides matchers for `java.util.Optional`.

## Usage

The artifact available at Maven Central:

```xml
<dependency>
    <groupId>com.github.baev</groupId>
    <artifactId>hamcrest-optional</artifactId>
    <version>1.0</version>
</dependency>
```

hamcrest-optional provides four matchers for `Optional`: `isEmpty()`,
`isPresent()`, `hasValue(Object)` and `hasValue(Matcher)`.

### isEmpty()

This matcher matches when the examined `Optional` contains no value.

```java
import static com.github.npathai.hamcrestopt.OptionalMatchers.isEmpty;

Optional<Object> optional = Optional.empty();
assertThat(optional, isEmpty());
```

### isPresent()

This matcher matches when the examined `Optional` contains a value.

```java
import static com.github.npathai.hamcrestopt.OptionalMatchers.isPresent;

Optional<String> optional = Optional.of("dummy value");
assertThat(optional, isPresent());
```

### hasValue(Object)

This matcher matches when the examined `Optional` contains a value that is
logically equal to the specified object.

```java
import static com.github.npathai.hamcrestopt.OptionalMatchers.hasValue;

Optional<String> optional = Optional.of("dummy value");
assertThat(optional, hasValue("dummy value"));
```

### hasValue(Matcher)

This matcher matches when the examined `Optional` contains a value that
satisfies the specified matcher.

```java
import static com.github.npathai.hamcrestopt.OptionalMatchers.hasValue;
import static org.hamcrest.Matchers.startsWith;

Optional<String> optional = Optional.of("dummy value");
assertThat(optional, hasValue(startsWith("dummy")));
```

## Development Guide

hamcrest-optional is build with [Maven](http://maven.apache.org/). If you want
to contribute code then

* Please write a test for your change.
* Ensure that you don't break the build by running `mvn test`.
* Fork the repo and create a pull request. (See [Understanding the GitHub Flow](https://guides.github.com/introduction/flow/index.html))

hamcrest-optional supports [Travis CI](https://travis-ci.org/) for continuous
integration. Your pull request is automatically build by Travis CI.
