---
title: "Non-nullity: equals/hashCode/toString throws NullPointerExcpetion"
layout: equalsverifier
---
This error occurs when the class under test can throw a `NullPointerException` when one of its fields is null and `equals`/`hashCode`/`toString` is called. For example, `equals` could contain this line:
<pre class="prettyprint">
return foo.equals(other.foo);
</pre>
It will throw a `NullPointerException` if `foo` is null. This can be avoided in two ways:

1. You can add a null check, like so:
<pre class="prettyprint">
return foo == null ? other.foo == null : foo.equals(other.foo);
</pre>

1. If you're certain the field can never be null (for instance, because the class's constructor explicitly checks for it), you can suppress `Warning.NULL_FIELDS` in your call to EqualsVerifier.
