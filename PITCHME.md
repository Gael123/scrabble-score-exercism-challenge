### SCRABBLE SCORE EXERCISM CHALLENGE:
PRESENTED BY:GAEL JEROP

---?color=linear-gradient(-15deg, #853b6e 20%, #002b36 60%)
@title[The Exercism challenge]

@snap[north-west span-75]

### ABOUT ME:

@snapend


An environmental engineer passionate about coding ,

Still a newbie started with Ruby on Rails about 8 months ago



---?color=linear-gradient(60deg, #002b36 40%, #ddaf3c 80%)
@title[The Exercism challenge]

@snap[north-west span-65]
## The  challenge:

@snapend

@snap[west span-75]
@ul[list-spaced-bullets text-09]
- Each letter of the alphabet is assigned a value
- Given a certain word  calculate the score

@ulend
@snapend
@snap[north-east span-55]

@snapend

<!-- @snap[south span-100]
@snapend -->

---
@title[The test]

@snap[north-west span-100 text-center bg-black]
#### Tests:

```ruby

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


```

---

@snap[north-west span-100 text-center bg-black]
```ruby
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


```
@snapend

---

@snap[west span-100 bg-black fragment]
```ruby

def test_scores_are_case_insensitive
    skip
    assert_equal 41, Scrabble.new('OXYPHENBUTAZONE').score
  end

  def test_convenient_scoring
    skip
    assert_equal 13, Scrabble.score('alacrity')
  end
end



```
@snapend

---?color=linear-gradient(60deg, #002b36 40%, #ddaf3c 80%)

@title[the code Solution]

@snap[north-west span-50 text-center]
#### The Code Solution:
@snapend
@snap[west span-55]
@ul[list-spaced-bullets text-09]
- Defined the module Scarabble
- Initialized it with word
@ulend
@snapend
@snapend

---
@snap[west span-100 bg-black fragment]
```ruby
module Scrabble

		attr_reader :word
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


```
@snapend

---

@snap[south span-80 text-gray text-08 bg-black]
```ruby

private
    def letter_scores
      { %w[a e i o u l n r s t] => 1,
        %w[d g] => 2,
        %w[b c m p] => 3,
        %w[f h v w y] => 4,
        %w[k] => 5,
        %w[j x] => 8,
        %w[q z] => 10
        }.freeze
    end
  end
    puts "Type in one word for scrabble scorer"
    word = gets.chomp
    puts "Scrabble score for " + word + " is "
     + Scrabble.new(word).score.to_s

```

@snapend







@snap[east span-50 text-center]


@snapend

@snap[south-east span-50 text-center text-06]


@snapend

