# Debug

Debug is a statement that allows outputting in the IO without marking the nearest containing function as having IO effect.

```stick
import io.println

-- this function have no IO effect, despite it causes changes in IO
fn say_hello():
    debug println("hello world")
    => "hello"  -- having no effect, this function needs to return something
```

As the name implies, this is intended for debugging, it may be turned off by a compiler configuration.
