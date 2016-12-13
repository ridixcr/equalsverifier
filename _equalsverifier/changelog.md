---
title: Changelog
---
* What's new in [version 1.x](#1.x)?
* What's new in [version 2.x](#2.x)?

**Well, you can now ...**

<a name="2.x"></a>

Version 2.1.8
-------------
* ...test classes that implement an abstract class that calls an abstract method in its `equals` or `hashCode` methods, when EqualsVerifier is called with `usingGetClass`. ([Issue 161](https://github.com/jqno/equalsverifier/issues/161))

Version 2.1.7
-------------
* ...use single value enums again ([Issue 157](https://github.com/jqno/equalsverifier/pull/157); thanks Stephan!)

Version 2.1.6
-------------
_October 1, 2016_

* ...no longer get NullPointerExceptions in situations where annotations which are available at compile time, are not available at runtime. ([Issue 153](https://github.com/jqno/equalsverifier/issues/153) and [Issue 154](https://github.com/jqno/equalsverifier/issues/154))

Version 2.1.5
-------------
_August 6, 2016_

* ...avoid adding prefab values for `java.util.Vector` and `java.util.Stack`. ([Issue 151](https://github.com/jqno/equalsverifier/pull/151))

Version 2.1.4
-------------
_July 25, 2016_

* ...use Guava's Range with full reflection support. ([Issue 150](https://github.com/jqno/equalsverifier/pull/150); thanks Stephan!)

Version 2.1.3
-------------
_July 17, 2016_

* ...use EqualsVerifier when older versions of Google Guava are on the classpath. ([Issue 149](https://github.com/jqno/equalsverifier/issues/149))

Version 2.1.2
-------------
_June 20, 2016_

* ...use EqualsVerifier concurrently. ([Issue 148](https://github.com/jqno/equalsverifier/pull/148); thanks Borys!)

Version 2.1.1
-------------
_June 14, 2016_

* ...not get VerifyErrors in certain situations, such as when running unit tests with coverage in IntelliJ. ([Issue 147](https://github.com/jqno/equalsverifier/issues/147))
* ...have the (current) latest version of ByteBuddy. ([Issue 145](https://github.com/jqno/equalsverifier/issues/145); thanks Vincent!)

Version 2.1
-----------
_May 22, 2016_

* ...suppress `Warning.STRICT_HASHCODE` to let EqualsVerifier allow `hashCode` methods that don't use all the fields that are also used in `equals`, or even constant `hashCode`s. ([Issue 142](https://github.com/jqno/equalsverifier/issues/142))
* ...assert, within a class's `equals` or `hashCode` method, on the length of its array field. ([Issue 143](https://github.com/jqno/equalsverifier/issues/143))
* ...get an equalsverifier.jar file without Objenesis's meta-data in the `META-INF` folder. ([Issue 144](https://github.com/jqno/equalsverifier/issues/144))
* ...no longer get a `ReflectionException` when EqualsVerifier is unable to read annotations on fields in certain situations. (Issue 14, [Comment 21](https://github.com/jqno/equalsverifier/issues/114#issuecomment-206463710))

Version 2.0.2
-------------
_April 3, 2016_

* ...test classes that implement an abstract class that calls an abstract method in its `equals` or `hashCode` methods. ([Issue 138](https://github.com/jqno/equalsverifier/issues/138))
* ...use EqualsVerifier on a JVM that doesn't have `javax.naming.Reference` available. ([Issue 114](https://github.com/jqno/equalsverifier/issues/114))

Version 2.0.1
-------------
_March 13, 2016_

* ...test classes that have a static final reference to a recursive data structure, without adding prefab values.
* ...test classes that have a generic parameter that extends `Comparable`. ([Issue 136](https://github.com/jqno/equalsverifier/issues/136))
* ...no longer have `com.google.code.findbugs.annotations` show up on your classpath. ([Issue 135](https://github.com/jqno/equalsverifier/issues/135); thanks Stephan!)

Version 2.0
-----------
_March 6, 2016_

If you're upgrading from EqualsVerifier 1, please see the [migration guide]({{ pcurl('equalsverifier/migration1to2') }}).

* ...no longer use EqualsVerifier with Java 6.
* ...no longer use `EqualsVerifier.forExamples`. Use `#forClass` or `#forRelaxedEqualExamples` instead.
* ...no longer use `#debug()` (which didn't do anything, anyway).
* ...expect "all fields should be used" to be the default behaviour. ([Issue 65](https://github.com/jqno/equalsverifier/issues/65))
    * Suppress `Warning.ALL_FIELDS_SHOULD_BE_USED` to revert back to the old behaviour.
    * `#forRelaxedEqualExamples` implicitly suppresses `Warning.ALL_FIELDS_SHOULD_BE_USED`.
    * Suppressing `Warning.IDENTICAL_COPY_FOR_VERSIONED_ENTITY` implicitly suppresses `Warning.ALL_FIELDS_SHOULD_BE_USED`.
    * `#allFieldsShouldBeUsedExcept()` is now removed.
    * Use `#withIgnoredFields()` to disregard specific fields, while expecting all remaining fields to be used in `equals`.
    * Use `#withOnlyTheseFields()` to expect that the given fields are used, and that the remaining fields are not used. ([Issue 128](https://github.com/jqno/equalsverifier/issues/128))
* ...expect EqualsVerifier to fail when `equals` isn't overridden (i.e., inherited directly from `Object`). ([Issue 66](https://github.com/jqno/equalsverifier/issues/66))
    * Suppress `Warning.INHERITED_DIRECTLY_FROM_OBJECT` to revert back to the old behaviour.
* ...refer to the generic contents of containers, such as `List` and `Optional`, in the implementation of `equals` and `hashCode`. ([Issue 84](https://github.com/jqno/equalsverifier/issues/84))
* ...get more useful information from the stack trace if EqualsVerifier fails.
* ...have better compatibility with Java 8. ([Issue 115](https://github.com/jqno/equalsverifier/issues/115))
* ...know that EqualsVerifier's code quality has been improved, as a result of adding CheckStyle and FindBugs, and doing mutation tests with PIT.


<a name="1.x"></a>

Version 1.7.8
-------------
_February 26, 2016_

* ...use EqualsVerifier and Java 8's `-parameters` compiler option in the same project.

Version 1.7.7
-------------
_January 18, 2016_

* ...use EqualsVerifier together with Cobertura. ([Issue 132](https://github.com/jqno/equalsverifier/issues/132))

Version 1.7.6
-------------
_December 21, 2015_

* ...have a field whose type is an interface that defines `equals`. ([Issue 130](https://github.com/jqno/equalsverifier/issues/130))
* ...get 100% mutation coverage with [PIT](http://pitest.org/) on your `equals` and `hashCode` methods. ([Issue 131](https://github.com/jqno/equalsverifier/issues/131))

Version 1.7.5
-------------
_August 29, 2015_

* ...get symmetry warnings if the symmetry violation only occurs in the subclass of a versioned entity. (Issue 123, [Comment 10](https://github.com/jqno/equalsverifier/issues/123#issuecomment-134201349))
* ...get a warning when the id check on a versioned entity is implemented incorrectly. (Issue 123, [Comment 17](https://github.com/jqno/equalsverifier/issues/123#issuecomment-133151013))
* ...omit suppression of `Warning.NONFINAL_FIELDS` on classes marked `@Embeddable` and `@MappedSuperclass`. ([Issue 124](https://github.com/jqno/equalsverifier/issues/124) and Issue 123, [Comment 15](https://github.com/jqno/equalsverifier/issues/123#issuecomment-134168785))
* ...use singleton enums without null-checking. ([Issue 125](https://github.com/jqno/equalsverifier/issues/125))

Version 1.7.4
-------------
_August 17, 2015_

* ...avoid adding prefab values for
    * JavaFX (Java 8 only), ([Issue 120](https://github.com/jqno/equalsverifier/issues/120))
    * `javax.naming.Reference`. ([Issue 118](https://github.com/jqno/equalsverifier/issues/118))
* ...avoid exceptions thrown from SBT. ([Issue 119](https://github.com/jqno/equalsverifier/issues/119))
* ...get better reporting on subclasses of versioned entities. ([Issue 123](https://github.com/jqno/equalsverifier/issues/123))

Version 1.7.3
-------------
_July 18, 2015_

* ...use a protected or default-visibility `cachedHashCode` field with `#withCachedHashCode()`. ([Issue 110](https://github.com/jqno/equalsverifier/issues/110))
* ...have a static final field with `null` value without getting a `NullPointerException`. ([Issue 116](https://github.com/jqno/equalsverifier/issues/116))
* ...know that several things have been improved behind-the-scenes :).

Version 1.7.2
-------------
_March 28, 2015_

* ...use Eclipse's JDT null annotations, including the Java 8 style type annotations.
* ...have a static field with an empty array in the class under test, without getting an `ArrayIndexOutOfBoundsException`. ([Issue 106](https://github.com/jqno/equalsverifier/issues/106))
* ...revel in the fact that all dependencies have been updated ([Issue 107](https://github.com/jqno/equalsverifier/issues/107)) and that several potential bugs have been solved using [PIT](http://pitest.org/).

Version 1.7.1
-------------
_March 11, 2015_

* ...use EqualsVerifier again, without suppressing 1.7's `REFERENCE_EQUALITY` warning, on classes containing:
    * certain interfaces, and classes which don't redefine `equals`.  (Issue 104, [Comment 6](https://github.com/jqno/equalsverifier/issues/104#issuecomment-87377326))
    * a static final lambda field. ([Issue 105](https://github.com/jqno/equalsverifier/issues/105))

Version 1.7
-----------
_March 4, 2015_

* ...verify classes that cached their hashCode, using `#withCachedHashCode()`. ([Issue 60](https://github.com/jqno/equalsverifier/issues/60); thanks Niall!)
* ...avoid adding prefab values for several Java Collections interface classes, including `SortedSet` and `TreeSet`. ([Issue 103](https://github.com/jqno/equalsverifier/issues/103))
* ...get an error message when you accidentally use `==` instead of `equals` on an object field inside your `equals` method, and suppress this using `Warning.REFERENCE_EQUALITY`. ([Issue 104](https://github.com/jqno/equalsverifier/issues/104))

Version 1.6
-----------
_January 17, 2015_

* ...set default @Nonnull annotations on your classes ([Issue 50](https://github.com/jqno/equalsverifier/issues/50))
    * using Findbugs's `@DefaultAnnotation` or `@DefaultAnnotationForFields`.
    * using a JSR 305 annotation (see [this StackOverflow question](http://stackoverflow.com/q/11776302/127863)).
    * you can put them on the class, or on the package.
    * you can override the default by placing `@Nullable` or `@CheckForNull` on a field.
* ...verify stateless classes. ([Issue 46](https://github.com/jqno/equalsverifier/issues/46))
* ...verify classes with stateless fields. ([Issue 100](https://github.com/jqno/equalsverifier/issues/100) and [Issue 101](https://github.com/jqno/equalsverifier/issues/101))
* ...verify the consistency of `hashCode` in a stateless object. ([Issue 97](https://github.com/jqno/equalsverifier/issues/97&colspec=ID%20Type%20Status%20Priority%20Milestone%20Reporter%20Summary))
* ...verify classes where equality is fully defined in a superclass, for example using Apache Commons's [`EqualsBuilder.reflectionEquals`](http://commons.apache.org/proper/commons-lang/javadocs/api-3.3.2/org/apache/commons/lang3/builder/EqualsBuilder.html#reflectionEquals%28java.lang.Object,%20java.lang.Object,%20boolean%29). ([Issue 102](https://github.com/jqno/equalsverifier/issues/102))

Version 1.5.1
-------------
_December 5, 2014_

* ...use EqualsVerifier when incompatible versions of ASM and/or CGLib are on the classpath. EqualsVerifier is now shipped as an "uber jar" which contains all its dependencies inside. ([Issue 96](https://github.com/jqno/equalsverifier/issues/96))
* ...use EqualsVerifier with older versions of Google Guava on the classpath. ([Issue 98](https://github.com/jqno/equalsverifier/issues/98))
* ...build EqualsVerifier itself using Maven instead of Ant+Ivy.

Version 1.5
-----------
_August 20, 2014_

* ...use EqualsVerifer in Java 8! Classes containing Java 8 language features are now supported, and prefab values for new Java 8 API classes have been added. ([Issue 92](https://github.com/jqno/equalsverifier/issues/92))
* ...stop adding prefab values for [Joda-Time](http://www.joda.org/joda-time/) and [Google Guava](https://code.google.com/p/guava-libraries/), because EqualsVerifier now provides them for you. ([Issue 83](https://github.com/jqno/equalsverifier/issues/83))
* ...have correct error messages when your class contains multi-dimensional arrays. ([Issue 90](https://github.com/jqno/equalsverifier/issues/90) and [Issue 94](https://github.com/jqno/equalsverifier/issues/94))
* ...use `Arrays.equals` instead of `Arrays.deepEquals` on `Object[]` fields. ([Issue 94](https://github.com/jqno/equalsverifier/issues/94))
* ...use the super class's `equals` method when specifying `#allFieldsShouldBeUsed()` ([Issue 95](https://github.com/jqno/equalsverifier/issues/95); thanks Dean!)
* ...get better error messages when `equals` or `hashCode` are themselves abstract.
* ...find and understand EqualsVerifier's unit tests more easily, as they have been heavily refactored.

Version 1.4.1
-------------
_March 18, 2014_

* ...pass enums through EqualsVerifier without error. ([Issue 87](https://github.com/jqno/equalsverifier/issues/87))
* ...get more thorough reflexivity and symmetry tests, which will catch small mistakes such as the one in [Issue 88](https://github.com/jqno/equalsverifier/issues/88).

Version 1.4
-----------
_December 27, 2013_

* ...have confidence that EqualsVerifier covers 100% of your `equals` and `hashCode` methods. ([FAQ]({{ pcurl('equalsverifier/faq#coverage') }}))
* ...specifically ignore certain fields using `#allFieldsShouldBeUsedExcept()`. ([Issue 82](https://github.com/jqno/equalsverifier/issues/82))
* ...test classes that have an array field, but that don't declare an `equals` method.
* ...get clearer error messages around abstract delegation. This clarifies especially classes that contain Joda-Time `LocalDate` fields.
* ...stop worrying about adding prefab values for BitSet. ([Issue 86](https://github.com/jqno/equalsverifier/issues/86))

Version 1.3.1
-------------
_June 9, 2013_

* ...read error messages on the [new EqualsVerifier website](http://www.jqno.nl/equalsverifier/errormessages) at [jqno.nl](http://www.jqno.nl/equalsverifier), which matches EqualsVerifier's fully qualified name: `nl.jqno.equalsverifier.EqualsVerifier`.
* ...disregard .debug(), as it is deprecated. Relevant exceptions are now included as a cause in the stack trace.
* ...test "versioned entity" classes where a zero id field indicates that the object is new, by suppressing `Warning.IDENTICAL_COPY_FOR_VERSIONED_ENTITY`. ([Issue 80](https://github.com/jqno/equalsverifier/issues/80))
* ...get more accurate transitivity errors. ([Issue 78](https://github.com/jqno/equalsverifier/issues/78))
* ...stop worrying about exceptions thrown in toString. ([Issue 79](https://github.com/jqno/equalsverifier/issues/79))
* ...stop worrying about adding prefab values for UUID, to avoid that pesky recursion warning. ([Issue 81](https://github.com/jqno/equalsverifier/issues/81))

Version 1.3
-----------
_June 9, 2013_

Please don't use version 1.3; it's a broken release. Use 1.3.1 instead.

Version 1.2
-----------
_March 26, 2013_

* ...get a transitivity error message for classes that use `or` in their equals method. ([Issue 75](https://github.com/jqno/equalsverifier/issues/75); blog post about [the problem](http://www.jqno.nl/post/2013/02/17/reaction-to-cedric-beusts-equals-challenge/) and [the solution](http://www.jqno.nl/post/2013/03/26/on-transitivity))
* ...expect more robustness from EqualsVerifier when the `toString` method of the class under tests throws exceptions.
* ...use single value enums (and hence, singletons) in your classes, even if they don't count for `equals` and `hashCode`. ([Issue 74](https://github.com/jqno/equalsverifier/issues/74))
* ...use `forRelaxedEqualExamples` with classes containing null fields. ([Issue 73](https://github.com/jqno/equalsverifier/issues/73))
* ...run EqualsVerifier's test suite with less chance of false negatives. ([Issue 77](https://github.com/jqno/equalsverifier/issues/77))
* ...build EqualsVerifier using Ant 1.9. ([Issue 76](https://github.com/jqno/equalsverifier/issues/76))

Version 1.1.4
-----------
_January 14, 2013_

* ... fork EqualsVerifier on GitHub! EqualsVerifier has moved its code to GitHub. The project frontpage will remain at Google Code.
* ... use EqualsVerifier on a class whose superclasses have no declarations for `equals` and `hashCode`. ([Issue 63](https://github.com/jqno/equalsverifier/issues/63))
* ... get an error when using `#allFieldsShouldBeUsed()` on a class that has fields but no declarations for `equals` and `hashCode` (and hence doesn't use these fields). ([Issue 67](https://github.com/jqno/equalsverifier/issues/67))
* ... get a more informative error message on Abstract Delegation errors: EqualsVerifier now also mentions the name of the abstract method that was called.

Version 1.1.3
-------------
_April 21, 2012_

* ... add static fields to your classes that are tested with `#allFieldsShouldBeUsed()`. EqualsVerifier will no longer complain if these static fields aren't used in your `equals` and `hashCode` methods. ([Issue 57](https://github.com/jqno/equalsverifier/issues/57))
* ... get a complaint from EqualsVerifier when your `equals` method works incorrectly if a field in the class under test is null. ([Issue 59](https://github.com/jqno/equalsverifier/issues/59))

Version 1.1.2
-------------
_March 1, 2012_

* ... stop worrying about EqualsVerifier _recursively_ changing the value of non-final static fields, causing other tests to fail. (Issue 55, [Comment 8](http://github.com/jqno/equalsverifier/issues/55#issuecomment-87376895))

Version 1.1.1
-------------
_February 21, 2012_

* ... suppress `Warning.IDENTICAL_COPY` if you want to use reference equality in an overridden `equals` method. ([Issue 56](https://github.com/jqno/equalsverifier/issues/56))

Version 1.1
-----------
_February 11, 2012_

* ... get a warning if you forgot to include a field in your `equals` or `hashCode` method, by calling the `#allFieldsShouldBeUsed()` method on EqualsVerifier. ([Issue 53](https://github.com/jqno/equalsverifier/issues/53))
* ... get an error message if you include a reference-equality check (`this == obj`), followed by an incorrect instanceof check in your `equals` method. EqualsVerifier will now notice if you do an instanceof check for a class other than the one that you are testing. (Issue 55, [Comment 2](http://github.com/jqno/equalsverifier/issues/55#issuecomment-87376889))
* ... stop worrying about EqualsVerifier changing the value of non-final static fields, causing other tests to fail. ([Issue 52](https://github.com/jqno/equalsverifier/issues/52) and [Issue 55](https://github.com/jqno/equalsverifier/issues/55))
* ... stop worrying about adding prefab values for `File`, `List`, `Set`, `Map` and `Collection` to avoid unjustified warning. ([Issue 49](https://github.com/jqno/equalsverifier/issues/49) and [Issue 51](https://github.com/jqno/equalsverifier/issues/51))

Version 1.0.2
-------------
_August 14, 2011_

* ... find EqualsVerifier in Maven Central! ([Issue 36](https://github.com/jqno/equalsverifier/issues/36))
* ... get an error message when you forget to include an `instanceof` check or a `getClass()` check in your `equals` method. ([Issue 47](https://github.com/jqno/equalsverifier/issues/47))
* ... use EqualsVerifier on a class whose superclass has abstract declarations for `equals` and `hashCode`. ([Issue 48](https://github.com/jqno/equalsverifier/issues/48))

Version 1.0.1
-------------
_April 17, 2011_

* ... use EqualsVerifier on dynamically generated classes by disabling annotation processing. ([Issue 41](https://github.com/jqno/equalsverifier/issues/41))
* ... use EqualsVerifier on classes that are a subclass of one of the classes from `rt.jar`, which are loaded by the system classloader. ([Issue 43](https://github.com/jqno/equalsverifier/issues/43))
* ... use EqualsVerifier on classes with `float` or `double` fields but no `equals` method. ([Issue 44](https://github.com/jqno/equalsverifier/issues/44))
* ... stop worrying about adding prefab values for `Throwable` and `Exception`, to avoid that pesky recursion warning. ([Issue 45](https://github.com/jqno/equalsverifier/issues/45))

Version 1.0
-----------
_February 23, 2011_

* ... use the following annotations on your classes and fields: EqualsVerifier will know what to do!
    * `@Immutable`: EqualsVerifier will not complain about non-final fields if your class is `@Immutable`. (It doesn't matter in which package the annotation is defined; `javax.annotations.concurrent.Immutable`, `net.jcip.annotations.Immutable` or your own implementation will all work fine.)
    * `@Nonnull`, `@NonNull` and `@NotNull`: EqualsVerifier will not check for potential `NullPointerException`s for any field marked with any of these annotations. (Again: the source package doesn't matter.) This is similar to calling `suppress(Warning.NULL_FIELDS)`, but on a per-field basis, instead of all-or-nothing. ([Issue 28](https://github.com/jqno/equalsverifier/issues/28))
    * `@Entity`: EqualsVerifier will not complain about non-final fields if your class is a JPA Entity. Note that this only works for `javax.persistence.Entity`, not for `Entity` annotations from other packages. ([Issue 37](https://github.com/jqno/equalsverifier/issues/37))
    * `@Transient`: Fields marked with this annotation (again, only from `javax.persistence.Transient`), will be treated the same as fields marked with Java's `transient` modifier; i.e., EqualsVerifier will complain if they are used in the `equals` contract.
* ... see which field throws a potential `NullPointerException`, instead of having to guess which one it was. ([Issue 39](https://github.com/jqno/equalsverifier/issues/39))
* ... be sure that EqualsVerifier doesn't detect recursive data structures where there are none. ([Issue 34](https://github.com/jqno/equalsverifier/issues/34))
* ... stop worrying about adding prefab values for `BigDecimal` and `BigInteger`, to avoid that pesky recursion warning. ([Issue 34](https://github.com/jqno/equalsverifier/issues/34))

Version 0.7
-----------
_November 15, 2010_

* ... test `equals` methods that use a call to `getClass()`, instead of an `instanceof` check, to determine the type of the object passed in, by calling the `#useGetClass()` method on EqualsVerifier.
* ... get a warning when you use a transient field in your `equals` or `hashCode` method. Don't worry; you can suppress this warning too.
* ... stop worrying about adding prefab values for certain Java API classes, like `Date`, `GregorianCalendar`, or `Pattern`, to avoid that pesky recursion warning.
* ... get a link to the [Error messages]({{ pcurl('equalsverifier/errormessages') }}) page to get more help, when EqualsVerifier finds an error.
* ... enjoy many javadoc improvements (including the one in [Issue 32](https://github.com/jqno/equalsverifier/issues/32)).
* Also, the back end is almost completely re-written.

Version 0.6.5
-------------
_August 5, 2010_

* ... use EqualsVerifier on classes with fields of a wide variety of Java API types, without getting 'Recursive datastructure' errors all the time. ([Issue 30](https://github.com/jqno/equalsverifier/issues/30))
* ... get a more helpful error message when `equals`, `hashCode` or `toString` throws something other than a `NullPointerException` when one of the fields in `null`. ([Issue 31](https://github.com/jqno/equalsverifier/issues/31))

Version 0.6.4
-------------
_June 13, 2010_

* ... get an appropriate error message when `Arrays.hashCode()` or `Arrays.deepHashCode()` should have been used, instead of a message that a certain field is used in `equals` but not in `hashCode` or the other way around. ([Issue 27](https://github.com/jqno/equalsverifier/issues/27))
* ... get less frequent non-nullity errors on `toString`.

Version 0.6.3
-------------
_May 18, 2010_

* ... test the equals/hashCode contract for classes that don't override `equals` or `hashCode`. ([Issue 23](https://github.com/jqno/equalsverifier/issues/23))
* ... use EqualsVerifier in conjuction with the [EclEmma](http://www.eclemma.org/) code coverage tool. ([Issue 22](https://github.com/jqno/equalsverifier/issues/22))
* ... test classes that contain (indirect) references to non-static inner classes, without getting messages about recursive data structures. ([Issue 21](https://github.com/jqno/equalsverifier/issues/21))

Version 0.6.2
-------------
_February 11, 2010_

* ... use `#withPrefabValues()` for recursive data structure fields in superclasses again. ([Issue 20](https://github.com/jqno/equalsverifier/issues/20))

Version 0.6.1
-------------
_February 6, 2010_

* ... use `#withPrefabValues()` for fields which delegate to abstract methods again. ([Issue 14](https://github.com/jqno/equalsverifier/issues/14))
* ... access the `#verify()` method more quickly using autocompletion in IDEs. (The method `#verbose()` has been renamed to `#debug()`.)

Version 0.6
-----------
_January 30, 2010_

* ... use a more consistent API. `#with(Feature)` is now `#suppress(Warning)`, which feels more Java-y. Former features that were not warnings, are now proper methods on EqualsVerifier: `#verbose()` and `#withRedefinedSuperclass()`.
* ... get better error messages:
    * many messages now span multiple lines for improved readability;
    * hashCodes are printed (where relevant);
    * unexpected exceptions are no longer eaten by EqualsVerifier, so they can be read without calling `#verbose()`;
    * calls to abstract methods from within `equals` and `hashCode`, which cannot be resolved, are now detected and properly reported. ([Issue 14](https://github.com/jqno/equalsverifier/issues/14))
* ... verify classes that contain fields whose `equals` methods might throw `NullPointerException`s. ([Issue 19](https://github.com/jqno/equalsverifier/issues/19))
* ... be sure that EqualsVerifier doesn't detect recursive data structures where there are none. ([Issue 18](https://github.com/jqno/equalsverifier/issues/18))
* ... use fields of type `Class` in your classes. ([Issue 17](https://github.com/jqno/equalsverifier/issues/17))

Version 0.5
-----------
_September 1, 2009_

* ... test classes that contain fields of interface or abstract class types (such as Lists, and other Collection types). ([Issue 12](https://github.com/jqno/equalsverifier/issues/12))
* ... step through the source code in Eclipse after adding the EqualsVerifier jar to your project. ([Issue 11](https://github.com/jqno/equalsverifier/issues/11))

Version 0.4
-----------
_August 29, 2009_

* ... verify equality rules that are more relaxed than simple field-by-field comparison. ([Issue 9](https://github.com/jqno/equalsverifier/issues/9))

Version 0.3
-----------
_August 1, 2009_

* ... use EqualsVerifier without having to call `#withPrefabValues(...)` all the time. ([Issue 7](https://github.com/jqno/equalsverifier/issues/7))

Version 0.2
-----------
_July 3, 2009_

* ... use the _fields are never null_ feature on classes instantiated with `#forClass(Class)`. ([Issue 1](https://github.com/jqno/equalsverifier/issues/1))
* ... check if `Arrays.deepEquals` was used for multidimensional and `Object` arrays. ([Issue 3](https://github.com/jqno/equalsverifier/issues/3))
* ... access optional features through a clean enum instead of through lots of different method calls. ([Issue 4](https://github.com/jqno/equalsverifier/issues/4))
* ... use EqualsVerifier in unit test frameworks other than JUnit 4 ([Issue 5](https://github.com/jqno/equalsverifier/issues/5))
* ... have stacktraces be printed to `System.err`. ([Issue 6](https://github.com/jqno/equalsverifier/issues/6))

Version 0.1
-----------
_June 1, 2009_

* ... use EqualsVerifier!

