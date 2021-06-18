![Untitled](https://user-images.githubusercontent.com/4121550/122529655-acd0da00-d058-11eb-8a3d-e91e7dda0a9a.png)
https://dbdiagram.io/d/60cc3ad60c1ff875fcd56632

```sql
Table users {
  id int [pk, increment] // auto-increment
  name varchar
  email varchar
  created_at timestamp [default: `now()`]
}

Table followers {
  id int [pk, increment] // auto-increment
  user_id int [ref: > users.id]
  follower_id int [ref: > users.id]
}

Table posts {
  id int [pk, increment] // auto-increment
  user_id int [ref: > users.id]
  type varchar
  description varchar
  total_likes int
  total_hashtags int
  tatal_comments int
  created_at datetime [default: `now()`]
  updated_at datetime 
}

Table comments {
   id int [pk, increment]
   post_id int [ref: > posts.id]
   user_id int [ref: > users.id]
   description varchar
}

Table likes {
  id int [pk, increment]
  post_id int [ref: > posts.id]
  user_id int [ref: > users.id]
}

Table hashtags {
  id int [pk, increment]
  description varchar
  post_id int [ref: > posts.id]
}

Table posts_hashtags{
  id int [pk, increment]
  hashtag_id int [ref: > hashtags.id]
  post_id int [ref: > posts.id]
}
```
