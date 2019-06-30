Ticket: Durable Writes
======================

**Problem:**

**User Story**

"As a user, I should be confident that creating a new account will succeed, so I can start reviewing movies right away."

---

**Task**

For this ticket, you'll be required to increase the durability of the **addUser** method in _UsersDAO.js_ from the default Write Concern of **w: 1**.

When a new user registers for MFlix, their information must be added to the database before they can do anything else on the site. For this reason, we want to make sure that the data written by the **addUser** method will not be rolled back in the case of a network or server error.

We can decrease the chances of a rollback by increasing the write durability of the **addUser** method. To use a non-default Write Concern with the ***insert()*** method, pass a new Object to the method specifying the level of Write Concern. You can read more about this in the Node.js docs.

---

**Testing and Running the Application**

There are no unit or integration tests for this lab.

Please complete the multiple choice question below, and then implement the correct Write Concern in the **addUser** method.

The implementation of this task will not be tested, but using the default of **w: 1** might result in a rollback of your users' account data!

---

Which of the following Write Concerns is more durable than the default?

**Correct answers:**

**WriteConcern.W2 and WriteConcern.MAJORITY**

In a 3-node replica set, the above two Write Concerns will both wait until ***two*** nodes have applied a _WRITE_. This is because **2 out of 3** nodes is a **majority** -  ***more durable*** than only waiting for **one** node to apply it.

**Incorrect answers:**

_WriteConcern.W1_

Default Write Concern in MongoDB - does not represent higher durability.

_WriteConcern.W0_

Will **not** wait for any nodes to apply a _WRITE_ before sending an acknowledgement - less durable _WRITE_ than the default - **WriteConcern.W1**.

**Updated _addUser_ method (using _w: majority_ ):**

```
static async addUser(userInfo) {
  try {
    // here's where the new Write Concern is specified
    await users.insertOne({ ...userInfo }, { w: "majority" })
    return { success: true }
  } catch (e) {
    if (String(e).startsWith("MongoError: E11000 duplicate key error")) {
      return { error: "A user with the given email already exists." }
    }
    console.error(`Error occurred while adding new user, ${e}.`)
    return { error: e }
  }
}
```