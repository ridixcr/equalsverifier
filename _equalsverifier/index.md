---
title: EqualsVerifier
blog: equalsverifier
layout: equalsverifier
permalink: /equalsverifier/
---
Quick start
-----------
EqualsVerifier 2.0 requires Java 7 or higher. EqualsVerifier 1.x requires Java 6 or higher.

If you are upgrading from version 1 to version 2, please see the [migration guide]({{ pcurl('equalsverifier/migration1to2') }}).

1. Get EqualsVerifier.
    * Maven users, add this to your POM:

        <pre class="prettyprint">
        &lt;dependency>
            &lt;groupId>nl.jqno.equalsverifier&lt;/groupId>
            &lt;artifactId>equalsverifier&lt;/artifactId>
            &lt;version>2.1.5&lt;/version>
            &lt;scope>test&lt;/scope>
        &lt;/dependency>
        </pre>
    * ANT users, make sure the most recent EqualsVerifier jar is on the classpath. You can download it from [maven.org](http://search.maven.org/#search|gav|1|g%3A%22nl.jqno.equalsverifier%22%20AND%20a%3A%22equalsverifier%22).

    EqualsVerifier doesn't have any dependencies of its own.

2. Use, as follows, in your unit test:
    <pre class="prettyprint">
    @Test
    public void equalsContract() {
        EqualsVerifier.forClass(My.class).verify();
    }
    </pre>
    Or, if you prefer to use a `getClass()` check instead of an `instanceof` check in the body of your `equals` method:

    <pre class="prettyprint">
    @Test
    public void equalsContract() {
        EqualsVerifier.forClass(My.class)
                .usingGetClass()
                .verify();
    }
    </pre>
    With some warnings suppressed:

    <pre class="prettyprint">
    @Test
    public void equalsContract() {
        EqualsVerifier.forClass(My.class)
                .suppress(Warning.NONFINAL_FIELDS, Warning.NULL_FIELDS)
                .verify();
    }
    </pre>

When EqualsVerifier detects a problem, it will explain what it thinks is wrong. In some cases (mostly when it needs more information), it will say what to do to fix the problem.


Need help?
----------
Please take a look at the [Help page]({{ pcurl('equalsverifier/help') }}).


Fork me on GitHub!
------------------
The source for this project is hosted on [GitHub](https://github.com/jqno/equalsverifier). The [issue tracker](https://code.google.com/p/equalsverifier/issues/list) can be found on Google Code.

Pull Requests are welcome! But please also [open an issue](https://code.google.com/p/equalsverifier/issues/list) or [send a message to the Google Group](https://groups.google.com/forum/?fromgroups#!forum/equalsverifier) so we can discuss it.
