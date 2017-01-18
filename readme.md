
### Assumptions

Audience already know a bit of Clojure. This talk won't cover basics of Clojure like syntax etc for the sake of time.

### Clojure Script Hello world

```Clojure
(ns hello-world.core)

(enable-console-print!)

(println "Hello world!")
```

#### Create the build config

```Clojure
(require 'cljs.build.api)

(cljs.build.api/build "src"
 {:output-to "out/main.js"})

```

#### Compile using the ClojureScript compiler

java -cp cljs.jar:src clojure.main build.clj


Take a look at the ~out~ directory. You should see a structure similar to the following

```
total 8
drwxr-xr-x   5 kp  staff  170 Jan 18 15:13 cljs
drwxr-xr-x  12 kp  staff  408 Jan 18 15:13 goog
drwxr-xr-x   6 kp  staff  204 Jan 18 15:30 hello_world
-rw-r--r--   1 kp  staff  295 Jan 18 15:13 main.js

```


Let's take a look at how the core.js file looks. This is what you should see in that directory

```
// Compiled by ClojureScript 1.9.293 {}
goog.provide('hello_world.core');
goog.require('cljs.core');
cljs.core.enable_console_print_BANG_.call(null);
cljs.core.println.call(null,"Hello world!");

//# sourceMappingURL=core.js.map

```





### Compiling a cljs file just using the ClojureScript compiler
### How does it work?
### Different Javascript platforms that ClojureScript supports
### Major differences from Clojure.
### Clojure Script interoperability with Javascript
### Targeting Clojure and ClojureScript in the same code base
### Tooling 
   * ClJSBUILD
   * Editor integration, how does it work with emacs repl
   * Figwheel
