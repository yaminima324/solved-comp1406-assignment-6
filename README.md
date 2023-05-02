Download Link: https://assignmentchef.com/product/solved-comp1406-assignment-6
<br>
In this assignment, you will simulate an on-line music centre called the <strong>MusicExchangeCenter</strong> where <strong>Users</strong> log in and download <strong>Songs</strong> from other  user’s computers.   It is similar to the operation of the original Napster program  that operated a few years ago where users shared songs.   You won’t be doing  any downloading or internet programming.  Instead, you will just simulate what happens in real life.   The  assignment will give you familiarity with <strong>ArrayLists</strong>.

<h1>(1) The Song/ User Classes</h1>

Here are simple <strong>Song</strong> and <strong>User</strong> classes that represent a song that is available at the Music Exchange Center and a user of the Music Exchange Center that logs in to download music:




<strong>public class </strong>Song {     <strong>private </strong>String      <strong>title</strong>;     <strong>private </strong>String      <strong>artist</strong>;     <strong>private int         </strong><strong>duration</strong>;




<strong>public </strong>Song()  {         <strong>this</strong>(<strong>“”</strong>, <strong>“”</strong>, 0, 0);

}

<strong>public </strong>Song(String t, String a, <strong>int </strong>m, <strong>int </strong>s)  {         <strong>title </strong>= t;         <strong>artist </strong>= a;

<strong>duration </strong>= m * 60 + s;

}      <strong>public </strong>String getTitle() { <strong>return </strong><strong>title</strong>; }     <strong>public </strong>String getArtist() { <strong>return </strong><strong>artist</strong>; }     <strong>public int </strong>getDuration() { <strong>return </strong><strong>duration</strong>; }

<strong>public int </strong>getMinutes() {         <strong>return </strong><strong>duration </strong>/ 60;

}      <strong>public int </strong>getSeconds() {         <strong>return </strong><strong>duration </strong>% 60;

}

<strong>public </strong>String toString()  {         <strong>return</strong>(<strong>“</strong><strong>”</strong><strong>” </strong>+ <strong>title </strong>+ <strong>“</strong><strong>”</strong><strong> by ” </strong>+ <strong>artist </strong>+ <strong>” ” </strong>


(<strong>duration </strong>/ 60) + <strong>“:” </strong>+ (<strong>duration</strong>%60));

} } <strong>public class </strong>User {  <strong>private </strong>String <strong>userName</strong>;

<strong>private boolean </strong><strong>online</strong>;




<strong>public </strong>User()  { <strong>this</strong>(<strong>“”</strong>); }




<strong>public </strong>User(String u)  {        <strong>userName </strong>= u;

<strong>online </strong>= <strong>false</strong>;

}

<strong>public </strong>String getUserName() { <strong>return </strong><strong>userName</strong>; }  <strong>public boolean </strong>isOnline() { <strong>return </strong><strong>online</strong>; }




<strong>public </strong>String toString()  {

String s = <strong>“” </strong>+ <strong>userName </strong>+ <strong>“: XXX songs (“</strong>;   <strong>if </strong>(!<strong>online</strong>) s += <strong>“not “</strong>;

<strong>return </strong>s + <strong>“online)”</strong>;

}

}




Do the following in the <strong>User</strong> class:




<ul>

 <li>Add a <strong>songList</strong> attribute which is an <strong>ArrayList</strong> of <strong>Song</strong> This list will contain all the songs that this user has on his/her hard drive to be made available to the Music Exchange Center community.  Adjust the 2nd constructor to ensure that this attribute is initialized properly.  Write a get method for the attribute as well.</li>

 <li>Adjust the <strong>toString()</strong> method so that the XXX is replaced by the number of songs available in his/her song list.</li>

 <li>Create a method called <strong>addSong(Song s)</strong> which adds a given song to the user’s song list.</li>

 <li>Create a method called <strong>totalSongTime()</strong> that returns an integer indicating the total duration (i.e., amount of time) (in seconds) that all of the user’s songs would require if played.</li>

</ul>




________________________________________________________________________________




<h1>(2) The MusicExchangeCenter Class <sub> </sub></h1>

Implement a class called <strong>MusicExchangeCenter</strong> which represents  the company website that users log in and out of in order to  download music.   The class should have this attribute:




<ul>

 <li><strong><u>users</u></strong> – an <strong>ArrayList</strong> of all registered <strong>Users</strong> (which may be either logged on or not logged on).</li>

</ul>




Create the following methods:

