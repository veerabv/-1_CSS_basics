1. Add css to HTML
3 ways,
    - inline style --> style within the element tag
    - internal -> this is write within the html doc between the style tage
    - external  -> write css rule in different file and import it to the html file


    background: red; => in this background is property and red is value

      section { -> this is called selector
            background: #ff1b68;
        }
      ** the whole thing is called a rule 


2. setting up css rule 
3. selectors , properties and values

    selectors:
    element -> h1 , ul ,etc..

    class -> add a class attribute in the html tag and name the class and use the name for style
        .blog {
            color : red;
        }

    universal -> * is the universal selector
        * {
            color : red;
        }

    id -> same as class but use attribute id
        #blog {
            color:red;
        }

    attribute -> we can use the style with attribute

    <button disabled>
    Click
    </button>

    [disabled]{
        color : red;
    }
            


4. Conflicting styles:




## how to import and change the fonts

proprtty is "font-family"

google fonts link-> https://fonts.google.com/

add the embed code in the head tag of the html and use the font in css file

## cascading 
 adding multiple rules to the same element or selector. in cascading the same property overrides the old rule propertty


.section-title {
    color : #2ddf5c;
}

.section-title {
    width : auto;
}

.section-title {
    height: inherit;
    color: teal;
}

in this color teal overrirdes the color #2ddf5c



## specificity order : 

inline Styles > #id selectors > .class , :pseudo-class and [attribute] selectors > <tag> , ::pseudo-elements selectprs

.section-title {
    color : #2ddf5c;
}

h1 {
    color : white;
    font-family: "Anton", sans-serif;  /* sans-serif is the default style we can see that in browser default*/
}

but here cascading wont work , specificity apply

## understanding the inheritence 

the style is inherit from the parent 