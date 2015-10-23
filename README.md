# Blog Fake API

Use it to play with your Front-end MV* JS.

### Install:
```
npm install
```

### Run:
```
npm start
```

## Routes

### Resources

- http://localhost:3000/users
- http://localhost:3000/categories
- http://localhost:3000/posts
- http://localhost:3000/comments
- http://localhost:3000/profile

### Home
http://localhost:3000

### Plural routes

```
GET    /posts
GET    /posts/1
POST   /posts
PUT    /posts/1
PATCH  /posts/1
DELETE /posts/1
```

### Singular routes

```
GET    /profile
POST   /profile
PUT    /profile
PATCH  /profile
```

### Filter

Use `.` to access deep properties

```
GET /posts?title=Foo
GET /posts?id=1&id=2
GET /comments?user.name=John
```

### Slice

Add `_start` and `_end` or `_limit` (an `X-Total-Count` header is included in the response)

```
GET /posts?_start=20&_end=30
GET /posts/1/comments?_start=20&_end=30
GET /posts?_limit=10
```

### Sort

Add `_sort` and `_order` (ascending order by default)

```
GET /posts?_sort=views&_order=DESC
```

### Range

Add `_gte` or `_lte`

```
GET /posts?views_gte=10&views_lte=20
```

### Full-text search

Add `q`

```
GET /posts?q=internet
```

### Relationships

To include children resources, add `_embed`

```
GET /posts?_embed=comments
GET /posts/1?_embed=comments
```

To include parent resource, add `_expand`

```
GET /comments?_expand=post
GET /comments/1?_expand=post
```

To get nested resources (by default one level, [add routes](#add-routes) for more)

```
GET /posts/1/comments
```
