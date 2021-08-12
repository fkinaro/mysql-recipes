## 1. String functions
- Formatting
  - Concatenating
  - Setting case and quotes
  - Trimming and padding
- Extracting text
- Searching strings
  - Finding a substring
  - String lengths
  - Comparing and searching
  - Replacing & inserting into other strings
- Converting string types
- Compressing strings

### Concatenating strings
- Use the ```CONCAT()``` function. Example:
    ```mysql
    SELECT CONCAT(formal_title, '. ', name_first, SPACE(1), name_last) AS Birder,
    CONCAT(common_name, ' - ', birds.scientific_name) AS Bird,
    time_seen AS 'When Spotted'
    FROM birdwatchers.bird_sightings
    JOIN birdwatchers.humans USING(human_id)
    JOIN rookery.birds USING(bird_id)
    GROUP BY human_id DESC
    LIMIT 4;
    ```
### Setting case and quotes
#### Setting Case
- Done using ```LOWER()``` and ```UPPER()``` or ```LCASE()``` and ```UCASE()```.
    ```mysql
    USE registration;

    SELECT LCASE(username) AS User,
    UCASE(email) AS Email
    FROM user;
    ```
#### Setting Quotes
- Using ```QUOTE()```.
- This function takes a string and returns it enclosed in single quotes.
- Single quotes within the returned string are escaped using a backslash.
- Use case: It sanitizes input for special characters such as backslashes, null bytes, and CTRL Z. This facilitates smooth working with other programming languages and SQL as well.


![Escaped Quotes](quotes.png "Sample usage of the QUOTES(function)")