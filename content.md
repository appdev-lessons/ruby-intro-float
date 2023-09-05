# The Float class

Ruby calls decimal numbers `Float`s. To create a `Float` rather than an `Integer`, just make sure to include a decimal point:

```ruby
pp 5.class
pp 5.0.class
```
{: .repl #integers_vs_floats title="Integer vs Float Class" points="1"}

- `"12".to_i.to_f` would return data of class? (You can use the runnable code block above to test.)
- Float
    - Yes! The `String` 12 is converted to an integer, and then to a float
{: .free_text #to_f title="What Class?" points="1" answer="1" }

## Methods

### + - * / ** (math) 

The math methods work mostly like you'd expect, and similarly to the [ones for integers](https://learn.firstdraft.com/lessons/70#-------math).

The main difference to keep in mind is with `/`. Division with floats works the way that we're used to — it returns fractional results, as a `Float`:

```ruby
pp 12.0 / 5.0
```
{: .repl #float_division title="Float Division" points="1"}

Try the following by uncommenting (remove the leading `#`) each line, and commenting (add a leading `#`) the previous line, and see what you get:

```ruby
pp 12 / 5
# pp 12.0 / 5
# pp 12 / 5.0
```
{: .repl #more_float_division title="More Float Division" points="1"}

What did you discover? If _either_ side is a float, float division will be performed!

This is why `Integer`'s `.to_f` method can come in handy while doing math; at some point if you need to do division and need a fractional answer, then convert it to a `Float` first.

One other thing to keep in mind: you can use `**` in conjunction with fractions to calculate roots, since 9<sup>1/2</sup> is the same as the square root of 9, 8<sup>1/3</sup> is the same as the cube root of 8, etc.

```ruby
pp 9 ** 0.5
pp 8 ** (1/3.0)
```
{: .repl #float_power_of title="Fractional Powers" points="1"}

Let's put some `Float` math to good use. Recall the Pythagorean Theorem for a triangle, where `a` and `b` are the lengths of the shorter sides, and `c` is the length of the longest side:

<!-- ![](assets/float/pythagorous.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1677034341/pythagorous_axrds0.png)

In the graded code block below, calculate `c` and print it out using the provided `a` and `b` variables:

```ruby
a = 2.8
b = 4.5

# calculate c and print it
c = 
```
{: .repl #hypotenuse title="Hypotenuse" readonly_lines="[1,2]"}

```ruby
describe "Hypotenuse" do
  it "should print '5.3'" do
    path = "/tmp/code.rb"

    File.foreach(path) do |line|
      if line.match(/^p.*5.3/)
        expect(line).to_not match(/5.3/),
          "Expected graded code block to NOT print the Float literal '5.3', but did."
      end
    end
    
    expect { require_relative(path) }.to output(/5.3/).to_stdout
  end
end
```
{: .repl-test #hypotenuse_test_1 for="hypotenuse" title="Hypotenuse should print '5.3'" points="1"}

### round 

`Float`s can round themselves. Play around with the `.round` method:

```ruby
pi = 3.1415926535897932384626433832795028841976939937510
pp pi.round(3)
```
{: .repl #round_pi title="Round pi" points="1"}

Once you're comfortable with it, get this graded code block to pass by outputting the result of: 10 divided by 3, rounded to 5 decimal places.

```ruby
# what is 10 divided by 3 rounded to 5 decimals?
```
{: .repl #rounding title="Rounding"}

```ruby
describe "Rounding" do
  it "should print '3.33333'" do
    path = "/tmp/code.rb"

    File.foreach(path) do |line|
      if line.match(/^p.*3.33333/)
        expect(line).to_not match(/3.33333/),
          "Expected graded code block to NOT print the Float literal '3.33333', but did."
      end
    end
    
    expect { require_relative(path) }.to output(/3.33333/).to_stdout
  end
end
```
{: .repl-test #rounding_test_1 for="rounding" title="Rounding should print '3.33333'" points="1"}

### rand 

The `rand` method that we met earlier can also be called with no arguments, in which case it returns a `Float` between 0 and 1. This is very handy for e.g. probabilities. Give it a try:

```ruby
pp rand
```
{: .repl #random title="Random Float" points="1"}

- Let's pause and recall. You can use the previous runnable code block to sandbox. Check everything below that is true:
- `"5"` is an `Integer` object
    - No, keep in mind the `""` quotes
- `"5" + 5` would result in `10`
    - No, we need to convert one or both objects to add them
- `"5" + "5"` would result in `10`
    - No, think about how string addition is different from integer addition
- `"5".to_f + "5".to_f` would result in `10.0`
    - Yes!
- `"5".to_f + "5".to_f` would result in `10`
    - No, it would return a `Float`, `10.0`
- `5.0` is a `Float`
    - Yes!
- `.to_i` is a "noun" in our grammar
    - No, remember `noun.verb`
- `.to_i` is a method
    - Yes!
{: .choose_all #recall title="Recall" points="3" answer="[4,6,8]" }

##  Conclusion

That's it for `Float`. Next up, we'll learn to manipulate dates and times with the `Date` and `Time` classes.

- Approximately how long (in minutes) did this lesson take you to complete?
{: .free_text_number #time_taken title="Time taken" points="1" answer="any" }

<span style="font-size: large">**When you are done here, close the window and return to Canvas for the next lesson in the series.**</span>

----
