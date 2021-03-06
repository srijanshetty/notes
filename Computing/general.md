Turing Machines
===============

## Acceptance, Rejection and Loop

- We are given for a specification of a languages. For example given an encoding of a Turing machine and a string does the TM accept the string or not. Now we have to create a Turing machine which tells us whether a random encoding belongs to this language or not. That is, we are checking for membership.
- At any given point of time, we only know a subset of strings which belong to this language. Of course, if we knew the entire set of strings which belonged to this language, we are essentially done.

## Decider

- A decider can enumerate the entire set for us. Because it can tell whether a string belongs to this language or not.

## Recognizer

- A recognizer on the other hand gives us a "current" subset of strings which it has accepted. For other strings it may loop. This looping could be indefinite or it could mean that after a lot of time the string may get accepted or rejected. So, in essence we cannot enumerate the entire set of the language.
- Deciders is a model of computation, this means that it has limitations. So, are TM. The only problem is that we assume that TM are the most powerful model of computation that we have.
- Problems are unsolvable because of their intrinsic hardness. Acceptance problem is hard because we cannot determine if the TM will loop on an input or not.

URLs vs. URIs: Differences and Examples
=======================================

> A Uniform Resource Identifier (URI) is a compact sequence of
> characters that identifies an abstract or physical resource.

> A URI can be further classified as a locator, a name, or both. The
> term "Uniform Resource Locator" (URL) refers to the subset of URIs
> that, in addition to identifying a resource, provide a means of
> locating the resource by describing its primary access mechanism
> (e.g., its network "location").

[Wikipedia captures this
well](http://en.wikipedia.org/wiki/Uniform_Resource_Identifier "Uniform Resource Identifier - Wikipedia, the free encyclopedia")
with the following simplification:

> One can classify URIs as locators (URLs), or as names (URNs), or as
> both. A Uniform Resource Name (URN) functions like a person's name,
> while a Uniform Resource Locator (URL) resembles that person's street
> address. In other words: the URN defines an item's identity, while the
> URL provides a method for finding it.

So we get a few things from these descriptions:

1.  First of all (as we see in the diagram as well) a URL is **a type of
    URI**. So if someone tells you that a URL is not a URI, he's wrong.
    But that doesn't mean all URIs are URLs. All butterflies fly, but
    not everything that flies is a butterfly.
2.  The part that makes a URI a URL is the inclusion of the "access
    mechanism", or "network location", e.g. `http://` or `ftp://`.
3.  The URN is the "globally unique" part of the identification; it's a
    unique name.

So let's look at some examples of URIs--again from the RFC:

-   `ftp://ftp.is.co.za/rfc/rfc1808.txt`
-   `http://www.ietf.org/rfc/rfc2396.txt`
-   `ldap://[2001:db8::7]/c=GB?objectClass?one`
-   `mailto:John.Doe@example.com`
-   `news:comp.infosystems.www.servers.unix`
-   `tel:+1-816-555-1212`
-   `telnet://192.0.2.16:80/`
-   `urn:oasis:names:specification:docbook:dtd:xml:4.1.2`

Those are all URIs, and some of them are URLs. Which are URLs? The ones
that show you how to get to them. Again, the name vs. address analogy
serves well.
