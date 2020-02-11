---?color=linear-gradient(-15deg, #853b6e 20%, #002b36 60%)
### SCRABBLE SCORE EXERCISM CHALLENGE:
PRESENTED BY:GAEL JEROP

---?color=linear-gradient(-15deg, #853b6e 20%, #002b36 60%)
@title[The Exercism challenge]

@snap[north-west span-75]

### ABOUT ME:

@snapend


An environmental engineer passionate about coding ,

Still a newbie started with Ruby on Rails about 8 months ago

--?color=linear-gradient(-15deg, #853b6e 20%, #002b36 60%)
### SCRABBLE SCORE EXERCISM CHALLENGE:
PRESENTED BY:GAEL JEROP

---?color=linear-gradient(60deg, #002b36 40%, #ddaf3c 80%)
@title[The Exercism challenge]

@snap[north-west span-65]
## The  Challenge:

@snapend

@snap[west span-75]
@ul[list-spaced-bullets text-10]
- Given a word  compute the  scrabble score
- Each letter of the alphabet is assigned a value


@ulend
@snapend
@snap[north-east span-55]

@snapend
---?color=linear-gradient(60deg, #002b36 40%, #ddaf3c 80%)
@title[The Exercism challenge]

@snap[north-west span-65]
## The  Challenge:

@snapend

@snap[west span-75]
@ul[list-spaced-bullets text-10]
- Cabbage should score a total of 14
- 3 points for B, twice
- 2 points for G


@ulend
@snapend
@snap[north-east span-55]

@snapend
---?color=linear-gradient(60deg, #002b36 40%, #ddaf3c 80%)
@title[The Exercism challenge]

@snap[north-west span-65]
## The  Challenge:

@snapend

@snap[west span-75]
@ul[list-spaced-bullets text-09]
- 3 points for C
- 1 point for A, twice
- 1 point for E



@ulend
@snapend
@snap[north-east span-55]

@snapend

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

@snap[north-west span-100 bg-black fragment]
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

@snap[north-west span-85 text-center]
## The Code Solution:
@snapend
@snap[west span-100]
@ul[list-spaced-bullets text-09]
- Created a class called scrabble that implements a method called score.
- Score accepts one word as a parameter and returns the score associated with that word
@ulend
@snapend
@snapend

---

@snap[west span-100 bg-black fragment]
```ruby
module Scrabble
  attr_reader :word
letter_scores =
      { %w[a e i o u l n r s t] => 1,
        %w[d g] => 2,
        %w[b c m p] => 3,
        %w[f h v w y] => 4,
        %w[k] => 5,
        %w[j x] => 8,
        %w[q z] => 10
        }
		letter_scores.default = 0
    letter_scores.freeze


    def initialize(word)
			@word = word
			@word = " " if word == nil || word.length == 0
			@word = @word.gsub(/\W/,"").upcase
		 end





```
@snapend

---?color=linear-gradient(60deg, #002b36 40%, #ddaf3c 80%)

@title[the code Solution]

@snap[north-west span-85 text-center]

## The Code Solution:
@snapend
@snap[west span-100]
@ul[list-spaced-bullets text-09]
- Initiliazed word as an instance variable,
- The score method below takes the string “word”, and turns it into an array, in which each letter is an element

@ulend
@snapend
@snapend

---



@snap[west span-100 text-gray bg-black fragment]
```ruby
def score(word)
         letters = word.upcase.split('').reduce(0) {|total, current|total + letter_scores[current]}

    end

     total
    end



    puts "Type in one word for scrabble scorer"
    word = gets.chomp
    puts ("Scrabble score for #{word} is #{scrabble.score(word).to_s}")

```

@snapend

---?color=linear-gradient(60deg, #002b36 40%, #ddaf3c 80%)

@title[the code Solution]

@snap[north-west span-85 text-center]

## The Code Solution:
@snapend
@snap[west span-100]
@ul[list-spaced-bullets text-09]
- The "reduce” method  calculates a score: Since it’s a numeric score, I initialized the total with 0
- Then, for each letter in our word, we add the number of points associated with that word to our total.
@ulend
@snapend
@snapend

---?color=linear-gradient(-15deg, #853b6e 20%, #002b36 60%)

@title[the code Solution]

@snap[south-west span-100 text-center]
## Thank You:
@snapend

