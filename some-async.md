```clojure
╭─skelter@Suehss-Laptop  ~/work/pillowtalk  ‹master›
╰─$ lein repl
nREPL server started on port 63066
REPL-y 0.1.10
Clojure 1.5.1
Exit: Control+D or (exit) or (quit)
Commands: (user/help)
Docs: (doc function-name-here)
      (find-doc "part-of-name-here")
Source: (source function-name-here)
          (user/sourcery function-name-here)
Javadoc: (javadoc java-object-or-class-here)
Examples from clojuredocs.org: [clojuredocs or cdoc]
				         (user/clojuredocs name-here)
	           (user/clojuredocs "ns-here" "name-here")
user=> (use 'clojure.core.async)
nil
user=> (def mychan (chan))
#'user/mychan
user=> (type mychan)
clojure.core.async.impl.channels.ManyToManyChannel
user=> (>!! mychan "hooo doggy! 1")
 ^C
user=> (go (>!! mychan "hooo doggy! 1"))
												   
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@6de9b48b>
user=> (go (println "Cool! " (<!! mychan)))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@36489670>
user=> Cool!  hooo doggy! 1
												   
user=> (expand-macro)
CompilerException java.lang.RuntimeException: Unable to resolve symbol: expand-macro in this context, compiling:(NO_SOURCE_PATH:1:1)
												   
user=> (macroexpand)
ArityException Wrong number of args (0) passed to: core$macroexpand  clojure.lang.AFn.throwArity (AFn.java:437)
												   
user=> (macroexpand (go (println "Cool! " (<!! mychan))))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@5886f847>
Cool!  hooo doggy! 1
user=> (macroexpand '(go (println "Cool! " (<!! mychan))))
(let* [c__2430__auto__ (clojure.core.async/chan 1) captured-bindings__2431__auto__ (clojure.lang.Var/getThreadBindingFrame)] (clojure.core.async.impl.dispatch/run (clojure.core/fn [] (clojure.core/let [f__2432__auto__ (clojure.core/fn state-machine__2301__auto__ ([] (clojure.core.async.impl.ioc-macros/aset-all! (java.util.concurrent.atomic.AtomicReferenceArray. 5) 0 state-machine__2301__auto__ 1 1)) ([state_2524] (clojure.core/let [old-frame__2302__auto__ (clojure.lang.Var/getThreadBindingFrame)] (try (clojure.lang.Var/resetThreadBindingFrame (clojure.core.async.impl.ioc-macros/aget-object state_2524 3)) (clojure.core/loop [] (clojure.core/let [result__2303__auto__ (clojure.core/case (clojure.core/int (clojure.core.async.impl.ioc-macros/aget-object state_2524 1)) 1 (clojure.core/let [inst_2521 (<!! mychan) inst_2522 (println "Cool! " inst_2521) state_2524 state_2524] (clojure.core.async.impl.ioc-macros/return-chan state_2524 inst_2522)))] (if (clojure.core/identical? result__2303__auto__ :recur) (recur) result__2303__auto__))) (finally (clojure.lang.Var/resetThreadBindingFrame old-frame__2302__auto__)))))) state__2433__auto__ (clojure.core/-> (f__2432__auto__) (clojure.core.async.impl.ioc-macros/aset-all! clojure.core.async.impl.ioc-macros/USER-START-IDX c__2430__auto__ clojure.core.async.impl.ioc-macros/BINDINGS-IDX captured-bindings__2431__auto__))] (clojure.core.async.impl.ioc-macros/run-state-machine state__2433__auto__)))) c__2430__auto__)
user=> (pretty-print (macroexpand '(go (println "Cool! " (<!! mychan)))))
CompilerException java.lang.RuntimeException: Unable to resolve symbol: pretty-print in this context, compiling:(NO_SOURCE_PATH:1:1)
												   
user=> (go (println "Cool! " (<!! mychan)))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@15f068b9>
user=> (go (>!! mychan "hooo doggy! 2"))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@18438d57>
Cool!  hooo doggy! 2
user=> (go (>!! mychan "hooo doggy! 3"))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@115c6cb>
user=> (go (println "Cool! " (<!! mychan)))
												   #<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@195dbaab>
Cool!  hooo doggy! 3
user=> (go (println "Cool! " (<!! mychan)))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@424de67>
user=> (close! mychan)
nilCool!  nil

user=> (close! mychan)
nil
user=> (mychan)
ClassCastException clojure.core.async.impl.channels.ManyToManyChannel cannot be cast to clojure.lang.IFn  user/eval2623 (NO_SOURCE_FILE:1)
												   
user=> mychan
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@76aa3e9a>
user=> (go (println "Cool! " (<!! mychan)))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@780eb73e>Cool!  nil
												   
user=> (closed? mychan)
CompilerException java.lang.RuntimeException: Unable to resolve symbol: closed? in this context, compiling:(NO_SOURCE_PATH:1:1)
												   
user=> (go (println "Cool! " (<!! mychan)))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@2f46ccac>
Cool!  nil

user=> (go (>!! mychan "hooo doggy! 4"))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@53627086>

user=> (go (println "Cool! " (<!! mychan)))
#<ManyToManyChannel clojure.core.async.impl.channels.ManyToManyChannel@4d91e365>
Cool!  nil

user=>
```

