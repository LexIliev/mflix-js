Ticket: Handling Errors
=======================

**Problem:**

**Task**

For this ticket, you'll be required to make the API more robust by handling exceptions. Specifically, what should happen if an incorrectly formatted **_id** is passed to the **getMovieByID()** method in **moviesDAO.js**?

In this case, an error will be thrown to **getMovieByID()**, because of an invalid ID. However, the method does not need to _return_ this error. Instead, if this error is thrown, the method should return **null**.

A try/catch block is already included for you in **getMovieByID()**. Use the variable **e** to figure out if the invalid ID error is being thrown, and then return _null_ in this case.

> **Hint**:
>
> When the error **е** is caught, it has type _Error_. You might want to convert this to a string.
---

**Testing and Running the Application**

You can run the unit tests for this ticket by running:

```
npm test -t error-handling
```

Once the unit tests are passing, run the application with:

```
npm start
```

Now proceed to the status page to run the full suite of integration tests and get your validation code.

<details>
  <summary>After passing the relevant unit tests, what is the validation code for Error Handling?</summary>
   Answer: 5ae9b76a703c7c603202ef22
</details>