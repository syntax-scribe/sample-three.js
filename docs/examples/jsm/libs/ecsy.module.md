[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ecsy.module.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 110 |
| 🧱 Classes | 14 |
| 📊 Variables & Constants | 82 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/libs/ecsy.module.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ids` | `any[]` | let/var | `[]` | ✗ |
| `T` | `any` | let/var | `Components[n]` | ✗ |
| `operator` | `any` | let/var | `T.operator === "not" ? "!" : T.operator` | ✗ |
| `hasWindow` | `boolean` | let/var | `typeof window !== "undefined"` | ✗ |
| `now` | `any` | let/var | `hasWindow && typeof window.performance !== "undefined" ? performance.now.bind...` | ✗ |
| `system` | `any` | let/var | `new SystemClass(this.world, attributes)` | ✗ |
| `stats` | `{ numSystems: number; systems: {}; }` | let/var | `{ numSystems: this._systems.length, systems: {}, }` | ✗ |
| `system` | `any` | let/var | `this._systems[i]` | ✗ |
| `systemStats` | `{ queries: {}; executeTime: any; }` | let/var | `(stats.systems[system.getName()] = { queries: {}, executeTime: system.execute...` | ✗ |
| `clone` | `any` | let/var | `new this.T()` | ✗ |
| `listeners` | `{}` | let/var | `this._listeners` | ✗ |
| `listenerArray` | `any` | let/var | `this._listeners[eventName]` | ✗ |
| `listenerArray` | `any` | let/var | `this._listeners[eventName]` | ✗ |
| `entity` | `any` | let/var | `manager._entities[i]` | ✗ |
| `query` | `any` | let/var | `this._queries[queryName]` | ✗ |
| `query` | `any` | let/var | `this._queries[queryName]` | ✗ |
| `query` | `any` | let/var | `this._queries[queryName]` | ✗ |
| `query` | `any` | let/var | `this._queries[key]` | ✗ |
| `stats` | `{}` | let/var | `{}` | ✗ |
| `schema` | `any` | let/var | `this.constructor.schema` | ✗ |
| `schemaProp` | `any` | let/var | `schema[key]` | ✗ |
| `type` | `any` | let/var | `schemaProp.type` | ✗ |
| `schema` | `any` | let/var | `this.constructor.schema` | ✗ |
| `prop` | `any` | let/var | `schema[key]` | ✗ |
| `schema` | `any` | let/var | `this.constructor.schema` | ✗ |
| `schemaProp` | `any` | let/var | `schema[key]` | ✗ |
| `type` | `any` | let/var | `schemaProp.type` | ✗ |
| `schema` | `any` | let/var | `this.constructor.schema` | ✗ |
| `clone` | `any` | let/var | `new this.T(this.entityManager)` | ✗ |
| `component` | `any` | let/var | `componentPool ? componentPool.acquire() : new Component(values)` | ✗ |
| `component` | `any` | let/var | `entity._components[Component._typeId]` | ✗ |
| `Components` | `any[]` | let/var | `entity._ComponentTypes` | ✗ |
| `entity` | `any` | let/var | `this.entitiesToRemove[i]` | ✗ |
| `entity` | `any` | let/var | `this.entitiesWithComponentsToRemove[i]` | ✗ |
| `component` | `any` | let/var | `entity._componentsToRemove[Component._typeId]` | ✗ |
| `stats` | `{ numEntities: number; numQueries: nu...` | let/var | `{ numEntities: this._entities.length, numQueries: Object.keys(this._queryMana...` | ✗ |
| `pool` | `any` | let/var | `this.componentsManager._componentPool[ecsyComponentId]` | ✗ |
| `ENTITY_CREATED` | `"EntityManager#ENTITY_CREATE"` | let/var | `"EntityManager#ENTITY_CREATE"` | ✗ |
| `ENTITY_REMOVED` | `"EntityManager#ENTITY_REMOVED"` | let/var | `"EntityManager#ENTITY_REMOVED"` | ✗ |
| `COMPONENT_ADDED` | `"EntityManager#COMPONENT_ADDED"` | let/var | `"EntityManager#COMPONENT_ADDED"` | ✗ |
| `COMPONENT_REMOVE` | `"EntityManager#COMPONENT_REMOVE"` | let/var | `"EntityManager#COMPONENT_REMOVE"` | ✗ |
| `schema` | `any` | let/var | `Component.schema` | ✗ |
| `prop` | `any` | let/var | `schema[propName]` | ✗ |
| `Version` | `"0.3.1"` | let/var | `"0.3.1"` | ✗ |
| `proxyMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `proxyHandler` | `{ set(target: any, prop: any): never; }` | let/var | `{ set(target, prop) { throw new Error( `Tried to write to "${target.construct...` | ✗ |
| `component` | `any` | let/var | `this._components[Component._typeId]` | ✗ |
| `component` | `any` | let/var | `this._componentsToRemove[Component._typeId]` | ✗ |
| `component` | `any` | let/var | `this._components[Component._typeId]` | ✗ |
| `query` | `any` | let/var | `this.queries[i]` | ✗ |
| `srcComponent` | `any` | let/var | `src._components[ecsyComponentId]` | ✗ |
| `DEFAULT_OPTIONS` | `{ entityPoolSize: number; entityClass...` | let/var | `{ entityPoolSize: 0, entityClass: Entity, }` | ✗ |
| `event` | `CustomEvent<{ world: this; version: s...` | let/var | `new CustomEvent("ecsy-world-created", { detail: { world: this, version: Versi...` | ✗ |
| `stats` | `{ entities: { numEntities: number; nu...` | let/var | `{ entities: this.entityManager.stats(), system: this.systemManager.stats(), }` | ✗ |
| `query` | `any` | let/var | `this._mandatoryQueries[i]` | ✗ |
| `queryConfig` | `any` | let/var | `this.constructor.queries[queryName]` | ✗ |
| `Components` | `any` | let/var | `queryConfig.components` | ✗ |
| `validEvents` | `string[]` | let/var | `["added", "removed", "changed"]` | ✗ |
| `eventMapping` | `{ added: string; removed: string; cha...` | let/var | `{ added: Query.prototype.ENTITY_ADDED, removed: Query.prototype.ENTITY_REMOVE...` | ✗ |
| `event` | `any` | let/var | `queryConfig.listen[eventName]` | ✗ |
| `eventList` | `any[]` | let/var | `(this.queries[queryName][eventName] = [])` | ✗ |
| `eventList` | `any[]` | let/var | `(this.queries[queryName][eventName] = [])` | ✗ |
| `eventList` | `any[]` | let/var | `(this.queries[queryName][eventName] = [])` | ✗ |
| `query` | `any` | let/var | `this.queries[queryName]` | ✗ |
| `json` | `{ name: any; enabled: boolean; execut...` | let/var | `{ name: this.getName(), enabled: this.enabled, executeTime: this.executeTime,...` | ✗ |
| `queries` | `any` | let/var | `this.constructor.queries` | ✗ |
| `query` | `any` | let/var | `this.queries[queryName]` | ✗ |
| `queryDefinition` | `any` | let/var | `queries[queryName]` | ✗ |
| `jsonQuery` | `{ key: any; }` | let/var | `(json.queries[queryName] = { key: this._queries[queryName].key, })` | ✗ |
| `methods` | `string[]` | let/var | `["added", "removed", "changed"]` | ✗ |
| `mandatoryProperties` | `string[]` | let/var | `["name", "default", "copy", "clone"]` | ✗ |
| `Types` | `{ Number: any; Boolean: any; String: ...` | let/var | `{ Number: createType({ name: "Number", default: 0, copy: copyValue, clone: cl...` | ✗ |
| `result` | `string` | let/var | `""` | ✗ |
| `characters` | `string` | let/var | `"ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"` | ✗ |
| `charactersLength` | `number` | let/var | `characters.length` | ✗ |
| `wrapFunctions` | `string[]` | let/var | `["error", "warning", "log"]` | ✗ |
| `Version` | `string` | let/var | `""` | ✗ |
| `worldsBeforeLoading` | `any[]` | let/var | `[]` | ✗ |
| `world` | `any` | let/var | `e.detail.world` | ✗ |
| `peer` | `any` | let/var | `new Peer(remoteId, { host: "peerjs.ecsy.io", secure: true, port: 443, config:...` | ✗ |
| `event` | `CustomEvent<{ world: any; version: st...` | let/var | `new CustomEvent("ecsy-world-created", { detail: { world: world, version: Vers...` | ✗ |
| `urlParams` | `URLSearchParams` | let/var | `new URLSearchParams(window.location.search)` | ✗ |


---

## Functions

### `queryKey(Components: any): string`

**JSDoc:**
```typescript
/**
 * Get a key from a list of components
 * @param {Array(Component)} Components Array of components to generate the key
 * @private
 */
```

**Parameters:**

- **`Components`** `any`

**Returns:** `string`

**Calls:**

- `componentRegistered`
- `ids.push`
- `ids.sort().join`

<details><summary>Code</summary>

```typescript
function queryKey(Components) {
  var ids = [];
  for (var n = 0; n < Components.length; n++) {
    var T = Components[n];

    if (!componentRegistered(T)) {
      throw new Error(`Tried to create a query with an unregistered component`);
    }

    if (typeof T === "object") {
      var operator = T.operator === "not" ? "!" : T.operator;
      ids.push(operator + T.Component._typeId);
    } else {
      ids.push(T._typeId);
    }
  }

  return ids.sort().join("-");
}
```
</details>

### `componentRegistered(T: any): boolean`

**Parameters:**

- **`T`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function componentRegistered(T) {
  return (
    (typeof T === "object" && T.Component._typeId !== undefined) ||
    (T.isComponent && T._typeId !== undefined)
  );
}
```
</details>

### `SystemManager.registerSystem(SystemClass: any, attributes: any): this`

**Parameters:**

- **`SystemClass`** `any`
- **`attributes`** `any`

**Returns:** `this`

**Calls:**

- `this.getSystem`
- `console.warn`
- `SystemClass.getName`
- `system.init`
- `this._systems.push`
- `this._executeSystems.push`
- `this.sortSystems`

<details><summary>Code</summary>

```typescript
registerSystem(SystemClass, attributes) {
    if (!SystemClass.isSystem) {
      throw new Error(
        `System '${SystemClass.name}' does not extend 'System' class`
      );
    }

    if (this.getSystem(SystemClass) !== undefined) {
      console.warn(`System '${SystemClass.getName()}' already registered.`);
      return this;
    }

    var system = new SystemClass(this.world, attributes);
    if (system.init) system.init(attributes);
    system.order = this._systems.length;
    this._systems.push(system);
    if (system.execute) {
      this._executeSystems.push(system);
      this.sortSystems();
    }
    return this;
  }
```
</details>

### `SystemManager.unregisterSystem(SystemClass: any): this`

**Parameters:**

- **`SystemClass`** `any`

**Returns:** `this`

**Calls:**

- `this.getSystem`
- `console.warn`
- `SystemClass.getName`
- `this._systems.splice`
- `this._systems.indexOf`
- `this._executeSystems.splice`
- `this._executeSystems.indexOf`

**Internal Comments:**
```
// @todo Add system.unregister() call to free resources
```

<details><summary>Code</summary>

```typescript
unregisterSystem(SystemClass) {
    let system = this.getSystem(SystemClass);
    if (system === undefined) {
      console.warn(
        `Can unregister system '${SystemClass.getName()}'. It doesn't exist.`
      );
      return this;
    }

    this._systems.splice(this._systems.indexOf(system), 1);

    if (system.execute) {
      this._executeSystems.splice(this._executeSystems.indexOf(system), 1);
    }

    // @todo Add system.unregister() call to free resources
    return this;
  }
```
</details>

### `SystemManager.sortSystems(): void`

**Returns:** `void`

**Calls:**

- `this._executeSystems.sort`

<details><summary>Code</summary>

```typescript
sortSystems() {
    this._executeSystems.sort((a, b) => {
      return a.priority - b.priority || a.order - b.order;
    });
  }
```
</details>

### `SystemManager.getSystem(SystemClass: any): any`

**Parameters:**

- **`SystemClass`** `any`

**Returns:** `any`

**Calls:**

- `this._systems.find`

<details><summary>Code</summary>

```typescript
getSystem(SystemClass) {
    return this._systems.find((s) => s instanceof SystemClass);
  }
```
</details>

### `SystemManager.getSystems(): any[]`

**Returns:** `any[]`

<details><summary>Code</summary>

```typescript
getSystems() {
    return this._systems;
  }
```
</details>

### `SystemManager.removeSystem(SystemClass: any): void`

**Parameters:**

- **`SystemClass`** `any`

**Returns:** `void`

**Calls:**

- `this._systems.indexOf`
- `this._systems.splice`

<details><summary>Code</summary>

```typescript
removeSystem(SystemClass) {
    var index = this._systems.indexOf(SystemClass);
    if (!~index) return;

    this._systems.splice(index, 1);
  }
```
</details>

### `SystemManager.executeSystem(system: any, delta: any, time: any): void`

**Parameters:**

- **`system`** `any`
- **`delta`** `any`
- **`time`** `any`

**Returns:** `void`

**Calls:**

- `system.canExecute`
- `now`
- `system.execute`
- `system.clearEvents`

<details><summary>Code</summary>

```typescript
executeSystem(system, delta, time) {
    if (system.initialized) {
      if (system.canExecute()) {
        let startTime = now();
        system.execute(delta, time);
        system.executeTime = now() - startTime;
        this.lastExecutedSystem = system;
        system.clearEvents();
      }
    }
  }
```
</details>

### `SystemManager.stop(): void`

**Returns:** `void`

**Calls:**

- `this._executeSystems.forEach`
- `system.stop`

<details><summary>Code</summary>

```typescript
stop() {
    this._executeSystems.forEach((system) => system.stop());
  }
```
</details>

### `SystemManager.execute(delta: any, time: any, forcePlay: any): void`

**Parameters:**

- **`delta`** `any`
- **`time`** `any`
- **`forcePlay`** `any`

**Returns:** `void`

**Calls:**

- `this._executeSystems.forEach`
- `this.executeSystem`

<details><summary>Code</summary>

```typescript
execute(delta, time, forcePlay) {
    this._executeSystems.forEach(
      (system) =>
        (forcePlay || system.enabled) && this.executeSystem(system, delta, time)
    );
  }
```
</details>

### `SystemManager.stats(): { numSystems: number; systems: {}; }`

**Returns:** `{ numSystems: number; systems: {}; }`

**Calls:**

- `system.getName`
- `system.ctx[name].stats`

<details><summary>Code</summary>

```typescript
stats() {
    var stats = {
      numSystems: this._systems.length,
      systems: {},
    };

    for (var i = 0; i < this._systems.length; i++) {
      var system = this._systems[i];
      var systemStats = (stats.systems[system.getName()] = {
        queries: {},
        executeTime: system.executeTime,
      });
      for (var name in system.ctx) {
        systemStats.queries[name] = system.ctx[name].stats();
      }
    }

    return stats;
  }
```
</details>

### `ObjectPool.acquire(): any`

**Returns:** `any`

**Calls:**

- `this.expand`
- `Math.round`
- `this.freeList.pop`

**Internal Comments:**
```
// Grow the list by 20%ish if we're out
```

<details><summary>Code</summary>

```typescript
acquire() {
    // Grow the list by 20%ish if we're out
    if (this.freeList.length <= 0) {
      this.expand(Math.round(this.count * 0.2) + 1);
    }

    var item = this.freeList.pop();

    return item;
  }
```
</details>

### `ObjectPool.release(item: any): void`

**Parameters:**

- **`item`** `any`

**Returns:** `void`

**Calls:**

- `item.reset`
- `this.freeList.push`

<details><summary>Code</summary>

```typescript
release(item) {
    item.reset();
    this.freeList.push(item);
  }
```
</details>

### `ObjectPool.expand(count: any): void`

**Parameters:**

- **`count`** `any`

**Returns:** `void`

**Calls:**

- `this.freeList.push`

<details><summary>Code</summary>

```typescript
expand(count) {
    for (var n = 0; n < count; n++) {
      var clone = new this.T();
      clone._pool = this;
      this.freeList.push(clone);
    }
    this.count += count;
  }
```
</details>

### `ObjectPool.totalSize(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
totalSize() {
    return this.count;
  }
```
</details>

### `ObjectPool.totalFree(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
totalFree() {
    return this.freeList.length;
  }
```
</details>

### `ObjectPool.totalUsed(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
totalUsed() {
    return this.count - this.freeList.length;
  }
```
</details>

### `EventDispatcher.addEventListener(eventName: string, listener: Function): void`

**JSDoc:**
```typescript
/**
   * Add an event listener
   * @param {String} eventName Name of the event to listen
   * @param {Function} listener Callback to trigger when the event is fired
   */
```

**Parameters:**

- **`eventName`** `string`
- **`listener`** `Function`

**Returns:** `void`

**Calls:**

- `listeners[eventName].indexOf`
- `listeners[eventName].push`

<details><summary>Code</summary>

```typescript
addEventListener(eventName, listener) {
    let listeners = this._listeners;
    if (listeners[eventName] === undefined) {
      listeners[eventName] = [];
    }

    if (listeners[eventName].indexOf(listener) === -1) {
      listeners[eventName].push(listener);
    }
  }
```
</details>

### `EventDispatcher.hasEventListener(eventName: string, listener: Function): boolean`

**JSDoc:**
```typescript
/**
   * Check if an event listener is already added to the list of listeners
   * @param {String} eventName Name of the event to check
   * @param {Function} listener Callback for the specified event
   */
```

**Parameters:**

- **`eventName`** `string`
- **`listener`** `Function`

**Returns:** `boolean`

**Calls:**

- `this._listeners[eventName].indexOf`

<details><summary>Code</summary>

```typescript
hasEventListener(eventName, listener) {
    return (
      this._listeners[eventName] !== undefined &&
      this._listeners[eventName].indexOf(listener) !== -1
    );
  }
```
</details>

### `EventDispatcher.removeEventListener(eventName: string, listener: Function): void`

**JSDoc:**
```typescript
/**
   * Remove an event listener
   * @param {String} eventName Name of the event to remove
   * @param {Function} listener Callback for the specified event
   */
```

**Parameters:**

- **`eventName`** `string`
- **`listener`** `Function`

**Returns:** `void`

**Calls:**

- `listenerArray.indexOf`
- `listenerArray.splice`

<details><summary>Code</summary>

```typescript
removeEventListener(eventName, listener) {
    var listenerArray = this._listeners[eventName];
    if (listenerArray !== undefined) {
      var index = listenerArray.indexOf(listener);
      if (index !== -1) {
        listenerArray.splice(index, 1);
      }
    }
  }
```
</details>

### `EventDispatcher.dispatchEvent(eventName: string, entity: Entity, component: Component): void`

**JSDoc:**
```typescript
/**
   * Dispatch an event
   * @param {String} eventName Name of the event to dispatch
   * @param {Entity} entity (Optional) Entity to emit
   * @param {Component} component
   */
```

**Parameters:**

- **`eventName`** `string`
- **`entity`** `Entity`
- **`component`** `Component`

**Returns:** `void`

**Calls:**

- `listenerArray.slice`
- `array[i].call`

<details><summary>Code</summary>

```typescript
dispatchEvent(eventName, entity, component) {
    this.stats.fired++;

    var listenerArray = this._listeners[eventName];
    if (listenerArray !== undefined) {
      var array = listenerArray.slice(0);

      for (var i = 0; i < array.length; i++) {
        array[i].call(this, entity, component);
      }
    }
  }
```
</details>

### `EventDispatcher.resetCounters(): void`

**JSDoc:**
```typescript
/**
   * Reset stats counters
   */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
resetCounters() {
    this.stats.fired = this.stats.handled = 0;
  }
```
</details>

### `Query.addEntity(entity: Entity): void`

**JSDoc:**
```typescript
/**
   * Add entity to this query
   * @param {Entity} entity
   */
```

**Parameters:**

- **`entity`** `Entity`

**Returns:** `void`

**Calls:**

- `entity.queries.push`
- `this.entities.push`
- `this.eventDispatcher.dispatchEvent`

<details><summary>Code</summary>

```typescript
addEntity(entity) {
    entity.queries.push(this);
    this.entities.push(entity);

    this.eventDispatcher.dispatchEvent(Query.prototype.ENTITY_ADDED, entity);
  }
```
</details>

### `Query.removeEntity(entity: Entity): void`

**JSDoc:**
```typescript
/**
   * Remove entity from this query
   * @param {Entity} entity
   */
```

**Parameters:**

- **`entity`** `Entity`

**Returns:** `void`

**Calls:**

- `this.entities.indexOf`
- `this.entities.splice`
- `entity.queries.indexOf`
- `entity.queries.splice`
- `this.eventDispatcher.dispatchEvent`

<details><summary>Code</summary>

```typescript
removeEntity(entity) {
    let index = this.entities.indexOf(entity);
    if (~index) {
      this.entities.splice(index, 1);

      index = entity.queries.indexOf(this);
      entity.queries.splice(index, 1);

      this.eventDispatcher.dispatchEvent(
        Query.prototype.ENTITY_REMOVED,
        entity
      );
    }
  }
```
</details>

### `Query.match(entity: any): boolean`

**Parameters:**

- **`entity`** `any`

**Returns:** `boolean`

**Calls:**

- `entity.hasAllComponents`
- `entity.hasAnyComponents`

<details><summary>Code</summary>

```typescript
match(entity) {
    return (
      entity.hasAllComponents(this.Components) &&
      !entity.hasAnyComponents(this.NotComponents)
    );
  }
```
</details>

### `Query.toJSON(): { key: string; reactive: boolean; components: { included: any; not: any[]; }; numEntities: number; }`

**Returns:** `{ key: string; reactive: boolean; components: { included: any; not: any[]; }; numEntities: number; }`

**Calls:**

- `this.Components.map`
- `this.NotComponents.map`

<details><summary>Code</summary>

```typescript
toJSON() {
    return {
      key: this.key,
      reactive: this.reactive,
      components: {
        included: this.Components.map((C) => C.name),
        not: this.NotComponents.map((C) => C.name),
      },
      numEntities: this.entities.length,
    };
  }
```
</details>

### `Query.stats(): { numComponents: any; numEntities: number; }`

**JSDoc:**
```typescript
/**
   * Return stats for this query
   */
```

**Returns:** `{ numComponents: any; numEntities: number; }`

<details><summary>Code</summary>

```typescript
stats() {
    return {
      numComponents: this.Components.length,
      numEntities: this.entities.length,
    };
  }
```
</details>

### `QueryManager.onEntityRemoved(entity: any): void`

**Parameters:**

- **`entity`** `any`

**Returns:** `void`

**Calls:**

- `entity.queries.indexOf`
- `query.removeEntity`

<details><summary>Code</summary>

```typescript
onEntityRemoved(entity) {
    for (var queryName in this._queries) {
      var query = this._queries[queryName];
      if (entity.queries.indexOf(query) !== -1) {
        query.removeEntity(entity);
      }
    }
  }
```
</details>

### `QueryManager.onEntityComponentAdded(entity: Entity, Component: Component): void`

**JSDoc:**
```typescript
/**
   * Callback when a component is added to an entity
   * @param {Entity} entity Entity that just got the new component
   * @param {Component} Component Component added to the entity
   */
```

**Parameters:**

- **`entity`** `Entity`
- **`Component`** `Component`

**Returns:** `void`

**Calls:**

- `query.NotComponents.indexOf`
- `query.entities.indexOf`
- `query.removeEntity`
- `query.Components.indexOf`
- `query.match`
- `query.addEntity`

**Internal Comments:**
```
// @todo Use bitmask for checking components?
// Check each indexed query to see if we need to add this entity to the list
// Add the entity only if:
// Component is in the query
// and Entity has ALL the components of the query
// and Entity is not already in the query
```

<details><summary>Code</summary>

```typescript
onEntityComponentAdded(entity, Component) {
    // @todo Use bitmask for checking components?

    // Check each indexed query to see if we need to add this entity to the list
    for (var queryName in this._queries) {
      var query = this._queries[queryName];

      if (
        !!~query.NotComponents.indexOf(Component) &&
        ~query.entities.indexOf(entity)
      ) {
        query.removeEntity(entity);
        continue;
      }

      // Add the entity only if:
      // Component is in the query
      // and Entity has ALL the components of the query
      // and Entity is not already in the query
      if (
        !~query.Components.indexOf(Component) ||
        !query.match(entity) ||
        ~query.entities.indexOf(entity)
      )
        continue;

      query.addEntity(entity);
    }
  }
```
</details>

### `QueryManager.onEntityComponentRemoved(entity: Entity, Component: Component): void`

**JSDoc:**
```typescript
/**
   * Callback when a component is removed from an entity
   * @param {Entity} entity Entity to remove the component from
   * @param {Component} Component Component to remove from the entity
   */
```

**Parameters:**

- **`entity`** `Entity`
- **`Component`** `Component`

**Returns:** `void`

**Calls:**

- `query.NotComponents.indexOf`
- `query.entities.indexOf`
- `query.match`
- `query.addEntity`
- `query.Components.indexOf`
- `query.removeEntity`

<details><summary>Code</summary>

```typescript
onEntityComponentRemoved(entity, Component) {
    for (var queryName in this._queries) {
      var query = this._queries[queryName];

      if (
        !!~query.NotComponents.indexOf(Component) &&
        !~query.entities.indexOf(entity) &&
        query.match(entity)
      ) {
        query.addEntity(entity);
        continue;
      }

      if (
        !!~query.Components.indexOf(Component) &&
        !!~query.entities.indexOf(entity) &&
        !query.match(entity)
      ) {
        query.removeEntity(entity);
        continue;
      }
    }
  }
```
</details>

### `QueryManager.getQuery(Components: Component): any`

**JSDoc:**
```typescript
/**
   * Get a query for the specified components
   * @param {Component} Components Components that the query should have
   */
```

**Parameters:**

- **`Components`** `Component`

**Returns:** `any`

**Calls:**

- `queryKey`

<details><summary>Code</summary>

```typescript
getQuery(Components) {
    var key = queryKey(Components);
    var query = this._queries[key];
    if (!query) {
      this._queries[key] = query = new Query(Components, this._world);
    }
    return query;
  }
```
</details>

### `QueryManager.stats(): {}`

**JSDoc:**
```typescript
/**
   * Return some stats from this class
   */
```

**Returns:** `{}`

**Calls:**

- `this._queries[queryName].stats`

<details><summary>Code</summary>

```typescript
stats() {
    var stats = {};
    for (var queryName in this._queries) {
      stats[queryName] = this._queries[queryName].stats();
    }
    return stats;
  }
```
</details>

### `Component.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `source.hasOwnProperty`
- `prop.type.copy`
- `this.checkUndefinedAttributes`

**Internal Comments:**
```
// @DEBUG
```

<details><summary>Code</summary>

```typescript
copy(source) {
    const schema = this.constructor.schema;

    for (const key in schema) {
      const prop = schema[key];

      if (source.hasOwnProperty(key)) {
        this[key] = prop.type.copy(source[key], this[key]);
      }
    }

    // @DEBUG
    {
      this.checkUndefinedAttributes(source);
    }

    return this;
  }
```
</details>

### `Component.clone(): any`

**Returns:** `any`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {
    return new this.constructor().copy(this);
  }
```
</details>

### `Component.reset(): void`

**Returns:** `void`

**Calls:**

- `schemaProp.hasOwnProperty`
- `schemaProp.type.copy`
- `type.copy`

<details><summary>Code</summary>

```typescript
reset() {
    const schema = this.constructor.schema;

    for (const key in schema) {
      const schemaProp = schema[key];

      if (schemaProp.hasOwnProperty("default")) {
        this[key] = schemaProp.type.copy(schemaProp.default, this[key]);
      } else {
        const type = schemaProp.type;
        this[key] = type.copy(type.default, this[key]);
      }
    }
  }
```
</details>

### `Component.dispose(): void`

**Returns:** `void`

**Calls:**

- `this._pool.release`

<details><summary>Code</summary>

```typescript
dispose() {
    if (this._pool) {
      this._pool.release(this);
    }
  }
```
</details>

### `Component.getName(): any`

**Returns:** `any`

**Calls:**

- `this.constructor.getName`

<details><summary>Code</summary>

```typescript
getName() {
    return this.constructor.getName();
  }
```
</details>

### `Component.checkUndefinedAttributes(src: any): void`

**Parameters:**

- **`src`** `any`

**Returns:** `void`

**Calls:**

- `Object.keys(src).forEach`
- `schema.hasOwnProperty`
- `console.warn`

**Internal Comments:**
```
// Check that the attributes defined in source are also defined in the schema (x6)
```

<details><summary>Code</summary>

```typescript
checkUndefinedAttributes(src) {
    const schema = this.constructor.schema;

    // Check that the attributes defined in source are also defined in the schema
    Object.keys(src).forEach((srcKey) => {
      if (!schema.hasOwnProperty(srcKey)) {
        console.warn(
          `Trying to set attribute '${srcKey}' not defined in the '${this.constructor.name}' schema. Please fix the schema, the attribute value won't be set`
        );
      }
    });
  }
```
</details>

### `EntityPool.expand(count: any): void`

**Parameters:**

- **`count`** `any`

**Returns:** `void`

**Calls:**

- `this.freeList.push`

<details><summary>Code</summary>

```typescript
expand(count) {
    for (var n = 0; n < count; n++) {
      var clone = new this.T(this.entityManager);
      clone._pool = this;
      this.freeList.push(clone);
    }
    this.count += count;
  }
```
</details>

### `EntityManager.getEntityByName(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getEntityByName(name) {
    return this._entitiesByNames[name];
  }
```
</details>

### `EntityManager.createEntity(name: any): any`

**JSDoc:**
```typescript
/**
   * Create a new entity
   */
```

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this._entityPool.acquire`
- `console.warn`
- `this._entities.push`
- `this.eventDispatcher.dispatchEvent`

<details><summary>Code</summary>

```typescript
createEntity(name) {
    var entity = this._entityPool.acquire();
    entity.alive = true;
    entity.name = name || "";
    if (name) {
      if (this._entitiesByNames[name]) {
        console.warn(`Entity name '${name}' already exist`);
      } else {
        this._entitiesByNames[name] = entity;
      }
    }

    this._entities.push(entity);
    this.eventDispatcher.dispatchEvent(ENTITY_CREATED, entity);
    return entity;
  }
```
</details>

### `EntityManager.entityAddComponent(entity: Entity, Component: Component, values: any): void`

**JSDoc:**
```typescript
/**
   * Add a component to an entity
   * @param {Entity} entity Entity where the component will be added
   * @param {Component} Component Component to be added to the entity
   * @param {Object} values Optional values to replace the default attributes
   */
```

**Parameters:**

- **`entity`** `Entity`
- **`Component`** `Component`
- **`values`** `any`

**Returns:** `void`

**Calls:**

- `Component.getName`
- `entity._ComponentTypes.indexOf`
- `console.warn`
- `entity._ComponentTypes.push`
- `this.world.componentsManager.getComponentsPool`
- `componentPool.acquire`
- `component.copy`
- `this._queryManager.onEntityComponentAdded`
- `this.world.componentsManager.componentAddedToEntity`
- `this.eventDispatcher.dispatchEvent`

**Internal Comments:**
```
// @todo Probably define Component._typeId with a default value and avoid using typeof
```

<details><summary>Code</summary>

```typescript
entityAddComponent(entity, Component, values) {
    // @todo Probably define Component._typeId with a default value and avoid using typeof
    if (
      typeof Component._typeId === "undefined" &&
      !this.world.componentsManager._ComponentsMap[Component._typeId]
    ) {
      throw new Error(
        `Attempted to add unregistered component "${Component.getName()}"`
      );
    }

    if (~entity._ComponentTypes.indexOf(Component)) {
      {
        console.warn(
          "Component type already exists on entity.",
          entity,
          Component.getName()
        );
      }
      return;
    }

    entity._ComponentTypes.push(Component);

    if (Component.__proto__ === SystemStateComponent) {
      entity.numStateComponents++;
    }

    var componentPool = this.world.componentsManager.getComponentsPool(
      Component
    );

    var component = componentPool
      ? componentPool.acquire()
      : new Component(values);

    if (componentPool && values) {
      component.copy(values);
    }

    entity._components[Component._typeId] = component;

    this._queryManager.onEntityComponentAdded(entity, Component);
    this.world.componentsManager.componentAddedToEntity(Component);

    this.eventDispatcher.dispatchEvent(COMPONENT_ADDED, entity, Component);
  }
```
</details>

### `EntityManager.entityRemoveComponent(entity: Entity, Component: any, immediately: Bool): void`

**JSDoc:**
```typescript
/**
   * Remove a component from an entity
   * @param {Entity} entity Entity which will get removed the component
   * @param {*} Component Component to remove from the entity
   * @param {Bool} immediately If you want to remove the component immediately instead of deferred (Default is false)
   */
```

**Parameters:**

- **`entity`** `Entity`
- **`Component`** `any`
- **`immediately`** `Bool`

**Returns:** `void`

**Calls:**

- `entity._ComponentTypes.indexOf`
- `this.eventDispatcher.dispatchEvent`
- `this._entityRemoveComponentSync`
- `this.entitiesWithComponentsToRemove.push`
- `entity._ComponentTypes.splice`
- `entity._ComponentTypesToRemove.push`
- `this._queryManager.onEntityComponentRemoved`
- `entity.remove`

**Internal Comments:**
```
// Check each indexed query to see if we need to remove it (x5)
// Check if the entity was a ghost waiting for the last system state component to be removed
```

<details><summary>Code</summary>

```typescript
entityRemoveComponent(entity, Component, immediately) {
    var index = entity._ComponentTypes.indexOf(Component);
    if (!~index) return;

    this.eventDispatcher.dispatchEvent(COMPONENT_REMOVE, entity, Component);

    if (immediately) {
      this._entityRemoveComponentSync(entity, Component, index);
    } else {
      if (entity._ComponentTypesToRemove.length === 0)
        this.entitiesWithComponentsToRemove.push(entity);

      entity._ComponentTypes.splice(index, 1);
      entity._ComponentTypesToRemove.push(Component);

      entity._componentsToRemove[Component._typeId] =
        entity._components[Component._typeId];
      delete entity._components[Component._typeId];
    }

    // Check each indexed query to see if we need to remove it
    this._queryManager.onEntityComponentRemoved(entity, Component);

    if (Component.__proto__ === SystemStateComponent) {
      entity.numStateComponents--;

      // Check if the entity was a ghost waiting for the last system state component to be removed
      if (entity.numStateComponents === 0 && !entity.alive) {
        entity.remove();
      }
    }
  }
```
</details>

### `EntityManager._entityRemoveComponentSync(entity: any, Component: any, index: any): void`

**Parameters:**

- **`entity`** `any`
- **`Component`** `any`
- **`index`** `any`

**Returns:** `void`

**Calls:**

- `entity._ComponentTypes.splice`
- `component.dispose`
- `this.world.componentsManager.componentRemovedFromEntity`

**Internal Comments:**
```
// Remove T listing on entity and property ref, then free the component. (x5)
```

<details><summary>Code</summary>

```typescript
_entityRemoveComponentSync(entity, Component, index) {
    // Remove T listing on entity and property ref, then free the component.
    entity._ComponentTypes.splice(index, 1);
    var component = entity._components[Component._typeId];
    delete entity._components[Component._typeId];
    component.dispose();
    this.world.componentsManager.componentRemovedFromEntity(Component);
  }
```
</details>

### `EntityManager.entityRemoveAllComponents(entity: Entity, immediately: any): void`

**JSDoc:**
```typescript
/**
   * Remove all the components from an entity
   * @param {Entity} entity Entity from which the components will be removed
   */
```

**Parameters:**

- **`entity`** `Entity`
- **`immediately`** `any`

**Returns:** `void`

**Calls:**

- `this.entityRemoveComponent`

<details><summary>Code</summary>

```typescript
entityRemoveAllComponents(entity, immediately) {
    let Components = entity._ComponentTypes;

    for (let j = Components.length - 1; j >= 0; j--) {
      if (Components[j].__proto__ !== SystemStateComponent)
        this.entityRemoveComponent(entity, Components[j], immediately);
    }
  }
```
</details>

### `EntityManager.removeEntity(entity: Entity, immediately: Bool): void`

**JSDoc:**
```typescript
/**
   * Remove the entity from this manager. It will clear also its components
   * @param {Entity} entity Entity to remove from the manager
   * @param {Bool} immediately If you want to remove the component immediately instead of deferred (Default is false)
   */
```

**Parameters:**

- **`entity`** `Entity`
- **`immediately`** `Bool`

**Returns:** `void`

**Calls:**

- `this._entities.indexOf`
- `this.entityRemoveAllComponents`
- `this.eventDispatcher.dispatchEvent`
- `this._queryManager.onEntityRemoved`
- `this._releaseEntity`
- `this.entitiesToRemove.push`

**Internal Comments:**
```
// Remove from entity list (x5)
```

<details><summary>Code</summary>

```typescript
removeEntity(entity, immediately) {
    var index = this._entities.indexOf(entity);

    if (!~index) throw new Error("Tried to remove entity not in list");

    entity.alive = false;
    this.entityRemoveAllComponents(entity, immediately);

    if (entity.numStateComponents === 0) {
      // Remove from entity list
      this.eventDispatcher.dispatchEvent(ENTITY_REMOVED, entity);
      this._queryManager.onEntityRemoved(entity);
      if (immediately === true) {
        this._releaseEntity(entity, index);
      } else {
        this.entitiesToRemove.push(entity);
      }
    }
  }
```
</details>

### `EntityManager._releaseEntity(entity: any, index: any): void`

**Parameters:**

- **`entity`** `any`
- **`index`** `any`

**Returns:** `void`

**Calls:**

- `this._entities.splice`
- `entity._pool.release`

<details><summary>Code</summary>

```typescript
_releaseEntity(entity, index) {
    this._entities.splice(index, 1);

    if (this._entitiesByNames[entity.name]) {
      delete this._entitiesByNames[entity.name];
    }
    entity._pool.release(entity);
  }
```
</details>

### `EntityManager.removeAllEntities(): void`

**JSDoc:**
```typescript
/**
   * Remove all entities from this manager
   */
```

**Returns:** `void`

**Calls:**

- `this.removeEntity`

<details><summary>Code</summary>

```typescript
removeAllEntities() {
    for (var i = this._entities.length - 1; i >= 0; i--) {
      this.removeEntity(this._entities[i]);
    }
  }
```
</details>

### `EntityManager.processDeferredRemoval(): void`

**Returns:** `void`

**Calls:**

- `this._entities.indexOf`
- `this._releaseEntity`
- `entity._ComponentTypesToRemove.pop`
- `component.dispose`
- `this.world.componentsManager.componentRemovedFromEntity`

<details><summary>Code</summary>

```typescript
processDeferredRemoval() {
    if (!this.deferredRemovalEnabled) {
      return;
    }

    for (let i = 0; i < this.entitiesToRemove.length; i++) {
      let entity = this.entitiesToRemove[i];
      let index = this._entities.indexOf(entity);
      this._releaseEntity(entity, index);
    }
    this.entitiesToRemove.length = 0;

    for (let i = 0; i < this.entitiesWithComponentsToRemove.length; i++) {
      let entity = this.entitiesWithComponentsToRemove[i];
      while (entity._ComponentTypesToRemove.length > 0) {
        let Component = entity._ComponentTypesToRemove.pop();

        var component = entity._componentsToRemove[Component._typeId];
        delete entity._componentsToRemove[Component._typeId];
        component.dispose();
        this.world.componentsManager.componentRemovedFromEntity(Component);

        //this._entityRemoveComponentSync(entity, Component, index);
      }
    }

    this.entitiesWithComponentsToRemove.length = 0;
  }
```
</details>

### `EntityManager.queryComponents(Components: any): any`

**JSDoc:**
```typescript
/**
   * Get a query based on a list of components
   * @param {Array(Component)} Components List of components that will form the query
   */
```

**Parameters:**

- **`Components`** `any`

**Returns:** `any`

**Calls:**

- `this._queryManager.getQuery`

<details><summary>Code</summary>

```typescript
queryComponents(Components) {
    return this._queryManager.getQuery(Components);
  }
```
</details>

### `EntityManager.count(): number`

**JSDoc:**
```typescript
/**
   * Return number of entities
   */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
count() {
    return this._entities.length;
  }
```
</details>

### `EntityManager.stats(): { numEntities: number; numQueries: number; queries: {}; numComponentPool: number; componentPool: {}; eventDispatcher: { fired: number; handled: number; }; }`

**JSDoc:**
```typescript
/**
   * Return some stats
   */
```

**Returns:** `{ numEntities: number; numQueries: number; queries: {}; numComponentPool: number; componentPool: {}; eventDispatcher: { fired: number; handled: number; }; }`

**Calls:**

- `Object.keys`
- `this._queryManager.stats`
- `pool.T.getName`
- `pool.totalUsed`

<details><summary>Code</summary>

```typescript
stats() {
    var stats = {
      numEntities: this._entities.length,
      numQueries: Object.keys(this._queryManager._queries).length,
      queries: this._queryManager.stats(),
      numComponentPool: Object.keys(this.componentsManager._componentPool)
        .length,
      componentPool: {},
      eventDispatcher: this.eventDispatcher.stats,
    };

    for (var ecsyComponentId in this.componentsManager._componentPool) {
      var pool = this.componentsManager._componentPool[ecsyComponentId];
      stats.componentPool[pool.T.getName()] = {
        used: pool.totalUsed(),
        size: pool.count,
      };
    }

    return stats;
  }
```
</details>

### `ComponentManager.hasComponent(Component: any): boolean`

**Parameters:**

- **`Component`** `any`

**Returns:** `boolean`

**Calls:**

- `this.Components.indexOf`

<details><summary>Code</summary>

```typescript
hasComponent(Component) {
    return this.Components.indexOf(Component) !== -1;
  }
```
</details>

### `ComponentManager.registerComponent(Component: any, objectPool: any): void`

**Parameters:**

- **`Component`** `any`
- **`objectPool`** `any`

**Returns:** `void`

**Calls:**

- `this.Components.indexOf`
- `console.warn`
- `Component.getName`
- `this.Components.push`

<details><summary>Code</summary>

```typescript
registerComponent(Component, objectPool) {
    if (this.Components.indexOf(Component) !== -1) {
      console.warn(
        `Component type: '${Component.getName()}' already registered.`
      );
      return;
    }

    const schema = Component.schema;

    if (!schema) {
      throw new Error(
        `Component "${Component.getName()}" has no schema property.`
      );
    }

    for (const propName in schema) {
      const prop = schema[propName];

      if (!prop.type) {
        throw new Error(
          `Invalid schema for component "${Component.getName()}". Missing type for "${propName}" property.`
        );
      }
    }

    Component._typeId = this.nextComponentId++;
    this.Components.push(Component);
    this._ComponentsMap[Component._typeId] = Component;
    this.numComponents[Component._typeId] = 0;

    if (objectPool === undefined) {
      objectPool = new ObjectPool(Component);
    } else if (objectPool === false) {
      objectPool = undefined;
    }

    this._componentPool[Component._typeId] = objectPool;
  }
```
</details>

### `ComponentManager.componentAddedToEntity(Component: any): void`

**Parameters:**

- **`Component`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
componentAddedToEntity(Component) {
    this.numComponents[Component._typeId]++;
  }
```
</details>

### `ComponentManager.componentRemovedFromEntity(Component: any): void`

**Parameters:**

- **`Component`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
componentRemovedFromEntity(Component) {
    this.numComponents[Component._typeId]--;
  }
```
</details>

### `ComponentManager.getComponentsPool(Component: any): any`

**Parameters:**

- **`Component`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getComponentsPool(Component) {
    return this._componentPool[Component._typeId];
  }
```
</details>

### `wrapImmutableComponent(T: any, component: any): any`

**Parameters:**

- **`T`** `any`
- **`component`** `any`

**Returns:** `any`

**Calls:**

- `proxyMap.get`
- `proxyMap.set`

<details><summary>Code</summary>

```typescript
function wrapImmutableComponent(T, component) {
  if (component === undefined) {
    return undefined;
  }

  let wrappedComponent = proxyMap.get(component);

  if (!wrappedComponent) {
    wrappedComponent = new Proxy(component, proxyHandler);
    proxyMap.set(component, wrappedComponent);
  }

  return wrappedComponent;
}
```
</details>

### `Entity.getComponent(Component: any, includeRemoved: any): any`

**Parameters:**

- **`Component`** `any`
- **`includeRemoved`** `any`

**Returns:** `any`

**Calls:**

- `wrapImmutableComponent`

<details><summary>Code</summary>

```typescript
getComponent(Component, includeRemoved) {
    var component = this._components[Component._typeId];

    if (!component && includeRemoved === true) {
      component = this._componentsToRemove[Component._typeId];
    }

    return  wrapImmutableComponent(Component, component)
      ;
  }
```
</details>

### `Entity.getRemovedComponent(Component: any): any`

**Parameters:**

- **`Component`** `any`

**Returns:** `any`

**Calls:**

- `wrapImmutableComponent`

<details><summary>Code</summary>

```typescript
getRemovedComponent(Component) {
    const component = this._componentsToRemove[Component._typeId];

    return  wrapImmutableComponent(Component, component)
      ;
  }
```
</details>

### `Entity.getComponents(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
getComponents() {
    return this._components;
  }
```
</details>

### `Entity.getComponentsToRemove(): {}`

**Returns:** `{}`

<details><summary>Code</summary>

```typescript
getComponentsToRemove() {
    return this._componentsToRemove;
  }
```
</details>

### `Entity.getComponentTypes(): any[]`

**Returns:** `any[]`

<details><summary>Code</summary>

```typescript
getComponentTypes() {
    return this._ComponentTypes;
  }
```
</details>

### `Entity.getMutableComponent(Component: any): any`

**Parameters:**

- **`Component`** `any`

**Returns:** `any`

**Calls:**

- `query.Components.indexOf`
- `query.eventDispatcher.dispatchEvent`

**Internal Comments:**
```
// @todo accelerate this check. Maybe having query._Components as an object
// @todo add Not components
```

<details><summary>Code</summary>

```typescript
getMutableComponent(Component) {
    var component = this._components[Component._typeId];

    if (!component) {
      return;
    }

    for (var i = 0; i < this.queries.length; i++) {
      var query = this.queries[i];
      // @todo accelerate this check. Maybe having query._Components as an object
      // @todo add Not components
      if (query.reactive && query.Components.indexOf(Component) !== -1) {
        query.eventDispatcher.dispatchEvent(
          Query.prototype.COMPONENT_CHANGED,
          this,
          component
        );
      }
    }
    return component;
  }
```
</details>

### `Entity.addComponent(Component: any, values: any): this`

**Parameters:**

- **`Component`** `any`
- **`values`** `any`

**Returns:** `this`

**Calls:**

- `this._entityManager.entityAddComponent`

<details><summary>Code</summary>

```typescript
addComponent(Component, values) {
    this._entityManager.entityAddComponent(this, Component, values);
    return this;
  }
```
</details>

### `Entity.removeComponent(Component: any, forceImmediate: any): this`

**Parameters:**

- **`Component`** `any`
- **`forceImmediate`** `any`

**Returns:** `this`

**Calls:**

- `this._entityManager.entityRemoveComponent`

<details><summary>Code</summary>

```typescript
removeComponent(Component, forceImmediate) {
    this._entityManager.entityRemoveComponent(this, Component, forceImmediate);
    return this;
  }
```
</details>

### `Entity.hasComponent(Component: any, includeRemoved: any): boolean`

**Parameters:**

- **`Component`** `any`
- **`includeRemoved`** `any`

**Returns:** `boolean`

**Calls:**

- `this._ComponentTypes.indexOf`
- `this.hasRemovedComponent`

<details><summary>Code</summary>

```typescript
hasComponent(Component, includeRemoved) {
    return (
      !!~this._ComponentTypes.indexOf(Component) ||
      (includeRemoved === true && this.hasRemovedComponent(Component))
    );
  }
```
</details>

### `Entity.hasRemovedComponent(Component: any): boolean`

**Parameters:**

- **`Component`** `any`

**Returns:** `boolean`

**Calls:**

- `this._ComponentTypesToRemove.indexOf`

<details><summary>Code</summary>

```typescript
hasRemovedComponent(Component) {
    return !!~this._ComponentTypesToRemove.indexOf(Component);
  }
```
</details>

### `Entity.hasAllComponents(Components: any): boolean`

**Parameters:**

- **`Components`** `any`

**Returns:** `boolean`

**Calls:**

- `this.hasComponent`

<details><summary>Code</summary>

```typescript
hasAllComponents(Components) {
    for (var i = 0; i < Components.length; i++) {
      if (!this.hasComponent(Components[i])) return false;
    }
    return true;
  }
```
</details>

### `Entity.hasAnyComponents(Components: any): boolean`

**Parameters:**

- **`Components`** `any`

**Returns:** `boolean`

**Calls:**

- `this.hasComponent`

<details><summary>Code</summary>

```typescript
hasAnyComponents(Components) {
    for (var i = 0; i < Components.length; i++) {
      if (this.hasComponent(Components[i])) return true;
    }
    return false;
  }
```
</details>

### `Entity.removeAllComponents(forceImmediate: any): any`

**Parameters:**

- **`forceImmediate`** `any`

**Returns:** `any`

**Calls:**

- `this._entityManager.entityRemoveAllComponents`

<details><summary>Code</summary>

```typescript
removeAllComponents(forceImmediate) {
    return this._entityManager.entityRemoveAllComponents(this, forceImmediate);
  }
```
</details>

### `Entity.copy(src: any): this`

**Parameters:**

- **`src`** `any`

**Returns:** `this`

**Calls:**

- `this.addComponent`
- `this.getComponent`
- `component.copy`

**Internal Comments:**
```
// TODO: This can definitely be optimized
```

<details><summary>Code</summary>

```typescript
copy(src) {
    // TODO: This can definitely be optimized
    for (var ecsyComponentId in src._components) {
      var srcComponent = src._components[ecsyComponentId];
      this.addComponent(srcComponent.constructor);
      var component = this.getComponent(srcComponent.constructor);
      component.copy(srcComponent);
    }

    return this;
  }
```
</details>

### `Entity.clone(): Entity`

**Returns:** `Entity`

**Calls:**

- `new Entity(this._entityManager).copy`

<details><summary>Code</summary>

```typescript
clone() {
    return new Entity(this._entityManager).copy(this);
  }
```
</details>

### `Entity.reset(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
reset() {
    this.id = this._entityManager._nextEntityId++;
    this._ComponentTypes.length = 0;
    this.queries.length = 0;

    for (var ecsyComponentId in this._components) {
      delete this._components[ecsyComponentId];
    }
  }
```
</details>

### `Entity.remove(forceImmediate: any): any`

**Parameters:**

- **`forceImmediate`** `any`

**Returns:** `any`

**Calls:**

- `this._entityManager.removeEntity`

<details><summary>Code</summary>

```typescript
remove(forceImmediate) {
    return this._entityManager.removeEntity(this, forceImmediate);
  }
```
</details>

### `World.registerComponent(Component: any, objectPool: any): this`

**Parameters:**

- **`Component`** `any`
- **`objectPool`** `any`

**Returns:** `this`

**Calls:**

- `this.componentsManager.registerComponent`

<details><summary>Code</summary>

```typescript
registerComponent(Component, objectPool) {
    this.componentsManager.registerComponent(Component, objectPool);
    return this;
  }
```
</details>

### `World.registerSystem(System: any, attributes: any): this`

**Parameters:**

- **`System`** `any`
- **`attributes`** `any`

**Returns:** `this`

**Calls:**

- `this.systemManager.registerSystem`

<details><summary>Code</summary>

```typescript
registerSystem(System, attributes) {
    this.systemManager.registerSystem(System, attributes);
    return this;
  }
```
</details>

### `World.hasRegisteredComponent(Component: any): boolean`

**Parameters:**

- **`Component`** `any`

**Returns:** `boolean`

**Calls:**

- `this.componentsManager.hasComponent`

<details><summary>Code</summary>

```typescript
hasRegisteredComponent(Component) {
    return this.componentsManager.hasComponent(Component);
  }
```
</details>

### `World.unregisterSystem(System: any): this`

**Parameters:**

- **`System`** `any`

**Returns:** `this`

**Calls:**

- `this.systemManager.unregisterSystem`

<details><summary>Code</summary>

```typescript
unregisterSystem(System) {
    this.systemManager.unregisterSystem(System);
    return this;
  }
```
</details>

### `World.getSystem(SystemClass: any): any`

**Parameters:**

- **`SystemClass`** `any`

**Returns:** `any`

**Calls:**

- `this.systemManager.getSystem`

<details><summary>Code</summary>

```typescript
getSystem(SystemClass) {
    return this.systemManager.getSystem(SystemClass);
  }
```
</details>

### `World.getSystems(): any[]`

**Returns:** `any[]`

**Calls:**

- `this.systemManager.getSystems`

<details><summary>Code</summary>

```typescript
getSystems() {
    return this.systemManager.getSystems();
  }
```
</details>

### `World.execute(delta: any, time: any): void`

**Parameters:**

- **`delta`** `any`
- **`time`** `any`

**Returns:** `void`

**Calls:**

- `now`
- `this.systemManager.execute`
- `this.entityManager.processDeferredRemoval`

<details><summary>Code</summary>

```typescript
execute(delta, time) {
    if (!delta) {
      time = now() / 1000;
      delta = time - this.lastTime;
      this.lastTime = time;
    }

    if (this.enabled) {
      this.systemManager.execute(delta, time);
      this.entityManager.processDeferredRemoval();
    }
  }
```
</details>

### `World.stop(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
stop() {
    this.enabled = false;
  }
```
</details>

### `World.play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
play() {
    this.enabled = true;
  }
```
</details>

### `World.createEntity(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.entityManager.createEntity`

<details><summary>Code</summary>

```typescript
createEntity(name) {
    return this.entityManager.createEntity(name);
  }
```
</details>

### `World.stats(): { entities: { numEntities: number; numQueries: number; queries: {}; numComponentPool: number; componentPool: {}; eventDispatcher: { fired: number; handled: number; }; }; system: { numSystems: number; systems: {}; }; }`

**Returns:** `{ entities: { numEntities: number; numQueries: number; queries: {}; numComponentPool: number; componentPool: {}; eventDispatcher: { fired: number; handled: number; }; }; system: { numSystems: number; systems: {}; }; }`

**Calls:**

- `this.entityManager.stats`
- `this.systemManager.stats`

<details><summary>Code</summary>

```typescript
stats() {
    var stats = {
      entities: this.entityManager.stats(),
      system: this.systemManager.stats(),
    };

    return stats;
  }
```
</details>

### `System.canExecute(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
canExecute() {
    if (this._mandatoryQueries.length === 0) return true;

    for (let i = 0; i < this._mandatoryQueries.length; i++) {
      var query = this._mandatoryQueries[i];
      if (query.entities.length === 0) {
        return false;
      }
    }

    return true;
  }
```
</details>

### `System.getName(): any`

**Returns:** `any`

**Calls:**

- `this.constructor.getName`

<details><summary>Code</summary>

```typescript
getName() {
    return this.constructor.getName();
  }
```
</details>

### `System.stop(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
stop() {
    this.executeTime = 0;
    this.enabled = false;
  }
```
</details>

### `System.play(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
play() {
    this.enabled = true;
  }
```
</details>

### `System.clearEvents(): void`

**Returns:** `void`

**Calls:**

- `Array.isArray`

<details><summary>Code</summary>

```typescript
clearEvents() {
    for (let queryName in this.queries) {
      var query = this.queries[queryName];
      if (query.added) {
        query.added.length = 0;
      }
      if (query.removed) {
        query.removed.length = 0;
      }
      if (query.changed) {
        if (Array.isArray(query.changed)) {
          query.changed.length = 0;
        } else {
          for (let name in query.changed) {
            query.changed[name].length = 0;
          }
        }
      }
    }
  }
```
</details>

### `System.toJSON(): { name: any; enabled: boolean; executeTime: number; priority: any; queries: {}; }`

**Returns:** `{ name: any; enabled: boolean; executeTime: number; priority: any; queries: {}; }`

**Calls:**

- `this.getName`
- `Array.isArray`
- `methods.forEach`

<details><summary>Code</summary>

```typescript
toJSON() {
    var json = {
      name: this.getName(),
      enabled: this.enabled,
      executeTime: this.executeTime,
      priority: this.priority,
      queries: {},
    };

    if (this.constructor.queries) {
      var queries = this.constructor.queries;
      for (let queryName in queries) {
        let query = this.queries[queryName];
        let queryDefinition = queries[queryName];
        let jsonQuery = (json.queries[queryName] = {
          key: this._queries[queryName].key,
        });

        jsonQuery.mandatory = queryDefinition.mandatory === true;
        jsonQuery.reactive =
          queryDefinition.listen &&
          (queryDefinition.listen.added === true ||
            queryDefinition.listen.removed === true ||
            queryDefinition.listen.changed === true ||
            Array.isArray(queryDefinition.listen.changed));

        if (jsonQuery.reactive) {
          jsonQuery.listen = {};

          const methods = ["added", "removed", "changed"];
          methods.forEach((method) => {
            if (query[method]) {
              jsonQuery.listen[method] = {
                entities: query[method].length,
              };
            }
          });
        }
      }
    }

    return json;
  }
```
</details>

### `Not(Component: any): { operator: string; Component: any; }`

**Parameters:**

- **`Component`** `any`

**Returns:** `{ operator: string; Component: any; }`

<details><summary>Code</summary>

```typescript
function Not(Component) {
  return {
    operator: "not",
    Component: Component,
  };
}
```
</details>

### `copyValue(src: any): any`

**Parameters:**

- **`src`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(src) => src
```
</details>

### `cloneValue(src: any): any`

**Parameters:**

- **`src`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(src) => src
```
</details>

### `copyArray(src: any, dest: any): any`

**Parameters:**

- **`src`** `any`
- **`dest`** `any`

**Returns:** `any`

**Calls:**

- `src.slice`
- `dest.push`

<details><summary>Code</summary>

```typescript
(src, dest) => {
  if (!src) {
    return src;
  }

  if (!dest) {
    return src.slice();
  }

  dest.length = 0;

  for (let i = 0; i < src.length; i++) {
    dest.push(src[i]);
  }

  return dest;
}
```
</details>

### `cloneArray(src: any): any`

**Parameters:**

- **`src`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(src) => src && src.slice()
```
</details>

### `copyJSON(src: any): any`

**Parameters:**

- **`src`** `any`

**Returns:** `any`

**Calls:**

- `JSON.parse`

<details><summary>Code</summary>

```typescript
(src) => JSON.parse(JSON.stringify(src))
```
</details>

### `cloneJSON(src: any): any`

**Parameters:**

- **`src`** `any`

**Returns:** `any`

**Calls:**

- `JSON.parse`

<details><summary>Code</summary>

```typescript
(src) => JSON.parse(JSON.stringify(src))
```
</details>

### `copyCopyable(src: any, dest: any): any`

**Parameters:**

- **`src`** `any`
- **`dest`** `any`

**Returns:** `any`

**Calls:**

- `src.clone`
- `dest.copy`

<details><summary>Code</summary>

```typescript
(src, dest) => {
  if (!src) {
    return src;
  }

  if (!dest) {
    return src.clone();
  }

  return dest.copy(src);
}
```
</details>

### `cloneClonable(src: any): any`

**Parameters:**

- **`src`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
(src) => src && src.clone()
```
</details>

### `createType(typeDefinition: any): any`

**Parameters:**

- **`typeDefinition`** `any`

**Returns:** `any`

**Calls:**

- `mandatoryProperties.filter`
- `typeDefinition.hasOwnProperty`
- `undefinedProperties.join`

<details><summary>Code</summary>

```typescript
function createType(typeDefinition) {
  var mandatoryProperties = ["name", "default", "copy", "clone"];

  var undefinedProperties = mandatoryProperties.filter((p) => {
    return !typeDefinition.hasOwnProperty(p);
  });

  if (undefinedProperties.length > 0) {
    throw new Error(
      `createType expects a type definition with the following properties: ${undefinedProperties.join(
        ", "
      )}`
    );
  }

  typeDefinition.isType = true;

  return typeDefinition;
}
```
</details>

### `generateId(length: any): string`

**Parameters:**

- **`length`** `any`

**Returns:** `string`

**Calls:**

- `characters.charAt`
- `Math.floor`
- `Math.random`

<details><summary>Code</summary>

```typescript
function generateId(length) {
  var result = "";
  var characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
  var charactersLength = characters.length;
  for (var i = 0; i < length; i++) {
    result += characters.charAt(Math.floor(Math.random() * charactersLength));
  }
  return result;
}
```
</details>

### `injectScript(src: any, onLoad: any): void`

**Parameters:**

- **`src`** `any`
- **`onLoad`** `any`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `(document.head || document.documentElement).appendChild`

**Internal Comments:**
```
// @todo Use link to the ecsy-devtools repo? (x4)
```

<details><summary>Code</summary>

```typescript
function injectScript(src, onLoad) {
  var script = document.createElement("script");
  // @todo Use link to the ecsy-devtools repo?
  script.src = src;
  script.onload = onLoad;
  (document.head || document.documentElement).appendChild(script);
}
```
</details>

### `hookConsoleAndErrors(connection: any): void`

**Parameters:**

- **`connection`** `any`

**Returns:** `void`

**Calls:**

- `wrapFunctions.forEach`
- `console[key].bind`
- `connection.send`
- `JSON.stringify`
- `fn.apply`
- `window.addEventListener`

<details><summary>Code</summary>

```typescript
function hookConsoleAndErrors(connection) {
  var wrapFunctions = ["error", "warning", "log"];
  wrapFunctions.forEach((key) => {
    if (typeof console[key] === "function") {
      var fn = console[key].bind(console);
      console[key] = (...args) => {
        connection.send({
          method: "console",
          type: key,
          args: JSON.stringify(args),
        });
        return fn.apply(null, args);
      };
    }
  });

  window.addEventListener("error", (error) => {
    connection.send({
      method: "error",
      error: JSON.stringify({
        message: error.error.message,
        stack: error.error.stack,
      }),
    });
  });
}
```
</details>

### `includeRemoteIdHTML(remoteId: any): HTMLDivElement`

**Parameters:**

- **`remoteId`** `any`

**Returns:** `HTMLDivElement`

**Calls:**

- `document.createElement`
- `document.body.appendChild`

<details><summary>Code</summary>

```typescript
function includeRemoteIdHTML(remoteId) {
  let infoDiv = document.createElement("div");
  infoDiv.style.cssText = `
    align-items: center;
    background-color: #333;
    color: #aaa;
    display:flex;
    font-family: Arial;
    font-size: 1.1em;
    height: 40px;
    justify-content: center;
    left: 0;
    opacity: 0.9;
    position: absolute;
    right: 0;
    text-align: center;
    top: 0;
  `;

  infoDiv.innerHTML = `Open ECSY devtools to connect to this page using the code:&nbsp;<b style="color: #fff">${remoteId}</b>&nbsp;<button onClick="generateNewCode()">Generate new code</button>`;
  document.body.appendChild(infoDiv);

  return infoDiv;
}
```
</details>

### `enableRemoteDevtools(remoteId: any): void`

**Parameters:**

- **`remoteId`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`
- `window.localStorage.clear`
- `generateId`
- `window.localStorage.setItem`
- `window.location.reload`
- `window.localStorage.getItem`
- `includeRemoteIdHTML`
- `worldsBeforeLoading.push`
- `window.addEventListener`
- `peer.on`
- `connection.on`
- `document.createElement`
- `script.setAttribute`
- `script.parentNode.removeChild`
- `window.removeEventListener`
- `worldsBeforeLoading.forEach`
- `window.dispatchEvent`
- `(document.head || document.documentElement).appendChild`
- `script.onload`
- `hookConsoleAndErrors`
- `eval`
- `connection.send`
- `injectScript`

**Internal Comments:**
```
// This is used to collect the worlds created before the communication is being established (x2)
// var peer = new Peer(remoteId); (x2)
// infoDiv.style.visibility = "hidden"; (x4)
// Receive messages (x4)
// Once the script is injected we don't need to listen (x4)
// Inject PeerJS script (x3)
```

<details><summary>Code</summary>

```typescript
function enableRemoteDevtools(remoteId) {
  if (!hasWindow) {
    console.warn("Remote devtools not available outside the browser");
    return;
  }

  window.generateNewCode = () => {
    window.localStorage.clear();
    remoteId = generateId(6);
    window.localStorage.setItem("ecsyRemoteId", remoteId);
    window.location.reload(false);
  };

  remoteId = remoteId || window.localStorage.getItem("ecsyRemoteId");
  if (!remoteId) {
    remoteId = generateId(6);
    window.localStorage.setItem("ecsyRemoteId", remoteId);
  }

  let infoDiv = includeRemoteIdHTML(remoteId);

  window.__ECSY_REMOTE_DEVTOOLS_INJECTED = true;
  window.__ECSY_REMOTE_DEVTOOLS = {};

  let Version = "";

  // This is used to collect the worlds created before the communication is being established
  let worldsBeforeLoading = [];
  let onWorldCreated = (e) => {
    var world = e.detail.world;
    Version = e.detail.version;
    worldsBeforeLoading.push(world);
  };
  window.addEventListener("ecsy-world-created", onWorldCreated);

  let onLoaded = () => {
    // var peer = new Peer(remoteId);
    var peer = new Peer(remoteId, {
      host: "peerjs.ecsy.io",
      secure: true,
      port: 443,
      config: {
        iceServers: [
          { url: "stun:stun.l.google.com:19302" },
          { url: "stun:stun1.l.google.com:19302" },
          { url: "stun:stun2.l.google.com:19302" },
          { url: "stun:stun3.l.google.com:19302" },
          { url: "stun:stun4.l.google.com:19302" },
        ],
      },
      debug: 3,
    });

    peer.on("open", (/* id */) => {
      peer.on("connection", (connection) => {
        window.__ECSY_REMOTE_DEVTOOLS.connection = connection;
        connection.on("open", function () {
          // infoDiv.style.visibility = "hidden";
          infoDiv.innerHTML = "Connected";

          // Receive messages
          connection.on("data", function (data) {
            if (data.type === "init") {
              var script = document.createElement("script");
              script.setAttribute("type", "text/javascript");
              script.onload = () => {
                script.parentNode.removeChild(script);

                // Once the script is injected we don't need to listen
                window.removeEventListener(
                  "ecsy-world-created",
                  onWorldCreated
                );
                worldsBeforeLoading.forEach((world) => {
                  var event = new CustomEvent("ecsy-world-created", {
                    detail: { world: world, version: Version },
                  });
                  window.dispatchEvent(event);
                });
              };
              script.innerHTML = data.script;
              (document.head || document.documentElement).appendChild(script);
              script.onload();

              hookConsoleAndErrors(connection);
            } else if (data.type === "executeScript") {
              let value = eval(data.script);
              if (data.returnEval) {
                connection.send({
                  method: "evalReturn",
                  value: value,
                });
              }
            }
          });
        });
      });
    });
  };

  // Inject PeerJS script
  injectScript(
    "https://cdn.jsdelivr.net/npm/peerjs@0.3.20/dist/peer.min.js",
    onLoaded
  );
}
```
</details>

### `onWorldCreated(e: any): void`

**Parameters:**

- **`e`** `any`

**Returns:** `void`

**Calls:**

- `worldsBeforeLoading.push`

<details><summary>Code</summary>

```typescript
(e) => {
    var world = e.detail.world;
    Version = e.detail.version;
    worldsBeforeLoading.push(world);
  }
```
</details>

### `onLoaded(): void`

**Returns:** `void`

**Calls:**

- `peer.on`
- `connection.on`
- `document.createElement`
- `script.setAttribute`
- `script.parentNode.removeChild`
- `window.removeEventListener`
- `worldsBeforeLoading.forEach`
- `window.dispatchEvent`
- `(document.head || document.documentElement).appendChild`
- `script.onload`
- `hookConsoleAndErrors`
- `eval`
- `connection.send`

**Internal Comments:**
```
// var peer = new Peer(remoteId); (x2)
// infoDiv.style.visibility = "hidden"; (x4)
// Receive messages (x4)
// Once the script is injected we don't need to listen (x4)
```

<details><summary>Code</summary>

```typescript
() => {
    // var peer = new Peer(remoteId);
    var peer = new Peer(remoteId, {
      host: "peerjs.ecsy.io",
      secure: true,
      port: 443,
      config: {
        iceServers: [
          { url: "stun:stun.l.google.com:19302" },
          { url: "stun:stun1.l.google.com:19302" },
          { url: "stun:stun2.l.google.com:19302" },
          { url: "stun:stun3.l.google.com:19302" },
          { url: "stun:stun4.l.google.com:19302" },
        ],
      },
      debug: 3,
    });

    peer.on("open", (/* id */) => {
      peer.on("connection", (connection) => {
        window.__ECSY_REMOTE_DEVTOOLS.connection = connection;
        connection.on("open", function () {
          // infoDiv.style.visibility = "hidden";
          infoDiv.innerHTML = "Connected";

          // Receive messages
          connection.on("data", function (data) {
            if (data.type === "init") {
              var script = document.createElement("script");
              script.setAttribute("type", "text/javascript");
              script.onload = () => {
                script.parentNode.removeChild(script);

                // Once the script is injected we don't need to listen
                window.removeEventListener(
                  "ecsy-world-created",
                  onWorldCreated
                );
                worldsBeforeLoading.forEach((world) => {
                  var event = new CustomEvent("ecsy-world-created", {
                    detail: { world: world, version: Version },
                  });
                  window.dispatchEvent(event);
                });
              };
              script.innerHTML = data.script;
              (document.head || document.documentElement).appendChild(script);
              script.onload();

              hookConsoleAndErrors(connection);
            } else if (data.type === "executeScript") {
              let value = eval(data.script);
              if (data.returnEval) {
                connection.send({
                  method: "evalReturn",
                  value: value,
                });
              }
            }
          });
        });
      });
    });
  }
```
</details>


---

## Classes

### `SystemManager`

<details><summary>Class Code</summary>

```ts
class SystemManager {
  constructor(world) {
    this._systems = [];
    this._executeSystems = []; // Systems that have `execute` method
    this.world = world;
    this.lastExecutedSystem = null;
  }

  registerSystem(SystemClass, attributes) {
    if (!SystemClass.isSystem) {
      throw new Error(
        `System '${SystemClass.name}' does not extend 'System' class`
      );
    }

    if (this.getSystem(SystemClass) !== undefined) {
      console.warn(`System '${SystemClass.getName()}' already registered.`);
      return this;
    }

    var system = new SystemClass(this.world, attributes);
    if (system.init) system.init(attributes);
    system.order = this._systems.length;
    this._systems.push(system);
    if (system.execute) {
      this._executeSystems.push(system);
      this.sortSystems();
    }
    return this;
  }

  unregisterSystem(SystemClass) {
    let system = this.getSystem(SystemClass);
    if (system === undefined) {
      console.warn(
        `Can unregister system '${SystemClass.getName()}'. It doesn't exist.`
      );
      return this;
    }

    this._systems.splice(this._systems.indexOf(system), 1);

    if (system.execute) {
      this._executeSystems.splice(this._executeSystems.indexOf(system), 1);
    }

    // @todo Add system.unregister() call to free resources
    return this;
  }

  sortSystems() {
    this._executeSystems.sort((a, b) => {
      return a.priority - b.priority || a.order - b.order;
    });
  }

  getSystem(SystemClass) {
    return this._systems.find((s) => s instanceof SystemClass);
  }

  getSystems() {
    return this._systems;
  }

  removeSystem(SystemClass) {
    var index = this._systems.indexOf(SystemClass);
    if (!~index) return;

    this._systems.splice(index, 1);
  }

  executeSystem(system, delta, time) {
    if (system.initialized) {
      if (system.canExecute()) {
        let startTime = now();
        system.execute(delta, time);
        system.executeTime = now() - startTime;
        this.lastExecutedSystem = system;
        system.clearEvents();
      }
    }
  }

  stop() {
    this._executeSystems.forEach((system) => system.stop());
  }

  execute(delta, time, forcePlay) {
    this._executeSystems.forEach(
      (system) =>
        (forcePlay || system.enabled) && this.executeSystem(system, delta, time)
    );
  }

  stats() {
    var stats = {
      numSystems: this._systems.length,
      systems: {},
    };

    for (var i = 0; i < this._systems.length; i++) {
      var system = this._systems[i];
      var systemStats = (stats.systems[system.getName()] = {
        queries: {},
        executeTime: system.executeTime,
      });
      for (var name in system.ctx) {
        systemStats.queries[name] = system.ctx[name].stats();
      }
    }

    return stats;
  }
}
```
</details>

#### Methods

##### `registerSystem(SystemClass: any, attributes: any): this`

<details><summary>Code</summary>

```ts
registerSystem(SystemClass, attributes) {
    if (!SystemClass.isSystem) {
      throw new Error(
        `System '${SystemClass.name}' does not extend 'System' class`
      );
    }

    if (this.getSystem(SystemClass) !== undefined) {
      console.warn(`System '${SystemClass.getName()}' already registered.`);
      return this;
    }

    var system = new SystemClass(this.world, attributes);
    if (system.init) system.init(attributes);
    system.order = this._systems.length;
    this._systems.push(system);
    if (system.execute) {
      this._executeSystems.push(system);
      this.sortSystems();
    }
    return this;
  }
```
</details>

##### `unregisterSystem(SystemClass: any): this`

<details><summary>Code</summary>

```ts
unregisterSystem(SystemClass) {
    let system = this.getSystem(SystemClass);
    if (system === undefined) {
      console.warn(
        `Can unregister system '${SystemClass.getName()}'. It doesn't exist.`
      );
      return this;
    }

    this._systems.splice(this._systems.indexOf(system), 1);

    if (system.execute) {
      this._executeSystems.splice(this._executeSystems.indexOf(system), 1);
    }

    // @todo Add system.unregister() call to free resources
    return this;
  }
```
</details>

##### `sortSystems(): void`

<details><summary>Code</summary>

```ts
sortSystems() {
    this._executeSystems.sort((a, b) => {
      return a.priority - b.priority || a.order - b.order;
    });
  }
```
</details>

##### `getSystem(SystemClass: any): any`

<details><summary>Code</summary>

```ts
getSystem(SystemClass) {
    return this._systems.find((s) => s instanceof SystemClass);
  }
```
</details>

##### `getSystems(): any[]`

<details><summary>Code</summary>

```ts
getSystems() {
    return this._systems;
  }
```
</details>

##### `removeSystem(SystemClass: any): void`

<details><summary>Code</summary>

```ts
removeSystem(SystemClass) {
    var index = this._systems.indexOf(SystemClass);
    if (!~index) return;

    this._systems.splice(index, 1);
  }
```
</details>

##### `executeSystem(system: any, delta: any, time: any): void`

<details><summary>Code</summary>

```ts
executeSystem(system, delta, time) {
    if (system.initialized) {
      if (system.canExecute()) {
        let startTime = now();
        system.execute(delta, time);
        system.executeTime = now() - startTime;
        this.lastExecutedSystem = system;
        system.clearEvents();
      }
    }
  }
```
</details>

##### `stop(): void`

<details><summary>Code</summary>

```ts
stop() {
    this._executeSystems.forEach((system) => system.stop());
  }
```
</details>

##### `execute(delta: any, time: any, forcePlay: any): void`

<details><summary>Code</summary>

```ts
execute(delta, time, forcePlay) {
    this._executeSystems.forEach(
      (system) =>
        (forcePlay || system.enabled) && this.executeSystem(system, delta, time)
    );
  }
```
</details>

##### `stats(): { numSystems: number; systems: {}; }`

<details><summary>Code</summary>

```ts
stats() {
    var stats = {
      numSystems: this._systems.length,
      systems: {},
    };

    for (var i = 0; i < this._systems.length; i++) {
      var system = this._systems[i];
      var systemStats = (stats.systems[system.getName()] = {
        queries: {},
        executeTime: system.executeTime,
      });
      for (var name in system.ctx) {
        systemStats.queries[name] = system.ctx[name].stats();
      }
    }

    return stats;
  }
```
</details>

### `ObjectPool`

<details><summary>Class Code</summary>

```ts
class ObjectPool {
  // @todo Add initial size
  constructor(T, initialSize) {
    this.freeList = [];
    this.count = 0;
    this.T = T;
    this.isObjectPool = true;

    if (typeof initialSize !== "undefined") {
      this.expand(initialSize);
    }
  }

  acquire() {
    // Grow the list by 20%ish if we're out
    if (this.freeList.length <= 0) {
      this.expand(Math.round(this.count * 0.2) + 1);
    }

    var item = this.freeList.pop();

    return item;
  }

  release(item) {
    item.reset();
    this.freeList.push(item);
  }

  expand(count) {
    for (var n = 0; n < count; n++) {
      var clone = new this.T();
      clone._pool = this;
      this.freeList.push(clone);
    }
    this.count += count;
  }

  totalSize() {
    return this.count;
  }

  totalFree() {
    return this.freeList.length;
  }

  totalUsed() {
    return this.count - this.freeList.length;
  }
}
```
</details>

#### Methods

##### `acquire(): any`

<details><summary>Code</summary>

```ts
acquire() {
    // Grow the list by 20%ish if we're out
    if (this.freeList.length <= 0) {
      this.expand(Math.round(this.count * 0.2) + 1);
    }

    var item = this.freeList.pop();

    return item;
  }
```
</details>

##### `release(item: any): void`

<details><summary>Code</summary>

```ts
release(item) {
    item.reset();
    this.freeList.push(item);
  }
```
</details>

##### `expand(count: any): void`

<details><summary>Code</summary>

```ts
expand(count) {
    for (var n = 0; n < count; n++) {
      var clone = new this.T();
      clone._pool = this;
      this.freeList.push(clone);
    }
    this.count += count;
  }
```
</details>

##### `totalSize(): number`

<details><summary>Code</summary>

```ts
totalSize() {
    return this.count;
  }
```
</details>

##### `totalFree(): number`

<details><summary>Code</summary>

```ts
totalFree() {
    return this.freeList.length;
  }
```
</details>

##### `totalUsed(): number`

<details><summary>Code</summary>

```ts
totalUsed() {
    return this.count - this.freeList.length;
  }
```
</details>

### `EventDispatcher`

<details><summary>Class Code</summary>

```ts
class EventDispatcher {
  constructor() {
    this._listeners = {};
    this.stats = {
      fired: 0,
      handled: 0,
    };
  }

  /**
   * Add an event listener
   * @param {String} eventName Name of the event to listen
   * @param {Function} listener Callback to trigger when the event is fired
   */
  addEventListener(eventName, listener) {
    let listeners = this._listeners;
    if (listeners[eventName] === undefined) {
      listeners[eventName] = [];
    }

    if (listeners[eventName].indexOf(listener) === -1) {
      listeners[eventName].push(listener);
    }
  }

  /**
   * Check if an event listener is already added to the list of listeners
   * @param {String} eventName Name of the event to check
   * @param {Function} listener Callback for the specified event
   */
  hasEventListener(eventName, listener) {
    return (
      this._listeners[eventName] !== undefined &&
      this._listeners[eventName].indexOf(listener) !== -1
    );
  }

  /**
   * Remove an event listener
   * @param {String} eventName Name of the event to remove
   * @param {Function} listener Callback for the specified event
   */
  removeEventListener(eventName, listener) {
    var listenerArray = this._listeners[eventName];
    if (listenerArray !== undefined) {
      var index = listenerArray.indexOf(listener);
      if (index !== -1) {
        listenerArray.splice(index, 1);
      }
    }
  }

  /**
   * Dispatch an event
   * @param {String} eventName Name of the event to dispatch
   * @param {Entity} entity (Optional) Entity to emit
   * @param {Component} component
   */
  dispatchEvent(eventName, entity, component) {
    this.stats.fired++;

    var listenerArray = this._listeners[eventName];
    if (listenerArray !== undefined) {
      var array = listenerArray.slice(0);

      for (var i = 0; i < array.length; i++) {
        array[i].call(this, entity, component);
      }
    }
  }

  /**
   * Reset stats counters
   */
  resetCounters() {
    this.stats.fired = this.stats.handled = 0;
  }
}
```
</details>

#### Methods

##### `addEventListener(eventName: string, listener: Function): void`

<details><summary>Code</summary>

```ts
addEventListener(eventName, listener) {
    let listeners = this._listeners;
    if (listeners[eventName] === undefined) {
      listeners[eventName] = [];
    }

    if (listeners[eventName].indexOf(listener) === -1) {
      listeners[eventName].push(listener);
    }
  }
```
</details>

##### `hasEventListener(eventName: string, listener: Function): boolean`

<details><summary>Code</summary>

```ts
hasEventListener(eventName, listener) {
    return (
      this._listeners[eventName] !== undefined &&
      this._listeners[eventName].indexOf(listener) !== -1
    );
  }
```
</details>

##### `removeEventListener(eventName: string, listener: Function): void`

<details><summary>Code</summary>

```ts
removeEventListener(eventName, listener) {
    var listenerArray = this._listeners[eventName];
    if (listenerArray !== undefined) {
      var index = listenerArray.indexOf(listener);
      if (index !== -1) {
        listenerArray.splice(index, 1);
      }
    }
  }
```
</details>

##### `dispatchEvent(eventName: string, entity: Entity, component: Component): void`

<details><summary>Code</summary>

```ts
dispatchEvent(eventName, entity, component) {
    this.stats.fired++;

    var listenerArray = this._listeners[eventName];
    if (listenerArray !== undefined) {
      var array = listenerArray.slice(0);

      for (var i = 0; i < array.length; i++) {
        array[i].call(this, entity, component);
      }
    }
  }
```
</details>

##### `resetCounters(): void`

<details><summary>Code</summary>

```ts
resetCounters() {
    this.stats.fired = this.stats.handled = 0;
  }
```
</details>

### `Query`

<details><summary>Class Code</summary>

```ts
class Query {
  /**
   * @param {Array(Component)} Components List of types of components to query
   */
  constructor(Components, manager) {
    this.Components = [];
    this.NotComponents = [];

    Components.forEach((component) => {
      if (typeof component === "object") {
        this.NotComponents.push(component.Component);
      } else {
        this.Components.push(component);
      }
    });

    if (this.Components.length === 0) {
      throw new Error("Can't create a query without components");
    }

    this.entities = [];

    this.eventDispatcher = new EventDispatcher();

    // This query is being used by a reactive system
    this.reactive = false;

    this.key = queryKey(Components);

    // Fill the query with the existing entities
    for (var i = 0; i < manager._entities.length; i++) {
      var entity = manager._entities[i];
      if (this.match(entity)) {
        // @todo ??? this.addEntity(entity); => preventing the event to be generated
        entity.queries.push(this);
        this.entities.push(entity);
      }
    }
  }

  /**
   * Add entity to this query
   * @param {Entity} entity
   */
  addEntity(entity) {
    entity.queries.push(this);
    this.entities.push(entity);

    this.eventDispatcher.dispatchEvent(Query.prototype.ENTITY_ADDED, entity);
  }

  /**
   * Remove entity from this query
   * @param {Entity} entity
   */
  removeEntity(entity) {
    let index = this.entities.indexOf(entity);
    if (~index) {
      this.entities.splice(index, 1);

      index = entity.queries.indexOf(this);
      entity.queries.splice(index, 1);

      this.eventDispatcher.dispatchEvent(
        Query.prototype.ENTITY_REMOVED,
        entity
      );
    }
  }

  match(entity) {
    return (
      entity.hasAllComponents(this.Components) &&
      !entity.hasAnyComponents(this.NotComponents)
    );
  }

  toJSON() {
    return {
      key: this.key,
      reactive: this.reactive,
      components: {
        included: this.Components.map((C) => C.name),
        not: this.NotComponents.map((C) => C.name),
      },
      numEntities: this.entities.length,
    };
  }

  /**
   * Return stats for this query
   */
  stats() {
    return {
      numComponents: this.Components.length,
      numEntities: this.entities.length,
    };
  }
}
```
</details>

#### Methods

##### `addEntity(entity: Entity): void`

<details><summary>Code</summary>

```ts
addEntity(entity) {
    entity.queries.push(this);
    this.entities.push(entity);

    this.eventDispatcher.dispatchEvent(Query.prototype.ENTITY_ADDED, entity);
  }
```
</details>

##### `removeEntity(entity: Entity): void`

<details><summary>Code</summary>

```ts
removeEntity(entity) {
    let index = this.entities.indexOf(entity);
    if (~index) {
      this.entities.splice(index, 1);

      index = entity.queries.indexOf(this);
      entity.queries.splice(index, 1);

      this.eventDispatcher.dispatchEvent(
        Query.prototype.ENTITY_REMOVED,
        entity
      );
    }
  }
```
</details>

##### `match(entity: any): boolean`

<details><summary>Code</summary>

```ts
match(entity) {
    return (
      entity.hasAllComponents(this.Components) &&
      !entity.hasAnyComponents(this.NotComponents)
    );
  }
```
</details>

##### `toJSON(): { key: string; reactive: boolean; components: { included: any; not: any[]; }; numEntities: number; }`

<details><summary>Code</summary>

```ts
toJSON() {
    return {
      key: this.key,
      reactive: this.reactive,
      components: {
        included: this.Components.map((C) => C.name),
        not: this.NotComponents.map((C) => C.name),
      },
      numEntities: this.entities.length,
    };
  }
```
</details>

##### `stats(): { numComponents: any; numEntities: number; }`

<details><summary>Code</summary>

```ts
stats() {
    return {
      numComponents: this.Components.length,
      numEntities: this.entities.length,
    };
  }
```
</details>

### `QueryManager`

<details><summary>Class Code</summary>

```ts
class QueryManager {
  constructor(world) {
    this._world = world;

    // Queries indexed by a unique identifier for the components it has
    this._queries = {};
  }

  onEntityRemoved(entity) {
    for (var queryName in this._queries) {
      var query = this._queries[queryName];
      if (entity.queries.indexOf(query) !== -1) {
        query.removeEntity(entity);
      }
    }
  }

  /**
   * Callback when a component is added to an entity
   * @param {Entity} entity Entity that just got the new component
   * @param {Component} Component Component added to the entity
   */
  onEntityComponentAdded(entity, Component) {
    // @todo Use bitmask for checking components?

    // Check each indexed query to see if we need to add this entity to the list
    for (var queryName in this._queries) {
      var query = this._queries[queryName];

      if (
        !!~query.NotComponents.indexOf(Component) &&
        ~query.entities.indexOf(entity)
      ) {
        query.removeEntity(entity);
        continue;
      }

      // Add the entity only if:
      // Component is in the query
      // and Entity has ALL the components of the query
      // and Entity is not already in the query
      if (
        !~query.Components.indexOf(Component) ||
        !query.match(entity) ||
        ~query.entities.indexOf(entity)
      )
        continue;

      query.addEntity(entity);
    }
  }

  /**
   * Callback when a component is removed from an entity
   * @param {Entity} entity Entity to remove the component from
   * @param {Component} Component Component to remove from the entity
   */
  onEntityComponentRemoved(entity, Component) {
    for (var queryName in this._queries) {
      var query = this._queries[queryName];

      if (
        !!~query.NotComponents.indexOf(Component) &&
        !~query.entities.indexOf(entity) &&
        query.match(entity)
      ) {
        query.addEntity(entity);
        continue;
      }

      if (
        !!~query.Components.indexOf(Component) &&
        !!~query.entities.indexOf(entity) &&
        !query.match(entity)
      ) {
        query.removeEntity(entity);
        continue;
      }
    }
  }

  /**
   * Get a query for the specified components
   * @param {Component} Components Components that the query should have
   */
  getQuery(Components) {
    var key = queryKey(Components);
    var query = this._queries[key];
    if (!query) {
      this._queries[key] = query = new Query(Components, this._world);
    }
    return query;
  }

  /**
   * Return some stats from this class
   */
  stats() {
    var stats = {};
    for (var queryName in this._queries) {
      stats[queryName] = this._queries[queryName].stats();
    }
    return stats;
  }
}
```
</details>

#### Methods

##### `onEntityRemoved(entity: any): void`

<details><summary>Code</summary>

```ts
onEntityRemoved(entity) {
    for (var queryName in this._queries) {
      var query = this._queries[queryName];
      if (entity.queries.indexOf(query) !== -1) {
        query.removeEntity(entity);
      }
    }
  }
```
</details>

##### `onEntityComponentAdded(entity: Entity, Component: Component): void`

<details><summary>Code</summary>

```ts
onEntityComponentAdded(entity, Component) {
    // @todo Use bitmask for checking components?

    // Check each indexed query to see if we need to add this entity to the list
    for (var queryName in this._queries) {
      var query = this._queries[queryName];

      if (
        !!~query.NotComponents.indexOf(Component) &&
        ~query.entities.indexOf(entity)
      ) {
        query.removeEntity(entity);
        continue;
      }

      // Add the entity only if:
      // Component is in the query
      // and Entity has ALL the components of the query
      // and Entity is not already in the query
      if (
        !~query.Components.indexOf(Component) ||
        !query.match(entity) ||
        ~query.entities.indexOf(entity)
      )
        continue;

      query.addEntity(entity);
    }
  }
```
</details>

##### `onEntityComponentRemoved(entity: Entity, Component: Component): void`

<details><summary>Code</summary>

```ts
onEntityComponentRemoved(entity, Component) {
    for (var queryName in this._queries) {
      var query = this._queries[queryName];

      if (
        !!~query.NotComponents.indexOf(Component) &&
        !~query.entities.indexOf(entity) &&
        query.match(entity)
      ) {
        query.addEntity(entity);
        continue;
      }

      if (
        !!~query.Components.indexOf(Component) &&
        !!~query.entities.indexOf(entity) &&
        !query.match(entity)
      ) {
        query.removeEntity(entity);
        continue;
      }
    }
  }
```
</details>

##### `getQuery(Components: Component): any`

<details><summary>Code</summary>

```ts
getQuery(Components) {
    var key = queryKey(Components);
    var query = this._queries[key];
    if (!query) {
      this._queries[key] = query = new Query(Components, this._world);
    }
    return query;
  }
```
</details>

##### `stats(): {}`

<details><summary>Code</summary>

```ts
stats() {
    var stats = {};
    for (var queryName in this._queries) {
      stats[queryName] = this._queries[queryName].stats();
    }
    return stats;
  }
```
</details>

### `Component`

<details><summary>Class Code</summary>

```ts
class Component {
  constructor(props) {
    if (props !== false) {
      const schema = this.constructor.schema;

      for (const key in schema) {
        if (props && props.hasOwnProperty(key)) {
          this[key] = props[key];
        } else {
          const schemaProp = schema[key];
          if (schemaProp.hasOwnProperty("default")) {
            this[key] = schemaProp.type.clone(schemaProp.default);
          } else {
            const type = schemaProp.type;
            this[key] = type.clone(type.default);
          }
        }
      }

      if ( props !== undefined) {
        this.checkUndefinedAttributes(props);
      }
    }

    this._pool = null;
  }

  copy(source) {
    const schema = this.constructor.schema;

    for (const key in schema) {
      const prop = schema[key];

      if (source.hasOwnProperty(key)) {
        this[key] = prop.type.copy(source[key], this[key]);
      }
    }

    // @DEBUG
    {
      this.checkUndefinedAttributes(source);
    }

    return this;
  }

  clone() {
    return new this.constructor().copy(this);
  }

  reset() {
    const schema = this.constructor.schema;

    for (const key in schema) {
      const schemaProp = schema[key];

      if (schemaProp.hasOwnProperty("default")) {
        this[key] = schemaProp.type.copy(schemaProp.default, this[key]);
      } else {
        const type = schemaProp.type;
        this[key] = type.copy(type.default, this[key]);
      }
    }
  }

  dispose() {
    if (this._pool) {
      this._pool.release(this);
    }
  }

  getName() {
    return this.constructor.getName();
  }

  checkUndefinedAttributes(src) {
    const schema = this.constructor.schema;

    // Check that the attributes defined in source are also defined in the schema
    Object.keys(src).forEach((srcKey) => {
      if (!schema.hasOwnProperty(srcKey)) {
        console.warn(
          `Trying to set attribute '${srcKey}' not defined in the '${this.constructor.name}' schema. Please fix the schema, the attribute value won't be set`
        );
      }
    });
  }
}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy(source) {
    const schema = this.constructor.schema;

    for (const key in schema) {
      const prop = schema[key];

      if (source.hasOwnProperty(key)) {
        this[key] = prop.type.copy(source[key], this[key]);
      }
    }

    // @DEBUG
    {
      this.checkUndefinedAttributes(source);
    }

    return this;
  }
```
</details>

##### `clone(): any`

<details><summary>Code</summary>

```ts
clone() {
    return new this.constructor().copy(this);
  }
```
</details>

##### `reset(): void`

<details><summary>Code</summary>

```ts
reset() {
    const schema = this.constructor.schema;

    for (const key in schema) {
      const schemaProp = schema[key];

      if (schemaProp.hasOwnProperty("default")) {
        this[key] = schemaProp.type.copy(schemaProp.default, this[key]);
      } else {
        const type = schemaProp.type;
        this[key] = type.copy(type.default, this[key]);
      }
    }
  }
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {
    if (this._pool) {
      this._pool.release(this);
    }
  }
```
</details>

##### `getName(): any`

<details><summary>Code</summary>

```ts
getName() {
    return this.constructor.getName();
  }
```
</details>

##### `checkUndefinedAttributes(src: any): void`

<details><summary>Code</summary>

```ts
checkUndefinedAttributes(src) {
    const schema = this.constructor.schema;

    // Check that the attributes defined in source are also defined in the schema
    Object.keys(src).forEach((srcKey) => {
      if (!schema.hasOwnProperty(srcKey)) {
        console.warn(
          `Trying to set attribute '${srcKey}' not defined in the '${this.constructor.name}' schema. Please fix the schema, the attribute value won't be set`
        );
      }
    });
  }
```
</details>

### `SystemStateComponent`

<details><summary>Class Code</summary>

```ts
class SystemStateComponent extends Component {}
```
</details>

### `EntityPool`

<details><summary>Class Code</summary>

```ts
class EntityPool extends ObjectPool {
  constructor(entityManager, entityClass, initialSize) {
    super(entityClass, undefined);
    this.entityManager = entityManager;

    if (typeof initialSize !== "undefined") {
      this.expand(initialSize);
    }
  }

  expand(count) {
    for (var n = 0; n < count; n++) {
      var clone = new this.T(this.entityManager);
      clone._pool = this;
      this.freeList.push(clone);
    }
    this.count += count;
  }
}
```
</details>

#### Methods

##### `expand(count: any): void`

<details><summary>Code</summary>

```ts
expand(count) {
    for (var n = 0; n < count; n++) {
      var clone = new this.T(this.entityManager);
      clone._pool = this;
      this.freeList.push(clone);
    }
    this.count += count;
  }
```
</details>

### `EntityManager`

<details><summary>Class Code</summary>

```ts
class EntityManager {
  constructor(world) {
    this.world = world;
    this.componentsManager = world.componentsManager;

    // All the entities in this instance
    this._entities = [];
    this._nextEntityId = 0;

    this._entitiesByNames = {};

    this._queryManager = new QueryManager(this);
    this.eventDispatcher = new EventDispatcher();
    this._entityPool = new EntityPool(
      this,
      this.world.options.entityClass,
      this.world.options.entityPoolSize
    );

    // Deferred deletion
    this.entitiesWithComponentsToRemove = [];
    this.entitiesToRemove = [];
    this.deferredRemovalEnabled = true;
  }

  getEntityByName(name) {
    return this._entitiesByNames[name];
  }

  /**
   * Create a new entity
   */
  createEntity(name) {
    var entity = this._entityPool.acquire();
    entity.alive = true;
    entity.name = name || "";
    if (name) {
      if (this._entitiesByNames[name]) {
        console.warn(`Entity name '${name}' already exist`);
      } else {
        this._entitiesByNames[name] = entity;
      }
    }

    this._entities.push(entity);
    this.eventDispatcher.dispatchEvent(ENTITY_CREATED, entity);
    return entity;
  }

  // COMPONENTS

  /**
   * Add a component to an entity
   * @param {Entity} entity Entity where the component will be added
   * @param {Component} Component Component to be added to the entity
   * @param {Object} values Optional values to replace the default attributes
   */
  entityAddComponent(entity, Component, values) {
    // @todo Probably define Component._typeId with a default value and avoid using typeof
    if (
      typeof Component._typeId === "undefined" &&
      !this.world.componentsManager._ComponentsMap[Component._typeId]
    ) {
      throw new Error(
        `Attempted to add unregistered component "${Component.getName()}"`
      );
    }

    if (~entity._ComponentTypes.indexOf(Component)) {
      {
        console.warn(
          "Component type already exists on entity.",
          entity,
          Component.getName()
        );
      }
      return;
    }

    entity._ComponentTypes.push(Component);

    if (Component.__proto__ === SystemStateComponent) {
      entity.numStateComponents++;
    }

    var componentPool = this.world.componentsManager.getComponentsPool(
      Component
    );

    var component = componentPool
      ? componentPool.acquire()
      : new Component(values);

    if (componentPool && values) {
      component.copy(values);
    }

    entity._components[Component._typeId] = component;

    this._queryManager.onEntityComponentAdded(entity, Component);
    this.world.componentsManager.componentAddedToEntity(Component);

    this.eventDispatcher.dispatchEvent(COMPONENT_ADDED, entity, Component);
  }

  /**
   * Remove a component from an entity
   * @param {Entity} entity Entity which will get removed the component
   * @param {*} Component Component to remove from the entity
   * @param {Bool} immediately If you want to remove the component immediately instead of deferred (Default is false)
   */
  entityRemoveComponent(entity, Component, immediately) {
    var index = entity._ComponentTypes.indexOf(Component);
    if (!~index) return;

    this.eventDispatcher.dispatchEvent(COMPONENT_REMOVE, entity, Component);

    if (immediately) {
      this._entityRemoveComponentSync(entity, Component, index);
    } else {
      if (entity._ComponentTypesToRemove.length === 0)
        this.entitiesWithComponentsToRemove.push(entity);

      entity._ComponentTypes.splice(index, 1);
      entity._ComponentTypesToRemove.push(Component);

      entity._componentsToRemove[Component._typeId] =
        entity._components[Component._typeId];
      delete entity._components[Component._typeId];
    }

    // Check each indexed query to see if we need to remove it
    this._queryManager.onEntityComponentRemoved(entity, Component);

    if (Component.__proto__ === SystemStateComponent) {
      entity.numStateComponents--;

      // Check if the entity was a ghost waiting for the last system state component to be removed
      if (entity.numStateComponents === 0 && !entity.alive) {
        entity.remove();
      }
    }
  }

  _entityRemoveComponentSync(entity, Component, index) {
    // Remove T listing on entity and property ref, then free the component.
    entity._ComponentTypes.splice(index, 1);
    var component = entity._components[Component._typeId];
    delete entity._components[Component._typeId];
    component.dispose();
    this.world.componentsManager.componentRemovedFromEntity(Component);
  }

  /**
   * Remove all the components from an entity
   * @param {Entity} entity Entity from which the components will be removed
   */
  entityRemoveAllComponents(entity, immediately) {
    let Components = entity._ComponentTypes;

    for (let j = Components.length - 1; j >= 0; j--) {
      if (Components[j].__proto__ !== SystemStateComponent)
        this.entityRemoveComponent(entity, Components[j], immediately);
    }
  }

  /**
   * Remove the entity from this manager. It will clear also its components
   * @param {Entity} entity Entity to remove from the manager
   * @param {Bool} immediately If you want to remove the component immediately instead of deferred (Default is false)
   */
  removeEntity(entity, immediately) {
    var index = this._entities.indexOf(entity);

    if (!~index) throw new Error("Tried to remove entity not in list");

    entity.alive = false;
    this.entityRemoveAllComponents(entity, immediately);

    if (entity.numStateComponents === 0) {
      // Remove from entity list
      this.eventDispatcher.dispatchEvent(ENTITY_REMOVED, entity);
      this._queryManager.onEntityRemoved(entity);
      if (immediately === true) {
        this._releaseEntity(entity, index);
      } else {
        this.entitiesToRemove.push(entity);
      }
    }
  }

  _releaseEntity(entity, index) {
    this._entities.splice(index, 1);

    if (this._entitiesByNames[entity.name]) {
      delete this._entitiesByNames[entity.name];
    }
    entity._pool.release(entity);
  }

  /**
   * Remove all entities from this manager
   */
  removeAllEntities() {
    for (var i = this._entities.length - 1; i >= 0; i--) {
      this.removeEntity(this._entities[i]);
    }
  }

  processDeferredRemoval() {
    if (!this.deferredRemovalEnabled) {
      return;
    }

    for (let i = 0; i < this.entitiesToRemove.length; i++) {
      let entity = this.entitiesToRemove[i];
      let index = this._entities.indexOf(entity);
      this._releaseEntity(entity, index);
    }
    this.entitiesToRemove.length = 0;

    for (let i = 0; i < this.entitiesWithComponentsToRemove.length; i++) {
      let entity = this.entitiesWithComponentsToRemove[i];
      while (entity._ComponentTypesToRemove.length > 0) {
        let Component = entity._ComponentTypesToRemove.pop();

        var component = entity._componentsToRemove[Component._typeId];
        delete entity._componentsToRemove[Component._typeId];
        component.dispose();
        this.world.componentsManager.componentRemovedFromEntity(Component);

        //this._entityRemoveComponentSync(entity, Component, index);
      }
    }

    this.entitiesWithComponentsToRemove.length = 0;
  }

  /**
   * Get a query based on a list of components
   * @param {Array(Component)} Components List of components that will form the query
   */
  queryComponents(Components) {
    return this._queryManager.getQuery(Components);
  }

  // EXTRAS

  /**
   * Return number of entities
   */
  count() {
    return this._entities.length;
  }

  /**
   * Return some stats
   */
  stats() {
    var stats = {
      numEntities: this._entities.length,
      numQueries: Object.keys(this._queryManager._queries).length,
      queries: this._queryManager.stats(),
      numComponentPool: Object.keys(this.componentsManager._componentPool)
        .length,
      componentPool: {},
      eventDispatcher: this.eventDispatcher.stats,
    };

    for (var ecsyComponentId in this.componentsManager._componentPool) {
      var pool = this.componentsManager._componentPool[ecsyComponentId];
      stats.componentPool[pool.T.getName()] = {
        used: pool.totalUsed(),
        size: pool.count,
      };
    }

    return stats;
  }
}
```
</details>

#### Methods

##### `getEntityByName(name: any): any`

<details><summary>Code</summary>

```ts
getEntityByName(name) {
    return this._entitiesByNames[name];
  }
```
</details>

##### `createEntity(name: any): any`

<details><summary>Code</summary>

```ts
createEntity(name) {
    var entity = this._entityPool.acquire();
    entity.alive = true;
    entity.name = name || "";
    if (name) {
      if (this._entitiesByNames[name]) {
        console.warn(`Entity name '${name}' already exist`);
      } else {
        this._entitiesByNames[name] = entity;
      }
    }

    this._entities.push(entity);
    this.eventDispatcher.dispatchEvent(ENTITY_CREATED, entity);
    return entity;
  }
```
</details>

##### `entityAddComponent(entity: Entity, Component: Component, values: any): void`

<details><summary>Code</summary>

```ts
entityAddComponent(entity, Component, values) {
    // @todo Probably define Component._typeId with a default value and avoid using typeof
    if (
      typeof Component._typeId === "undefined" &&
      !this.world.componentsManager._ComponentsMap[Component._typeId]
    ) {
      throw new Error(
        `Attempted to add unregistered component "${Component.getName()}"`
      );
    }

    if (~entity._ComponentTypes.indexOf(Component)) {
      {
        console.warn(
          "Component type already exists on entity.",
          entity,
          Component.getName()
        );
      }
      return;
    }

    entity._ComponentTypes.push(Component);

    if (Component.__proto__ === SystemStateComponent) {
      entity.numStateComponents++;
    }

    var componentPool = this.world.componentsManager.getComponentsPool(
      Component
    );

    var component = componentPool
      ? componentPool.acquire()
      : new Component(values);

    if (componentPool && values) {
      component.copy(values);
    }

    entity._components[Component._typeId] = component;

    this._queryManager.onEntityComponentAdded(entity, Component);
    this.world.componentsManager.componentAddedToEntity(Component);

    this.eventDispatcher.dispatchEvent(COMPONENT_ADDED, entity, Component);
  }
```
</details>

##### `entityRemoveComponent(entity: Entity, Component: any, immediately: Bool): void`

<details><summary>Code</summary>

```ts
entityRemoveComponent(entity, Component, immediately) {
    var index = entity._ComponentTypes.indexOf(Component);
    if (!~index) return;

    this.eventDispatcher.dispatchEvent(COMPONENT_REMOVE, entity, Component);

    if (immediately) {
      this._entityRemoveComponentSync(entity, Component, index);
    } else {
      if (entity._ComponentTypesToRemove.length === 0)
        this.entitiesWithComponentsToRemove.push(entity);

      entity._ComponentTypes.splice(index, 1);
      entity._ComponentTypesToRemove.push(Component);

      entity._componentsToRemove[Component._typeId] =
        entity._components[Component._typeId];
      delete entity._components[Component._typeId];
    }

    // Check each indexed query to see if we need to remove it
    this._queryManager.onEntityComponentRemoved(entity, Component);

    if (Component.__proto__ === SystemStateComponent) {
      entity.numStateComponents--;

      // Check if the entity was a ghost waiting for the last system state component to be removed
      if (entity.numStateComponents === 0 && !entity.alive) {
        entity.remove();
      }
    }
  }
```
</details>

##### `_entityRemoveComponentSync(entity: any, Component: any, index: any): void`

<details><summary>Code</summary>

```ts
_entityRemoveComponentSync(entity, Component, index) {
    // Remove T listing on entity and property ref, then free the component.
    entity._ComponentTypes.splice(index, 1);
    var component = entity._components[Component._typeId];
    delete entity._components[Component._typeId];
    component.dispose();
    this.world.componentsManager.componentRemovedFromEntity(Component);
  }
```
</details>

##### `entityRemoveAllComponents(entity: Entity, immediately: any): void`

<details><summary>Code</summary>

```ts
entityRemoveAllComponents(entity, immediately) {
    let Components = entity._ComponentTypes;

    for (let j = Components.length - 1; j >= 0; j--) {
      if (Components[j].__proto__ !== SystemStateComponent)
        this.entityRemoveComponent(entity, Components[j], immediately);
    }
  }
```
</details>

##### `removeEntity(entity: Entity, immediately: Bool): void`

<details><summary>Code</summary>

```ts
removeEntity(entity, immediately) {
    var index = this._entities.indexOf(entity);

    if (!~index) throw new Error("Tried to remove entity not in list");

    entity.alive = false;
    this.entityRemoveAllComponents(entity, immediately);

    if (entity.numStateComponents === 0) {
      // Remove from entity list
      this.eventDispatcher.dispatchEvent(ENTITY_REMOVED, entity);
      this._queryManager.onEntityRemoved(entity);
      if (immediately === true) {
        this._releaseEntity(entity, index);
      } else {
        this.entitiesToRemove.push(entity);
      }
    }
  }
```
</details>

##### `_releaseEntity(entity: any, index: any): void`

<details><summary>Code</summary>

```ts
_releaseEntity(entity, index) {
    this._entities.splice(index, 1);

    if (this._entitiesByNames[entity.name]) {
      delete this._entitiesByNames[entity.name];
    }
    entity._pool.release(entity);
  }
```
</details>

##### `removeAllEntities(): void`

<details><summary>Code</summary>

```ts
removeAllEntities() {
    for (var i = this._entities.length - 1; i >= 0; i--) {
      this.removeEntity(this._entities[i]);
    }
  }
```
</details>

##### `processDeferredRemoval(): void`

<details><summary>Code</summary>

```ts
processDeferredRemoval() {
    if (!this.deferredRemovalEnabled) {
      return;
    }

    for (let i = 0; i < this.entitiesToRemove.length; i++) {
      let entity = this.entitiesToRemove[i];
      let index = this._entities.indexOf(entity);
      this._releaseEntity(entity, index);
    }
    this.entitiesToRemove.length = 0;

    for (let i = 0; i < this.entitiesWithComponentsToRemove.length; i++) {
      let entity = this.entitiesWithComponentsToRemove[i];
      while (entity._ComponentTypesToRemove.length > 0) {
        let Component = entity._ComponentTypesToRemove.pop();

        var component = entity._componentsToRemove[Component._typeId];
        delete entity._componentsToRemove[Component._typeId];
        component.dispose();
        this.world.componentsManager.componentRemovedFromEntity(Component);

        //this._entityRemoveComponentSync(entity, Component, index);
      }
    }

    this.entitiesWithComponentsToRemove.length = 0;
  }
```
</details>

##### `queryComponents(Components: any): any`

<details><summary>Code</summary>

```ts
queryComponents(Components) {
    return this._queryManager.getQuery(Components);
  }
```
</details>

##### `count(): number`

<details><summary>Code</summary>

```ts
count() {
    return this._entities.length;
  }
```
</details>

##### `stats(): { numEntities: number; numQueries: number; queries: {}; numComponentPool: number; componentPool: {}; eventDispatcher: { fired: number; handled: number; }; }`

<details><summary>Code</summary>

```ts
stats() {
    var stats = {
      numEntities: this._entities.length,
      numQueries: Object.keys(this._queryManager._queries).length,
      queries: this._queryManager.stats(),
      numComponentPool: Object.keys(this.componentsManager._componentPool)
        .length,
      componentPool: {},
      eventDispatcher: this.eventDispatcher.stats,
    };

    for (var ecsyComponentId in this.componentsManager._componentPool) {
      var pool = this.componentsManager._componentPool[ecsyComponentId];
      stats.componentPool[pool.T.getName()] = {
        used: pool.totalUsed(),
        size: pool.count,
      };
    }

    return stats;
  }
```
</details>

### `ComponentManager`

<details><summary>Class Code</summary>

```ts
class ComponentManager {
  constructor() {
    this.Components = [];
    this._ComponentsMap = {};

    this._componentPool = {};
    this.numComponents = {};
    this.nextComponentId = 0;
  }

  hasComponent(Component) {
    return this.Components.indexOf(Component) !== -1;
  }

  registerComponent(Component, objectPool) {
    if (this.Components.indexOf(Component) !== -1) {
      console.warn(
        `Component type: '${Component.getName()}' already registered.`
      );
      return;
    }

    const schema = Component.schema;

    if (!schema) {
      throw new Error(
        `Component "${Component.getName()}" has no schema property.`
      );
    }

    for (const propName in schema) {
      const prop = schema[propName];

      if (!prop.type) {
        throw new Error(
          `Invalid schema for component "${Component.getName()}". Missing type for "${propName}" property.`
        );
      }
    }

    Component._typeId = this.nextComponentId++;
    this.Components.push(Component);
    this._ComponentsMap[Component._typeId] = Component;
    this.numComponents[Component._typeId] = 0;

    if (objectPool === undefined) {
      objectPool = new ObjectPool(Component);
    } else if (objectPool === false) {
      objectPool = undefined;
    }

    this._componentPool[Component._typeId] = objectPool;
  }

  componentAddedToEntity(Component) {
    this.numComponents[Component._typeId]++;
  }

  componentRemovedFromEntity(Component) {
    this.numComponents[Component._typeId]--;
  }

  getComponentsPool(Component) {
    return this._componentPool[Component._typeId];
  }
}
```
</details>

#### Methods

##### `hasComponent(Component: any): boolean`

<details><summary>Code</summary>

```ts
hasComponent(Component) {
    return this.Components.indexOf(Component) !== -1;
  }
```
</details>

##### `registerComponent(Component: any, objectPool: any): void`

<details><summary>Code</summary>

```ts
registerComponent(Component, objectPool) {
    if (this.Components.indexOf(Component) !== -1) {
      console.warn(
        `Component type: '${Component.getName()}' already registered.`
      );
      return;
    }

    const schema = Component.schema;

    if (!schema) {
      throw new Error(
        `Component "${Component.getName()}" has no schema property.`
      );
    }

    for (const propName in schema) {
      const prop = schema[propName];

      if (!prop.type) {
        throw new Error(
          `Invalid schema for component "${Component.getName()}". Missing type for "${propName}" property.`
        );
      }
    }

    Component._typeId = this.nextComponentId++;
    this.Components.push(Component);
    this._ComponentsMap[Component._typeId] = Component;
    this.numComponents[Component._typeId] = 0;

    if (objectPool === undefined) {
      objectPool = new ObjectPool(Component);
    } else if (objectPool === false) {
      objectPool = undefined;
    }

    this._componentPool[Component._typeId] = objectPool;
  }
```
</details>

##### `componentAddedToEntity(Component: any): void`

<details><summary>Code</summary>

```ts
componentAddedToEntity(Component) {
    this.numComponents[Component._typeId]++;
  }
```
</details>

##### `componentRemovedFromEntity(Component: any): void`

<details><summary>Code</summary>

```ts
componentRemovedFromEntity(Component) {
    this.numComponents[Component._typeId]--;
  }
```
</details>

##### `getComponentsPool(Component: any): any`

<details><summary>Code</summary>

```ts
getComponentsPool(Component) {
    return this._componentPool[Component._typeId];
  }
```
</details>

### `Entity`

<details><summary>Class Code</summary>

```ts
class Entity {
  constructor(entityManager) {
    this._entityManager = entityManager || null;

    // Unique ID for this entity
    this.id = entityManager._nextEntityId++;

    // List of components types the entity has
    this._ComponentTypes = [];

    // Instance of the components
    this._components = {};

    this._componentsToRemove = {};

    // Queries where the entity is added
    this.queries = [];

    // Used for deferred removal
    this._ComponentTypesToRemove = [];

    this.alive = false;

    //if there are state components on a entity, it can't be removed completely
    this.numStateComponents = 0;
  }

  // COMPONENTS

  getComponent(Component, includeRemoved) {
    var component = this._components[Component._typeId];

    if (!component && includeRemoved === true) {
      component = this._componentsToRemove[Component._typeId];
    }

    return  wrapImmutableComponent(Component, component)
      ;
  }

  getRemovedComponent(Component) {
    const component = this._componentsToRemove[Component._typeId];

    return  wrapImmutableComponent(Component, component)
      ;
  }

  getComponents() {
    return this._components;
  }

  getComponentsToRemove() {
    return this._componentsToRemove;
  }

  getComponentTypes() {
    return this._ComponentTypes;
  }

  getMutableComponent(Component) {
    var component = this._components[Component._typeId];

    if (!component) {
      return;
    }

    for (var i = 0; i < this.queries.length; i++) {
      var query = this.queries[i];
      // @todo accelerate this check. Maybe having query._Components as an object
      // @todo add Not components
      if (query.reactive && query.Components.indexOf(Component) !== -1) {
        query.eventDispatcher.dispatchEvent(
          Query.prototype.COMPONENT_CHANGED,
          this,
          component
        );
      }
    }
    return component;
  }

  addComponent(Component, values) {
    this._entityManager.entityAddComponent(this, Component, values);
    return this;
  }

  removeComponent(Component, forceImmediate) {
    this._entityManager.entityRemoveComponent(this, Component, forceImmediate);
    return this;
  }

  hasComponent(Component, includeRemoved) {
    return (
      !!~this._ComponentTypes.indexOf(Component) ||
      (includeRemoved === true && this.hasRemovedComponent(Component))
    );
  }

  hasRemovedComponent(Component) {
    return !!~this._ComponentTypesToRemove.indexOf(Component);
  }

  hasAllComponents(Components) {
    for (var i = 0; i < Components.length; i++) {
      if (!this.hasComponent(Components[i])) return false;
    }
    return true;
  }

  hasAnyComponents(Components) {
    for (var i = 0; i < Components.length; i++) {
      if (this.hasComponent(Components[i])) return true;
    }
    return false;
  }

  removeAllComponents(forceImmediate) {
    return this._entityManager.entityRemoveAllComponents(this, forceImmediate);
  }

  copy(src) {
    // TODO: This can definitely be optimized
    for (var ecsyComponentId in src._components) {
      var srcComponent = src._components[ecsyComponentId];
      this.addComponent(srcComponent.constructor);
      var component = this.getComponent(srcComponent.constructor);
      component.copy(srcComponent);
    }

    return this;
  }

  clone() {
    return new Entity(this._entityManager).copy(this);
  }

  reset() {
    this.id = this._entityManager._nextEntityId++;
    this._ComponentTypes.length = 0;
    this.queries.length = 0;

    for (var ecsyComponentId in this._components) {
      delete this._components[ecsyComponentId];
    }
  }

  remove(forceImmediate) {
    return this._entityManager.removeEntity(this, forceImmediate);
  }
}
```
</details>

#### Methods

##### `getComponent(Component: any, includeRemoved: any): any`

<details><summary>Code</summary>

```ts
getComponent(Component, includeRemoved) {
    var component = this._components[Component._typeId];

    if (!component && includeRemoved === true) {
      component = this._componentsToRemove[Component._typeId];
    }

    return  wrapImmutableComponent(Component, component)
      ;
  }
```
</details>

##### `getRemovedComponent(Component: any): any`

<details><summary>Code</summary>

```ts
getRemovedComponent(Component) {
    const component = this._componentsToRemove[Component._typeId];

    return  wrapImmutableComponent(Component, component)
      ;
  }
```
</details>

##### `getComponents(): {}`

<details><summary>Code</summary>

```ts
getComponents() {
    return this._components;
  }
```
</details>

##### `getComponentsToRemove(): {}`

<details><summary>Code</summary>

```ts
getComponentsToRemove() {
    return this._componentsToRemove;
  }
```
</details>

##### `getComponentTypes(): any[]`

<details><summary>Code</summary>

```ts
getComponentTypes() {
    return this._ComponentTypes;
  }
```
</details>

##### `getMutableComponent(Component: any): any`

<details><summary>Code</summary>

```ts
getMutableComponent(Component) {
    var component = this._components[Component._typeId];

    if (!component) {
      return;
    }

    for (var i = 0; i < this.queries.length; i++) {
      var query = this.queries[i];
      // @todo accelerate this check. Maybe having query._Components as an object
      // @todo add Not components
      if (query.reactive && query.Components.indexOf(Component) !== -1) {
        query.eventDispatcher.dispatchEvent(
          Query.prototype.COMPONENT_CHANGED,
          this,
          component
        );
      }
    }
    return component;
  }
```
</details>

##### `addComponent(Component: any, values: any): this`

<details><summary>Code</summary>

```ts
addComponent(Component, values) {
    this._entityManager.entityAddComponent(this, Component, values);
    return this;
  }
```
</details>

##### `removeComponent(Component: any, forceImmediate: any): this`

<details><summary>Code</summary>

```ts
removeComponent(Component, forceImmediate) {
    this._entityManager.entityRemoveComponent(this, Component, forceImmediate);
    return this;
  }
```
</details>

##### `hasComponent(Component: any, includeRemoved: any): boolean`

<details><summary>Code</summary>

```ts
hasComponent(Component, includeRemoved) {
    return (
      !!~this._ComponentTypes.indexOf(Component) ||
      (includeRemoved === true && this.hasRemovedComponent(Component))
    );
  }
```
</details>

##### `hasRemovedComponent(Component: any): boolean`

<details><summary>Code</summary>

```ts
hasRemovedComponent(Component) {
    return !!~this._ComponentTypesToRemove.indexOf(Component);
  }
```
</details>

##### `hasAllComponents(Components: any): boolean`

<details><summary>Code</summary>

```ts
hasAllComponents(Components) {
    for (var i = 0; i < Components.length; i++) {
      if (!this.hasComponent(Components[i])) return false;
    }
    return true;
  }
```
</details>

##### `hasAnyComponents(Components: any): boolean`

<details><summary>Code</summary>

```ts
hasAnyComponents(Components) {
    for (var i = 0; i < Components.length; i++) {
      if (this.hasComponent(Components[i])) return true;
    }
    return false;
  }
```
</details>

##### `removeAllComponents(forceImmediate: any): any`

<details><summary>Code</summary>

```ts
removeAllComponents(forceImmediate) {
    return this._entityManager.entityRemoveAllComponents(this, forceImmediate);
  }
```
</details>

##### `copy(src: any): this`

<details><summary>Code</summary>

```ts
copy(src) {
    // TODO: This can definitely be optimized
    for (var ecsyComponentId in src._components) {
      var srcComponent = src._components[ecsyComponentId];
      this.addComponent(srcComponent.constructor);
      var component = this.getComponent(srcComponent.constructor);
      component.copy(srcComponent);
    }

    return this;
  }
```
</details>

##### `clone(): Entity`

<details><summary>Code</summary>

```ts
clone() {
    return new Entity(this._entityManager).copy(this);
  }
```
</details>

##### `reset(): void`

<details><summary>Code</summary>

```ts
reset() {
    this.id = this._entityManager._nextEntityId++;
    this._ComponentTypes.length = 0;
    this.queries.length = 0;

    for (var ecsyComponentId in this._components) {
      delete this._components[ecsyComponentId];
    }
  }
```
</details>

##### `remove(forceImmediate: any): any`

<details><summary>Code</summary>

```ts
remove(forceImmediate) {
    return this._entityManager.removeEntity(this, forceImmediate);
  }
```
</details>

### `World`

<details><summary>Class Code</summary>

```ts
class World {
  constructor(options = {}) {
    this.options = Object.assign({}, DEFAULT_OPTIONS, options);

    this.componentsManager = new ComponentManager(this);
    this.entityManager = new EntityManager(this);
    this.systemManager = new SystemManager(this);

    this.enabled = true;

    this.eventQueues = {};

    if (hasWindow && typeof CustomEvent !== "undefined") {
      var event = new CustomEvent("ecsy-world-created", {
        detail: { world: this, version: Version },
      });
      window.dispatchEvent(event);
    }

    this.lastTime = now() / 1000;
  }

  registerComponent(Component, objectPool) {
    this.componentsManager.registerComponent(Component, objectPool);
    return this;
  }

  registerSystem(System, attributes) {
    this.systemManager.registerSystem(System, attributes);
    return this;
  }

  hasRegisteredComponent(Component) {
    return this.componentsManager.hasComponent(Component);
  }

  unregisterSystem(System) {
    this.systemManager.unregisterSystem(System);
    return this;
  }

  getSystem(SystemClass) {
    return this.systemManager.getSystem(SystemClass);
  }

  getSystems() {
    return this.systemManager.getSystems();
  }

  execute(delta, time) {
    if (!delta) {
      time = now() / 1000;
      delta = time - this.lastTime;
      this.lastTime = time;
    }

    if (this.enabled) {
      this.systemManager.execute(delta, time);
      this.entityManager.processDeferredRemoval();
    }
  }

  stop() {
    this.enabled = false;
  }

  play() {
    this.enabled = true;
  }

  createEntity(name) {
    return this.entityManager.createEntity(name);
  }

  stats() {
    var stats = {
      entities: this.entityManager.stats(),
      system: this.systemManager.stats(),
    };

    return stats;
  }
}
```
</details>

#### Methods

##### `registerComponent(Component: any, objectPool: any): this`

<details><summary>Code</summary>

```ts
registerComponent(Component, objectPool) {
    this.componentsManager.registerComponent(Component, objectPool);
    return this;
  }
```
</details>

##### `registerSystem(System: any, attributes: any): this`

<details><summary>Code</summary>

```ts
registerSystem(System, attributes) {
    this.systemManager.registerSystem(System, attributes);
    return this;
  }
```
</details>

##### `hasRegisteredComponent(Component: any): boolean`

<details><summary>Code</summary>

```ts
hasRegisteredComponent(Component) {
    return this.componentsManager.hasComponent(Component);
  }
```
</details>

##### `unregisterSystem(System: any): this`

<details><summary>Code</summary>

```ts
unregisterSystem(System) {
    this.systemManager.unregisterSystem(System);
    return this;
  }
```
</details>

##### `getSystem(SystemClass: any): any`

<details><summary>Code</summary>

```ts
getSystem(SystemClass) {
    return this.systemManager.getSystem(SystemClass);
  }
```
</details>

##### `getSystems(): any[]`

<details><summary>Code</summary>

```ts
getSystems() {
    return this.systemManager.getSystems();
  }
```
</details>

##### `execute(delta: any, time: any): void`

<details><summary>Code</summary>

```ts
execute(delta, time) {
    if (!delta) {
      time = now() / 1000;
      delta = time - this.lastTime;
      this.lastTime = time;
    }

    if (this.enabled) {
      this.systemManager.execute(delta, time);
      this.entityManager.processDeferredRemoval();
    }
  }
```
</details>

##### `stop(): void`

<details><summary>Code</summary>

```ts
stop() {
    this.enabled = false;
  }
```
</details>

##### `play(): void`

<details><summary>Code</summary>

```ts
play() {
    this.enabled = true;
  }
```
</details>

##### `createEntity(name: any): any`

<details><summary>Code</summary>

```ts
createEntity(name) {
    return this.entityManager.createEntity(name);
  }
```
</details>

##### `stats(): { entities: { numEntities: number; numQueries: number; queries: {}; numComponentPool: number; componentPool: {}; eventDispatcher: { fired: number; handled: number; }; }; system: { numSystems: number; systems: {}; }; }`

<details><summary>Code</summary>

```ts
stats() {
    var stats = {
      entities: this.entityManager.stats(),
      system: this.systemManager.stats(),
    };

    return stats;
  }
```
</details>

### `System`

<details><summary>Class Code</summary>

```ts
class System {
  canExecute() {
    if (this._mandatoryQueries.length === 0) return true;

    for (let i = 0; i < this._mandatoryQueries.length; i++) {
      var query = this._mandatoryQueries[i];
      if (query.entities.length === 0) {
        return false;
      }
    }

    return true;
  }

  getName() {
    return this.constructor.getName();
  }

  constructor(world, attributes) {
    this.world = world;
    this.enabled = true;

    // @todo Better naming :)
    this._queries = {};
    this.queries = {};

    this.priority = 0;

    // Used for stats
    this.executeTime = 0;

    if (attributes && attributes.priority) {
      this.priority = attributes.priority;
    }

    this._mandatoryQueries = [];

    this.initialized = true;

    if (this.constructor.queries) {
      for (var queryName in this.constructor.queries) {
        var queryConfig = this.constructor.queries[queryName];
        var Components = queryConfig.components;
        if (!Components || Components.length === 0) {
          throw new Error("'components' attribute can't be empty in a query");
        }

        // Detect if the components have already been registered
        let unregisteredComponents = Components.filter(
          (Component) => !componentRegistered(Component)
        );

        if (unregisteredComponents.length > 0) {
          throw new Error(
            `Tried to create a query '${
              this.constructor.name
            }.${queryName}' with unregistered components: [${unregisteredComponents
              .map((c) => c.getName())
              .join(", ")}]`
          );
        }

        var query = this.world.entityManager.queryComponents(Components);

        this._queries[queryName] = query;
        if (queryConfig.mandatory === true) {
          this._mandatoryQueries.push(query);
        }
        this.queries[queryName] = {
          results: query.entities,
        };

        // Reactive configuration added/removed/changed
        var validEvents = ["added", "removed", "changed"];

        const eventMapping = {
          added: Query.prototype.ENTITY_ADDED,
          removed: Query.prototype.ENTITY_REMOVED,
          changed: Query.prototype.COMPONENT_CHANGED, // Query.prototype.ENTITY_CHANGED
        };

        if (queryConfig.listen) {
          validEvents.forEach((eventName) => {
            if (!this.execute) {
              console.warn(
                `System '${this.getName()}' has defined listen events (${validEvents.join(
                  ", "
                )}) for query '${queryName}' but it does not implement the 'execute' method.`
              );
            }

            // Is the event enabled on this system's query?
            if (queryConfig.listen[eventName]) {
              let event = queryConfig.listen[eventName];

              if (eventName === "changed") {
                query.reactive = true;
                if (event === true) {
                  // Any change on the entity from the components in the query
                  let eventList = (this.queries[queryName][eventName] = []);
                  query.eventDispatcher.addEventListener(
                    Query.prototype.COMPONENT_CHANGED,
                    (entity) => {
                      // Avoid duplicates
                      if (eventList.indexOf(entity) === -1) {
                        eventList.push(entity);
                      }
                    }
                  );
                } else if (Array.isArray(event)) {
                  let eventList = (this.queries[queryName][eventName] = []);
                  query.eventDispatcher.addEventListener(
                    Query.prototype.COMPONENT_CHANGED,
                    (entity, changedComponent) => {
                      // Avoid duplicates
                      if (
                        event.indexOf(changedComponent.constructor) !== -1 &&
                        eventList.indexOf(entity) === -1
                      ) {
                        eventList.push(entity);
                      }
                    }
                  );
                }
              } else {
                let eventList = (this.queries[queryName][eventName] = []);

                query.eventDispatcher.addEventListener(
                  eventMapping[eventName],
                  (entity) => {
                    // @fixme overhead?
                    if (eventList.indexOf(entity) === -1)
                      eventList.push(entity);
                  }
                );
              }
            }
          });
        }
      }
    }
  }

  stop() {
    this.executeTime = 0;
    this.enabled = false;
  }

  play() {
    this.enabled = true;
  }

  // @question rename to clear queues?
  clearEvents() {
    for (let queryName in this.queries) {
      var query = this.queries[queryName];
      if (query.added) {
        query.added.length = 0;
      }
      if (query.removed) {
        query.removed.length = 0;
      }
      if (query.changed) {
        if (Array.isArray(query.changed)) {
          query.changed.length = 0;
        } else {
          for (let name in query.changed) {
            query.changed[name].length = 0;
          }
        }
      }
    }
  }

  toJSON() {
    var json = {
      name: this.getName(),
      enabled: this.enabled,
      executeTime: this.executeTime,
      priority: this.priority,
      queries: {},
    };

    if (this.constructor.queries) {
      var queries = this.constructor.queries;
      for (let queryName in queries) {
        let query = this.queries[queryName];
        let queryDefinition = queries[queryName];
        let jsonQuery = (json.queries[queryName] = {
          key: this._queries[queryName].key,
        });

        jsonQuery.mandatory = queryDefinition.mandatory === true;
        jsonQuery.reactive =
          queryDefinition.listen &&
          (queryDefinition.listen.added === true ||
            queryDefinition.listen.removed === true ||
            queryDefinition.listen.changed === true ||
            Array.isArray(queryDefinition.listen.changed));

        if (jsonQuery.reactive) {
          jsonQuery.listen = {};

          const methods = ["added", "removed", "changed"];
          methods.forEach((method) => {
            if (query[method]) {
              jsonQuery.listen[method] = {
                entities: query[method].length,
              };
            }
          });
        }
      }
    }

    return json;
  }
}
```
</details>

#### Methods

##### `canExecute(): boolean`

<details><summary>Code</summary>

```ts
canExecute() {
    if (this._mandatoryQueries.length === 0) return true;

    for (let i = 0; i < this._mandatoryQueries.length; i++) {
      var query = this._mandatoryQueries[i];
      if (query.entities.length === 0) {
        return false;
      }
    }

    return true;
  }
```
</details>

##### `getName(): any`

<details><summary>Code</summary>

```ts
getName() {
    return this.constructor.getName();
  }
```
</details>

##### `stop(): void`

<details><summary>Code</summary>

```ts
stop() {
    this.executeTime = 0;
    this.enabled = false;
  }
```
</details>

##### `play(): void`

<details><summary>Code</summary>

```ts
play() {
    this.enabled = true;
  }
```
</details>

##### `clearEvents(): void`

<details><summary>Code</summary>

```ts
clearEvents() {
    for (let queryName in this.queries) {
      var query = this.queries[queryName];
      if (query.added) {
        query.added.length = 0;
      }
      if (query.removed) {
        query.removed.length = 0;
      }
      if (query.changed) {
        if (Array.isArray(query.changed)) {
          query.changed.length = 0;
        } else {
          for (let name in query.changed) {
            query.changed[name].length = 0;
          }
        }
      }
    }
  }
```
</details>

##### `toJSON(): { name: any; enabled: boolean; executeTime: number; priority: any; queries: {}; }`

<details><summary>Code</summary>

```ts
toJSON() {
    var json = {
      name: this.getName(),
      enabled: this.enabled,
      executeTime: this.executeTime,
      priority: this.priority,
      queries: {},
    };

    if (this.constructor.queries) {
      var queries = this.constructor.queries;
      for (let queryName in queries) {
        let query = this.queries[queryName];
        let queryDefinition = queries[queryName];
        let jsonQuery = (json.queries[queryName] = {
          key: this._queries[queryName].key,
        });

        jsonQuery.mandatory = queryDefinition.mandatory === true;
        jsonQuery.reactive =
          queryDefinition.listen &&
          (queryDefinition.listen.added === true ||
            queryDefinition.listen.removed === true ||
            queryDefinition.listen.changed === true ||
            Array.isArray(queryDefinition.listen.changed));

        if (jsonQuery.reactive) {
          jsonQuery.listen = {};

          const methods = ["added", "removed", "changed"];
          methods.forEach((method) => {
            if (query[method]) {
              jsonQuery.listen[method] = {
                entities: query[method].length,
              };
            }
          });
        }
      }
    }

    return json;
  }
```
</details>

### `TagComponent`

<details><summary>Class Code</summary>

```ts
class TagComponent extends Component {
  constructor() {
    super(false);
  }
}
```
</details>


---