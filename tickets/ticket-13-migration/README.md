Ticket: Migration
=================

**Problem:**

**Task**

For this ticket, you'll be required to complete the command-line script located in the _migrations_ directory of _src_ called **movie-last-updated-migration.js**.

Things always change, and a requirement has come down that the _lastupdated_ value in each document of the _movies_ collection needs to be stored as an **ISODate** rather than a **String**.

Complete the script so it updates the format of _lastupdated_ using a bulk write. You can find the exact Node.js syntax in the docs.

Navigate to **src/migrations**.

To perform the migration, run the script:

```
node movie-last-updated-migration.js
```

---

**Testing and Running the Application**

You can run the unit tests for this ticket by running:

```
npm test -t migration
```

Once the unit tests are passing, run the application with:

```
npm start
```

Now proceed to the status page to run the full suite of integration tests and get your validation code.

<details>
  <summary>After passing the relevant tests, what is the validation code for Migration?</summary>
   Answer: 5ad9f6a64fec134d116fb06f
</details>