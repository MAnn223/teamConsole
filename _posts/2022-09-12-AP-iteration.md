---
keywords: fastai
description: Focus is on iteration.  This example uses 2D array with simple ASCII art.  The idea of this example was to incorporate ASCII art with a nursery rhyme.
title: Iteration with 2D Array
toc: true
categories: [units]
image: /images/boolean.png
permalink: /unit/3
type: ap
week: 4
nb_path: _notebooks/2022-09-12-AP-iteration.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-09-12-AP-iteration.ipynb
-->

<div class="container" id="notebook-container">
        
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-java"><pre><span></span><span class="cm">/*</span>
<span class="cm"> * Creator: Nighthawk Coding Society</span>
<span class="cm"> * Mini Lab Name: Hello Series,featuring Monkey Jumpers</span>
<span class="cm"> * Level: Beginner</span>
<span class="cm"> */</span>

<span class="cm">/**</span>
<span class="cm"> * Class for Monkeys: a 2D array of Monkeys</span>
<span class="cm"> * As well as method to print the Poem</span>
<span class="cm"> */</span>
<span class="kd">class</span> <span class="nc">MonkeyLoop</span> <span class="p">{</span>
    <span class="c1">//The area between class definition and the 1st method is where we keep data for object in Java</span>
    <span class="n">String</span> <span class="o">[][]</span> <span class="n">monkeys</span><span class="p">;</span>    <span class="c1">//2D Array: AP CSA Unit 8: 2D array of strings</span>
                            <span class="c1">//2D array is like a grid [x][y]</span>
                            <span class="c1">// or like a spreadsheet [row][column]</span>

    <span class="cm">/**</span>
<span class="cm">     * Constructor initializes a 2D array of Monkeys</span>
<span class="cm">     */</span>
    <span class="kd">public</span> <span class="nf">MonkeyLoop</span><span class="p">()</span> <span class="p">{</span>
        <span class="c1">//Storing Data in 2D arrays</span>
        <span class="n">monkeys</span> <span class="o">=</span> <span class="k">new</span> <span class="n">String</span><span class="o">[][]</span><span class="p">{</span>   <span class="c1">//2D array above is just a name, &quot;new&quot; makes a container (&quot;object&quot;)</span>
                <span class="c1">//Monkey 0</span>
                <span class="p">{</span>
                        <span class="s">&quot;ʕง ͠° ͟ل͜ ͡°)ʔ &quot;</span><span class="p">,</span>      <span class="c1">//[0][0] eyes</span>
                        <span class="s">&quot;  \\_⏄_/  &quot;</span><span class="p">,</span>      <span class="c1">//[0][1] chin</span>
                        <span class="s">&quot;  --0--   &quot;</span><span class="p">,</span>       <span class="c1">//[0][2] body</span>
                        <span class="s">&quot;  ⎛   ⎞   &quot;</span>        <span class="c1">//[0][3] legs</span>
                <span class="p">},</span>
                <span class="c1">//Monkey 1</span>
                <span class="p">{</span>
                        <span class="s">&quot; ʕ༼ ◕_◕ ༽ʔ&quot;</span><span class="p">,</span>       <span class="c1">//[1][0]</span>
                        <span class="s">&quot;  \\_⎏_/  &quot;</span><span class="p">,</span>
                        <span class="s">&quot;  ++1++  &quot;</span><span class="p">,</span>
                        <span class="s">&quot;   ⌋ ⌊   &quot;</span>
                <span class="p">},</span>
                <span class="c1">//Monkey 2</span>
                <span class="p">{</span>
                        <span class="s">&quot; ʕ(▀ ⍡ ▀)ʔ&quot;</span><span class="p">,</span>       <span class="c1">//[2][0]</span>
                        <span class="s">&quot;  \\_⎐_/ &quot;</span><span class="p">,</span>
                        <span class="s">&quot;  &lt;-2-&gt;  &quot;</span><span class="p">,</span>
                        <span class="s">&quot;  〈  〉 &quot;</span>
                <span class="p">},</span>
                <span class="c1">//Monkey 3</span>
                <span class="p">{</span>
                        <span class="s">&quot;ʕ ͡° ͜ʖ ° ͡ʔ&quot;</span><span class="p">,</span>        <span class="c1">//[3][0]</span>
                        <span class="s">&quot;  \\_⍾_/  &quot;</span><span class="p">,</span>
                        <span class="s">&quot;  ==3==  &quot;</span><span class="p">,</span>
                        <span class="s">&quot;  _/ \\_  &quot;</span>
                <span class="p">},</span>
                <span class="c1">//Monkey 4</span>
                <span class="p">{</span>
                        <span class="s">&quot;  (◕‿◕✿) &quot;</span><span class="p">,</span>          <span class="c1">//[4][0]</span>
                        <span class="s">&quot;  \\_⍾_/ &quot;</span><span class="p">,</span>          <span class="c1">//[4][1]</span>
                        <span class="s">&quot;  ==4==  &quot;</span><span class="p">,</span>          <span class="c1">//[4][2]</span>
                        <span class="s">&quot;  _/ \\_ &quot;</span>           <span class="c1">//[4][3]</span>
                <span class="p">},</span>

        <span class="p">};</span>
    <span class="p">}</span>

    <span class="cm">/**</span>
<span class="cm">     * Loop and print monkeys in array</span>
<span class="cm">     * ... repeat until you reach zero  ...</span>
<span class="cm">     */</span>
    <span class="kd">public</span> <span class="kt">void</span> <span class="nf">printPoem</span><span class="p">()</span> <span class="p">{</span>
        <span class="c1">//begin the poem</span>
        <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">();</span>
        <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="s">&quot;Monkey Jumpers Poem in Java Loopy&quot;</span><span class="p">);</span>

        <span class="c1">// monkeys (non-primitive) defined in constructor knows its length</span>
        <span class="kt">int</span> <span class="n">monkeyCount</span> <span class="o">=</span> <span class="n">monkeys</span><span class="p">.</span><span class="na">length</span><span class="p">;</span>
        <span class="k">for</span> <span class="p">(</span><span class="kt">int</span> <span class="n">i</span> <span class="o">=</span> <span class="n">monkeyCount</span><span class="p">;</span> <span class="n">i</span> <span class="o">&gt;=</span> <span class="mi">1</span><span class="p">;</span> <span class="n">i</span><span class="o">--</span><span class="p">)</span>  <span class="c1">//loops through 2D array length backwards</span>
        <span class="p">{</span>

            <span class="c1">//this print statement shows current count of Monkeys</span>
            <span class="c1">//  concatenation (+) of the loop variable and string to form a countdown message</span>
            <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="n">i</span> <span class="o">+</span> <span class="s">&quot; little monkeys jumping on the bed...&quot;</span><span class="p">);</span>

            <span class="c1">//how many separate parts are there in a monkey monkey?</span>
            <span class="k">for</span> <span class="p">(</span><span class="kt">int</span> <span class="n">row</span> <span class="o">=</span> <span class="mi">0</span><span class="p">;</span> <span class="n">row</span> <span class="o">&lt;</span> <span class="n">monkeyCount</span><span class="p">;</span> <span class="n">row</span><span class="o">++</span><span class="p">)</span> <span class="p">{</span>  <span class="c1">//cycles through &quot;cells&quot; of 2d array</span>

                <span class="cm">/*cycles through columns to print</span>
<span class="cm">                each monkey part by part, will eventually print entire column*/</span>
                <span class="k">for</span> <span class="p">(</span><span class="kt">int</span> <span class="n">col</span> <span class="o">=</span> <span class="mi">0</span><span class="p">;</span> <span class="n">col</span> <span class="o">&lt;</span> <span class="n">monkeys</span><span class="o">[</span><span class="n">row</span><span class="o">]</span><span class="p">.</span><span class="na">length</span><span class="p">;</span> <span class="n">col</span><span class="o">++</span><span class="p">)</span> <span class="p">{</span>

                    <span class="c1">// prints specific part of the monkey from the column</span>
                    <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">print</span><span class="p">(</span><span class="n">monkeys</span><span class="o">[</span><span class="n">row</span><span class="o">][</span><span class="n">col</span><span class="o">]</span> <span class="o">+</span> <span class="s">&quot; &quot;</span><span class="p">);</span>

                    <span class="c1">//this is new line between separate parts</span>
                    <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">();</span>
                <span class="p">}</span>

                <span class="c1">//this new line gives separation between stanza of poem</span>
                <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">();</span>
            <span class="p">}</span>

            <span class="c1">//countdown for poem, decrementing monkeyCount variable by 1</span>
            <span class="n">monkeyCount</span> <span class="o">-=</span> <span class="mi">1</span><span class="p">;</span>
        <span class="p">}</span>

        <span class="c1">//out of all the loops, prints finishing messages</span>
        <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="s">&quot;No more monkeys jumping on the bed&quot;</span><span class="p">);</span>
        <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="s">&quot;0000000000000000000000000000000000&quot;</span><span class="p">);</span>
        <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="s">&quot;             THE END              &quot;</span><span class="p">);</span>
    <span class="p">}</span>

    <span class="cm">/**</span>
<span class="cm">    * A Java Driver/Test method that is the entry point for execution</span>
<span class="cm">    */</span>
    <span class="kd">public</span> <span class="kd">static</span> <span class="kt">void</span> <span class="nf">main</span><span class="p">(</span><span class="n">String</span><span class="o">[]</span> <span class="n">args</span><span class="p">)</span>  <span class="p">{</span>
        <span class="k">new</span> <span class="n">MonkeyLoop</span><span class="p">().</span><span class="na">printPoem</span><span class="p">();</span>   <span class="c1">//a new monkey list and output in one step</span>
    <span class="p">}</span>

