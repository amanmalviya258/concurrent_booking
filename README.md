Disclaimer: Contains no AI code.

Seat Booking System.

The Double Booking problem.
Two users click "Book" on seat A1 at the same instant. Only one should win.

User A ──► read seat A1 → "free" ──► write booking ──► success
User B ──► read seat A1 → "free" ──► write booking ──► ???
Without any protection, both succeed. Now two people fighting to #death for the same seat.

Strategy 1: Pessimistic Locking
Idea - Lock the resource before you read it. Hold the lock through the entire read check write cycle. Everyone else waits for that seat in a line.

Strategy 2: Optimistic Concurrency
Idea- Don't lock anything. Read freely, do your work, then attempt to write.
If someone changed the data in between your read and write, your write fails, #you then giveup and die.

//----------------------------------------------------

Tech Stack used: Redis, Go, HTML, CSS, Love.