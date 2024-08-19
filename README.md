<p><strong>Adding Password Hashing and Comparison to Your Node.js Project</strong></p>

<p><strong>Description:</strong>  
In this project, I integrated secure password hashing and comparison functionalities into a Node.js application using the bcrypt library. This approach ensures that passwords are handled securely by hashing them before storage and verifying them efficiently during authentication. Both asynchronous and synchronous methods were implemented to demonstrate how passwords can be hashed and compared in different scenarios.</p>

<p><strong>Technologies Used:</strong></p>
<ul>
  <li><strong>Node.js:</strong> JavaScript runtime for building scalable server-side applications.</li>
  <li><strong>bcrypt:</strong> Library for hashing and comparing passwords securely.</li>
</ul>

<p><strong>Features Implemented:</strong></p>
<ul>
  <li><strong>Asynchronous Password Hashing:</strong>
    <ul>
      <li>Added code to hash passwords asynchronously using <code>bcrypt.hash()</code>.</li>
      <li>Logged the generated hash to the console.</li>
      <li>Utilized <code>bcrypt.compare()</code> to verify if a given password matches the generated hash.</li>
    </ul>
  </li>
  <li><strong>Synchronous Password Hashing:</strong>
    <ul>
      <li>Incorporated code to hash passwords synchronously using <code>bcrypt.hashSync()</code>.</li>
      <li>Logged the resulting hash to the console.</li>
      <li>Compared the hash with the original password using <code>bcrypt.compareSync()</code>.</li>
    </ul>
  </li>
  <li><strong>Password Comparison:</strong>
    <ul>
      <li>Implemented password comparison functionality using <code>bcrypt.compare()</code>.</li>
      <li>Demonstrated the comparison process with both correct and incorrect passwords to ensure accurate verification.</li>
    </ul>
  </li>
</ul>
