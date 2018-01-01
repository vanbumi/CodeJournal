# Rails column types

[Stack Overflow](http://stackoverflow.com/questions/11889048/is-there-documentation-for-the-rails-column-types)

Guidelines built from personal experience:

String: 

* Limited to 255 characters (depending on DBMS)
* Use for short text fields (names, emails, etc)

Text: 

* Unlimited length (depending on DBMS)
* Use for comments, blog posts, etc. General rule of thumb: if it's captured via textarea, use Text. For input using textfields, use string.

Integer: 

* Whole numbers

Float: 

* Decimal numbers stored with floating point precision
* Precision is fixed, which can be problematic for some calculations; generally no good for math operations due to inaccurate rounding.

Decimal:

* Decimal numbers stored with precision that varies according to what is needed by your calculations; use these for math that needs to be accurate.
* See [this](http://stackoverflow.com/questions/3039650/ruby-bigdecimal-sanity-check-floating-point-newb) post for examples and an in-depth explanation on the differences between floats and decimals.

Boolean:

* Use to store true/false attributes (i.e. things that only have two states, like on/off)

Binary:

* Use to store images, movies, and other files in their original, raw format in chunks of data called blobs.

:primary_key

* This datatype is a placeholder that Rails translates into whatever primary key datatype your database of choice requires (i.e. serial primary key in postgreSQL). Its use is somewhat complicated and not recommended.

* Use model and migration constraints (like validates_uniqueness_of and add_index with the :unique => true option) instead to simulate primary key functionality on one of your own fields.

Date:

* Stores only a date (year, month, day)

Time:

* Stores only a time (hours, minutes, seconds)

DateTime:

* Stores both date and time

Timestamp

* Stores both date and time

* Note: For the purposes of Rails, both Timestamp and DateTime mean the same thing (use either type to store both date and time). For the TL;DR description of why both exist, read the bottom paragraph.

These are the types about which confusion often exists; I hope this helps. I really don't know why there isn't official documentation about these. Also, I imagine these database adapters you referred to were written by the same people who wrote Rails, so they probably didn't need any documentation to go by when they were writing the adapters. Hope this helps!

Note: the presence of both :DateTime and :Timestamp, from what I can find, is included by Rails mostly for compatibility with database systems. For instance, MySQL's TIMESTAMP datatype is stored as a unix timestamp. Its valid range goes from 1970 to 2038, and the time is stored as the number of seconds that have elapsed since the last epoch, which is supposedly standard, but in practice can differ from system to system. Recognizing that relative time was not a good thing to have in databases, MySQL later introduced the DATETIME datatype, which stores every digit in the year, month, day, hour, minute and second, at the cost of a size increase. The TIMESTAMP datatype was retained for backwards compatibility. Other database systems went through similar evolutions. Rails recognized that multiple standards existed, and provided interfaces to both. However, Rails ActiveRecord defaults both :Timestamp and :DateTime to UTC dates stored in MySql's DATETIME, so it makes no functional difference to Rails programmers. These exist so that users who wish to differentiate between the two can do so. (For a more in-depth explanation, see this SO answer).

## Integer

Tipe Data	Jangkauan SIGNED				Jangkauan UNSIGNED		Ukuran
TINYINT		-128 to 127						0 to 255				1 byte
SMALLINT	-32,768 to 32,767				0 to 65,535				2 bytes
MEDIUMINT	-8,388,608 to 8,388,607			0 to 16,777,215			3 bytes
INT			-2,147,483,648 to 2,147,483,647	0 to 4,294,967,295		4 bytes
BIGINT		-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807	0 to 18,446,744,073,709,551,615