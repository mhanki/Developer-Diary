# [Web Framework Project](https://github.com/mhanki/TypeScript-Sandbox/tree/main/projects/web-framework) Notes

**Project structure considerations:**

- [Eventing](https://github.com/mhanki/TypeScript-Sandbox/blob/main/web-framework/src/models/Eventing.ts) might have been okay to assign as a class field to the [User](https://github.com/mhanki/TypeScript-Sandbox/blob/main/web-framework/src/models/User.ts) class, because it seems unlikely that we would have to ever swap it out.
[Sync](https://github.com/mhanki/TypeScript-Sandbox/blob/main/web-framework/src/models/ApiSync.ts) on the other hand could change so that, for example, instead of syncing to an API, we might want to persist data in local storage. So it would be useful to be able to switch the class out if needed.

- Choosing inheritance for the [User](https://github.com/mhanki/TypeScript-Sandbox/blob/main/web-framework/src/models/User.ts) and [Model](https://github.com/mhanki/TypeScript-Sandbox/blob/main/web-framework/src/models/Model.ts) classes enables us to make use of the Model methods directly, instead of having to call a verbose ```user.model.method()``` as we would when using composition. In this case, using inheritance makes sense to be able to make use of shared methods, but also allowing to easily add custom methods for individual models.

**TypeScript Specifics:**

In TypeScript, the keys of an object can be a type (since in JavaScript, object keys are always strings, and strings can be types).  
Example from [Attributes](https://github.com/mhanki/TypeScript-Sandbox/blob/main/web-framework/src/models/Attributes.ts) class:
```TS
get<K extends keyof T>(key: K): T[K] {
  return this.data[key];
}
```
