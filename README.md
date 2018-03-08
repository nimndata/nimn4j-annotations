# nimn4j-annotations
Core annotations require to parse a Java object to Nimn format and vice versa (under draft)


## Annotations
### Class level
* **@Nimn**
* **@Nimn(sequence=["","",""])**: specify sequence of properties so that changing the order of fields in the class will not effect encoding /decoding
* **@NimnIgnoreProperties({"property1", "property2"})**
* **@NimnIgnoreProperties(ignoreExtra=true)**: Application will not throw error when nimn has data for a field which is not present in annotated class.

### Field level
**@NimnParser(parser.class)**: Helpful when 
* passwords or sensetive information need to be encrypted/decrypted
* when schema level encoding / decoding applies. Like for date/enum etc.

**@NimnIgnore**: An annotated field will be ignored. IDE plugin will also not warn.

**@NimnUnique** : annotated field will not be separated with boundary char. Allowed on enum or boolean type values only.

If field type is enum and all the instances are annotated with **@NimnChar**


Attension
* There is a possibility when you add a field into the class but miss to specify into the @Nimn(sequence), IDE plugin can warn you

## Deserializing
### Using constructors or factory methods
By default nimn4j use default constructor to create instance. Instead, you can annotate a factory methos or a constructor for the same using **@NimnCreator**.


What if a class is singleton, or it's object need to be taken from the pool?
polymorphic types
