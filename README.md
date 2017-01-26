# React Bootstrap Datatable

[![Build Status](https://travis-ci.org/Imballinst/react-bs-datatable.svg?branch=master)](https://travis-ci.org/Imballinst/react-bs-datatable)
[![npm version](https://badge.fury.io/js/react-bs-datatable.svg)](https://badge.fury.io/js/react-bs-datatable)

[![NPM](https://nodei.co/npm/react-bs-datatable.png)](https://nodei.co/npm/react-bs-datatable/)

Inspired by [react-data-components](https://github.com/carlosrocha/react-data-components). This library uses [react-bootstrap](http://react-bootstrap.github.io/) stylesheets and javascripts. In addition, this library also uses [font-awesome](http://fontawesome.io/) for the table header, clear filter, and other stuffs.

## Key features

1. Sorting
2. Filter
3. Pagination

## Props

* tableHeader **(Required)**: Array of objects, each consists of `title` and `prop`. Title is the text inside `th` and prop is used to match the body column with the header column.
* tableBody **(Required)**: Array of objects, each consists of `props` and `their value`. Each object will be rendered to the matching column.
* keyName **(Required)**: String. It is used to prepend the key property of children elements.
* rowsPerPage: Integer. Initial rows per page. Default: `5`.
* rowsPerPageOption: Array of integer, consists of pagination options. Default: `[5]`.
* sortable: Boolean. It determines whether the table will be sortable or not. Default: `false`.
* filterable: Boolean. It determines whether the table will be filterable or not. Default: `false`.
* initialSort: Object, consists of `prop` (String) and `isAscending` (Boolean). Default: `undefined`.

## Styling

This package doesn't include Bootstrap stylesheets. If you want to include it, you could do so by importing its CSS in your HTML **or** its SCSS [bootstrap-sass](https://github.com/twbs/bootstrap-sass) in your SCSS. You can also style the table by defining it in your SCSS.

```
.table-custom {
  .table-custom-thead {
    .table-custom-thead-col {
      &.sortable { // If and only if sortable is true
        &:hover {
          background: #000; // Your color of choice
          cursor: pointer; // Changes the cursor into a pointer on hover
        }
      }
    }
  }
}
```

## How to use

```
import React from 'react'; // Import React
import { render } from 'react-dom'; // Import render method
import Datatable from 'react-bs-datatable'; // Import this package

const tableHeader = [
  { title: 'Username', prop: 'userID'  },
  { title: 'Person Name', prop: 'name' },
];

const tableBody = [
  { userID: "i-am-tyler", name: "Tyler Olfson" },
  { userID: "sir-bobby", name: "Bobby Charly" }
];

render(
  <Datatable
    tableHeader={tableHeader}
    tableBody={tableBody}
    keyName="userTable"
    rowsPerPage={5}
    rowsPerPageOption={[5, 10, 15, 20]}
    sortable
    filterable
    initialSort={{prop: "userID", isAscending: true}}
  />,
  document.getElementById('test-datatable')
);
```

## Next features/improvements

- [ ] Sortable props for each column instead of globally
- [ ] Filterable props for each column instead of globally
- [ ] Checkbox for each row (for bulk action)
- [ ] Language diversity
- [ ] Custom table classes (it's fixed to striped, responsive, and hover at the moment)
- [ ] More extensive unit testing
- [ ] Custom position for filter input field, pagination options, and page navigation

## Contributing

Feel free to contribute by creating issues and/or pull requests. I will do my best to address them as fast as I can.
