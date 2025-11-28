import React, { useReducer } from "react";

const initialStudents = [
  { id: 1, name: "Bhaskar", status: "Absent" },
  { id: 2, name: "Raju", status: "Absent" },
  { id: 3, name: "Harsha", status: "Absent" }
];

function attendanceReducer(state, action) {
  switch (action.type) {
    case "MARK_PRESENT":
      return state.map(student =>
        student.id === action.id ? { ...student, status: "Present" } : student
      );

    case "MARK_ABSENT":
      return state.map(student =>
        student.id === action.id ? { ...student, status: "Absent" } : student
      );

    case "RESET":
      return state.map(student => ({ ...student, status: "Absent" }));

    default:
      return state;
  }
}

function App() {
  const [students, dispatch] = useReducer(attendanceReducer, initialStudents);

  return (
    <div style={{ padding: "20px" }}>
      <h1>Student Attendance Tracker</h1>

      <table border="1" cellPadding="10">
        <thead>
          <tr>
            <th>ID</th>
            <th>Student Name</th>
            <th>Status</th>
            <th>Actions</th>
          </tr>
        </thead>

        <tbody>
          {students.map(student => (
            <tr key={student.id}>
              <td>{student.id}</td>
              <td>{student.name}</td>
              <td>{student.status}</td>
              <td>
                <button
                  onClick={() =>
                    dispatch({ type: "MARK_PRESENT", id: student.id })
                  }
                >
                  Mark Present
                </button>

                <button
                  onClick={() =>
                    dispatch({ type: "MARK_ABSENT", id: student.id })
                  }
                  style={{ marginLeft: "10px" }}
                >
                  Mark Absent
                </button>
              </td>
            </tr>
          ))}
        </tbody>
      </table>

      <br />
      <button onClick={() => dispatch({ type: "RESET" })}>Reset All</button>

      <h2>Final Attendance List</h2>
      <ul>
        {students.map(s => (
          <li key={s.id}>
            {s.name} - {s.status}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;
