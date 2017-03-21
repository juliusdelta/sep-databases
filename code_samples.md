* Remove Duplicates in Query
  * Post.where.title.is_uniq?
  * SELECT DISTINCT title * FROM posts;
  
* Filter records using inequalities, pattern matching, ranges, and boolean logic 
  * Post.where.id < 5
  * SELECT * FROM posts WHERE id < 5;
  
  * Post.where.rating < 9
  * SELECT * FROM posts WHERE rating < 9;
  
  * Post.where.published = true
  * SELECT * FROM posts WHERE published = true;
  
* Sort records in a particular order
  * Post.sort_by(id)
  * SELECT * FROM posts ORDER BY id ASC;
  
* Limit the number of records returned
  * Post.all.limit(3)
  * SELECT * FROM posts LIMIT 3;
  
* Group records into sections
  * Post.all.rating.sort(author)
  * SELECT rating FROM posts GROUP BY author;
  
* Perform calculations using aggregate functions
  * Post.all.sum(rating)
  * SELECT * FROM posts, COUNT(rating);

* Join tables using cross join, inner join, and outer join
  // Inner 
  * Post.all.merge(categories, post.category)
    - The idea here is that the merge function will take the table to be joined, and the attribute to match as arguments
  * SELECT * FROM posts JOIN categories ON posts.posts_category = post.category;
  
  // Cross
  * Post.title && Post.author && Category.post
  * SELECT posts.title, posts.author, categories.post FROM posts, categories
  
  // Outer
  * Post.all.merge(users, post.author)
  * SELECT * FROM posts LEFT JOIN users ON post.author = author.name
