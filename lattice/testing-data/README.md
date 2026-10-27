# Testing data

Three Excel files for trying Lattice at https://uselattice.app. You don't need any of them for a first look: step ②'s
**Load sample** loads the same college as `sample-college.xlsx`.

The files hold teachers, rooms, sections and courses, not the week. Before uploading one in a fresh browser, click
**Load sample** once in step ② so step ① has the sample week (Mon–Fri, 8 periods, a break after P2, lunch in P4–P6).

| File | What it is | What you should see |
|---|---|---|
| `sample-college.xlsx` | The sample college: 3 departments, 9 sections, 25 teachers, 18 rooms, 54 courses (210 classes a week). | Step ② asks before replacing the data, then shows "Data looks complete". Step ③ **Generate timetable** gives a timetable with 0 clashes, score 18, in about 20 s. |
| `broken-import.xlsx` | The sample with three mistakes. | Nothing is imported. A red card lists `Rooms row 4: Type must be "classroom" or "lab", got "hall"`, `Courses row 5: teacher "Sharma" not found in Teachers sheet` and `Courses row 8: Lectures/Week must be a whole number ≥ 0, got "three"`. |
| `cannot-be-built.xlsx` | The sample with every lecture-only course of CSE A, B and C given to Dr. Anita Sharma. | Step ② warns that she teaches 42 periods a week but only 35 are free. Step ③ says *This timetable can't be built*, names her overload as the cause and offers *Move 7 periods to another teacher* and *Make a partial timetable*. |

The first solve after the server has been idle is slower (up to ~15 s more), because the server starts cold.
