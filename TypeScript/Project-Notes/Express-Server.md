# [Express Server](https://github.com/mhanki/TypeScript-Sandbox/tree/main/projects/express-server2) Notes

## How does the solution with decorators and controllers work

--> Node executes our code
--> Class definitions are read in - decorators are executed
--> Decorators associate route configuration info wih the method by using metadata
--> All method decorators run
--> The very last decorator to run is always the class decorator, so in this case, the @controller
--> Because of that, it can read the metadata from each method and add the complete route definitions to the router.

## Metadata

- Metadata is still experimential and a proposed feature to be added to JavaScript
- It's a little snippet of information that can essentially be tied to any type of object (so a method, property, or class definition)
- It can be used by TypeScript to actually provide/persist type information to JavaScript
- It's read and written by using the ```reflect-metadata```package