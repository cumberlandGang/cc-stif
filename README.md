# CC-STIF
cc-stif is the **C**umberland **C**ounty **S**imple **T**ext **I**nterchange **F**ormat. Like other interchange formats, it provides a way of transfering structured text between running programs or throughout programming languages.

## Why CC-STIF?
So, any seasoned programmer may be shaking their head at the creation of yet another interchange format. It has gotten to the point within the field that a very popular format is called "YAML", for "Yet Another". They are very common victims of the "Not-invented-here" syndrome.

Well, simply, other markup langauges / interchange formats were too featureful, and needlessly complex. If the project you're working with doesn't need all of JSON's bells (or whistles), why not use something with less of a code footprint?

Additionally, STIF attempts to reduce the number of extranneous characters you need in the document, while still being reasonably parsable in a single line. This reduces the amount of data needed to transmit over the network

## Structure of a CC-STIF document
There are three basic types in a CC-STIF document. These are **objects**, **Constants**, and **Lists**. **Maps** also exist, although they are just special versions of objects, as you will see in a second.

```
favoriteWebsites {
  favorite: http://www.github.com/
  honorableMentions: facebook,twitter,The Washington Post
  sitesIHate: {
		theWorst: 9gag.com
	      }
}

-mapExample1 {
thing1: thing2
thing3: thing4
}

-mapExample2 {
thing1: thing2,thing3
thing2: thing4,thing5
}

constant1: value

```

Here, we have an object. Objects can hold any STIF type (lists, constants, maps, or objects). We also have a couple of maps. The maps are simply objects which are constrained to a single type. This never has to be specified. Unlike JSON, values do not need to be contained inside of an object. Simply, when a STIF document is parsed, it will yeild an array of all of your data.

# License
MIT