# SimpleConfig

A very simple to use configuration library that allows for reading and writing easy-to-read configuration
files with as few lines of code as possible. It is leightweight and does not depend on any other libraries.

## Usage

Using SimpleConfig for your own projects is as easy as creating a class that extends SimpleConfig and has
one or many fields that will hold your configurable values. Let me give you an example:

```Java
public class MainConfig extends SimpleConfig {
    
	@Comment( "Enter a string value" )
	private String myString = "defaultValue";
	
	public String getMyString() {
		return this.myString;
	}
	
}
```

```Java
MainConfig config = new MainConfig();
try {
	config.initialize( new File( "config.cfg" ) );
} catch ( IOException e ) {
	logger.error( "Configuration could not be initialized", e );
}

// You may now call config.getMyString() in order to get the configured value
```

The configuration file produced by the above class would look like this:

```
{
	myString: "defaultValue"
}
```

Per default only primitive types as well as strings are supported yet your application may add custom value
converters in order to support custom types inside your configuration classes.

## License

SimpleConfig is distributed under the terms of the BSD 3-clause license. So feel free to use it in your own projects!

## Maven Repository

If you are using maven and want to simplify your life a bit then feel free to get the latest version of SimpleConfig
from my personal repository. Simply add the following lines to your pom.xml:

```XML
<repositories>
	<repository>
		<id>blackypaw-repo</id>
		<name>BlackyPaw Public Repository</name>
		<url>http://repo.blackypaw.com/content/groups/public/</url>
	</repository>
</repositories>
```

## Authors

SimpleConfig was developed by BlackyPaw with contributions of other authors who agreed to granting all rights on their
respective code contributions to BlackyPaw.

## Contact

If you wish to get in contact feel free to write an email: developers [at] blackypaw [dot] com
