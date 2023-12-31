| Index                                            |                           index                           |                                           index |
| :----------------------------------------------- | :-------------------------------------------------------: | ----------------------------------------------: |
| 75. [Intro](#75)                                 |            106. [Vanilla.js (Optional)](#106)             |        137. [Custom Hooks - Fetch Person](#137) |
| 76. [Github Repository](#76)                     |           107. [Short Circuit - Overview](#107)           |       138. [Custom Hooks - Generic Fetch](#138) |
| 77. [Setup](#77)                                 |           108. [Short Circuit - Examples](#108)           |            139. [Context API - Challenge](#139) |
| 78. [Overview](#78)                              |               109. [Ternary Operator](#109)               |        140. [Context API - Prop Drilling](#140) |
| 79. [Error Example](#79)                         |               110. [Toggle Challenge](#110)               |             141. [Context API - Solution](#141) |
| 80. [UseState Fundamentals](#80)                 |                111. [User Challenge](#111)                |          142. [Context API - Custom Hook](#142) |
| 81. [Initial Render and Re-renders](#81)         | 112. [UseEffect Cleanup Function - Setup/Challenge](#112) |         143. [Context API - Global Setup](#143) |
| 82. [General Rules of React Hooks](#82)          |          113. [UseEffect - Timer Example](#113)           |                  144. [Matching Projects](#144) |
| 83. [UseState Array Example - Setup](#83)        |     114. [UseEffect - Event Listeners Example](#114)      |                 145. [UseReducer - Intro](#145) |
| 84. [UseState Array Example - Complete](#84)     |         115. [You Might Not Need an Effect](#115)         |             146. [UseReducer - Challenge](#146) |
| 85. [UseState - Extra Info](#85)                 |              116. [Matching Projects](#116)               |                 147. [UseReducer - Setup](#147) |
| 86. [UseState Object Example - Setup](#86)       |      117. [Project Structure - Folder Example](#117)      |                     148. [Reducer Basics](#148) |
| 87. [Auto Batching Info](#87)                    |      118. [Project Structure - Named Exports](#118)       |          149. [Actions and Default State](#149) |
| 88. [UseState Object Example - Complete](#88)    |       119. [Project Structure - Export Group](#119)       |                         150. [Reset List](#150) |
| 89. [UseState Set Function "Gotcha"](#89)        |         120. [Leverage Javascript - Intro](#120)          |                      151. [Remove Person](#151) |
| 90. [UseState Functional Update Form](#90)       |       121. [Leverage Javascript - Challenge](#121)        |                      152. [Import/Export](#152) |
| 91. [UseState - SetTimeout Example](#91)         |        122. [Leverage Javascript - Complete](#122)        |                  153. [Matching Projects](#153) |
| 92. [Matching Project](#92)                      |                123. [Forms - Setup](#123)                 |                154. [Performance - Intro](#154) |
| 93. [Code Example](#93)                          |              124. [Controlled Inputs](#124)               |               155. [Component Re-renders](#155) |
| 94. [UseEffect - Fundamentals](#94)              |            125. [User Challenge - Setup](#125)            |                    156. [React Dev Tools](#156) |
| 95. [UseEffect - Multiple Effects](#95)          |        126. [User Challenge - Add New User](#126)         |                        157. [Lower State](#157) |
| 96. [UseEffect Fetch Challenge - Intro](#96)     |         127. [User Challenge - Remove User](#127)         |            158. [Lower State - Challenge](#158) |
| 97. [UseEffect Fetch Challenge - Complete](#97)  |               128. [Multiple Inputs](#128)                |                       159. [React.memo()](#159) |
| 98. [UseEffect Clean Up Info](#98)               |                129. [Checkbox Input](#129)                |                       160. [Mind Grenade](#160) |
| 99. [Multiple Returns](#99)                      |                 130. [Select Input](#130)                 |                   161. [UseCallback Hook](#161) |
| 100. [Multiple Returns - Fetch Data Setup](#100) |                 131. [FormData API](#131)                 | 162. [UseCallback Hook - Common Use Case](#162) |
| 101. [Multiple Returns - Fetch Data](#101)       |              132. [Matching Projects](#132)               |                       163. [UseMemo Hook](#163) |
| 102. [Fetch Error "Gotcha"](#102)                |              133. [useRef - DOM Node](#133)               |                 164. [UseTransition Hook](#164) |
| 103. [Order Matters](#103)                       |           134. [useRef - Initial Render](#134)            |                     165. [React Suspense](#165) |
| 104. [Fetch Function Location](#104)             |              135. [Matching Projects](#135)               |
| 105. [React Hooks Rules](#105)                   |            136. [Custom Hooks - Toggle](#136)             |

---

<br>

---

### 75. Intro<a id="75"></a>

<br>

### 76. Github Repository<a id="76"></a>

<br>

### 77. Setup<a id="77"></a>

- In 03-Advanced-react run the cmd

```sh
npm install && npm run dev
```

- http://localhost:5173/

<br>

### 78. Overview<a id="78"></a>

- Preset, Dont need to change anything

- traditional Vite app
  - removed boilerplate
  - provided some assets (css, data)
    - just so we can focus on important stuff
  - removed <StrictMode>, so it's less logs

---

#### Advanced Topics

- src/tutorial/01-useState directory
- work in the starter folder
- complete code in the final folder
- in order to work on topic import component from 'starter' to src/App.jsx
- in order to test final import component from 'final' to src/App.jsx
- setup challenges
- in the beginning examples with numbers and buttons :):):)

- In src/App.jsx

```js
import Starter from "./tutorial/1-useState/starter/1-error-example";
import Final from "./tutorial/1-useState/final/1-error-example";

function App() {
  return (
    <div className="container">
      <Starter />
      <Final />
    </div>
  );
}

export default App;
```

<br>

### 79. Error Example<a id="79"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/01-error-example.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Setup Challenge for src/tutorial/01-useState/starter/01-error-example.jsx :

- create count variable
- display value in the JSX
- add button and increase the value
- the reason for bug - we don't trigger re-render (reference next lecture)

- In src/tutorial/01-useState/starter/01-error-example.jsx

```js
const ErrorExample = () => {
  let count = 0;

  const handleClick = () => {
    count = count + 1;
    console.log(count);
    // preserve value between renders
    // trigger re-render
  };
  return (
    <div>
      <h2>{count}</h2>
      <button type="button" className="btn" onClick={handleClick}>
        increment
      </button>
    </div>
  );
};

export default ErrorExample;
```

<br>

### 80. UseState Fundamentals<a id="80"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/02-useState-basics.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Setup Challenge for src/tutorial/01-useState/starter/02-useState-basics.jsx :

[Javascript Nuggets - Destructuring (Array)](https://www.youtube.com/watch?v=qhECs40xMec&list=PLnHJACx3NwAfRUcuKaYhZ6T5NRIpzgNGJ&index=7&t=9s)

- useState hook, which is function that react library provide
- returns an array with two elements: the current state value, and a function that we can use to update the state
- accepts default value as an argument
- state update triggers re-render

- In src/tutorial/01-useState/starter/02-useState-basics.jsx

```js
import { useState } from "react";

const UseStateBasics = () => {
  // console.log(useState());
  // console.log(useState('jo koy'));
  // const value = useState()[0];
  // const handler = useState()[1];
  // console.log(value, handler);

  // destructure array and set default value 0
  const [count, setCount] = useState(0);

  const handleClick = () => {
    // console.log(count)
    setCount(count + 1);
    // be careful, we can set any value
    // setCount('pants');
  };
  return (
    <div>
      <h4>You clicked {count} times</h4>
      <button className="btn" onClick={handleClick}>
        Click me
      </button>
    </div>
  );
};

export default UseStateBasics;
```

<br>

### 81. Initial Render and Re-renders<a id="81"></a>

In a React application, the initial render is the first time that the component tree is rendered to the DOM. It happens when the application first loads, or when the root component is first rendered. This is also known as "mounting" the components.

Re-renders, on the other hand, happen when the component's state or props change, and the component needs to be updated in the DOM to reflect these changes. React uses a virtual DOM to optimize the process of updating the actual DOM, so that only the necessary changes are made.

There are a few ways that you can trigger a re-render in a React component:

- By changing the component's state or props. When the component's state or props change, React will re-render the component to reflect these changes.

- When the parent element re-renders, even if the component's state or props have not changed.

<br>

### 82. General Rules of React Hooks<a id="82"></a>

- all hooks starts with "use" (both -react and custom hooks)
- to work with hooks, component must be uppercase
- invoke hooks inside function/component body
- don't call hooks conditionally (cover later), means dont call hooks inside if-else
- set functions don't update state immediately (cover later)

<br>

### 83. UseState Array Example - Setup<a id="83"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/03-useState-array.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Setup Challenge : 1. render the list

- import data
- setup a state value
  - people - default value equal to data
- display list(people) in the browser

- In src/tutorial/01-useState/starter/03-useState-array.jsx

```js
import React from "react";
import { data } from "../../../data";
const UseStateArray = () => {
  const [people, setPeople] = React.useState(data);

  return (
    <div>
      {people.map((person) => {
        const { id, name } = person;
        return (
          <div key={id} className="item">
            <h4>{name}</h4>
          </div>
        );
      })}
    </div>
  );
};

export default UseStateArray;
```

<br>

### 84. UseState Array Example - Complete<a id="84"></a>

2. remove items

- create two functions

  - one that removes single item from the list
  - one that clears entire list

[Javascript Nuggets - Filter and Find](https://www.youtube.com/watch?v=KeYxsev737s&list=PLnHJACx3NwAfRUcuKaYhZ6T5NRIpzgNGJ&index=4)

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/03-useState-array.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/01-useState/starter/03-useState-array.jsx

```js
import React from "react";
import { data } from "../../../data";
const UseStateArray = () => {
  const [people, setPeople] = React.useState(data);

  // ref callback function
  const removeItem = (id) => {
    // id does not match
    // return ture: only return match item i.e id
    // return false: return all items except unmatch one i.e id
    let newPeople = people.filter((person) => person.id !== id);
    setPeople(newPeople);
  };

  // empty array -old ref
  // const clearAllItems = () => {
  //   setPeople([]);
  // };

  return (
    <div>
      {people.map((person) => {
        const { id, name } = person;
        return (
          <div key={id} className="item">
            <h4>{name}</h4>
            <button onClick={() => removeItem(id)}>remove</button>
          </div>
        );
      })}

      <button
        className="btn"
        style={{ marginTop: "2rem" }}
        onClick={() => setPeople([])}
      >
        clear items
      </button>
    </div>
  );
};

export default UseStateArray;
```

<br>

### 85. UseState - Extra Info<a id="85"></a>

<br>

### 86. UseState Object Example - Setup<a id="86"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/04-useState-object.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Setup Challenge :

- setup three state values
  - name(string)
  - age(number)
  - hobby(string)
- render in the browser
- create a button
  - setup a function
    - update all three state values
- as a result once the user clicks the button,
  new person is displayed in the browser

<br>

- In src/tutorial/01-useState/starter/04-useState-object.jsx

```js
import { useState } from "react";

// 1. setup details
const UseStateObject = () => {
  const [name, setName] = useState("peter");
  const [age, setAge] = useState(24);
  const [hobby, setHobby] = useState("read books");

  // 3. setup callback function to change useState
  const displayPerson = () => {
    setName("john");
    setAge(28);
    setHobby("scream at the computer");
  };
  return (
    // 2. setup JSX display
    <>
      <h3>{name}</h3>
      <h3>{age}</h3>
      <h4>Enjoys To: {hobby}</h4>
      <button className="btn" onClick={displayPerson}>
        show john
      </button>
    </>
  );
};

export default UseStateObject;
```

<br>

### 87. Auto Batching Info<a id="87"></a>

In React, "batching" refers to the process of grouping multiple state updates into a single update. This can be useful in certain cases because it allows React to optimize the rendering of your components by minimizing the number of DOM updates that it has to perform.

By default, React uses a technique called "auto-batching" to group state updates that occur within the same event loop into a single update. This means that if you call the state update function multiple times in a short period of time, React will only perform a single re-render for all of the updates.

React 18 ensures that state updates invoked from any location will be batched by default. This will batch state updates, including native event handlers, asynchronous operations, timeouts, and intervals.

<br>

### 88. UseState Object Example - Complete<a id="88"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/04-useState-object.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/01-useState/starter/04-useState-object.jsx

```js
import { useState } from "react";

// 1. setup person default value as obj, using usestate
const UseStateObject = () => {
  const [person, setPerson] = useState({
    name: "peter",
    age: 24,
    hobby: "read books",
  });

  // 2. setup setPerson obj using useState
  const displayPerson = () => {
    setPerson({ name: "john", age: 28, hobby: "scream at the computer" });
    // be careful, don't overwrite
    // setPerson('shakeAndBake');
    // setPerson({ name: 'susan' });
    // setPerson({ ...person, name: 'susan' });   // only change name, and dont touch age, hobby
  };

  return (
    // 3. modigy jsx to access property -without destructure
    <>
      <h3>{person.name}</h3>
      <h3>{person.age}</h3>
      <h4>Enjoys To: {person.hobby}</h4>
      <button className="btn" onClick={displayPerson}>
        show john
      </button>
    </>
  );
};

export default UseStateObject;
```

<br>

### 89. UseState Set Function "Gotcha"<a id="89"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/05-useState-gotcha.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Setup Challenge :

- setup a state value and the button
- add functionality to increase value by 1
- log a state value, right after setFunction

Keep in mind that the state update function setState does not immediately mutate the state. Instead, it schedules an update to the state and tells React that it needs to re-render the component. The actual state update will be performed as part of the next rendering cycle. Be mindful when you need to set state value based on a different state value.

trivial example

- In src/tutorial/01-useState/starter/05-useState-gotcha.jsx

```js
import { useState } from "react";

const UseStateGotcha = () => {
  const [value, setValue] = useState(0);

  const handleClick = () => {
    setValue(value + 1);
    //  be careful it's the old value
    console.log(value);
    //  so if you have any functionality
    // that relies on the latest value
    // it will be wrong !!!
  };
  return (
    <div>
      <h1>{value}</h1>
      <button className="btn" onClick={handleClick}>
        increase
      </button>
    </div>
  );
};

export default UseStateGotcha;
```

<br>

### 90. UseState Functional Update Form<a id="90"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/05-useState-gotcha.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/01-useState/starter/05-useState-gotcha.jsx

```js
import { useState } from "react";

const UseStateGotcha = () => {
  const [value, setValue] = useState(0);

  const handleClick = () => {
    setValue((currentState) => {
      const newState = currentState + 1;
      return newState;
    });

    console.log(value);
  };
  return (
    <div>
      <h1>{value}</h1>
      <button className="btn" onClick={handleClick}>
        increase
      </button>
    </div>
  );
};

export default UseStateGotcha;
```

<br>

### 91. UseState - SetTimeout Example<a id="91"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/01-useState/starter/05-useState-gotcha.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/01-useState/starter/05-useState-gotcha.jsx

```js
import { useState } from "react";

const UseStateGotcha = () => {
  const [value, setValue] = useState(0);

  const handleClick = () => {
    // setTimeout(() => {
    // console.log('clicked the button');
    //   setValue(value + 1);
    // }, 3000);
    setTimeout(() => {
      console.log("clicked the button");
      setValue((currentState) => {
        return currentState + 1;
      });
    }, 3000);
  };

  return (
    <div>
      <h1>{value}</h1>
      <button className="btn" onClick={handleClick}>
        increase
      </button>
    </div>
  );
};

export default UseStateGotcha;
```

<br>

### 92. Matching Project<a id="92"></a>

<br>

### 93. Code Example<a id="93"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/02-useEffect/starter/01-code-example.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/02-useEffect/starter/01-code-example.jsx

```js
import { useState } from "react";

const ComponentExample = () => {
  const [value, setValue] = useState(0);

  const sayHello = () => {
    console.log("hello there");
    // be careful
    // setValue(value + 1);
  };

  sayHello();
  return (
    <div>
      <h1>value : {value}</h1>
      <button className="btn" onClick={() => setValue(value + 1)}>
        click me
      </button>
    </div>
  );
};
export default ComponentExample;
```

---

- the problem starts when we update the state

```js
import { useState } from "react";

const ComponentExample = () => {
  const [value, setValue] = useState(0);

  const sayHello = () => {
    console.log("hello there");
    // be careful, you will have infinite loop
    setValue(value + 1);
  };

  sayHello();

  return (
    <div>
      <h1>value : {value}</h1>
      <button className="btn" onClick={() => setValue(value + 1)}>
        click me
      </button>
    </div>
  );
};
export default ComponentExample;
```

- initial render - setup state value and invoke sayHello
- in the sayHello update state, trigger re-render

- re-render - setup state value and invoke sayHello
- in the sayHello update state, trigger re-render

- repeat
- repeat
- repeat
  ..................................................

- but what about fetching data?

<br>

### 94. UseEffect - Fundamentals<a id="94"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/02-useEffect/starter/02-useEffect-basics.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

useEffect is a hook in React that allows you to perform side effects in function components.There is no need for urban dictionary - basically any work outside of the component. Some examples of side effects are: subscriptions, fetching data, directly updating the DOM, event listeners, timers, etc.

- useEffect hook
- accepts two arguments (second optional)
- first argument - cb function
- second argument - dependency array
- by default runs on each render (initial and re-render)
- cb can't return promise (so can't make it async)
- if dependency array empty [] runs only on initial render

- In src/tutorial/02-useEffect/starter/02-useEffect-basics.jsx

```js
import { useState, useEffect } from "react";

const UseEffectBasics = () => {
  const [value, setValue] = useState(0);
  const sayHello = () => {
    console.log("hello there");
  };

  sayHello();

  // useEffect(() => {
  //   console.log('hello from useEffect');
  // });

  // only going to run once, wont create infinity loop
  useEffect(() => {
    console.log("hello from useEffect");
  }, []);

  return (
    <div>
      <h1>value : {value}</h1>
      <button className="btn" onClick={() => setValue(value + 1)}>
        click me
      </button>
    </div>
  );
};
export default UseEffectBasics;
```

<br>

### 95. UseEffect - Multiple Effects<a id="95"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/02-useEffect/starter/03-multiple-effects.jsx";
function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/02-useEffect/starter/03-multiple-effects.jsx

```js
import { useState, useEffect } from "react";

const MultipleEffects = () => {
  const [value, setValue] = useState(0);
  const [secondValue, setSecondValue] = useState(0);

  useEffect(() => {
    console.log("hello from first useEffect");
  }, [value]);

  useEffect(() => {
    console.log("hello from second useEffect");
  }, [secondValue]);

  return (
    <div>
      <h1>value : {value}</h1>
      <button className="btn" onClick={() => setValue(value + 1)}>
        value
      </button>
      <h1>second value : {secondValue}</h1>
      <button className="btn" onClick={() => setSecondValue(secondValue + 1)}>
        second value
      </button>
    </div>
  );
};
export default MultipleEffects;
```

<br>

### 96. UseEffect Fetch Challenge - Intro<a id="96"></a>

[Javascript Nuggets - Fetch API](https://www.youtube.com/watch?v=C_VIKzfpRrg&list=PLnHJACx3NwAfRUcuKaYhZ6T5NRIpzgNGJ&index=18&t=343s)

- later in the course we will use axios

Setup Challenge :

- import useState and useEffect
- setup state value
  - users - default value []
- setup useEffect
- MAKE SURE IT RUNS ONLY ON INITIAL RENDER
- in the cb, create a function which performs fetch functionality
  - use url I provided in the starter file
  - you can use .then or async
  - set users equal to result
  - iterate over the list and display image, user name and link
- DON'T WORRY ABOUT CSS, MOST IMPORTANT LOGIC !!!

<br>

### 97. UseEffect Fetch Challenge - Complete<a id="97"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/02-useEffect/starter/04-fetch-data.jsx";
function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/02-useEffect/starter/04-fetch-data.jsx

```js
import { useState, useEffect } from "react";

const url = "https://api.github.com/users";

const FetchData = () => {
  const [users, setUsers] = useState([]);

  // run only once when component load
  useEffect(() => {
    // you can also setup function outside
    const fetchData = async () => {
      try {
        const response = await fetch(url);
        const users = await response.json();
        setUsers(users);
      } catch (error) {
        console.log(error);
      }
    };
    fetchData();
  }, []);

  // writing jsx part
  return (
    <section>
      <h3>github users</h3>
      <ul className="users">
        {users.map((user) => {
          const { id, login, avatar_url, html_url } = user;
          return (
            <li key={id}>
              <img src={avatar_url} alt={login} />
              <div>
                <h5>{login}</h5>
                <a href={html_url}>profile</a>
              </div>
            </li>
          );
        })}
      </ul>
    </section>
  );
};
export default FetchData;
```

<br>

### 98. UseEffect Clean Up Info<a id="98"></a>

<br>

### 99. Multiple Returns<a id="99"></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/03-conditional-rendering/starter/01-multiple-returns-basics.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Vanilla JS

```js
const sayHello = (name) => {
  // cond: if user provide the name, then
  if (name) {
    return `Hello, ${name}`;
    // exit the function, skip rest of the code
  }

  // so if name provided, won't get to this line
  return "Hello, there";
};

const firstResp = sayHello("john");
console.log(firstResp); // Hello, john
const secondResp = sayHello();
console.log(secondResp); // Hello, there
```

---

- In src/tutorial/03-conditional-rendering/starter/01-multiple-returns-basics.jsx
- if no explicit return by default function returns 'undefined'

```js
import { useEffect, useState } from "react";

const MultipleReturnsBasics = () => {
  // while fetching data
  // convention with boolean values "isSomething"
  const [isLoading, setIsLoading] = useState(true);

  // run only once when component load
  useEffect(() => {
    setTimeout(() => {
      // done fetching data
      setIsLoading(false);
    }, 3000);
  }, []);

  // can return entire app
  if (isLoading) {
    return <h2>Loading...</h2>;
  }

  return <h2>My App</h2>;
};
export default MultipleReturnsBasics;
```

<br>

### 100. Multiple Returns - Fetch Data Setup, Part 1<a id='100'></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/03-conditional-rendering/starter/02-multiple-returns-fetch-data.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Setup Challenge :

- practice on setting up state values and data fetching
- create state variable
  - user - default value null
- fetch data from the url (for now just log result)
- if you see user object in the console, continue with the videos

- In src/tutorial/03-conditional-rendering/starter/02-multiple-returns-fetch-data.jsx"

```js
import { useEffect, useState } from "react";
const url = "https://api.github.com/users/QuincyLarson";

const MultipleReturnsFetchData = () => {
  const [user, setUser] = useState(null);

  // run only once when component load
  useEffect(() => {
    const fetchUser = async () => {
      try {
        const resp = await fetch(url);
        const user = await resp.json();
        console.log(user);
      } catch (error) {
        // fetch only cares about network errors
        // will work with axios
        console.log(error);
      }
    };
    fetchUser();
  }, []);

  return <h2>Fetch Example</h2>;
};
export default MultipleReturnsFetchData;
```

<br>

### 101. Multiple Returns - Fetch Data, Part 2<a id='101'></a>

Data Fetching :

- usually three options

  - loading - waiting for data to arrive (display loading state)
  - error - there was an error (display error message)
  - success - received data (display data)

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/03-conditional-rendering/starter/02-multiple-returns-fetch-data.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/03-conditional-rendering/starter/02-multiple-returns-fetch-data.jsx"

```js
import { useEffect, useState } from "react";
const url = "https://api.github.com/users/QuincyLarson";

const MultipleReturnsFetchData = () => {
  // convention to setup booleans with isSomething
  const [isLoading, setIsLoading] = useState(true);
  const [isError, setIsError] = useState(false);
  const [user, setUser] = useState(null);

  useEffect(() => {
    const fetchUser = async () => {
      try {
        const resp = await fetch(url);
        const user = await resp.json();
        // console.log(user);
        setUser(user);
      } catch (error) {
        setIsError(true);
        console.log(error);
      }
      // hide loading
      setIsLoading(false);
    };
    fetchUser();
  }, []);

  // order matters
  // don't place user JSX before loading or error
  if (isLoading) {
    return <h2>Loading...</h2>;
  }

  if (isError) {
    return <h2>There was an error...</h2>;
  }

  return (
    <div>
      <img
        style={{ width: "150px", borderRadius: "25px" }}
        src={user.avatar_url}
        alt={user.name}
      />
      <h2>{user.name}</h2>
      <h4>works at {user.company}</h4>
      <p>{user.bio}</p>
    </div>
  );
};

export default MultipleReturnsFetchData;
```

<br>

### 102. Fetch Error "Gotcha" (Optional) <a id='102'></a>

Unlike for example Axios, by default, the fetch() API does not consider HTTP status codes in the 4xx or 5xx range to be errors. Instead, it considers these status codes to be indicative of a successful request,

```js
try {
const resp = await fetch(url);
// console.log(resp);

if (!resp.ok) {
  setIsError(true);
  setIsLoading(false);
  return;
}

const user = await resp.json();
setUser(user);

}

```

<br>

### 103. Order Matters<a id='103'></a>

- In src/tutorial/03-conditional-rendering/starter/02-multiple-returns-fetch-data.jsx"

```js
import Starter from "./tutorial/03-conditional-rendering/starter/02-multiple-returns-fetch-data.jsx";
```

Please don't dismiss this topic. A lot of questions in course Q&A.

Challenge :

- destructure properties and remove user from JSX
- you might or might not encounter the bug

```js
return (
  <div>
    <img
      style={{ width: "100px", borderRadius: "25px" }}
      src={avatar_url}
      alt={name}
    />
    <h2>{name}</h2>
    <h4>works at {company}</h4>
    <p>{bio}</p>
  </div>
);
```

---

Please don't dismiss this topic. A lot of questions in course Q&A.

Challenge :

- destructure properties and remove user from JSX
- you might or might not encounter the bug

```js
import { useEffect, useState } from "react";
import Starter from "./tutorial/03-conditional-rendering/starter/02-multiple-returns-fetch-data.jsx";

const url = "https://api.github.com/users/QuincyLarson";

const MultipleReturnsFetchData = () => {
  const [isLoading, setIsLoading] = useState(true);
  const [isError, setIsError] = useState(false);
  const [user, setUser] = useState(null);

  useEffect(() => {
    const fetchUser = async () => {
      try {
        const resp = await fetch(url);
        // console.log(resp);
        if (!resp.ok) {
          setIsError(true);
          setIsLoading(false);
          return;
        }

        const user = await resp.json();
        setUser(user);
      } catch (error) {
        setIsError(true);
        // console.log(error);
      }
      // hide loading
      setIsLoading(false);
    };
    fetchUser();
  }, []);

  // order matters
  // don't place user JSX before loading or error

  if (isLoading) {
    return <h2>Loading...</h2>;
  }
  if (isError) {
    return <h2>There was an error...</h2>;
  }

  // destructuring user data received from Network
  const { avatar_url, name, company, bio } = user;
  return (
    <div>
      <img
        style={{ width: "150px", borderRadius: "25px" }}
        src={avatar_url}
        alt={name}
      />
      <h2>{name}</h2>
      <h4>works at {company}</h4>
      <p>{bio}</p>
    </div>
  );
};
export default MultipleReturnsFetchData;
```

---

##### Order Matters - Solution

- before returns from Network

```js
const [user, setUser] = useState(null);
console.log(user); // still null
// we can't pull out properties from null
const { avatar_url, name, company, bio } = user;
```

- after returns from Network

```js
console.log(user); // user object;
const { avatar_url, name, company, bio } = user;
```

```js
return (
  <div>
    <img
      style={{ width: "100px", borderRadius: "25px" }}
      src={avatar_url}
      alt={name}
    />
    <h2>{name}</h2>
    <h4>works at {company}</h4>
    <p>{bio}</p>
  </div>
);
```

---

Vanilla JS

```js
const someObject = {
  name: "jo koy",
};
// this is cool
someObject.name; // returns 'jo koy'
someObject.propertyThatDoesNotExist; // returns undefined

// not cool at all, javascript will scream, yell and complain
const randomValue = null;
randomValue.name;

// this is ok
const randomList = [];
console.log(randomList[0]); // returns undefined

// not cool at all, javascript will scream, yell and complain
console.log(randomList[0].name);
```

<br>

### 104. Fetch Function Location<a id='104'></a>

- The question is can we place or define fetchData async function outside the useEffect
- Yes we can but we shouldn't do, becuse if place outside then we have to place fetchData in dependeny array [fetchData] in 2nd args, that will trigger infinity loop

```js
const fetchData = async () => {
  // fetch data
};

useEffect(() => {
  fetchData();
}, []);
```

- DON'T ADD fetchData to dependency array !!!
- IT WILL TRIGGER INFINITE LOOP !!!

<br>

### 105. React Hooks Rules<a id='105'></a>

- In src/App.jsx setup import and container div

```js
import Starter from "./tutorial/03-conditional-rendering/starter/03-hooks-rule.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/03-conditional-rendering/starter/03-hooks-rule.jsx"

```js
import { useState, useEffect } from "react";

const Example = () => {
  const [condition, setCondition] = useState(true);
  if (condition) {
    // won't work
    const [state, setState] = useState(false);
  }

  if (condition) {
    return <h2>Hello There</h2>;
  }

  // this will also fail, useState after if condition
  useEffect(() => {
    console.log("hello there");
  }, []);
  return <h2>example</h2>;
};

export default Example;
```

<br>

### 106. Vanilla.js (Optional)<a id='106'></a>

Vanilla JS

In JavaScript, a value is considered "truthy" if the condition is evaluated to true when used in a boolean context. A value is considered "falsy" if the condition is evaluated to false when used in a boolean context.

##### Here is a list of values that are considered falsy in JavaScript:

- false
- 0 (zero)
- "" (empty string)
- null
- undefined
- NaN (Not a Number)

##### All other values, including objects and arrays, are considered truthy.

For example:

```js
const x = "Hello";
const y = "";
const z = 0;

if (x) {
  console.log("x is truthy");
}

if (y) {
  console.log("y is truthy");
} else {
  console.log("y is falsy");
}

if (z) {
  console.log("z is truthy");
} else {
  console.log("z is falsy");
}

// Output:
// "x is truthy"
// "y is falsy"
// "z is falsy"
```

In this example, the variable x is a non-empty string, which is considered truthy, so the first if statement is executed. The variable y is an empty string, which is considered falsy, so the else block of the second if statement is executed. The variable z is the number 0, which is considered falsy, so the else block of the third if statement is executed.

---

Vanilla JS

In JavaScript, short-circuit evaluation is a technique that allows you to use logical operators (such as && and ||) to perform conditional evaluations in a concise way.

The && operator (logical AND) returns the first operand if it is "falsy", or the second operand if the first operand is "truthy".

For example:

```js
const x = 0;
const y = 1;

console.log(x && y); // Output: 0 (the first operand is falsy, so it is returned)
console.log(y && x); // Output: 0 (the second operand is falsy, so it is returned)
```

The || operator (logical OR) returns the first operand if it is "truthy", or the second operand if the first operand is "falsy".

For example:

```js
const x = 0;
const y = 1;

console.log(x || y); // Output: 1 (the first operand is falsy, so the second operand is returned)
console.log(y || x); // Output: 1 (the first operand is truthy, so it is returned)
```

Short-circuit evaluation can be useful in cases where you want to perform a certain action only if a certain condition is met, or you want to return a default value if a certain condition is not met.

For example:

```js
function displayName(name) {
  return name || "Anonymous";
}

console.log(displayName("Pizza")); // Output: "Pizza"
console.log(displayName()); // Output: "Anonymous"
```

In this example, the displayName() function returns the name property of the user object if it exists, or "Anonymous" if the name property is not present. This is done using the || operator and short-circuit evaluation.

<br>

### 107. Short Circuit - Overview<a id='107'></a>

- In src/App.jsx

```js
import Starter from "./tutorial/03-conditional-rendering/starter/04-short-circuit-overview.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/03-conditional-rendering/starter/04-short-circuit-overview.jsx"

Setup Challenge :

- create two state values
- one "falsy" and second "truthy"
- setup both conditions for each operator in JSX - hint {}
  - || OR
  - && AND

```js
import { useState } from "react";

const ShortCircuitOverview = () => {
  // falsy
  const [text, setText] = useState("");
  // truthy
  const [name, setName] = useState("susan");

  const codeExample = text || "hello world";

  // can't use if statements
  return (
    <div>
      {/* {if(someCondition){"won't work"}} */}

      <h4>Falsy OR : {text || "hello world"}</h4>
      <h4>Falsy AND {text && "hello world"}</h4>
      <h4>Truthy OR {name || "hello world"}</h4>
      <h4>Truthy AND {name && "hello world"}</h4>
      {codeExample}
    </div>
  );
};
export default ShortCircuitOverview;
```

<br>

### 108. Short Circuit - Examples<a id='108'></a>

- In src/App.jsx

```js
import Starter from "./tutorial/03-conditional-rendering/starter/05-short-circuit-examples.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Vanilla JS (Optional)
The ! operator is a logical operator in JavaScript that negates a boolean value. It is equivalent to the not operator in other programming languages.

For example:

```js
let isTrue = true;
let isFalse = false;

console.log(!isTrue); // outputs: false
console.log(!isFalse); // outputs: true
```

You can use the ! operator to test if a value is not truthy or falsy:

```js
let val = 0;
if (!val) {
  console.log("val is falsy");
}
```

You can also use the ! operator to convert a value to a boolean and negate it:

```js
let val = "hello";
let bool = !val; // bool is now false

val = "";
bool = !val; // bool is now true
```

---

- In src/tutorial/03-conditional-rendering/starter/05-short-circuit-examples.jsx"

```js
import { useState } from "react";

const ShortCircuitOverview = () => {
  // falsy
  const [text, setText] = useState("");
  // truthy
  const [name, setName] = useState("susan");
  const [user, setUser] = useState({ name: "john" });
  const [isEditing, setIsEditing] = useState(false);

  // can't use if statements
  // Usage on how to render value based on truthy and false value
  return (
    <div>
      <h2>{text || "default value"}</h2>

      {text && (
        <div>
          <h2> whatever return</h2>
          <h2>{name}</h2>
        </div>
      )}

      {/* NOT operator  */}
      {!text && (
        <div>
          <h2> whatever return</h2>
          <h2>{name}</h2>
        </div>
      )}

      {user && <SomeComponent name={user.name} />}

      <h2 style={{ margin: "1rem 0" }}>Ternary Operator</h2>

      <button className="btn">{isEditing ? "edit" : "add"}</button>

      {user ? (
        <div>
          <h4>hello there user {user.name}</h4>
        </div>
      ) : (
        <div>
          <h2>please login</h2>
        </div>
      )}
    </div>
  );
};

const SomeComponent = ({ name }) => {
  return (
    <div>
      <h4>hello there, {name}</h4>
      <button className="btn">log out</button>
    </div>
  );
};

export default ShortCircuitEvaluation;
```

<br>

### 109. Ternary Operator<a id='109'></a>

Vanilla JS

In JavaScript, the ternary operator is a way to concisely express a simple conditional statement. It is often called the "conditional operator" or the "ternary conditional operator".

Here is the basic syntax for using the ternary operator:

```js
condition ? expression1 : expression2;
```

If condition is truthy, the operator will return expression1. If condition is falsy, it will return expression2.

Jobster Example

[Jobster ](https://redux-toolkit-jobster.netlify.app/landing)

<br>

### 110. Toggle Challenge<a id='110'></a>

- In src/App.jsx

```js
import Starter from "./tutorial/03-conditional-rendering/starter/06-toggle-challenge.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/03-conditional-rendering/starter/06-toggle-challenge.jsx"

- create state value (boolean)
- return a button and a component/element
- when user clicks the button
  - toggle state value
  - conditionally render component/element

Initial Setup

```js
import { useState } from "react";

const ToggleChallenge = () => {
  const [showAlert, setShowAlert] = useState(false);

  const toggleAlert = () => {
    if (showAlert) {
      setShowAlert(false);
      return;
    }
    setShowAlert(true);
  };

  return (
    <div>
      <button className="btn" onClick={toggleAlert}>
        toggle alert
      </button>
      {showAlert && <Alert />}
    </div>
  );
};

const Alert = () => {
  return <div className="alert alert-danger">hello world</div>;
};
export default ToggleChallenge;
```

---

- Improvements in one line

```js
<button className='btn' onClick={() => setShowAlert(!showAlert)}>
```

<br>

### 111. User Challenge<a id='111'></a>

- In src/App.jsx

```js
import Starter from "./tutorial/03-conditional-rendering/starter/07-user-challenge.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In src/tutorial/03-conditional-rendering/starter/07-user-challenge.jsx"

- create state value
  - user - default value null
- create two functions
  - login - set's user equal to object with name property
  - logout - set's user equal to null
- in jsx use ? to display two different setups

- h4 with "hello there, user name" and logout button
- h4 with "please login " and login button

```js
import { useState } from "react";

const UserChallenge = () => {
  const [user, setUser] = useState(null);

  const login = () => {
    // normally connect to db or api
    setUser({ name: "vegan food truck" });
  };
  const logout = () => {
    setUser(null);
  };

  return (
    <div>
      {user ? (
        <div>
          <h4>hello there, {user.name}</h4>
          <button className="btn" onClick={logout}>
            logout
          </button>
        </div>
      ) : (
        <div>
          <h4>Please Login</h4>
          <button className="btn" onClick={login}>
            login
          </button>
        </div>
      )}
    </div>
  );
};

export default UserChallenge;
```

<br>

### 112. UseEffect Cleanup Function - Setup/Challenge<a id='112'></a>

- In src/App.jsx

```js
import Starter from "./tutorial/02-useEffect/starter/05-cleanup-function.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In ./tutorial/02-useEffect/starter/05-cleanup-function.jsx"

Will Cover After 03-conditional-rendering

- Setup Challenge :

- create state value
- in jsx return button which toggles state value
- based on condition return second component (simple return)
- inside second component create useEffect and run it only on initial render

```js
import { useEffect, useState } from "react";

const CleanupFunction = () => {
  const [toggle, setToggle] = useState(false);

  return (
    <div>
      <button className="btn" onClick={() => setToggle(!toggle)}>
        toggle component
      </button>

      {toggle && <RandomComponent />}
    </div>
  );
};

const RandomComponent = () => {
  useEffect(() => {
    console.log("hmm, this is interesting");
  }, []);
  return <h1>hello there</h1>;
};

export default CleanupFunction;
```

- Notes: everytime we toggle button the RandomComponent will mount and unmount, that cause initial render to run again and again.
- The re-render is not working here, thats why usage of useEffect that run only once in this setup make no sense

<br>

### 113. UseEffect - Timer Example<a id='113'></a>

Vanilla JS

```js
const intID = setInterval(() => {
  console.log("hello from interval");
}, 1000);
clearInterval(intID);
```

- In src/App.jsx

```js
import Starter from "./tutorial/02-useEffect/starter/05-cleanup-function.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In ./tutorial/02-useEffect/starter/05-cleanup-function.jsx"

```js
import { useEffect, useState } from "react";

const CleanupFunction = () => {
  const [toggle, setToggle] = useState(false);
  return (
    <div>
      <button className="btn" onClick={() => setToggle(!toggle)}>
        toggle component
      </button>
      {toggle && <RandomComponent />}
    </div>
  );
};

const RandomComponent = () => {
  useEffect(() => {
    // console.log('hmm, this is interesting');
    const intID = setInterval(() => {
      console.log("hello from interval");
    }, 1000);

    // does not stop, keeps going
    // every time we render component new interval gets created

    // how to use cleanup function to clean background interval
    return () => clearInterval(intID);
  }, []);

  return <h1>hello there</h1>;
};

export default CleanupFunction;
```

<br>

### 114. UseEffect - Event Listeners Example<a id='114'></a>

```js
const someFunc = () => {
  // some logic here
};
window.addEventListener("scroll", someFunc);
window.removeEventListener("scroll", someFunc);
```

---

- In src/App.jsx

```js
import Starter from "./tutorial/02-useEffect/starter/05-cleanup-function.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In ./tutorial/02-useEffect/starter/05-cleanup-function.jsx"

```js
import { useEffect, useState } from "react";

const CleanupFunction = () => {
  const [toggle, setToggle] = useState(false);
  return (
    <div>
      <button className="btn" onClick={() => setToggle(!toggle)}>
        toggle component
      </button>
      {toggle && <RandomComponent />}
    </div>
  );
};

const RandomComponent = () => {
  useEffect(() => {
    // console.log('hmm, this is interesting');
    const someFunc = () => {
      // some logic here
    };
    window.addEventListener("scroll", someFunc);

    // how to use cleanup function to clean background scroll
    return () => window.removeEventListener("scroll", someFunc);
  }, []);

  return <h1>hello there</h1>;
};

export default CleanupFunction;
```

<br>

### 115. You Might Not Need an Effect<a id='115'></a>

[You Might Not Need an Effect](https://beta.reactjs.org/learn/you-might-not-need-an-effect)

- will still utilize useEffect
- there is still plenty of code using useEffect

- fetching data
  replaced by libraries - react query, rtk query, swr or next.js

```js
import { useHook } from "library";

function Example() {
  const { data, error, isLoading } = useHook("url", fetcher);

  if (error) return <div>failed to load</div>;
  if (isLoading) return <div>loading...</div>;
  return <div>hello {data.name}!</div>;
}
```

- rest of them by refactoring code

<br>

### 116. Matching Projects<a id='116'></a>

<br>

### 117. Project Structure - Folder Example<a id='117'></a>

- In ./tutorial/04-project-structure/starter

There are more options to setup project

Normally somewhere in the src, we mostly do like this

/components/componentName.jsx
/screens/componentName.jsx

---

> 1 way to setup project when having few components/files

- create navbar folder inside it create following files

  - create Navbar.jsx (component) -rfca
  - create Navbar.css (styles)

```js
import "./Navbar.css";
const Navbar = () => {
  return (
    <div className="navbar">
      <h2>navbar component</h2>
    </div>
  );
};
export default Navbar;
```

```css
.navbar {
  background: blue;
  color: white;
}
```

---

- In src/App.jsx, import Navbar

```js
import Navbar from "./tutorial/04-project-structure/starter/Navbar";

function App() {
  return (
    <div className="container">
      <h2>Advanced React</h2>
    </div>
  );
}

export default App;
```

---

- create index.jsx(entry point) to avoid "import Final from 'pathToFolder/**Navbar/Navbar**" this problem

```js
export { default } from "./Navbar";
```

<br>

### 118. Project Structure - Named Exports<a id='118'></a>

> 2 Way of setting up project, when having alot of components/files

- In /tutorial/04-project-structure/starter

- only makes sense if you have quite a few files

- In starter folder create Pages subfolder

- Create and setup two components Home.jsx and About.jsx -rfca

```js
const Home = () => {
  return <div>Home Page</div>;
};
export default Home;
```

```js
const About = () => {
  return <div>About Page</div>;
};
export default About;
```

- create index.jsx, import both and export them

```js
import Home from "./Home";
import About from "./About";

export { Home, About };
```

---

- In the src/App.jxs, import component

```js
// import {Home, About} from 'pathToFolder/Pages
import { Home, About } from " /tutorial/04-project-structure/starter/Pages";

function App() {
  return (
    <div className="container">
      <Home />
      <About />
    </div>
  );
}

export default App;
```

<br>

### 119. Project Structure - Export Group<a id='119'></a>

> 3 Way of setting up project, when having specific use case

- In ./tutorial/04-project-structure/starter

- create Example folder
- setup two components FirstComponent.jsx, SecondComponent.jsx (setup simple returns) and index.jsx file
- FirstComponent.jsx

```js
const FirstComponent = () => {
  return <div>FirstComponent</div>;
};
export default FirstComponent;
```

- SecondComponent.jsx

```js
const SecondComponent = () => {
  return <div>SecondComponent</div>;
};
export default SecondComponent;
```

- index.jsx, setup return and render both components (import)

```js
import FirstComponent from "./FirstComponent";
import SecondComponent from "./SecondComponent";

const Example = () => {
  return (
    <div>
      <FirstComponent />
      <SecondComponent />
    </div>
  );
};
export default Example;
```

---

- In src/App.jsx, import/render index.jsx

```js
import Example from "./tutorial/04-project-structure/Example";
function App() {
  return (
    <div className="container">
      <Example />
    </div>
  );
}

export default App;
```

##### Project Structure - Extra Extensions

- code spell checker - works well with code and documents.
- glean - easy extract JSX into a new component

<br>

### 120. Leverage Javascript - Intro<a id='120'></a>

[Javascript Nuggets -Optional Chaining](https://www.youtube.com/watch?v=PuEGrylM1x8&list=PLnHJACx3NwAfRUcuKaYhZ6T5NRIpzgNGJ&index=12&t=254s)

- In ./tutorial/05-leverage-javascript/starter

Setup Challenge

- take a look at the people in array in data.js
- create List.jsx component
- in List.jsx import and iterate over people (data)
- for now just render name
- once you have list setup separate Person.jsx component
  - try glean extension
- in Person render
  - name, nickName, image

Yes, there will be a bug.

<br>

### 121. Leverage Javascript - Challenge<a id='121'></a>

1. In starter folder create List.jsx

```js
// coming from section03 src/data
import { people } from "../../../data";

const List = () => {
  return (
    <div>
      {people.map((person) => {
        return <div>{person.name}</div>;
      })}
    </div>
  );
};
export default List;
```

- modify with key

```js
// coming from section03 src/data
import { people } from "../../../data";

const List = () => {
  return (
    <div>
      {people.map((person) => {
        return <div key={person.id}>{person.name}</div>;
      })}
    </div>
  );
};
export default List;
```

---

- In src/App.jsx, import/render List component

```js
import Example from "./tutorial/05-leverage-javascript/starter/List";
function App() {
  return (
    <div className="container">
      <List />
    </div>
  );
}

export default App;
```

---

- after using glean extension extract Person.jsx component from List.jsx

```js
import { people } from "../../../data";
import Person from "./Person";

const List = () => {
  return (
    <div>
      {people.map((person) => {
        return <Person key={person.name} {...person} />;
      })}
    </div>
  );
};
export default List;
```

- Person.jsx, the template,
- NOTE THIS CODE WILL CREATE ERROR, because image does not exist in the first instance

```js
import React from "react";

export function Person({ name, nickName = "shakeAndBake", images }) {

// img is not in the first instance in array
  const img = images.[0].small.url;

  return (
    <div>
      <img src={img} alt={name} style={{ width: "50px" }} />
      <h4>{name} </h4>
      <p>Nickname : {nickName}</p>
    </div>
  );
}
```

<br>

### 122. Leverage Javascript - Complete<a id='122'></a>

##### Default Values - Vanilla JS (Optional)

In JavaScript, when defining a function, you can specify default values for its parameters. This means that if a caller of the function does not provide a value for a particular parameter, the default value will be used instead. Default parameters are defined by assigning a value to the parameter in the function definition.

For example, consider the following function, which takes two parameters, x and y, and returns their sum:

```js
function add(x, y) {
  return x + y;
}
```

If we call this function with only one argument, it will return NaN because y is undefined.

We can set default values for x,y as:

```js
function add(x = 0, y = 0) {
  return x + y;
}
```

Now, if we call add(3), the function will return 3, because the default value of 0 is used for the y parameter.

---

##### Optional Chaining - Vanilla JS (Optional)

n JavaScript, the optional chaining operator (?.) is a new feature that allows you to access properties of an object without worrying about whether the object or the property is null or undefined. It's a shorthand for a common pattern of checking for null or undefined before accessing an object's property.

For example, consider the following code, which accesses the firstName property of an object:

```js
const person = { name: { first: "John", last: "Doe" } };
console.log(person.name.first);
```

If the name property is null or undefined, this code will throw an error. To prevent this, we can use the optional chaining operator:

```js
console.log(person?.name?.first);
```

Now, if the person.name is null or undefined, this code will simply return undefined instead of throwing an error. This make the code more robust and readable.

---

- Person.jsx, the template
- NOTE: the images coming from data structure is nested

```js
import React from "react";
// coming from asset 03section
import avatar from "../../../assets/default-avatar.svg";

export function Person({ name, nickName = "shakeAndBake", images }) {
  // before optional chaining

  // if images exist get me the first one, if first one exist get me the small property, if small property exist get me the url
  // const img =
  //   (images && images[0] && images[0].small && images[0].small.url) || avatar;

  // ref. doing same functionality
  // Combining with the nullish coalescing operator ??
  // const img = images?.[0]?.small?.url ?? avatar;
  // ?? vs || - please utilize the search engine

  // if images exist get me the first one, if that exist get me small, if that exist get me the url
  // or we can say: check for images, check for firs one, check for small, check for url
  // if images not exist then show the default avatar
  const img = images?.[0]?.small?.url || avatar;

  return (
    <div>
      <img src={img} alt={name} style={{ width: "50px" }} />
      <h4>{name} </h4>
      <p>Nickname : {nickName}</p>
    </div>
  );
}
```

<br>

### 123. Forms - Setup<a id='123'></a>

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/06-forms/starter/01-controlled-inputs.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

Setup (for all form videos)

- In /tutorial/06-forms/starter/01-controlled-inputs.jsx

```js
const ControlledInputs = () => {
  return (
    <form className="form">
      <h4>controlled inputs</h4>
      <div className="form-row">
        {/* htmlFor & id property should match */}
        <label htmlFor="name" className="form-label">
          name
        </label>
        <input type="text" className="form-input" id="name" />
      </div>

      <div className="form-row">
        <label htmlFor="email" className="form-label">
          Email
        </label>
        <input type="email" className="form-input" id="email" />
      </div>

      <button type="submit" className="btn btn-block">
        submit
      </button>
    </form>
  );
};
export default ControlledInputs;
```

<br>

### 124. Controlled Inputs<a id='124'></a>

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/06-forms/starter/01-controlled-inputs.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- setup state values for name & email
- add value, onChange to each input
- setup onSubmit

```js
import { useState } from "react";
const ControlledInputs = () => {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");

  // const handleChange = (e) => {
  //   // for now we won't use it
  //   const name = e.target.name;
  //   const value = e.target.value;
  // };

  const handleSubmit = (e) => {
    e.preventDefault();
    // do something
    console.log(name, email);
  };

  return (
    <form className="form" onSubmit={handleSubmit}>
      <h4>controlled inputs</h4>

      <div className="form-row">
        <label htmlFor="name" className="form-label">
          name
        </label>
        <input
          type="text"
          className="form-input"
          value={name}
          onChange={(e) => setName(e.target.value)}
          id="name"
        />
      </div>

      <div className="form-row">
        <label htmlFor="email" className="form-label">
          Email
        </label>
        <input
          type="email"
          className="form-input"
          id="email"
          value={email}
          onChange={(e) => setEmail(e.target.value)}
        />
      </div>

      <button type="submit" className="btn btn-block">
        submit
      </button>
    </form>
  );
};
export default ControlledInputs;
```

- Note: we didn't submit or post the data via form using below button, but we used form onSubmit

<br>

### 125. User Challenge - Setup<a id='125'></a>

> **_Business Objective: Layout_**

<img src="notes/form.png" width="400">

- setup controlled input (name input)
- setup onSubmit (for now just placeholder)
- import data array (first array) from data
- create another state value (data as default)
- iterate over and display right after form (h4)
- when user submits the form add new person to the list

- Extra Challenge
  - add button and setup functionality to remove user

<br>

### 126. User Challenge - Add New User<a id='126'></a>

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/06-forms/starter/02-user-challenge.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In ./tutorial/06-forms/starter/02-user-challenge.jsx

```js
import { useState } from "react";
import { data } from "../../../data";

const UserChallenge = () => {
  const [name, setName] = useState("");
  const [users, setUsers] = useState(data);

  const handleSubmit = (e) => {
    e.preventDefault();
    // do something
    console.log(name);

    /*--- Functionality to add new user ---*/
    // if no value, do nothing
    if (!name) return;

    // if value, setup new user and add to current users
    const fakeId = Date.now();
    console.log(fakeId);

    // const newUser = { id: fakeId, name: name };
    const newUser = { id: fakeId, name };
    // copy all the user from state variable with new user
    const updatedUsers = [...users, newUser];
    // update state
    setUsers(updatedUsers);

    // clean out the input
    setName("");
  };

  return (
    <div>
      <form className="form" onSubmit={handleSubmit}>
        <h4>Add User</h4>

        <div className="form-row">
          <label htmlFor="name" className="form-label">
            name
          </label>
          <input
            type="text"
            className="form-input"
            value={name}
            onChange={(e) => setName(e.target.value)}
            id="name"
          />
        </div>

        <button type="submit" className="btn btn-block">
          submit
        </button>
      </form>

      {/* render users */}
      <h2>users</h2>
      {users.map((user) => {
        return (
          <div key={user.id}>
            <h4>{user.name}</h4>
          </div>
        );
      })}
    </div>
  );
};
export default UserChallenge;
```

<br>

### 127. User Challenge - Remove User<a id='127'></a>

- In ./tutorial/06-forms/starter/02-user-challenge.jsx

```js
import { useState } from "react";
import { data } from "../../../data";

const UserChallenge = () => {
  const [name, setName] = useState("");
  const [users, setUsers] = useState(data);

  const handleSubmit = (e) => {
    e.preventDefault();
    // do something
    console.log(name);

    /*--- Functionality to add new user ---*/
    // if no value, do nothing
    if (!name) return;

    // if value, setup new user and add to current users
    const fakeId = Date.now();
    console.log(fakeId);

    // const newUser = { id: fakeId, name: name };
    const newUser = { id: fakeId, name };
    // copy all the user from state variable with new user
    const updatedUsers = [...users, newUser];
    // update state
    setUsers(updatedUsers);

    // clean out the input
    setName("");
  };

  const removeUser = (id) => {
    const updatedUsers = users.filter((person) => person.id !== id);
    // update state
    setUsers(updatedUsers);
  };

  return (
    <div>
      <form className="form" onSubmit={handleSubmit}>
        <h4>Add User</h4>

        <div className="form-row">
          <label htmlFor="name" className="form-label">
            name
          </label>
          <input
            type="text"
            className="form-input"
            value={name}
            onChange={(e) => setName(e.target.value)}
            id="name"
          />
        </div>

        <button type="submit" className="btn btn-block">
          submit
        </button>
      </form>

      {/* render users */}
      <h2>users</h2>

      {users.map((user) => {
        return (
          <div key={user.id}>
            <h4>{user.name}</h4>

            <button onClick={() => removeUser(user.id)} className="btn">
              remove
            </button>
          </div>
        );
      })}
    </div>
  );
};
export default UserChallenge;
```

<br>

### 128. Multiple Inputs<a id='128'></a>

> **_Business Objective: Layout_**

<img src="notes/multipleinputs.png" width="400">

---

[Javascript Nuggets - Dynamic Object Keys](https://www.youtube.com/watch?v=_qxCYtWm0tw&list=PLnHJACx3NwAfRUcuKaYhZ6T5NRIpzgNGJ&index=3&t=97s)

- Instead of having three state value have one

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/06-forms/starter/03-multiple-inputs.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In ./tutorial/06-forms/starter/03-multiple-inputs.jsx

- inputs must have name attribute, when we use single handleChange function setup

```js
import { useState } from "react";

const MultipleInputs = () => {
  const [user, setUser] = useState({
    name: "",
    email: "",
    password: "",
  });

  const handleChange = (e) => {
    setUser({ ...user, [e.target.name]: e.target.value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log(user);
  };
  return (
    <div>
      <form className="form" onSubmit={handleSubmit}>
        <h4>Multiple Inputs</h4>
        {/* name */}
        <div className="form-row">
          <label htmlFor="name" className="form-label">
            name
          </label>
          <input
            type="text"
            className="form-input"
            id="name"
            name="name"
            value={user.name}
            onChange={handleChange}
          />
        </div>

        {/* email */}
        <div className="form-row">
          <label htmlFor="email" className="form-label">
            Email
          </label>
          <input
            type="email"
            className="form-input"
            id="email"
            name="email"
            value={user.email}
            onChange={handleChange}
          />
        </div>

        {/* password */}
        <div className="form-row">
          <label htmlFor="password" className="form-label">
            Password
          </label>
          <input
            type="password"
            className="form-input"
            id="password"
            name="password"
            value={user.password}
            onChange={handleChange}
          />
        </div>

        <button type="submit" className="btn btn-block">
          submit
        </button>
      </form>
    </div>
  );
};

export default MultipleInputs;
```

<br>

### 129. Checkbox Input<a id='129'></a>

> **_Business Objective: Layout_**

<img src="notes/selectinput.png" width="400">

---

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/06-forms/starter/04-other-inputs.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In tutorial/06-forms/starter/04-other-inputs.jsx

```js
import { useState } from "react";

const OtherInputs = () => {
  const [shipping, setShipping] = useState(false);

  const handleShipping = (e) => {
    console.log(e.target.checked);
    setShipping(e.target.checked);
  };

  return (
    <div>
      <form className="form">
        <h4>Other Inputs</h4>
        {/* name */}
        <div className="form-row" style={{ textAlign: "left" }}>
          <input
            type="checkbox"
            checked={shipping}
            id="shipping"
            name="shipping"
            onChange={handleShipping}
          />
          <label htmlFor="shipping"> Free Shipping </label>
        </div>

        <div className="form-row" style={{ textAlign: "left" }}>
          <label htmlFor="framework" className="form-label">
            Framework
          </label>
        </div>

        <button type="submit" className="btn btn-block">
          submit
        </button>
      </form>
    </div>
  );
};

export default OtherInputs;
```

<br>

### 130. Select Input<a id='130'></a>

- Continue...
- In tutorial/06-forms/starter/04-other-inputs.jsx

```js
import { useState } from "react";

const frameworks = ["react", "angular", "vue", "svelte"];

const OtherInputs = () => {
  const [shipping, setShipping] = useState(false);
  const [framework, setFramework] = useState("react");

  const handleShipping = (e) => {
    console.log(e.target.checked);
    setShipping(e.target.checked);
  };

  const handleFramework = (e) => {
    setFramework(e.target.value);
  };

  return (
    <div>
      <form className="form">
        <h4>Other Inputs</h4>
        {/* name */}
        <div className="form-row" style={{ textAlign: "left" }}>
          <input
            type="checkbox"
            checked={shipping}
            id="shipping"
            name="shipping"
            onChange={handleShipping}
          />
          <label htmlFor="shipping"> Free Shipping </label>
        </div>

        <div className="form-row" style={{ textAlign: "left" }}>
          <label htmlFor="framework" className="form-label">
            Framework
          </label>
          <select
            name="framework"
            id="framework"
            value={framework}
            onChange={handleFramework}
          >
            {frameworks.map((framework) => {
              return <option key={framework}>{framework}</option>;
            })}
          </select>
        </div>

        <button type="submit" className="btn btn-block">
          submit
        </button>
      </form>
    </div>
  );
};

export default OtherInputs;
```

<br>

### 131. FormData API<a id='131'></a>

> **_Business Objective: Layout_**

<img src="notes/formdataapi.png" width="500">

[JS Nuggets - FormData API](https://youtu.be/5-x4OUM-SP8)

- a great solution when you have bunch of inputs
- inputs must have name attribute

The FormData interface provides a way to construct a set of key/value pairs representing form fields and their values, which can be sent using the fetch() or XMLHttpRequest.send() method. It uses the same format a form would use if the encoding type were set to "multipart/form-data".

---

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/06-forms/starter/05-form-data.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In tutorial/06-forms/starter/05-form-data.jsx

```js
import { useState } from "react";

const UncontrolledInputs = () => {
  const [value, setValue] = useState(0);

  const handleSubmit = (e) => {
    e.preventDefault();

    // data is in array of array structure
    const formData = new FormData(e.currentTarget);
    // const name = formData.get('name');
    // console.log(name);
    // console.log([...formData.entries()]);

    // Object.fromEntries turn array data structure into object with key value pairs
    const newUser = Object.fromEntries(formData);
    // do something (post request, add to list, etc)
    console.log(newUser);
    // Gotcha - re-render won't clear out the values
    setValue(value + 1);
    // reset values
    e.currentTarget.reset();
  };
  return (
    <div>
      <form className="form" onSubmit={handleSubmit}>
        <h4>Form Data API</h4>

        {/* name */}
        <div className="form-row">
          <label htmlFor="name" className="form-label">
            name
          </label>
          <input type="text" className="form-input" id="name" name="name" />
        </div>

        {/* email */}
        <div className="form-row">
          <label htmlFor="email" className="form-label">
            Email
          </label>
          <input type="email" className="form-input" id="email" name="email" />
        </div>

        {/* password */}
        <div className="form-row">
          <label htmlFor="password" className="form-label">
            Password
          </label>
          <input
            type="password"
            className="form-input"
            id="password"
            name="password"
          />
        </div>

        <button type="submit" className="btn btn-block">
          submit
        </button>
      </form>
    </div>
  );
};
export default UncontrolledInputs;
```

---

- e.currentTarget

In React, e.currentTarget returns the DOM element that triggered the event.

- Object From Entries

The Object.fromEntries() static method transforms a list of key-value pairs into an object.

```js
const entries = new Map([
  ["foo", "bar"],
  ["baz", 42],
]);

const obj = Object.fromEntries(entries);

console.log(obj);
// Expected output: Object { foo: "bar", baz: 42 }
```

- reset()

The reset() method is a built-in method in HTML that can be used to reset all form controls to their initial values. When this method is called on a form element, it will clear any user-entered data and reset the values of all form elements to their default values.

<br>

### 132. Matching Projects<a id='132'></a>

- ref course read me

<br>

### 133. useRef - DOM Node<a id='133'></a>

> **_Business Objective: Layout_**

<img src="notes/useref1.png" width="500">

---

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/07-useRef/starter/01-useRef-basics.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In tutorial/07-useRef/starter/01-useRef-basics.jsx

- useRef DOES NOT TRIGGER RE-RENDER like useState whenever we update state
- preserves the value between renders
- target DOM nodes/elements
- THINK: useRef value as a container that the mental model of Jhon

```js
import { useEffect, useRef, useState } from "react";

const UseRefBasics = () => {
  const [value, setValue] = useState(0);
  const refContainer = useRef(null);

  console.log(refContainer);
  // {current:null}
  // set value ourselves or DOM node

  // useEffect(() => {
  //    console.log(refContainer.current);
  // });

  const isMounted = useRef(false);

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log(refContainer.current);

    // How to access useRef DOM node value
    // DOM node aka JSX
    const name = refContainer.current.value;
    console.log(name);
  };

  return (
    <div>
      <form className="form" onSubmit={handleSubmit}>
        <div className="form-row">
          <label htmlFor="name" className="form-label">
            Name
          </label>
          {/* How to use useRef in DOM node*/}
          <input
            type="text"
            id="name"
            ref={refContainer}
            className="form-input"
          />
        </div>

        <button type="submit" className="btn btn-block">
          submit
        </button>
      </form>

      <h1>value : {value}</h1>
      <button onClick={() => setValue(value + 1)} className="btn">
        increase
      </button>
    </div>
  );
};

export default UseRefBasics;
```

<br>

### 134. useRef - Initial Render<a id='134'></a>

- continue... 2 example

- In tutorial/07-useRef/starter/01-useRef-basics.jsx

- useRef DOES NOT TRIGGER RE-RENDER like useState whenever we update state
- preserves the value between renders
- target DOM nodes/elements
- THINK: useRef value as a container that the mental model of Jhon

```js
import { useEffect, useRef, useState } from "react";

const UseRefBasics = () => {
  const [value, setValue] = useState(0);
  const refContainer = useRef(null);
  const isMounted = useRef(false);

  console.log(refContainer);
  // {current:null}
  // set value ourselves or DOM node

  useEffect(() => {
    // console.log(refContainer.current);
    refContainer.current.focus();
  });

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log(refContainer.current);

    // How to access useRef DOM node value
    // DOM node aka JSX
    const name = refContainer.current.value;
    console.log(name);
  };

  useEffect(() => {
    if (!isMounted.current) {
      isMounted.current = true;
      return;
    }
    console.log("re-render");
  }, [value]);

  return (
    <div>
      <form className="form" onSubmit={handleSubmit}>
        <div className="form-row">
          <label htmlFor="name" className="form-label">
            Name
          </label>
          {/* How to use useRef in DOM node*/}
          <input
            type="text"
            id="name"
            ref={refContainer}
            className="form-input"
          />
        </div>

        <button type="submit" className="btn btn-block">
          submit
        </button>
      </form>

      <h1>value : {value}</h1>
      <button onClick={() => setValue(value + 1)} className="btn">
        increase
      </button>
    </div>
  );
};

export default UseRefBasics;
```

<br>

### 135. Matching Projects<a id='135'></a>

- ref course read me

<br>

### 136. Custom Hooks - Toggle<a id='136'></a>

> **_Business Objective: Layout_**

<img src="notes/togglehook.png" width="500">

---

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/08-custom-hooks/starter/01-toggle.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In /tutorial/08-custom-hooks/starter, create useToggle.js and write custom hook using useState hook

```js
import { useState } from "react";

const useToggle = (defaultValue) => {
  const [show, setShow] = useState(defaultValue);
  const toggle = () => {
    setShow(!show);
  };
  return { show, toggle };
};

export default useToggle;
```

---

- In /tutorial/08-custom-hooks/starter/01-toggle.jsx, use custom hook

```js
import useToggle from "./useToggle";

const ToggleExample = () => {
  const { show, toggle } = useToggle(true);
  return (
    <div>
      <h4>toggle custom hook</h4>
      <button className="btn" onClick={toggle}>
        toggle
      </button>
      {show && <h4>some stuff</h4>}
    </div>
  );
};
export default ToggleExample;
```

<br>

### 137. Custom Hooks - Fetch Person<a id='137'></a>

> **_Business Objective: Layout_**

<img src="notes/fetchdatahook.png" width="500">

---

- Challenge

- in App.jsx import 02-fetch-data
- take a look at the component
- and try to setup custom fetch hook
- hint :
  hook should return isLoading,isError,user
  and take url as parameter

useFetchPerson.js

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/08-custom-hooks/starter/02-fetch-data.jsx";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

---

- In tutorial/08-custom-hooks/starter, create useFetchPerson.js, and write custom hook

```js
import { useState, useEffect } from "react";

const useFetchPerson = (url) => {
  const [isLoading, setIsLoading] = useState(true);
  const [isError, setIsError] = useState(false);
  const [user, setUser] = useState(null);

  useEffect(() => {
    const fetchUser = async () => {
      try {
        const resp = await fetch(url);
        // console.log(resp);
        if (!resp.ok) {
          setIsError(true);
          setIsLoading(false);
          return;
        }

        const user = await resp.json();
        setUser(user);
      } catch (error) {
        setIsError(true);
        // console.log(error);
      }
      // hide loading
      setIsLoading(false);
    };
    fetchUser();
  }, []);

  return { isLoading, isError, user };
};

export default useFetchPerson;
```

---

- In tutorial/08-custom-hooks/starter/02-fetch-data.jsx, use custom hook useFetch function

```js
import useFetchPerson from "./useFetchPerson";

const url = "https://api.github.com/users/QuincyLarson";

const FetchData = () => {
  const { isLoading, isError, user } = useFetchPerson(url);

  // order matters
  // don't place user JSX before loading or error

  if (isLoading) {
    return <h2>Loading...</h2>;
  }
  if (isError) {
    return <h2>There was an error...</h2>;
  }
  const { avatar_url, name, company, bio } = user;
  return (
    <div>
      <img
        style={{ width: "150px", borderRadius: "25px" }}
        src={avatar_url}
        alt={name}
      />
      <h2>{name}</h2>
      <h4>works at {company}</h4>
      <p>{bio}</p>
    </div>
  );
};
export default FetchData;
```

<br>

### 138. Custom Hooks - Generic Fetch<a id='138'></a>

- In tutorial/08-custom-hooks/starter, create useFetch.js, generic custom hook function
- Generic Fetch

```js
import { useState, useEffect } from "react";

const useFetch = (url) => {
  const [isLoading, setIsLoading] = useState(true);
  const [isError, setIsError] = useState(false);
  // change state value
  const [data, setData] = useState(null);

  useEffect(() => {
    // change name
    const fetchData = async () => {
      try {
        const resp = await fetch(url);

        if (!resp.ok) {
          setIsError(true);
          setIsLoading(false);
          return;
        }
        // change to response
        const response = await resp.json();
        setData(response);
      } catch (error) {
        setIsError(true);
        // console.log(error);
      }
      // hide loading
      setIsLoading(false);
    };
    // invoke fetch data
    fetchData();
  }, []);

  return { isLoading, isError, data };
};

export default useFetch;
```

---

- modify code use useFetch hook instead of useFetchPerson
- In tutorial/08-custom-hooks/starter/02-fetch-data.jsx, use custom hook useFetch function

```js
import useFetch from "./useFetch";

const url = "https://api.github.com/users/QuincyLarson";

const FetchData = () => {
  const { isLoading, isError, data: user } = useFetch(url);

  // order matters
  // don't place user JSX before loading or error

  if (isLoading) {
    return <h2>Loading...</h2>;
  }
  if (isError) {
    return <h2>There was an error...</h2>;
  }
  const { avatar_url, name, company, bio } = user;
  return (
    <div>
      <img
        style={{ width: "150px", borderRadius: "25px" }}
        src={avatar_url}
        alt={name}
      />
      <h2>{name}</h2>
      <h4>works at {company}</h4>
      <p>{bio}</p>
    </div>
  );
};
export default FetchData;
```

---

<br>

### 139. Context API - Challenge<a id='139'></a>

- In src/App.jsx, import/render Starter component

```js
import Starter from "./tutorial/09-context-api/starter";

function App() {
  return (
    <div className="container">
      <Starter />
    </div>
  );
}

export default App;
```

```js
import Starter from "./tutorial/09-context-api/starter";
```

Challenge

- In starter folder create Navbar.jsx, NavLinks.jsx, UserContainer.jsx

- create three components and nest them in such way :
- Navbar.jsx

  - NavLinks.jsx (nested in Navbar)
    - UserContainer.jsx (nested in NavLinks)

- import Navbar.jsx in App.jsx (remove container - CSS)
- in Navbar.jsx setup
  - user state value
    - default value {name:'something'}
  - logout function
    - set user back to null
- pass both of them down to UserContainer.jsx
- display user and button
- on button click set user back to null

- extra challenge
- if user null, in UserContainer display <p>please login</p>

Navbar.jsx

```js
import { useState } from "react";
import NavLinks from "./NavLinks";

const Navbar = () => {
  const [user, setUser] = useState({ name: "bob" });
  const logout = () => {
    setUser(null);
  };
  return (
    <nav className="navbar">
      <h5>CONTEXT API</h5>
      <NavLinks user={user} logout={logout} />
    </nav>
  );
};
export default Navbar;
```

NavLinks.jsx

```js
import UserContainer from "./UserContainer";

const NavLinks = ({ user, logout }) => {
  return (
    <div className="nav-container">
      <ul className="nav-links">
        <li>
          <a href="#">home</a>
        </li>
        <li>
          <a href="#">about</a>
        </li>
      </ul>
      <UserContainer user={user} logout={logout} />
    </div>
  );
};
export default NavLinks;
```

UserContainer.jsx

```js
const UserContainer = ({ user, logout }) => {
  return (
    <div className="user-container">
      {user ? (
        <>
          <p>Hello There, {user.name.toUpperCase()}</p>
          <button type="button" className="btn" onClick={logout}>
            logout
          </button>
        </>
      ) : (
        <p>Please Login</p>
      )}
    </div>
  );
};
export default UserContainer;
```

<br>

### 140. Context API - Prop Drilling<a id='140'></a>

<br>

### 141. Context API - Solution<a id='141'></a>

<br>

### 142. Context API - Custom Hook<a id='142'></a>

<br>

### 143. Context API - Global Setup<a id='143'></a>

<br>

### 144. Matching Projects<a id='144'></a>

<br>

### 145. UseReducer - Intro<a id='145'></a>

<br>

### 146. UseReducer - Challenge<a id='146'></a>

<br>

### 147. UseReducer - Setup<a id='147'></a>

<br>

### 148. Reducer Basics<a id='148'></a>

<br>

### 149. Actions and Default State<a id='149'></a>

<br>

### 150. Reset List<a id='150'></a>

<br>

### 151. Remove Person<a id='151'></a>

<br>

### 152. Import/Export<a id='152'></a>

<br>

### 153. Matching Projects<a id='153'></a>

<br>

### 154. Performance - Intro<a id='154'></a>

<br>

### 155. Component Re-renders<a id='155'></a>

<br>

### 156. React Dev Tools<a id='156'></a>

<br>

### 157. Lower State<a id='157'></a>

<br>

### 158. Lower State - Challenge<a id='158'></a>

<br>

### 159. React.memo()<a id='159'></a>

<br>

### 160. Mind Grenade<a id='160'></a>

<br>

### 161. UseCallback Hook<a id='161'></a>

<br>

### 162. UseCallback Hook - Common Use Case<a id='162'></a>

<br>

### 163. UseMemo Hook<a id='163'></a>

<br>

### 164. UseTransition Hook<a id='164'></a>

<br>

### 165. React Suspense<a id='165'></a>

<br>
```
