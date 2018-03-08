# nimn4j-annotations
Core annotations require to parse a Java object to Nimn format and vice versa (under draft)


## Annotations
### Class level
* @Nimn
* @Nimn(sequence=["","",""])//specify sequence so that changing the order of fields in the class will not effect encoding /decoding
* @NimnIgnoreProperties({"property1", "property2"})
* @NimnIgnoreProperties(ignoreExtra=true)

### Field level
**@NimnParser(parser.class)**: Helpful when 
* passwords or sensetive information need to be encrypted/decrypted
* when schema level encoding / decoding applies. Like for date/enum etc.

**@NimnUnique** : annotated field will not be separated with boundary char. Allowed on enum or boolean type values only.

If field type is enum and all the instances are annotated with @NimnChar
