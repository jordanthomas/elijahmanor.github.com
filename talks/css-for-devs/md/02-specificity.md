# Specificity
<!-- .slide: data-state="backEndBrian juniorJacob" -->

> Specificity determines, which CSS rule is applied by the browsers --[CSS Specificity: Things You Should Know](http://www.smashingmagazine.com/2007/07/27/css-specificity-things-you-should-know/)

------

## Specificity Hierarchy

<div class="Split">
  <div class="Split-column">
    <div class="fragment">
      <h4>1. Inline Styles</h4>
      <pre class="language-markup"><code>&lt;div style="color: red;"&gt;&lt;/div&gt;</code></pre>
    </div>
    <div class="fragment">
      <h4>2. IDs</h4>
      <pre class="language-css"><code>#updateItem {}
#shoppingCart {}</code></pre>
    </div>
  </div>
  <div class="Split-column">
    <div class="fragment">
      <h4>3. Classes, attributes, & pseudo-classes</h4>
      <pre class="language-css"><code>.selected {}
[href^='http://'] {}
:nth-child(2n+1) {}</code></pre>
    </div>
    <div class="fragment">
      <h4>4. Elements & <br /> psuedo-elements</h4>
      <pre class="language-css"><code>table {}
.fa:after {}</code></pre>
    </div>
  </div>
</div>

------

## How to Measure Specificity

1. Start at 0
2. Add 1000 for each inline style
3. Add 100 for each ID
4. Add 10 for each class, attribute & pseudo-class
5. Add 1 for each element and pseudo-element

------

## Examples of Specificity

<div class="Split">
  <div class="Split-column">
    <div class="fragment">
      <pre class="language-css"><code>#submitButton {}</code></pre>
      <div class="Specificity">
        <div class="Specificity-score">
          <div class="Specificity-value Specificity-value--inline">0</div>
          <div class="Specificity-value Specificity-value--ids">1</div>
          <div class="Specificity-value Specificity-value--classes">0</div>
          <div class="Specificity-value Specificity-value--elements">0</div>
        </div>
      </div>
    </div>
    <div class="fragment">
      <pre class="language-css"><code>.Widget {}</code></pre>
      <div class="Specificity">
        <div class="Specificity-score">
          <div class="Specificity-value Specificity-value--inline">0</div>
          <div class="Specificity-value Specificity-value--ids">0</div>
          <div class="Specificity-value Specificity-value--classes">1</div>
          <div class="Specificity-value Specificity-value--elements">0</div>
        </div>
      </div>
    </div>
  </div>
  <div class="Split-column">
    <div class="fragment">
      <pre class="language-css"><code>.Widget.selected > ul {}</code></pre>
      <div class="Specificity">
        <div class="Specificity-score">
          <div class="Specificity-value Specificity-value--inline">0</div>
          <div class="Specificity-value Specificity-value--ids">0</div>
          <div class="Specificity-value Specificity-value--classes">2</div>
          <div class="Specificity-value Specificity-value--elements">1</div>
        </div>
      </div>
    </div>
    <div class="fragment">
      <pre class="language-css"><code>#statusBar[data-type='error'] {}</code></pre>
      <div class="Specificity">
        <div class="Specificity-score">
          <div class="Specificity-value Specificity-value--inline">0</div>
          <div class="Specificity-value Specificity-value--ids">1</div>
          <div class="Specificity-value Specificity-value--classes">1</div>
          <div class="Specificity-value Specificity-value--elements">0</div>
        </div>
      </div>
    </div>
  </div>
</div>

------

## Specificity Games
<!-- .slide: data-state="specificity" data-background="imgs/the-hunger-games.jpeg" -->

<div class="SpecificityGame">
  <div class="Specificity">
    <input class="Specificity-input" value="ul > li.selected input[type='checkbox']" />
    <div class="Specificity-score">
      <div class="Specificity-value Specificity-value--inline">0</div>
      <div class="Specificity-value Specificity-value--ids">0</div>
      <div class="Specificity-value Specificity-value--classes">0</div>
      <div class="Specificity-value Specificity-value--elements">0</div>
    </div>  
  </div>

  <div class="Specificity">
    <input class="Specificity-input" value="aside#sidebar a[href^='https']" />
    <div class="Specificity-score">
      <div class="Specificity-value Specificity-value--inline">0</div>
      <div class="Specificity-value Specificity-value--ids">0</div>
      <div class="Specificity-value Specificity-value--classes">0</div>
      <div class="Specificity-value Specificity-value--elements">0</div>
    </div>  
  </div>

  <button>May the odds be ever in your favor</button>
</div>

------

## Resources

* https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity
* https://css-tricks.com/specifics-on-css-specificity/
* http://www.standardista.com/css3/css-specificity/
* http://www.stuffandnonsense.co.uk/archives/css_specificity_wars.html
* http://specificity.keegan.st/