<ul>

 <li>A zero-parameter constructor that sets attributes properly.</li>

 <li>An <strong>onlineUsers()</strong> method that returns an <strong>ArrayList</strong> of all <strong>Users</strong> that are currently online.  Note that this method creates and returns a new <strong>ArrayList</strong> each  time it is called.</li>

 <li>An <strong>allAvailableSongs()</strong> method that returns a new <strong>ArrayList</strong> of all <strong>Songs</strong> currently available for download (i.e., all songs that are available from all logged-on users). Note that this method creates and returns a new <strong>ArrayList</strong> each time it is called.</li>

 <li>A <strong>toString()</strong> method that returns a string representation of the music center showing the number of users currently online as well as the number of songs currently available.</li>

</ul>

(e.g., <strong>“Music Exchange Center (3 users on line, 15 songs available)”</strong>).

<ul>

 <li>A <strong>userWithName(String s)</strong> method that finds and returns the user object with the given name if it is in the list of users. If not there, <strong>null</strong> should be returned.</li>

 <li>A <strong>registerUser(User x)</strong> method that adds a given <strong>User</strong> to the music center’s list of users, provided that there are no other users with the same userName.   If there are other users with the same userName, then this method does nothing. Use the <strong>userWithName()</strong> method above.</li>

 <li>An <strong>availableSongsByArtist(String artist)</strong> method that returns a new <strong>ArrayList</strong> of all <strong>Songs</strong> currently available for download by the specified artist. Note that this method creates and returns a new <strong>ArrayList</strong> each time it is called.</li>

</ul>

Go back to the <strong>User</strong> class and add these methods:

<ul>

 <li>A <strong>register(MusicExchangeCenter m)</strong> that makes use of the <strong>registerUser()</strong> method that you just wrote to register the user into the given <strong>MusicExchangeCenter</strong> <strong>m</strong>. (Note that this should be a one-line method).</li>

 <li>A <strong>logon(MusicExchangeCenter m)</strong> that simulates a user going online with the given music center.  (Assume that users can log onto at most one music center at a time).   Make use of the <strong>userWithName()</strong> method you wrote earlier.   Only allow the user to log on if he/she has already registered.</li>

 <li>A <strong>logoff(MusicExchangeCenter m)</strong> that simulates a user going offline from the given music center. Make use of the <strong>userWithName()</strong> method you wrote earlier.</li>

</ul>

Now we will test our code.   Since we will be testing our classes with the same users, you must add the following <strong>static</strong> methods to the <strong>User</strong> class (Each method creates and returns a unique user with some songs in their song list):




<em>// Various Users for test purposes </em><strong>public static </strong>User DiscoStew() {

User  discoStew = <strong>new </strong>User(<strong>“Disco Stew”</strong>);

discoStew.addSong(<strong>new </strong>Song(<strong>“Hey Jude”</strong>, <strong>“The Beatles”</strong>, 4, 35));     discoStew.addSong(<strong>new </strong>Song(<strong>“Barbie Girl”</strong>, <strong>“Aqua”</strong>, 3, 54));     discoStew.addSong(<strong>new </strong>Song(<strong>“Only You Can Rock Me”</strong>, <strong>“UFO”</strong>, 4, 59));     discoStew.addSong(<strong>new </strong>Song(<strong>“Paper Soup Cats”</strong>, <strong>“Jaw”</strong>, 4, 18));     <strong>return </strong>discoStew;

}

<strong>public static </strong>User SleepingSam() {

User sleepingSam = <strong>new </strong>User(<strong>“Sleeping Sam”</strong>);

sleepingSam.addSong(<strong>new </strong>Song(<strong>“Meadows”</strong>, <strong>“Sleepfest”</strong>, 7, 15));     sleepingSam.addSong(<strong>new </strong>Song(<strong>“Calm is Good”</strong>, <strong>“Waterfall”</strong>, 6, 22));     <strong>return </strong>sleepingSam;

}

<strong>public static </strong>User RonnieRocker() {

User ronnieRocker = <strong>new </strong>User(<strong>“Ronnie Rocker”</strong>);

ronnieRocker.addSong(<strong>new </strong>Song(<strong>“Rock is Cool”</strong>, <strong>“Yeah”</strong>, 4, 17));

ronnieRocker.addSong(<strong>new </strong>Song(<strong>“My Girl is Mean to Me”</strong>, <strong>“Can’t Stand Up”</strong>, 3, 29));     ronnieRocker.addSong(<strong>new </strong>Song(<strong>“Only You Can Rock Me”</strong>, <strong>“UFO”</strong>, 4, 52));

ronnieRocker.addSong(<strong>new </strong>Song(<strong>“We’re Not Gonna Take It”</strong>, <strong>“Twisted Sister”</strong>, 3, 9));     <strong>return </strong>ronnieRocker;

}

