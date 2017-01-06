#### generator
* generatorFunction
The function* declaration (function keyword followed by an asterisk) defines a generator function, which returns a Generator object.
`function* name( ) {}` 
* generator
The Generator object is returned by a generator function and it conforms to both the iterable protocol and the iterator protocol.
here “gen” is a generator.
`var gen = name();`
* yield*  generator
    function* f() { 
    	console.log(1);
    	yield "hello"; 
    	console.log(2); 
    	yield "world";
    }
    function* bb() { 
    	yield "aaa"; 
    
     //bb的generator到f的generator里取值
    	yield* f(); 
    	yield* f(); 
    	yield "bbb";
    }
    var B = bb();
    B.next(); //Object {value: "aaa", done: false}
    B.next(); //1, Object {value: "hello", done: false}
    B.next(); //2, Object {value: "world", done: false}
    B.next(); //1, Object {value: "hello", done: false}
    B.next(); //2, Object {value: "world", done: false}
    B.next(); //Object {value: "bbb", done: false}
    B.next(); //Object {value: undefined, done: true}
