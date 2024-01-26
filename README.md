# 문제1

<details>
  <summary>문제</summary>
  
```jsx
// App.jsx
import React from "react";

function App() {
const students = [
{ name: "Alice", age: 17, grade: "A" },
{ name: "Bob", age: 18, grade: "B" },
{ name: "Charlie", age: 16, grade: "C" },
{ name: "Diana", age: 19, grade: "D" },
];

// TODO: filter를 사용하여 18세 이상의 학생들만 선택하세요.
const filteredStudents = students.filter(/_ 여기에 코드 작성 _/);

return (

<div>
<h1>학생 목록</h1>
<ul>
{/_ TODO: map을 사용해서 filteredStudents를 여기에 렌더링하세요. _/}
{/_ TODO: 학생이름을 클릭하면 나이와 점수가 alert 돼야 해요._/}
</ul>
</div>
);
}

export default App;

````
</details>

<details>
  <summary>풀이</summary>

```jsx
// App.jsx
import React, { useState } from "react";
import FilterButtons from "./components/FilterButtons";
import StudentList from "./components/StudentList";

function App() {
  const initialStudents = [
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
  ];

  const [filteredStudents, setFilteredStudents] = useState(initialStudents);

  return (
    <div>
      <h1>학생 목록</h1>
      {/* TODO: FilterButtons 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <FilterButtons
        filteredStudents={filteredStudents}
        setFilteredStudents={setFilteredStudents}
        initialStudents={initialStudents}
      />

      {/* TODO: StudentList 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <StudentList filteredStudents={filteredStudents} />
    </div>
  );
}

export default App;

````

</details>

<br>

# 문제2

<details>
  <summary>문제</summary>
  
```jsx
import React, { useState } from "react";

function App() {
const students = [
{ name: "Alice", age: 17, grade: "A" },
{ name: "Bob", age: 18, grade: "B" },
{ name: "Charlie", age: 16, grade: "C" },
{ name: "Diana", age: 19, grade: "D" },
{ name: "Elmo", age: 20, grade: "E" },
{ name: "Fiona", age: 21, grade: "F" },
{ name: "Gabe", age: 22, grade: "A" },
{ name: "Hannah", age: 23, grade: "B" },
{ name: "Irene", age: 24, grade: "C" },
{ name: "Jenny", age: 25, grade: "D" },
{ name: "Kevin", age: 26, grade: "E" },
{ name: "Linda", age: 27, grade: "F" },
];

const [minAge, setMinAge] = useState(18);

// TODO: filter를 사용하여 minAge 이상의 학생들만 선택하세요.
const filteredStudents = students.filter((student) => student.age >= minAge);

// TODO: map을 사용하여 필터링된 학생들의 정보를 표시하세요.
const studentList = filteredStudents.map((student, index) => (

<li key={index}>
{student.name} - Age: {student.age}, Grade: {student.grade}
</li>
));

return (

<div>
<h1>학생 목록</h1>
다음 나이 이상의 학생목록만 출력해요 : {/_ TODO: input에 입력된 값(숫자) 이상의 나이를 가진 학생들만 출력하세요. _/}
<input type="number" /> 살 이상
<ul>{studentList}</ul>
</div>
);
}

export default App;

````
</details>

<details>
  <summary>풀이</summary>

```jsx
// App.jsx
import React, { useState } from "react";
import FilterButtons from "./components/FilterButtons";
import StudentList from "./components/StudentList";

function App() {
  const initialStudents = [
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
  ];

  const [filteredStudents, setFilteredStudents] = useState(initialStudents);

  return (
    <div>
      <h1>학생 목록</h1>
      {/* TODO: FilterButtons 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <FilterButtons
        filteredStudents={filteredStudents}
        setFilteredStudents={setFilteredStudents}
        initialStudents={initialStudents}
      />

      {/* TODO: StudentList 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <StudentList filteredStudents={filteredStudents} />
    </div>
  );
}

export default App;

````

</details>

<br>

# 문제3

<details>
  <summary>문제</summary>

```jsx
import React, { useState } from "react";

function App() {
  const [students, setStudents] = useState([
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
    { name: "Elmo", age: 20, grade: "E" },
    { name: "Fiona", age: 21, grade: "F" },
    { name: "Gabe", age: 22, grade: "A" },
    { name: "Hannah", age: 23, grade: "B" },
    { name: "Irene", age: 24, grade: "C" },
    { name: "Jenny", age: 25, grade: "D" },
    { name: "Kevin", age: 26, grade: "E" },
    { name: "Linda", age: 27, grade: "F" },
  ]);
  const [filteredStudents, setFilteredStudents] = useState(students);

  // TODO: filterByAge 함수를 작성하세요. 이 함수는 최소 나이를 매개변수로 받아 해당 나이 이상인 학생들로 필터링해야 합니다.
  const filterByAge = (minAge) => {
    // 여기에 코드를 작성하세요.
  };

  // TODO: filterByGrade 함수를 작성하세요. 이 함수는 특정 학점을 매개변수로 받아 해당 학점의 학생들로 필터링해야 합니다.
  const filterByGrade = (grade) => {
    // 여기에 코드를 작성하세요.
  };

  // TODO: resetFilter 함수를 작성하세요. 이 함수는 필터를 초기화하여 모든 학생들을 표시해야 합니다.
  const resetFilter = () => {
    // 여기에 코드를 작성하세요.
  };

  return (
    <div>
      <h1>학생 목록</h1>
      <button onClick={() => filterByAge(24)}>24세 이상</button>
      <button onClick={() => filterByGrade("A")}>A등급</button>
      <button onClick={resetFilter}>필터 초기화</button>
      <ul>
        {filteredStudents.map((student, index) => (
          <li key={index}>
            {student.name} - Age: {student.age}, Grade: {student.grade}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>풀이</summary>

```jsx
// componetents/FilterButtons
import React from "react";

// TODO: FilterButtons 컴포넌트를 작성하세요. 필터링 옵션을 선택하는 버튼들을 포함해야 합니다.
function FilterButtons({
  filteredStudents,
  setFilteredStudents,
  initialStudents,
}) {
  const filterByAge = (minAge) => {
    const newStudents = filteredStudents.filter(function (student) {
      return student.age >= minAge;
    });
    setFilteredStudents(newStudents);
  };

  const filterByGrade = (grade) => {
    const newStudents = filteredStudents.filter(function (student) {
      return student.grade === grade;
    });
    setFilteredStudents(newStudents);
  };

  const resetFilter = () => {
    setFilteredStudents(initialStudents);
  };

  return (
    <div>
      {/* 여기에 필터링 버튼들을 완성하세요. */}
      <button onClick={() => filterByAge(18)}>18세 이상</button>
      <button onClick={() => filterByGrade("A")}>A등급</button>
      <button onClick={resetFilter}>필터 초기화</button>
    </div>
  );
}