<strong>public static </strong>User CountryCandy() {

User countryCandy = <strong>new </strong>User(<strong>“Country Candy”</strong>);

countryCandy.addSong(<strong>new </strong>Song(<strong>“If I Had a Hammer”</strong>, <strong>“Long Road”</strong>, 4, 15));     countryCandy.addSong(<strong>new </strong>Song(<strong>“My Man is a 4×4 Driver”</strong>, <strong>“Ms. Lonely”</strong>, 3, 7));     countryCandy.addSong(<strong>new </strong>Song(<strong>“This Song is for Johnny”</strong>, <strong>“Lone Wolf”</strong>, 4, 22));     <strong>return </strong>countryCandy;

}

<strong>public static </strong>User PeterPunk() {

User peterPunk = <strong>new </strong>User(<strong>“Peter Punk”</strong>);

peterPunk.addSong(<strong>new </strong>Song(<strong>“Bite My Arms Off”</strong>, <strong>“Jaw”</strong>, 4, 12));     peterPunk.addSong(<strong>new </strong>Song(<strong>“Where’s My Sweater”</strong>, <strong>“The Knitters”</strong>, 3, 41));     peterPunk.addSong(<strong>new </strong>Song(<strong>“Is that My Toenail ?”</strong>, <strong>“Clip”</strong>, 4, 47));     peterPunk.addSong(<strong>new </strong>Song(<strong>“Anvil Headache”</strong>, <strong>“Clip”</strong>, 4, 34));     peterPunk.addSong(<strong>new </strong>Song(<strong>“My Hair is on Fire”</strong>, <strong>“Jaw”</strong>, 3, 55));     <strong>return </strong>peterPunk;

}




Now test your code with the following test program:




<strong>public class </strong>MusicExchangeTestProgram {     <strong>public static void </strong>main(String args[]) {         <em>// Create a new music exchange center </em>

<em>        </em>MusicExchangeCenter   mec = <strong>new </strong>MusicExchangeCenter();

<em>// Create some users and give them some songs </em>

<em>        </em>User discoStew = User.<em>DiscoStew</em>();

User sleepingSam = User.<em>SleepingSam</em>();

User ronnieRocker = User.<em>RonnieRocker</em>();

User countryCandy = User.<em>CountryCandy</em>();

User peterPunk = User.<em>PeterPunk</em>();




<em>// Register the users, except SleepingSam         </em>discoStew.register(mec);         ronnieRocker.register(mec);         countryCandy.register(mec);         peterPunk.register(mec);




<em>// Display the state of things before anyone logs on </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“Status: ” </strong>+ mec);

System.<strong><em>out</em></strong>.println(<strong>“On-Line Users: ” </strong>+ mec.onlineUsers());

System.<strong><em>out</em></strong>.println(<strong>“Available Songs: ” </strong>+ mec.allAvailableSongs() + <strong>“</strong><strong>
</strong><strong>“</strong>);

<em>// Attempt to log on two registered users and one unregistered user         </em>discoStew.logon(mec);

sleepingSam.logon(mec); <em>// Should not work         </em>ronnieRocker.logon(mec);

System.<strong><em>out</em></strong>.println(<strong>“Status: ” </strong>+ mec);

System.<strong><em>out</em></strong>.println(<strong>“On-Line Users: ” </strong>+ mec.onlineUsers());

System.<strong><em>out</em></strong>.println(<strong>“Available Songs: ” </strong>+ mec.allAvailableSongs() + <strong>“</strong><strong>
</strong><strong>“</strong>);

<em>// Log on two more users         </em>countryCandy.logon(mec);         peterPunk.logon(mec);

System.<strong><em>out</em></strong>.println(<strong>“Status: ” </strong>+ mec);

System.<strong><em>out</em></strong>.println(<strong>“On-Line Users: ” </strong>+ mec.onlineUsers());

System.<strong><em>out</em></strong>.println(<strong>“Available Songs: ” </strong>+ mec.allAvailableSongs());         System.<strong><em>out</em></strong>.println(<strong>“Available Songs By Jaw: ” </strong>


mec.availableSongsByArtist(<strong>“Jaw”</strong>) + <strong>“</strong><strong>
</strong><strong>“</strong>);

<em>// Log off three users (one is not even logged in)         </em>countryCandy.logoff(mec);         discoStew.logoff(mec);         sleepingSam.logoff(mec);

System.<strong><em>out</em></strong>.println(<strong>“Status: ” </strong>+ mec);

System.<strong><em>out</em></strong>.println(<strong>“On-Line Users: ” </strong>+ mec.onlineUsers());

System.<strong><em>out</em></strong>.println(<strong>“Available Songs: ” </strong>+ mec.allAvailableSongs());

System.<strong><em>out</em></strong>.println(<strong>“Available Songs By Jaw: ” </strong>


mec.availableSongsByArtist(<strong>“Jaw”</strong>) + <strong>“</strong><strong>
</strong><strong>“</strong>);

<em>// Log off the last two users         </em>peterPunk.logoff(mec);         ronnieRocker.logoff(mec);

System.<strong><em>out</em></strong>.println(<strong>“Status: ” </strong>+ mec);

System.<strong><em>out</em></strong>.println(<strong>“On-Line Users: ” </strong>+ mec.onlineUsers());

System.<strong><em>out</em></strong>.println(<strong>“Available Songs: ” </strong>+ mec.allAvailableSongs());         System.<strong><em>out</em></strong>.println(<strong>“Available Songs By Jaw: ” </strong>


mec.availableSongsByArtist(<strong>“Jaw”</strong>) + <strong>“</strong><strong>
</strong><strong>“</strong>);

}

}







