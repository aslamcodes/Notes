> A Cookie is just a key value pair in a dictionary
```embed
title: "How does cookie-based authentication work?"
image: "https://cdn.sstatic.net/Sites/stackoverflow/Img/apple-touch-icon@2.png?v=73d79a89bded"
description: "What would be a step-by-step description of how cookie-based authentication work? I’ve never done anything involving either authentication or cookies. What does the browser need to do? What does the"
url: "https://stackoverflow.com/questions/17769011/how-does-cookie-based-authentication-work/17769061#17769061"
```

1. Client provides username w password
2. Server looks up the username and verifies the password (returns 401 when not matched)
3. Server creates a session ID and **store** it in the *db associated with the user*
4. Server sends **response cookie** to the client and the client stores the cookie with expiration date
5. The client attaches the **cookie** every time it makes a request to the server for the actions that require auth.
6. On logout the cookies will be destroyed
