#Array and Hash Exercise

**A. Copy and paste the following data structure into pry:**

`instructors_array = ["Marc", "Gerry", "Mike"]`

1. Use pry to access the string `"Marc"`
2. Use pry to add your name to the end of the array?
3. Use pry to remove `"Mike"` from the array.
4. Use pry to access the last item in the array. 

**B. Copy and paste the following data structure into pry:**

`vladimir_putins_brain = { :launch_code => "a5Mjp257GHMGH23e5qxE", :fav_hobby => "Riding ponies", "prideful?" => true }`

1. Use pry to return the string `"Riding ponies"`
2. Use pry to return the string `"a5Mjp257GHMGH23e5qxE"`
3. Use pry to add the key-value pair `"number_of_wishes" => "three"` to `vladimir_putins_brain`
4. Use pry to add the key-value pair `4 => "four"`
5. Use pry to remove the key-value pair `"prideful?" => true`

**C. Given the following data structure:**

`boolean_hash = { true => "It's true!", false => "It's false" }`

1. What is the return value of `boolean_hash[2 + 2 == 4]`?
2. What is the return value of `boolean_hash["Marc" == "Gerry"]`?
3. What is the return value of `boolean_hash[9 > 10]`?
4. What is the return value of `boolean_hash[0]`?
5. What is the return value of `boolean_hash["Mike"]`?
6. What is the return value of `boolean_hash[false||true]`?
6. What is the return value of `boolean_hash[false||"Gerry"]`?


**D. Given the following data structure:**

    users = {
      "Marc" => {
        :github => "marcwright",
        :favorite_numbers => [12, 42, 75]
      },
      "Gerry" => {
        :github => "rgpass",
        :favorite_numbers => [11, 99, 24]
      },
      "Mike" => {
        :github => "drmikeh",
        :favorite_numbers => [17, 13, 21]
      }
    }

1. How would you access Gerry's Github handle (i.e. the string "rgpass")?
2. How would you add the number 7 to Mike's favorite numbers?
3. How would you add yourself to the users hash?
4. How would you return the array of Marc's favorite numbers?
5. How would you return the smallest of Mike's favorite numbers?
6. How would you return an array of Gerry's favorite numbers that are also even?

**E. Copy and paste the entirety of the following code snippet into pry.**


For the following array, how would I...

```
random_animals = ["porpoise", "camel", "lobster", "kangaroo", "wombat", "chameleon"]
```
* Print out a plural version of each animal on a new line(i.e. - porpoises, camels, etc)
* Return an array of the animals sorted alphabetically
* Return an array of the animals sorted reverse alphabetically
* Return an array of the animals with each individual string reversed
* Return an array of the animals sorted by word length (low to high)
* Return an array of the animals sorted alphabetically by the last character in the string