Here is the output that you should see:




Status: Music Exchange Center (0 users on-line, 0 songs available)

On-Line Users: []

Available Songs: []




Status: Music Exchange Center (2 users on-line, 8 songs available)

On-Line Users: [Disco Stew: 4 songs (online), Ronnie Rocker: 4 songs (online)]

Available Songs: [“Hey Jude” by The Beatles 4:35, “Barbie Girl” by Aqua 3:54, “Only You Can Rock

Me” by UFO 4:59, “Paper Soup Cats” by Jaw 4:18, “Rock is Cool” by Yeah 4:17, “My Girl is Mean to Me” by Can’t Stand Up 3:29, “Only You Can Rock Me” by UFO 4:52, “We’re Not Gonna Take It” by

Twisted Sister 3:9]




Status: Music Exchange Center (4 users on-line, 16 songs available)

On-Line Users: [Disco Stew: 4 songs (online), Ronnie Rocker: 4 songs (online), Country Candy: 3 songs (online), Peter Punk: 5 songs (online)]

Available Songs: [“Hey Jude” by The Beatles 4:35, “Barbie Girl” by Aqua 3:54, “Only You Can Rock

Me” by UFO 4:59, “Paper Soup Cats” by Jaw 4:18, “Rock is Cool” by Yeah 4:17, “My Girl is Mean to

Me” by Can’t Stand Up 3:29, “Only You Can Rock Me” by UFO 4:52, “We’re Not Gonna Take It” by

Twisted Sister 3:9, “If I Had a Hammer” by Long Road 4:15, “My Man is a 4×4 Driver” by Ms. Lonely

3:7, “This Song is for Johnny” by Lone Wolf 4:22, “Bite My Arms Off” by Jaw 4:12, “Where’s My

Sweater” by The Knitters 3:41, “Is that My Toenail ?” by Clip 4:47, “Anvil Headache” by Clip 4:34, “My Hair is on Fire” by Jaw 3:55]

Available Songs By Jaw: [“Paper Soup Cats” by Jaw 4:18, “Bite My Arms Off” by Jaw 4:12, “My Hair is on Fire” by Jaw 3:55]




Status: Music Exchange Center (2 users on-line, 9 songs available)

On-Line Users: [Ronnie Rocker: 4 songs (online), Peter Punk: 5 songs (online)]

Available Songs: [“Rock is Cool” by Yeah 4:17, “My Girl is Mean to Me” by Can’t Stand Up 3:29,

“Only You Can Rock Me” by UFO 4:52, “We’re Not Gonna Take It” by Twisted Sister 3:9, “Bite My Arms

Off” by Jaw 4:12, “Where’s My Sweater” by The Knitters 3:41, “Is that My Toenail ?” by Clip 4:47,

“Anvil Headache” by Clip 4:34, “My Hair is on Fire” by Jaw 3:55]

Available Songs By Jaw: [“Bite My Arms Off” by Jaw 4:12, “My Hair is on Fire” by Jaw 3:55]

Status: Music Exchange Center (0 users on-line, 0 songs available)

On-Line Users: []

Available Songs: []

Available Songs By Jaw: []

________________________________________________________________________________




<h2>(3) Downloading Music</h2>

Go back to the <strong>Song</strong> class and add to it an attribute called <strong>owner</strong> which will be a <strong>User</strong> object representing the user who happens to own this copy of this song.

