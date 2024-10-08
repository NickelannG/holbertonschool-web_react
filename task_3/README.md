## Task 8. Ambient Namespaces

Create a directory called `task_3` and copy these configuration files into it: `package.json`, `webpack.config.js`, `tsconfig.json`.

The first part of will require that you build an interface and a type. Inside a file named `interface.ts`:

Create a type `RowID` and set it equal to number
Create an interface RowElement that contains these 3 fields:
- `firstName`: `string`
- `lastName`: `string`
- `age?`: `number`

You are building the next part of the application architecture. The goal is to save the entities to a database. Because of time constraints, you can’t write a connector to the database, and you decided to download a library called `crud.js`. Copy this file into the `task_3/js` directory.

Here it is
```
export function insertRow(row) {
  console.log('Insert row', row);
  return Math.floor(Math.random() * Math.floor(1000));
}

export function deleteRow(rowId) {
  console.log('Delete row id', rowId);
  return;
}

export function updateRow(rowId, row) {
  console.log(`Update row ${rowId}`, row);

  return rowId;
}
```
Write an ambient file within `task_3/js`, named `crud.d.ts `containing the type declarations for each crud function. At the top of the file import RowID and RowElement from `interface.ts`.

In `main.ts`

- At the top of the file create a triple slash directive that includes all the dependencies from `crud.d.ts`
- Import the rowID type and rowElement from interface.ts
- Import everything from `crud.js` as `CRUD`

Create an object called row with the type `RowElement` with the fields set to these values:

- `firstName`: `Guillaume`
- `lastName`: `Salva`

Create a const variable named `newRowID` with the type `RowID` and assign the value the `insertRow` command.

Next, create a const variable named `updatedRow` with the type `RowElement` and update row with an age field set to `23`

Finally, call the `updateRow` and `deleteRow` commands.

Expected result:
```
const obj = {firstName: "Guillaume", lastName: "Salva"};
CRUD.insertRow(obj)
// Insert row {firstName: "Guillaume", lastName: "Salva"}

const updatedRow: RowElement = { firstName: "Guillaume", lastName: "Salva", age: 23 };
CRUD.updateRow(newRowID, updatedRow);
// Update row 125 {firstName: "Guillaume", lastName: "Salva", age: 23}

CRUD.deleteRow(125);
// Delete row id 125
```

Requirements:

When running `npm run build`, no TypeScript error should be displayed.
Every variable should use TypeScript when possible.
The main file and the ambient file should both import the types defined in the interface file.
You can easily test your ambient file by looking at the intellisense of your IDE when using the 3rd party functions.
