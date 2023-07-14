# Moogle

[See the Video](https://www.youtube.com/watch?v=sFuS4YfQ2fw)

## A Google clone for cow results
🐄 Exactly like Google, except the search results are about cows...

🔍 Uses Google's search functions, but sneakily adds the word "cow"...

## Regular Google search
```
 <form action="https://www.google.com/search">
                <div id="searchbar">
                    <input id="searchinput" type="text" name="q" placeholder="">
```
## Adding the cow element
The search form has a hidden input that just concatenates the word "cow" to the other search query...
```
<input type="hidden" name="q" value="cow">
```

## Advanced Moogle Search
Note the changes in the name="" input.
These cause the lookup handling labelled in the table headings.

```

    <td class="tableheading">this exact word or phrase:</td>
    <td><input id="exact" class="tableinput" type="text" name="as_epq"></td>

    <td class="tableheading">all these words:</td>
    <td><input id="all" class="tableinput" type="text" name="q"></td>

    <td class="tableheading">any of these words</td>
    <td><input id="any" class="tableinput" type="text" name="as_oq" placeholder=""></td>

    <td class="tableheading">none of these words</td>
    <td><input id="none" class="tableinput" type="text" name="as_eq" placeholder=""></td>
```

## Google Image Search
The hidden input is required to cause the search results to directly route to the images page.
```
<form action="http://www.google.com/search">
    <div id="searchbar">
        <i id="magnifier" class="fa fa-search"></i>
        <input type="hidden" name="tbm" value="isch">
        <input id="searchinput" type="text" name="q" placeholder="">
```

## Adding the cow element to image search
Another hidden field didn't work as before here, so I added a few JavaScript lines to add the word cow when the search is posted.
```
 <script>
            // Adds the word "cow" to the search query
            document.querySelector('form').addEventListener('submit', function(event) {
                var searchInput = document.getElementById('searchinput');
                searchInput.value += ' cow';
            });
        </script>
```

### This was submitted as Project 0:Search of CS50W
