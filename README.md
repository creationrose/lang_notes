#Objects in Javascript VS Ruby

##Basic Initialization


```javascript

function Book(title, author, numPages) {
  this.title = title;
  this.author = author;
  this.numPages = numPages;
}

var book = new Book("Harry Potter", "J.K. Rowling", 800);

```

--------


```ruby

class Book

 	def initialize(title, author, num_pages)
	 	@title = title
	 	@author = author
	 	@num_pages = num_pages
	end
end

	book = Book.new("Harry Potter", "J.K. Rowling", 800)

```


##Hash Initialization


```javascript
function Book(config) {
  this.title = config.title;
  this.author = config.author;
  this.numPages = config.numPages;
}

var book = new Book({
    title: "Harry Potter",
    author: "J.K. Rowling",
    numPages: 800});


```  

-------

```ruby

class Book
	attr_reader :title, :author, :num_pages
	def initialize(attributes)
		@title = attributes.fetch(title)
		@author = attirbutes.fetch(author)
		@num_pages = attributes.fetch(num_pages)
	end
end


book = Book.new({title: "Harry Potter", author: "J.K. Rowling", num_pages: 800})

```

This is the same as:

```ruby
book = Book.new({:title => "Harry Potter", :author => "J.K. Rowling", :num_pages => 800}) 

```

The hash rockets are used in older versions of Ruby, but since 1.9 I believe, the colons in front are valid.  Of course it's much easier to distinguish between symbols and the hash if you use the hash rocket. 

You will find in a lot of rails app that they use a colon instead of hash rocket. 
