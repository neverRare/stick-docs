# Debug

Debug is a statement that allows outputting in the IO without marking the nearest containing function as unsteady.

```stick
import io.println

-- this function is steady, despite it causes changes in IO
fn say_hello():
    debug println("hello world")
    => "hello"  -- being steady, this function needs to return something
```

As the name implies, this is intended for debugging, it may be turned off by a compiler configuration.
