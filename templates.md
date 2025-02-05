# EventEmmiter

```ts
class EventEmitter {
  constructor() {
    this.events = {};
  }

  on(event, listener) {
    this.events[event] = this.events[event] || [];
    this.events[event].push(listener);
    return this; // для цепочки вызова
  }

  once(event, listener) {
    const wrappedListener = (...args) => {
      this.off(event, wrappedListener);
      listener(...args);
    };
    this.on(event, wrappedListener);
    return this;
  }

  off(event, listener) {
    if (!this.events[event]) return this;
    this.events[event] = this.events[event].filter(l => l !== listener);
    return this;
  }

  emit(event, ...args) {
    if (this.events[event]) {
      try {
        this.events[event].forEach(listener => listener(...args));
      } catch (error) {
        console.error(`Error emitting event "${event}":`, error);
      }
    }
    return this; // для цепочки вызова
  }
}
```
