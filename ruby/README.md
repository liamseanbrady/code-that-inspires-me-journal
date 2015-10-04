Source: https://github.com/exercism/xruby/blob/master/ocr-numbers/example.rb


The code below defines a **custom enumerator** to more idiomatically iterate through a series of 'rows'. This shows how useful custom enumerators can be in making code more declarative in terms of the problem domain.

``` ruby
def initialize(text)
  @text = text.split("\n")
end

def convert
  numbers = []
  each_row do |row|
    numbers << values_in_row(row)
  end
  numbers
end

def each_row
  (0...row_count).step(4) do |row|
    yield row
  end
end

def row_count
  text.length
end
```


