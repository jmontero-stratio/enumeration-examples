# Scala Enumerations

This repository demonstrates the pros and cons of `scala.Enumeration` and examines alternative structures.

## Structure

**_src/main/java_** - two examples of Java `enum` classes.

**_src/main/scala_** - examples of various enumerations:

* _scala-lang-enum.scala_ - the `scala.Enumeration` example

* _klang_enum_weekday.scala_ and _klang_enum_planets.scala_ - examples using the DIY Enum class.

* _sealed-enum-weekday.scala_ and _sealed-enum-planets.scala_ - examples using sealed traits (or abstract class) and class objects (or classes).

**macros** - an SBT project containing the macros used in the _sealed-enum-planets.scala_ example.

## Running

	enum-eval (master)$ sbt
	> run
	[info] Compiling 5 Scala sources and 2 Java sources to enum-eval/target/scala-2.11/classes...
	[warn] enum-eval/src/main/scala/klang-enum-planets.scala:67: match may not be exhaustive.
	[warn] It would fail on the following inputs: $anon(), $anon(), $anon(), $anon(), $anon(), $anon(), $anon(), $anon()
	[warn]     planet match {
	[warn]     ^
	[warn] enum-eval/src/main/scala/klang-enum-weekday.scala:67: match may not be exhaustive.
	[warn] It would fail on the following inputs: $anon(), $anon(), $anon(), $anon(), $anon(), $anon(), $anon()
	[warn]   def weekend(d: WeekDay.EnumVal) = d match {
	[warn]                                     ^
	[warn] enum-eval/src/main/scala/sealed-enum-weekday.scala:32: match may not be exhaustive.
	[warn] It would fail on the following inputs: Fri, Mon, Thu, Tue, Wed
	[warn]   def weekend(d: WeekDay.EnumVal) = d match {
	[warn]                                     ^
	[warn] three warnings found

	Multiple main classes detected, select one to run:

	 [1] SealedEnum
	 [2] KlangEnum
	 [3] SealedEnumPlanets
	 [4] KlangEnumPlanets
	 [5] ScalaLangEnumeration

	Enter number: 3

	[info] Running SealedEnumPlanets
	TreeSet(Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, Neptune)
	TreeSet(Jupiter, Saturn, Uranus, Neptune)
	Your weight on Mercury is   26.4 kg
	Your weight on Venus   is   63.3 kg
	Your weight on Earth   is   70.0 kg
	Your weight on Mars    is   26.5 kg
	Your weight on Jupiter is  177.1 kg
	Your weight on Saturn  is   74.6 kg
	Your weight on Uranus  is   63.4 kg
	Your weight on Neptune is   79.7 kg
	[success] Total time: 18 s, completed 23-Aug-2014 10:22:05
	
**If you're interested in this content, sign up to our mailing list at http://underscore.io where we post updates and code samples about Scala, Scala Macros, and functional programming in general.**
