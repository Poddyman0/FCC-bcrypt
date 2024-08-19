<p><strong>For the following challenges, you will be working with a new starter project that is different from the previous one. You can find the new starter project on Gitpod, or clone it from GitHub.</strong></p>

<p><strong>BCrypt hashes are very secure.</strong>  
A hash is basically a fingerprint of the original data—always unique. This is accomplished by feeding the original data into an algorithm and returning a fixed length result. To further complicate this process and make it more secure, you can also salt your hash. Salting your hash involves adding random data to the original data before the hashing process, which makes it even harder to crack the hash.</p>

<p><strong>BCrypt hashes will always look like $2a$13$ZyprE5MRw2Q3WpNOGZWGbeG7ADUre1Q8QO.uUUtcbqloU0yvzavOm</strong>, which does have a structure. The first small bit of data <code>$2a</code> is defining what kind of hash algorithm was used. The next portion <code>$13</code> defines the cost. Cost is about how much power it takes to compute the hash. It is on a logarithmic scale of 2^cost and determines how many times the data is put through the hashing algorithm. For example, at a cost of 10, you are able to hash 10 passwords a second on an average computer, however, at a cost of 15, it takes 3 seconds per hash... and to take it further, at a cost of 31, it would take multiple days to complete a hash. A cost of 12 is considered very secure at this time. The last portion of your hash <code>$ZyprE5MRw2Q3WpNOGZWGbeG7ADUre1Q8QO.uUUtcbqloU0yvzavOm</code>, looks like one large string of numbers, periods, and letters, but it is actually two separate pieces of information. The first 22 characters is the salt in plain text, and the rest is the hashed password!</p>

<p><strong>Add all your code for these lessons in the server.js file between the code we have started you off with.</strong>  
Do not change or delete the code we have added for you.</p>

<p><strong>As a reminder, this project is being built upon the following starter project on Gitpod, or cloned from GitHub.</strong></p>

<p><strong>As hashing is designed to be computationally intensive, it is recommended to do so asynchronously on your server as to avoid blocking incoming connections while you hash.</strong></p>  
<ul>
  <li>All you have to do to hash a password asynchronously is call:</li>
</ul>
<pre><code>bcrypt.hash(myPlaintextPassword, saltRounds, (err, hash) => {
  /*Store hash in your db*/
});
</code></pre>
<p>Add this hashing function to your server (we've already defined the variables used in the function for you to use) and log it to the console for you to see! At this point, you would normally save the hash to your database.</p>

<p><strong>Now when you need to figure out if a new input is the same data as the hash you would just use the compare function.</strong></p>

<p><strong>Hashing synchronously is just as easy to do but can cause lag if using it server side with a high cost or with hashing done very often.</strong></p>  
<ul>
  <li>Hashing with this method is as easy as calling:</li>
</ul>
<pre><code>var hash = bcrypt.hashSync(myPlaintextPassword, saltRounds);
</code></pre>
<p>Add this method of hashing to your code and then log the result to the console. Again, the variables used are already defined in the server so you won't need to adjust them. You may notice even though you are hashing the same password as in the async function, the result in the console is different—this is due to the salt being randomly generated each time as seen by the first 22 characters in the third string of the hash. Now to compare a password input with the new sync hash, you would use the <code>compareSync</code> method:</p>
<pre><code>var result = bcrypt.compareSync(myPlaintextPassword, hash);
</code></pre>
<ul>
  <li>with the result being a boolean true or false.</li>
</ul>
<p>Add the function in and log the result to the console to see it working.</p>

<p><strong>Submit your page when you think you've got it right.</strong></p>

<pre><code>bcrypt.compare(myPlaintextPassword, hash, (err, res) => {
  /*res == true or false*/
});
</code></pre>
<p>Add this into your existing hash function (since you need to wait for the hash to complete before calling the compare function) after you log the completed hash and log 'res' to the console within the compare. You should see in the console a hash, and then 'true' is printed! If you change 'myPlaintextPassword' in the compare function to 'someOtherPlaintextPassword', then it should say false.</p>

<pre><code>bcrypt.hash('passw0rd!', 13, (err, hash) => {
  console.log(hash);
  //$2a$12$Y.PHPE15wR25qrrtgGkiYe2sXo98cjuMCG1YwSI5rJW1DSJp0gEYS
  bcrypt.compare('passw0rd!', hash, (err, res) => {
    console.log(res); //true
  });
});
</code></pre>

<p><strong>Submit your page when you think you've got it right.</strong></p>

<p><strong>BCrypt has already been added as a dependency, so require it as bcrypt in your server.</strong></p>

<p><strong>Submit your page when you think you've got it right.</strong></p>
