Scarabble score Exercim Challenge.
Presented By Gael Jerop.
**About Gael: **
Started Coding last Year from July previously from an engineering (environmental ) field academics
**The Challenge :Scrabble Score :**
each letter of the alphabet is assigned a value ,write code that calculate the score.
**The Code:**
	*Explaining The code:Solution*
	
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
			{ 	%w[a e i o u l n r s t] => 1,
				%w[d g] => 2,
			 	 %w[b c m p] => 3,
				 %w[f h v w y] => 4,
				  %w[k] => 5,
				   %w[j x] => 8,
				  %w[q z] => 10
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
	
	class ScrabbleTest < Minitest::Test
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
	
			
			
			
			
			
		
		
		
	