Note that a <strong>Song</strong> object may only be owned by one <strong>User</strong> and that many users can have copies of the same song.   Set it to <strong>null</strong> initially.   In the <strong>User</strong> class, adjust the <strong>addSong() </strong>method so that it sets the owner properly.

In the <strong>User</strong> class, add a method called <strong>requestCompleteSonglist(MusicExchangeCenter m)</strong>.  This method should gather the list of <u>all available songs from all users that are online</u> at the given music exchange center (i.e., the union of all of their local song lists), and then return an <strong>ArrayList&lt;String&gt;</strong> formatted as follows:




TITLE                          ARTIST          TIME   OWNER




<ol>

 <li>Hey Jude The Beatles      4:35   Disco Stew    2. Barbie Girl                    Aqua             3:54   Disco Stew    3. Only You Can Rock Me           UFO              4:59   Disco Stew</li>

 <li>Paper Soup Cats Jaw              4:18   Disco Stew</li>

 <li>Rock is Cool               Yeah             4:17   Ronnie Rocker    My Girl is Mean to Me          Can’t Stand Up   3:29   Ronnie Rocker    7. Only You Can Rock Me           UFO              4:52   Ronnie Rocker</li>

 <li>We’re Not Gonna Take It Twisted Sister   3:09   Ronnie Rocker etc..</li>

</ol>

Notice that the songs are numbered and that the title, artist, time and owner are all lined up nicely.   You should use the <strong>String.format()</strong> method as described in the notes.   Recall that <strong>%-30s</strong> in the format string will allow you to display a left-justified 30-character string.   Also, <strong>%2d</strong> and <strong>%02d</strong> will allow you to display numbers so that they take 2 places, the 0 indicating that a leading zero character is desired.

In the <strong>User</strong> class, add a method called <strong>requestSonglistByArtist(MusicExchangeCenter m, String artist)</strong>.  This method should gather the list of <u>all available songs <strong>by the given artist</strong> from all users that</u> <u>are online </u>at the given music exchange center (i.e., the union of all of their local song lists), and then return an <strong>ArrayList&lt;String&gt;</strong> formatted similar to that shown above.

In the <strong>MusicExchangeCenter</strong> class, add a method called <strong>getSong(String title, String ownerName)</strong> which returns the <strong>Song</strong> object with the given <strong>title</strong> owned by the user with the given <strong>ownerName</strong>, provided that the user is currently online and that the song exists.  Return <strong>null</strong> otherwise.  (<u>Hint</u>: you will need to search through the center’s <strong>users</strong> to find <strong>User</strong> with the matching <strong>ownerName</strong> and then search through that user’s songs to find the <strong>Song</strong> with the given <strong>title</strong>.  It may be a good idea to write an extra helper method in the <strong>User</strong> class called <strong>songWithTitle()</strong> that you can make use of).




In the <strong>User</strong> class, add a <strong>downloadSong(MusicExchangeCenter m, String title, String ownerName)</strong> method that simulates the downloading of one of the songs in the catalog.   It should use the <strong>getSong() </strong>method that you just wrote, and add the downloaded song to the user’s <strong>songList</strong> (if not <strong>null</strong>).

Test your code now with the following program:

<strong>import </strong>java.util.ArrayList;