export default FilterButtons;
```

</details>

<br>

# 문제4

<details>
  <summary>문제</summary>

```jsx
// App.jsx
import React, { useState } from "react";
import FilterButtons from "./components/FilterButtons";
import StudentList from "./components/StudentList";

function App() {
  const initialStudents = [
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
  ];

  const [filteredStudents, setFilteredStudents] = useState(initialStudents);

  return (
    <div>
      <h1>학생 목록</h1>
      {/* TODO: FilterButtons 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <FilterButtons
      /* 필요한 props를 여기에 전달하세요. */
      />

      {/* TODO: StudentList 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <StudentList
      /* 필요한 props를 여기에 전달하세요. */
      />
    </div>
  );
}

export default App;
```

```jsx
// componetents/FilterButtons
import React from "react";

// TODO: FilterButtons 컴포넌트를 작성하세요. 필터링 옵션을 선택하는 버튼들을 포함해야 합니다.
function FilterButtons(/* 필요한 props를 여기에 전달하세요 */ {}) {
  const filterByAge = (minAge) => {};
  const filterByGrade = (grade) => {};
  const resetFilter = () => {};

  return (
    <div>
      {/* 여기에 필터링 버튼들을 완성하세요. */}
      <button>18세 이상</button>
      <button>A등급</button>
      <button>필터 초기화</button>
    </div>
  );
}

export default FilterButtons;
```

```jsx
// componetents/StudentList

import React from "react";

// TODO: StudentList 컴포넌트를 작성하세요. props로 학생 목록을 받아와서 표시해야 합니다.
function StudentList(/* 필요한 props를 여기에 전달하세요 */ {}) {
  return (
    <ul>
      {/* 여기에 학생 목록을 표시하는 로직을 작성하세요. */}
      {/* ex: 홍길동 (20세) - A등급 */}
    </ul>
  );
}

export default StudentList;
```

</details>

<details>
  <summary>풀이</summary>

```jsx
// App.jsx
import React, { useState } from "react";
import FilterButtons from "./components/FilterButtons";
import StudentList from "./components/StudentList";

function App() {
  const initialStudents = [
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
  ];

  const [filteredStudents, setFilteredStudents] = useState(initialStudents);

  return (
    <div>
      <h1>학생 목록</h1>
      {/* TODO: FilterButtons 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <FilterButtons
        filteredStudents={filteredStudents}
        setFilteredStudents={setFilteredStudents}
        initialStudents={initialStudents}
      />

      {/* TODO: StudentList 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <StudentList filteredStudents={filteredStudents} />
    </div>
  );
}

export default App;
```

```jsx
// componetents/FilterButtons
import React from "react";

// TODO: FilterButtons 컴포넌트를 작성하세요. 필터링 옵션을 선택하는 버튼들을 포함해야 합니다.
function FilterButtons({
  filteredStudents,
  setFilteredStudents,
  initialStudents,
}) {
  const filterByAge = (minAge) => {
    const newStudents = filteredStudents.filter(function (student) {
      return student.age >= minAge;
    });
    setFilteredStudents(newStudents);
  };

  const filterByGrade = (grade) => {
    const newStudents = filteredStudents.filter(function (student) {
      return student.grade === grade;
    });
    setFilteredStudents(newStudents);
  };

  const resetFilter = () => {
    setFilteredStudents(initialStudents);
  };

  return (
    <div>
      {/* 여기에 필터링 버튼들을 완성하세요. */}
      <button onClick={() => filterByAge(18)}>18세 이상</button>
      <button onClick={() => filterByGrade("A")}>A등급</button>
      <button onClick={resetFilter}>필터 초기화</button>
    </div>
  );
}

export default FilterButtons;
```

```jsx
// componetents/StudentList

import React from "react";

// TODO: StudentList 컴포넌트를 작성하세요. props로 학생 목록을 받아와서 표시해야 합니다.
function StudentList({ filteredStudents }) {
  return (
    <ul>
      {/* 여기에 학생 목록을 표시하는 로직을 작성하세요. */}
      {/* ex: 홍길동 (20세) - A등급 */}
      {filteredStudents.map(function (student) {
        return (
          <div>
            <div>
              {student.name} ({student.age}세) - {student.grade} 등급
            </div>
          </div>
        );
      })}
    </ul>
  );
}

export default StudentList;
```

</details>
