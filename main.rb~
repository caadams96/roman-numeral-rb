# frozen_string_literal: false

ROMAN_MAP = { 1000 => 'M',
              500 => 'D',
              100 => 'C',
              50 => 'L',
              10 => 'X',
              5 => 'V',
              1 => 'I' }.freeze

LONG_TO_SHORT_MAP = { 'DCCCC' => 'CM',
                      'CCCC' => 'CD',
                      'LXXXX' => 'XC',
                      'XXXX' => 'XL',
                      'VIIII' => 'IX',
                      'IIII' => 'IV' }.freeze

def int_to_roman(number_input)
  roman_numeral = ''
  ROMAN_MAP.each do |key, val|
    difference = number_input - (number_input % key) # mask number and find difference
    amount = difference / key # find out how many times to make concatonation
    amount.times { roman_numeral += val } # concatonate roman value to roman numeral string
    number_input -= difference # update number input for next iteration
  end
  # find and replace any substrings that are the same as the hash key
  LONG_TO_SHORT_MAP.each do |key, val|
    roman_numeral = roman_numeral.sub(key, val)
  end
  roman_numeral
end

def roman_to_int(roman_input)
  amount = 0
  # replace the subtractive form of roman numeral with additive form
  LONG_TO_SHORT_MAP.invert.each do |key, val|
    roman_input = roman_input.sub(key, val)
  end
  # search and count the roman numerals substrings for to find integer value
  ROMAN_MAP.invert.each do |key, val|
    amount += roman_input.scan(key).count * val
  end
  amount
end

puts int_to_roman(999)
# puts roman_to_int('IV')

# def roman_to_int(roman_numeral)
# roman_thous
# end

50.times { |i| puts int_to_roman(i + 1) }
# int_to_roman(2449)