<span class="p">}</span>
<span class="n">MonkeyLoop</span><span class="p">.</span><span class="na">main</span><span class="p">(</span><span class="kc">null</span><span class="p">);</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>
Monkey Jumpers Poem in Java Loopy
5 little monkeys jumping on the bed...
ʕง ͠° ͟ل͜ ͡°)ʔ  
  \_⏄_/   
  --0--    
  ⎛   ⎞    

 ʕ༼ ◕_◕ ༽ʔ 
  \_⎏_/   
  ++1++   
   ⌋ ⌊    

 ʕ(▀ ⍡ ▀)ʔ 
  \_⎐_/  
  &lt;-2-&gt;   
  〈  〉  

ʕ ͡° ͜ʖ ° ͡ʔ 
  \_⍾_/   
  ==3==   
  _/ \_   

  (◕‿◕✿)  
  \_⍾_/  
  ==4==   
  _/ \_  

4 little monkeys jumping on the bed...
ʕง ͠° ͟ل͜ ͡°)ʔ  
  \_⏄_/   
  --0--    
  ⎛   ⎞    

 ʕ༼ ◕_◕ ༽ʔ 
  \_⎏_/   
  ++1++   
   ⌋ ⌊    

 ʕ(▀ ⍡ ▀)ʔ 
  \_⎐_/  
  &lt;-2-&gt;   
  〈  〉  

