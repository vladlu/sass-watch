# About

A simple system to "sass --watch" many files with different paths. 

# How to use

Just add a list of files/directories to watch to the `rules` file and run `sass-watch.sh`. 

It has exactly the same syntax as the default "sass --watch" command, but:
 
1. Use a newline instead of a space;
2. Use a space(s) instead of a colon;
2. Specify paths relative to the project root.

And:

- You can add empty lines for readability purposes;
- You can use comments that start from a `#` character.

## Example

An example of the `rules` file:

```
# Directories

public/styles/
admin/styles/

# Files

something/different/style.scss  another/directory/style.css
```

Which will be converted to:

```
../../public/styles/ ../../admin/styles/ ../..something/different/style.scss:../../another/directory/style.css
```

And that will be added to the `sass --watch --no-source-map` command. That's it!

#
    
* **It has to be installed in the `dev/` directory of the project root to work correctly.**


* It's also recommended to add this to `.gitignore` of your project:

    ```
    # sass-watch
        
    dev/sass-watch/*
    !dev/sass-watch/*.sh
    !dev/sass-watch/rules
    !dev/wp-prod/readme.txt
    ```

#

Version: 1.0.1

License: [MIT](https://github.com/vladlu/sass-watch/blob/master/LICENSE)
