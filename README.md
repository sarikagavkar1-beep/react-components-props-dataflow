# TaskFlow — React Components, Props & Data Flow Assignment

A clean React task manager demonstrating:
- Reusable React components
- Props and callback props
- Parent-to-child data flow
- Child-to-parent event flow
- React state with `useState`
- Derived data with `useMemo`
- Conditional rendering
- List rendering with stable keys
- Responsive CSS

## Project structure

```text
src/
  App.jsx       # Main state and component composition
  main.jsx      # React entry point
  styles.css    # Responsive UI styling
index.html
package.json
```

## Run locally

1. Install Node.js (LTS).
2. Open this folder in VS Code.
3. Open a terminal in the project folder.
4. Run:

```bash
npm install
npm run dev
```

5. Open the localhost URL shown by Vite.

To create a production build:

```bash
npm run build
```

## How the React data flow works

`App` owns the `tasks` state.

- `App` → `Header`: passes completion counts as props.
- `App` → `Stats`: passes the full task array.
- `App` → `TaskForm`: passes `onAddTask`.
- `App` → `TaskList`: passes tasks, filter, and callbacks.
- `TaskList` → `TaskItem`: passes each task and action callbacks.
- `TaskForm` calls `onAddTask(newTask)` to send data back to App.
- `TaskItem` calls `onToggle(id)` and `onDelete(id)` to request state changes in App.

This demonstrates one-way data flow while keeping state in the appropriate parent component.

## Upload to GitHub

### Option A — easiest

1. Go to https://github.com and sign in.
2. Click **New repository**.
3. Give it a name such as `react-components-props-assignment`.
4. Choose **Public** if your teacher needs a public link.
5. Create the repository.
6. On your computer, extract this ZIP.
7. Open PowerShell inside the extracted folder.
8. Run:

```bash
git init
git add .
git commit -m "React components props and data flow assignment"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with the HTTPS URL of the repository you created.

Your submission link will be:

`https://github.com/YOUR_USERNAME/react-components-props-assignment`

## Important

Do NOT upload `node_modules`. The repository only needs the source files and `package.json`; the teacher can run `npm install` to recreate dependencies.