ʕ ͡° ͜ʖ ° ͡ʔ 
  \_⍾_/   
  ==3==   
  _/ \_   

3 little monkeys jumping on the bed...
ʕง ͠° ͟ل͜ ͡°)ʔ  
  \_⏄_/   
  --0--    
  ⎛   ⎞    

 ʕ༼ ◕_◕ ༽ʔ 
  \_⎏_/   
  ++1++   
   ⌋ ⌊    

 ʕ(▀ ⍡ ▀)ʔ 
  \_⎐_/  
  &lt;-2-&gt;   
  〈  〉  

2 little monkeys jumping on the bed...
ʕง ͠° ͟ل͜ ͡°)ʔ  
  \_⏄_/   
  --0--    
  ⎛   ⎞    

 ʕ༼ ◕_◕ ༽ʔ 
  \_⎏_/   
  ++1++   
   ⌋ ⌊    

1 little monkeys jumping on the bed...
ʕง ͠° ͟ل͜ ͡°)ʔ  
  \_⏄_/   
  --0--    
  ⎛   ⎞    

No more monkeys jumping on the bed
0000000000000000000000000000000000
             THE END              
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Hacks-(Mini-lab)">Hacks (Mini-lab)<a class="anchor-link" href="#Hacks-(Mini-lab)"> </a></h2><blockquote><p>Build you own Jupyter Notebook.  Feel free to use any ASCII art of your choice, there are some much better ones <a href="https://www.asciiart.eu/animals/monkeys">here</a>.  My little guys were made up out of my head while looking at unicode characters.</p>
<ul>
<li>Print monkeys horizontally versus vertically.</li>
<li>Build more or entire rhyme for the "Monkey Jumpers" countdown poem</li>
<li>Add names or other properties to the monkeys</li>
</ul>
<p>In you notebook, illustrate or answer some of these questions.</p>
<ul>
<li>Is this program in more of an Imperative Programming Style or OOP style? Explain.<ul>
<li>Observe variable assignments.</li>
<li>Is each Monkey an object?</li>
<li>Build an where the monkey is an object versus two-dimensional array.  This would be leading into Unit 5 requirements.</li>
</ul>
</li>
<li>Study loops and zero based counting<ul>
<li>Study two-dimensional (2D) array references</li>
<li>Explain different way you can access a 2D array</li>
</ul>
</li>
</ul>
</blockquote>

</div>
</div>
</div>
</div>
 

