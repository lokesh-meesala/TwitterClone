# TwitterClone

## Execution Steps:
1. first create an environment to run the server in one terminal using the command:
erl -sname server
2. open two different terminals and run the following commands to start to clients:
erl -sname client1
erl -sname client2
3. compile the two-erlang file twitter_server.erl and twitter_client.erl using the command:
c(filename).
4. then start the main server using the command
twitter_server:start().
5. On the client terminals we execute following command to start the clients.
twitter_client:start().
## Demo Link:
https://www.youtube.com/watch?v=4ipU56Yt9jo
## Implemented Functionalities:
I have developed the twitter clone by using the web socket interfaces in the erlang using the WebSharper interface and used in-built erlang socket functionalities such as Client_Socket_Mapping, ListenSocket and await_connections functions. I had used ets for the in-built erlang storage BIFs to store the user and tweet information. After starting the client terminals, the prompts ask for commands to run. There are few predefined operation commands we use to show the implemented functionalities. The commands are
1. Register
2. Login
3. Tweet
4. Subscribe
5. Retweet
6. Query
7. Logout
## Register:
On giving the ‘register’ command, the terminal prompts to give user name and the server checks with the internal erlang database. If the user does not exist, then server creates the user and returns ‘Registered your Account!’ and if exists, then returns already exists message. This whole process related messages are also displayed promptly on server terminal. In the below demo, we have registered two users ‘Ahamad’ and ‘Lokesh’ and the accounts are registered successfully.
## Login:
After giving ‘Login’ command, the terminal prompts for username and after giving the username it gives ‘Signed into the account’ and appropriate process flow messages are printed on server terminal. In the demo screenshot, the users Ahamad and Lokesh are successfully signed in.
## Tweet:
After giving ‘Tweet’ command the terminal asks for the message to be tweeted and returns ‘Tweet Sent’ message and respective messages on the server terminal.
The tweets can also include hashtags and mentions.
If any other user subscribed to the tweeted account, the tweet is displayed on the other terminal as well with the message ‘Received a new tweet!’
In the demo given below, ahamad has sent a tweet and as Lokesh is subscribed to ahamad the tweet is displayed on the other terminal without any prompt. Also Lokesh has mentioned ahamad in the tweet as @Ahamad.
## Subscribe:
When ‘Subscribe’ command is used, the terminal asks for the username to subscribe to and returns ‘Subscribed!’ message on the terminal. The demo screenshot shows that Ahamad is subscribed to Lokesh and vice versa.
## Retweet:
By this ‘retweet’ option, the terminal takes details such as username of the user whose tweet you are retweeting and the message as well. After getting the details, ‘Retweeted’ message is displayed on the client and the request information is printed on server terminal.
Demo screenshot shows the retweeting the tweet of Ahamad by Lokesh.
## Query:
The query functionality returns 3 querying options for the user.
• My mentions: This option can be accessed by giving the option ‘1’ in the terminal and the result returns all the tweets mentioning the querying user to the terminal. The query operations and the information regarding the query is returned as JSON based API model on the server terminal. Demo screenshot shows the tweets Ahamad has mentioned in the terminal of Lokesh and other way as well.
• Hashtag Search: This option is enabled by the option ‘2’ in the terminal and the server asks for the hashtag string to be searched. The server searches through the database for the tweets including the hashtag and returns the tweets on the terminal. Demo screenshot shows the example of searching the tweets for the hashtags search strings Ahamad and Lokesh.
• Subscribed user Tweets: This option is accessed by the number ‘3’ and asks the client to see the subscribed user whose tweets needs to be displayed. After this the server extracts the tweets of the user from the database and displayed them on the server. The request and query flow are displayed on the server terminal. Demo shows the tweets of Lokesh to ahamad as a subscribed user.
## Logout:
The command ‘logout’ returns that ‘user is logged out successfully’ after logging out the user.
