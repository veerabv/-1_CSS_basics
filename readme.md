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


## combinators

1. Adjacent sibling => +  the selected element should be next to the combinator. 
div + p {  => here p should be next to div

    }

<div>
<p>vxc</p>   // this will not selected
</div>
<p>vvv</p> // only this will be selected because it select the sibling no the children

    
2. General sibling  => ~   it style the all element siblings 

div ~ p {

}
3. child            => > it style the direct children not the grand children

div > p {

}

4. Descendent  => it style all the P inside the div (child and grand child)

div p {

}

----------------------------------------------------------------------------

## Box Model

Deep Dive on "Margin Collapsing"
When working with margins, you can get unexpected results. 

Why are two adjacent elements sharing one margin even though each element has its own one?
Why does a parent element (e.g. <section>  as in the videos) suddenly take on the margin of the child element (e.g. <h1> )?
It's always related to margin collapsing. You can dive deeply into it with the help of the following awesome article: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing

There, three base cases are described:

Adjacent siblings which both have margins
A parent which holds one or more child elements where the first and/ or last (or the only) child has margins
An element without content, padding, border and height
Let's explore these cases:

1. Adjacent Siblings

In this case, the first element might have a margin of 10px  (on all sides let's say) and the second one has 5px  (or 20px  - the values don't matter).

CSS will collapse the margins and only add the bigger one between the elements. So if we got margins of 10px  and 5px , a 10px  margin would be added between the elements?

2. A parent with children that have a margin

To be precise, the first and/ or last or the only child has to have margins (top and/ or bottom). In that case, the parent elements margin will collapse with the child element(s)' margins. Again, the bigger margin wins and will be applied to the parent element.

If the parent element has padding, inline content (other than the child elements) or a border, this behavior should not occur, the child margin will instead be added to the content of the wrapping parent element.

3. An empty element with margins

This case probably doesn't occur that often but if you got an element with no content, no padding, no border and no height, then the top and bottom margin will be merged into one single margin. Again, the bigger one wins.