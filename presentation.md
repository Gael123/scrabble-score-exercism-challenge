<!DOCTYPE HTML>
<html>
 <head>
  <meta charset="utf-8"/>
  <title>
   Made with Remarkable!
  </title>
  <link href="http://cdnjs.cloudflare.com/ajax/libs/highlight.js/8.1/styles/github.min.css" rel="stylesheet"/>
  <style type="text/css">
   h1,h2{border-bottom:1px solid}html a:hover,html pre{background-color:#eee8d5}blockquote,body,h1,h2,h3,h4,h5,h6,html,img,li,ol,p,ul{margin:0;padding:0;font:inherit;vertical-align:baseline}img,ol,p,pre,ul{margin-bottom:20px}html *{font-family:ff-din-web-pro-1,ff-din-web-pro-2,sans-serif;font-size:16px;line-height:19.2px;color-profile:sRGB;color:#657b83}body{margin:40px 70px}p{font-weight:lighter}strong{font-weight:700}ol,ul{margin-left:2em}ol ol,ol ul,ul ol,ul ul{margin-top:10px}li{margin-bottom:3px}h1,h2,h3,h4,h5,h6{font-weight:lighter;text-transform:capitalize;margin-top:20px;margin-bottom:10px}.hljs-strong,h1,mark{font-weight:700}h1,h2{font-size:24.62px;line-height:29.55px}h3{font-size:23.44px;line-height:28.13px}h4,h5,h6{font-size:22.16px;line-height:26.59px}h1 img,h2 img,h3 img,h4 img,h5 img,h6 img,p img{margin-bottom:0}pre{white-space:pre;white-space:pre-wrap;word-wrap:break-word;padding:15px}code,pre{font-family:monospace}blockquote{border-left:4px solid;padding:0 15px}blockquote>:first-child{margin-top:0}blockquote>:last-child{margin-bottom:15px}h1{text-transform:uppercase}h3,h4,h5,h6{border-bottom:none}html body{background-color:#fdf6e3}html h1,html h2,html h3,html h4,html h5,html h6{border-color:#657b83}html pre{color:#586e75}html a,html a:active,html a:visited,html code.url,html h1,html h2,html h3,html h4,html h5,html h6{color:#b58900}@media print{body{margin:0}*{color:#000!important}}table{border-collapse:collapse}td,th{border:1px solid #657b83;padding:.5rem;text-align:left}.hljs{display:block;overflow-x:auto;padding:.5em;background:#fdf6e3;color:#657b83}.hljs-comment,.hljs-quote{color:#93a1a1}.hljs-addition,.hljs-keyword,.hljs-selector-tag{color:#859900}.hljs-doctag,.hljs-literal,.hljs-meta .hljs-meta-string,.hljs-number,.hljs-regexp,.hljs-string{color:#2aa198}.hljs-name,.hljs-section,.hljs-selector-class,.hljs-selector-id,.hljs-title{color:#268bd2}.hljs-attr,.hljs-attribute,.hljs-class .hljs-title,.hljs-template-variable,.hljs-type,.hljs-variable{color:#b58900}.hljs-bullet,.hljs-link,.hljs-meta,.hljs-meta .hljs-keyword,.hljs-selector-attr,.hljs-selector-pseudo,.hljs-subst,.hljs-symbol{color:#cb4b16}.hljs-built_in,.hljs-deletion{color:#dc322f}.hljs-formula{background:#eee8d5}.hljs-emphasis{font-style:italic}
  </style>
 </head>
 <body>
  <h1 id="scrabble-score-exercism-challenge">
   Scrabble Score Exercism Challenge.
  </h1>
  <h2 id="_1">
  </h2>
  <p>
   Presented By Gael Jerop.
  </p>
  <h2 id="about-gael">
   <strong>
    About Gael:
   </strong>
  </h2>
  <p>
   Started Coding last Year from July previously from an engineering (environmental ) field academics
  </p>
  <h2 id="the-challenge-scrabble-score">
   <strong>
    The Challenge :Scrabble Score :
   </strong>
  </h2>
  <p>
   each letter of the alphabet is assigned a value ,write code that calculate the score.
  </p>
  <h4 id="the-code">
   <strong>
    The Code:
   </strong>
  </h4>
  <pre><code>*Explaining The code:Solution*

defined the module 
scrabble and initialiaze it with the method that takes on one argument that is word,
Word is a string


module Scrabble 
    def initialize(word)
        @word = word
        @word = " " if word == nil || word.length == 0
        @word = @word.gsub(/\W/,"").upcase
     end

    def score(word)
         letters = word.upcase.split('')
         total = 0
        letters.each do |letter|
        total += letter_scores[letter]
    end

     total
    end
private
# scores for each letter
    def letter_scores
        {   %w[a e i o u l n r s t] =&gt; 1,
            %w[d g] =&gt; 2,
             %w[b c m p] =&gt; 3,
             %w[f h v w y] =&gt; 4,
              %w[k] =&gt; 5,
               %w[j x] =&gt; 8,
              %w[q z] =&gt; 10
                }.freeze
              end
            attr_reader :word  
        end
    puts "Type in one word for scrabble scorer"
    word = gets.chomp
    puts "Scrabble score for " + word + " is " + Scrabble.new(word).score.to_s

*test*
require 'minitest/autorun'
require_relative 'scrabble_score'

class ScrabbleTest &lt; Minitest::Test
  def test_empty_word_scores_zero
    assert_equal 0, Scrabble.new('').score
  end

  def test_whitespace_scores_zero
    skip
    assert_equal 0, Scrabble.new(" \t\n").score
  end

  def test_nil_scores_zero
    skip
    assert_equal 0, Scrabble.new(nil).score
  end

  def test_scores_very_short_word
    skip
    assert_equal 1, Scrabble.new('a').score
  end

  def test_scores_other_very_short_word
    skip
    assert_equal 4, Scrabble.new('f').score
  end

  def test_simple_word_scores_the_number_of_letters
    skip
    assert_equal 6, Scrabble.new('street').score
  end

  def test_complicated_word_scores_more
    skip
    assert_equal 22, Scrabble.new('quirky').score
  end

  def test_scores_are_case_insensitive
    skip
    assert_equal 41, Scrabble.new('OXYPHENBUTAZONE').score
  end

  def test_convenient_scoring
    skip
    assert_equal 13, Scrabble.score('alacrity')
  end
end
</code></pre>
  <script src="http://cdnjs.cloudflare.com/ajax/libs/highlight.js/8.1/highlight.min.js">
  </script>
  <script>
   hljs.initHighlightingOnLoad();
  </script>
  <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript">
  </script>
  <script type="text/javascript">
   MathJax.Hub.Config({"showProcessingMessages" : false,"messageStyle" : "none","tex2jax": { inlineMath: [ [ "$", "$" ] ] }});
  </script>
 </body>
</html>