# rfacts
### a very simple wrapper around requests/aiohttp for uselessfacts.jsph.pl
#### provides 1 object that implements 2 methods, and 5 attributes.
&nbsp;
### the `fact` constructor takes 2 kwargs:
* #### `language` - Type[str] - the language for the fact to be fetched, can be `en` or `de`
* #### `json` - Type[bool] - if the `get` methods should return the raw json or not
&nbsp;
### each instance of `fact` has the following attributes:
* #### `id` - Type[str] - the id of the fact
* #### `source` - Type[str] - the source for the fact
* #### `language` - Type[str] - the language of the fact
* #### `permalink` - Type[str] - the permanent link to this fact
* #### `text` - Type[str] - the text of the fact itself
&nbsp;
### examples:
```
from rfacts import fact

def main() -> None:
    x = fact()
    x.get()
    print(x.text)

if __name__ == "__main__":
    main()
```

```
from rfacts import fact
import asyncio

async def main() -> None:
    x = fact()
    await x.aget()
    print(x.text)

if __name__ == "__main__":
    asyncio.run(main())
```