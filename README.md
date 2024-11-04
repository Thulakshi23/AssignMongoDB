# AssignMongoDB
### 01. Create a Database called movies:
```sh
test> use movies

switched to db movies
```

### 02.Create a Collection called moviedetails:
```sh
movies> db.createCollection("moviedetails")
```

### 03. Create above 5 movie documents into a moviedetails collection.

```sh 
test> db.moviedetails.insertMany([
  { title: "Vikram", genre: "Drama", director: "Lokesh Kanakaraj", release_year: 2022 },
  { title: "Vettaiyan", genre: "Action", director: "Ganavel", release_year: 2024 },
  { title: "Kanguva", genre: "Fantasy", director: "Siva", release_year: 2025 },
  { title: "Leo", genre: "Action", director: "Lokesh Kanakaraj", release_year: 2023 },
  { title: "Vidamuyatchi", genre: "Thriller", director: "Magizh Thirumeni", release_year: 2025 }
])
```

### 04. List all documents created.
```sh 
test> db.moviedetails.find().pretty()

[
  {
    "_id": ObjectId("..."),
    "title": "Vikram",
    "genre": "Drama",
    "director": "Lokesh Kanakaraj",
    "release_year": 2022
  },
  {
    "_id": ObjectId("..."),
    "title": "Vettaiyan",
    "genre": "Action",
    "director": "Ganavel",
    "release_year": 2024
  },
  {
    "_id": ObjectId("..."),
    "title": "Kanguva",
    "genre": "Fantasy",
    "director": "Siva",
    "release_year": 2025
  },
  {
    "_id": ObjectId("..."),
    "title": "Leo",
    "genre": "Action",
    "director": "Lokesh Kanakaraj",
    "release_year": 2023
  },
  {
    "_id": ObjectId("..."),
    "title": "Vidamuyatchi",
    "genre": "Thriller",
    "director": "Magizh Thirumeni",
    "release_year": 2025
  }
]
```
### 05. List Lokesh Kanakaraj’s movies.
```sh 
test> db.moviedetails.find({ director: "Lokesh Kanakaraj" }).pretty()

[
  {
    "_id": ObjectId("..."),
    "title": "Vikram",
    "genre": "Drama",
    "director": "Lokesh Kanakaraj",
    "release_year": 2022
  },
  {
    "_id": ObjectId("..."),
    "title": "Leo",
    "genre": "Action",
    "director": "Lokesh Kanakaraj",
    "release_year": 2023
  }
]
```

### 06. List Lokesh Kanakaraj’s movies released in 2023.
```sh 
test> db.moviedetails.find({ director: "Lokesh Kanakaraj", release_year: 2023 }).pretty()

[
  {
    "_id": ObjectId("..."),
    "title": "Leo",
    "genre": "Action",
    "director": "Lokesh Kanakaraj",
    "release_year": 2023
  }
]
```

### 07. Delete the movie which you don’t like.
```sh 
test> db.moviedetails.deleteOne({ title: "Leo" })

{acknowledged : true, deletedCount: 1 }
```

### 08. Add the movie which is your favourite.
```sh
test> db.moviedetails.insertOne({ title: "Amaran", genre: "Action", director: "Rajkumar Periasamy", release_year: 2024 })

{
  "acknowledged" : true,
  "insertedId" : ObjectId("...")
}
```
### 09. List movie Directed by Magizh Thirumeni in 2025.
```sh
test> db.moviedetails.find({ director: "Magizh Thirumeni", release_year: 2025 }).pretty()

[
  {
    "_id": ObjectId("..."),
    "title": "Vidamuyatchi",
    "genre": "Thriller",
    "director": "Magizh Thirumeni",
    "release_year": 2025
  }
]
```
### 10.List out the Director’s Name in your document.
```sh
test> db.moviedetails.distinct("director")

[
    "Ganavel",
    "Lokesh Kanakaraj",
    "Rajkumar Periasamy",
    "Siva"
]















