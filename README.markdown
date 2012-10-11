# coldfusion-inflector

This is a ColdFusion component which provides the ability to transform
words from singular to plural (and back again), capitalises, CamelCases
and humanises.  It is based on the Ruby on Rails
[ActiveSupport::Inflector][rails-inflector] class.

## Example Usage

Copy the `Inflector.cfc` file somewhere CF can find it, and then:

```cfm
<cfset inflector = createobject("component", "Inflector")>
<cfset plural = inflector.pluralise("person")> <!--- people --->
<cfset singular = inflector.singularise("zombies")> <!--- zombie --->
```

## Pluralisation and Singularisation

Pluralisation and singularisation both take into account:

* Standard grammar rules: the plural is formed by adding `s` to the
  end of the singlar form.
* Special cases: specific cases the occur with some word forms, such
  as `analysis` to `analyses`.
* Irregulars: where the singluar/plural don't follow standard rules,
  e.g. `person` becomes `people`.
* Uncountables: words which are the same in both singular and plural
  form, e.g. `rice`, `money`.

## Other String Functions

* `capitalise` capitalises the first character in a string: `test`
  becomes `Test`
* `CamelCase` converts a given string to CamelCase, with all
  non-alphanumeric characters stripped: `camel_case` becomes `CamelCase`
* `variablise` converts a string to an underscore-separated list:
  `CamelCase` becomes `camel_case`
* `humanise` converts a string to a human-readable form:
  `CamelCase` becomes `Camel Case`
* `pad` pads a given string with spaces.

See `test/tests/InflectorTest.cfc` for how other strings are handled.

## Licensing and Attribution

coldfusion-inflector was developed by [Tim Blair][timblair] and is
released under the MIT license as detailed in the LICENSE file that
should be distributed with this library; the source code is
[freely available](http://github.com/timblair/coldfusion-inflector).

[rails-inflector]: http://api.rubyonrails.org/classes/ActiveSupport/Inflector.html
[timblair]: http://tim.bla.ir/
[cf-inflector]: http://github.com/timblair/coldfusion-inflector