<strong>public class </strong>MusicExchangeTestProgram2 {     <strong>public static void </strong>main(String args[]) {

ArrayList&lt;String&gt; catalog;




<em>// Create a new music exchange center </em>

<em>        </em>MusicExchangeCenter   mec = <strong>new </strong>MusicExchangeCenter();

<em>// Create some users and give them some songs </em>

<em>        </em>User discoStew = User.<em>DiscoStew</em>();

User sleepingSam = User.<em>SleepingSam</em>();

User ronnieRocker = User.<em>RonnieRocker</em>();

User countryCandy = User.<em>CountryCandy</em>();

User peterPunk = User.<em>PeterPunk</em>();




<em>// Register the users         </em>discoStew.register(mec);         ronnieRocker.register(mec);         sleepingSam.register(mec);         countryCandy.register(mec);         peterPunk.register(mec);




<em>// Log on all users </em>

<em>        </em>discoStew.logon(mec);         sleepingSam.logon(mec);         ronnieRocker.logon(mec);         countryCandy.logon(mec);         peterPunk.logon(mec);

System.<strong><em>out</em></strong>.println(<strong>“Status: ” </strong>+ mec);




<em>// Simulate a user requesting a list of songs         </em>catalog = discoStew.requestCompleteSonglist(mec);         System.<strong><em>out</em></strong>.println(<strong>“Complete Song List: “</strong>);         <strong>for </strong>(String s: catalog)

System.<strong><em>out</em></strong>.println(<strong>”  ” </strong>+ s);




<em>// Simulate a user downloading 3 songs from the list </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Disco Stew before downloading: ” </strong>+ discoStew);         discoStew.downloadSong(mec, <strong>“Bite My Arms Off”</strong>, <strong>“Peter Punk”</strong>);         discoStew.downloadSong(mec, <strong>“Meadows”</strong>, <strong>“Sleeping Sam”</strong>);         discoStew.downloadSong(mec, <strong>“If I Had a Hammer”</strong>, <strong>“Country Candy”</strong>);         discoStew.downloadSong(mec, <strong>“Sandy Toes”</strong>, <strong>“Country Candy”</strong>);         ronnieRocker.logoff(mec); <em>// log off Ronnie, next download should fail         </em>discoStew.downloadSong(mec, <strong>“Only You Can Rock Me”</strong>, <strong>“Ronnie Rocker”</strong>);         System.<strong><em>out</em></strong>.println(<strong>“Disco Stew after downloading: ” </strong>+ discoStew);

ronnieRocker.logon(mec); <em>// log on Ronnie, next download should work         </em>discoStew.downloadSong(mec, <strong>“Only You Can Rock Me”</strong>, <strong>“Ronnie Rocker”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Disco Stew after downloading Ronnie’s: ” </strong>+ discoStew + <strong>“</strong><strong>
</strong><strong>“</strong>);

<em>// Simulate a user requesting a list of songs by a specific artist </em>

<em>        </em>catalog = discoStew.requestSonglistByArtist(mec, <strong>“Jaw”</strong>);

System.<strong><em>out</em></strong>.println(<strong>“Song’s by Jaw: “</strong>);         <strong>for </strong>(String s: catalog)

System.<strong><em>out</em></strong>.println(<strong>”  ” </strong>+ s);

} }




Here is the expected output:




Status: Music Exchange Center (5 users on-line, 18 songs available)

Complete Song List:

TITLE                          ARTIST           TIME   OWNER

<ol>

 <li>Hey Jude The Beatles      4:35   Disco Stew    2. Barbie Girl                    Aqua             3:54   Disco Stew    3. Only You Can Rock Me           UFO              4:59   Disco Stew</li>

 <li>Paper Soup Cats Jaw              4:18   Disco Stew</li>

 <li>Rock is Cool Yeah             4:17   Ronnie Rocker    My Girl is Mean to Me          Can’t Stand Up   3:29   Ronnie Rocker    7. Only You Can Rock Me           UFO              4:52   Ronnie Rocker</li>

 <li>We’re Not Gonna Take It Twisted Sister   3:09   Ronnie Rocker</li>

 <li>Meadows Sleepfest        7:15   Sleeping Sam</li>

 <li>Calm is Good Waterfall        6:22   Sleeping Sam</li>

 <li>If I Had a Hammer Long Road        4:15   Country Candy   My Man is a 4×4 Driver         Ms. Lonely       3:07   Country Candy</li>

 <li>This Song is for Johnny Lone Wolf        4:22   Country Candy</li>

 <li>Bite My Arms Off Jaw              4:12   Peter Punk   Where’s My Sweater             The Knitters     3:41   Peter Punk   16. Is that My Toenail ?           Clip             4:47   Peter Punk   17. Anvil Headache                 Clip             4:34   Peter Punk</li>

 <li>My Hair is on Fire Jaw              3:55   Peter Punk</li>

</ol>

Disco Stew before downloading: Disco Stew: 4 songs (online)

Disco Stew after downloading: Disco Stew: 7 songs (online)

Disco Stew after downloading Ronnie’s: Disco Stew: 8 songs (online)

Song’s by Jaw:

TITLE                          ARTIST           TIME   OWNER

<ol>

 <li>Paper Soup Cats Jaw              4:18   Disco Stew</li>

 <li>Bite My Arms Off Jaw              4:12   Disco Stew</li>

 <li>Bite My Arms Off Jaw              4:12   Peter Punk</li>

 <li>My Hair is on Fire Jaw              3:55   Peter Punk</li>

</ol>

________________________________________________________________________________




<h2>(4) Paying the Price</h2>

Now….in order to make all of this legal, we must have a way to compensate the musical artists for their hard work and wonderful music.   The compensation depends on many factors.   An artist should receive 25 cents each time one of their songs is downloaded.   Hence, for each artist, we will keep track of how much money in <u>royalties</u> they have.    Add the following attributes to the <strong>MusicExchangeCenter</strong> class:

<strong><u>royalties</u></strong> – a <strong>HashMap</strong> with the artist’s name as the keys and the values are floats representing the total amount of royalties for that artist so far.  It should only contain artists who have had songs downloaded.

<strong><u>downloadedSongs</u></strong> – an <strong>ArrayList&lt;Song&gt;</strong> containing all of the songs that have been downloaded.   This list will, in general, contain duplicate <strong>Song</strong> objects.

Write a method in the <strong>MusicExchangeCenter</strong> class called <strong>displayRoyalties()</strong> that displays the royalties for all artists who have had <u>at least one of their songs downloaded</u>.   It should display a two-line header and then one line per artist showing the royalty amount as well as the artist name as follows:

Amount  Artist

—————

$0.75   Sleepfest

$1.50   Clip

$0.25   Jaw

$0.50   Long Road

$0.25   Yeah

$0.25   UFO




In the <strong>getSong()</strong> method in the <strong>MusicExchangeCenter</strong>, adjust the code so that if the song is found (i.e., able to be downloaded), then it is added to the <strong><u>downloadedSongs</u></strong> list.   Write the get method for the <strong><u>downloadedSongs</u></strong> attribute.

Write a method in the <strong>MusicExchangeCenter</strong> class called <strong>uniqueDownloads()</strong> that <u>returns</u> (i.e., not <u>displays</u>) a <strong>TreeSet</strong> of all downloaded <strong>Song</strong> objects such that the set is sorted alphabetically by song title.  There should be no duplicates songs in this set.

Write a method in the <strong>MusicExchangeCenter</strong> class called <strong>songsByPopularity()</strong> that <u>returns</u> (i.e., not <u>displays</u>) an <strong>ArrayList</strong> of <strong>Pair</strong> objects where the <u>key</u> of the pair is an <strong>Integer</strong> and the <u>value</u> is the <strong>Song</strong> object.   The integer <u>key</u> should represent the number of times that that song was downloaded.   The list returned should be sorted in decreasing order according to the number of times the song was downloaded.   To sort a list of Pair objects, you can use the following code:

Collections.<em>sort</em>(popular, <strong>new </strong>Comparator&lt;Pair&lt;Integer, Song&gt;&gt;() {     <strong>public int </strong>compare(Pair&lt;Integer, Song&gt; p1, Pair&lt;Integer, Song&gt; p2) {

// PUT YOUR CODE IN HERE

}

});

Just insert the missing code so that it returns an appropriate integer indicating whether pair <strong>p1</strong> comes before or after pair <strong>p2</strong> in the sort order (see notes page 281).




Here is a test program … make sure it works with your code:




<strong>import </strong>javafx.util.Pair;




<strong>public class </strong>MusicExchangeTestProgram3 {     <strong>public static void </strong>main(String args[]) {         <em>// Create a new music exchange center </em>

<em>        </em>MusicExchangeCenter   mec = <strong>new </strong>MusicExchangeCenter();




<em>// Create some users and give them some songs </em>

<em>        </em>User discoStew = User.<em>DiscoStew</em>();

User sleepingSam = User.<em>SleepingSam</em>();

User ronnieRocker = User.<em>RonnieRocker</em>();

User countryCandy = User.<em>CountryCandy</em>();

User peterPunk = User.<em>PeterPunk</em>();




<em>// Register the users         </em>discoStew.register(mec);         ronnieRocker.register(mec);         sleepingSam.register(mec);         countryCandy.register(mec);         peterPunk.register(mec);




<em>// Log on all users         </em>discoStew.logon(mec);         sleepingSam.logon(mec);         ronnieRocker.logon(mec);         countryCandy.logon(mec);         peterPunk.logon(mec);

System.<strong><em>out</em></strong>.println(<strong>“Status: ” </strong>+ mec);




<em>// Simulate users downloading various songs </em>

<em>        </em>discoStew.downloadSong(mec, <strong>“Bite My Arms Off”</strong>, <strong>“Peter Punk”</strong>);         discoStew.downloadSong(mec, <strong>“Meadows”</strong>, <strong>“Sleeping Sam”</strong>);         discoStew.downloadSong(mec, <strong>“If I Had a Hammer”</strong>, <strong>“Country Candy”</strong>);         discoStew.downloadSong(mec, <strong>“Is that My Toenail ?”</strong>, <strong>“Peter Punk”</strong>);         sleepingSam.downloadSong(mec, <strong>“Anvil Headache”</strong>, <strong>“Peter Punk”</strong>);         sleepingSam.downloadSong(mec, <strong>“Is that My Toenail ?”</strong>, <strong>“Disco Stew”</strong>);         sleepingSam.downloadSong(mec, <strong>“If I Had a Hammer”</strong>, <strong>“Country Candy”</strong>);         countryCandy.downloadSong(mec, <strong>“Anvil Headache”</strong>, <strong>“Peter Punk”</strong>);         countryCandy.downloadSong(mec, <strong>“Meadows”</strong>, <strong>“Sleeping Sam”</strong>);         countryCandy.downloadSong(mec, <strong>“If I Had a Hammer”</strong>, <strong>“Peter Punk”</strong>);         countryCandy.downloadSong(mec, <strong>“Only You Can Rock Me”</strong>, <strong>“Ronnie Rocker”</strong>);         countryCandy.downloadSong(mec, <strong>“Is that My Toenail ?”</strong>, <strong>“Disco Stew”</strong>);         peterPunk.downloadSong(mec, <strong>“Is that My Toenail ?”</strong>, <strong>“Country Candy”</strong>);         peterPunk.downloadSong(mec, <strong>“Rock is Cool”</strong>, <strong>“Ronnie Rocker”</strong>);         peterPunk.downloadSong(mec, <strong>“What?”</strong>, <strong>“Ronnie Rocker”</strong>);         peterPunk.downloadSong(mec, <strong>“Meadows”</strong>, <strong>“Sleeping Sam”</strong>);




<em>// Display the downloaded songs </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are the downloaded songs: “</strong>);

<strong>for </strong>(Song s: mec.getDownloadedSongs())

System.<strong><em>out</em></strong>.println(s);




<em>// Display the downloaded songs alphabetically </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are the unique downloaded songs alphabetically: “</strong>);         <strong>for </strong>(Song s: mec.uniqueDownloads())

System.<strong><em>out</em></strong>.println(s);




<em>// Display the downloaded songs in order of popularity </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are the downloaded songs by populariry: “</strong>);         <strong>for </strong>(Pair&lt;Integer,Song&gt; p: mec.songsByPopularity())

System.<strong><em>out</em></strong>.println(<strong>“(” </strong>+ p.getKey() + <strong>” downloads) ” </strong>+ p.getValue());

<em>// Display the royalties </em>

<em>        </em>System.<strong><em>out</em></strong>.println(<strong>“</strong><strong>
</strong><strong>Here are the royalties:</strong><strong>
</strong><strong>“</strong>);         mec.displayRoyalties();

}

}




Here is the expected output:










Status: Music Exchange Center (5 users on-line, 18 songs available)

Here are the downloaded songs:

“Bite My Arms Off” by Jaw 4:12

“Meadows” by Sleepfest 7:15

“If I Had a Hammer” by Long Road 4:15

“Is that My Toenail ?” by Clip 4:47 “Anvil Headache” by Clip 4:34

“Is that My Toenail ?” by Clip 4:47

“If I Had a Hammer” by Long Road 4:15

“Anvil Headache” by Clip 4:34

“Meadows” by Sleepfest 7:15

“Only You Can Rock Me” by UFO 4:52

“Is that My Toenail ?” by Clip 4:47

“Is that My Toenail ?” by Clip 4:47

“Rock is Cool” by Yeah 4:17

“Meadows” by Sleepfest 7:15




Here are the unique downloaded songs alphabetically:

“Anvil Headache” by Clip 4:34

“Bite My Arms Off” by Jaw 4:12

“If I Had a Hammer” by Long Road 4:15

“Is that My Toenail ?” by Clip 4:47

“Meadows” by Sleepfest 7:15

“Only You Can Rock Me” by UFO 4:52

“Rock is Cool” by Yeah 4:17




Here are the downloaded songs by populariry:

(4 downloads) “Is that My Toenail ?” by Clip 4:47

(3 downloads) “Meadows” by Sleepfest 7:15

(2 downloads) “Anvil Headache” by Clip 4:34

(2 downloads) “If I Had a Hammer” by Long Road 4:15

(1 downloads) “Bite My Arms Off” by Jaw 4:12

(1 downloads) “Only You Can Rock Me” by UFO 4:52

(1 downloads) “Rock is Cool” by Yeah 4:17




Here are the royalties:




Amount  Artist

—————

$0.75   Sleepfest

$1.50   Clip

$0.25   Jaw

$0.50   Long Road

$0.25   Yeah

$0.25   UFO

Process finished with exit code 0


