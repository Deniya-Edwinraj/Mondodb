MongoDB Exercise 01

**1. Create a Database called movies.**
``use movies``

**output:**
``switched to db movies``

**2. Create a collection called moviedetails.**
``db.createCollection("moviedetails")``

**output:**
``{ ok: 1 }``

**3. Create above 5 movie documents into a moviedetails collection.**
``db.moviedetails.insertMany([{MovieTitle:"Jurassic Park",Type:"Adventure",Director:"Steven Spielberg",ReleaseYear:"1993"},{MovieTitle:"Forrest Gump",Type:"Drama",Director:"Robert Zemeckies",ReleaseYear:"1994"},{MovieTitle:"Titanic",Type:"Romance",Director:"James Cameron",ReleaseYear:"1997"},{MovieTitle:"The Dark Knight",Type:"Action",Director:"Christopher Nolan",ReleaseYear:"2008"},{MovieTitle:"Avatar",Type:"Science Fiction",Director:"James Cameron",ReleaseYear:"2009"}])``

**output:**
``{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("654ca59942121c0782131bca"),
    '1': ObjectId("654ca59942121c0782131bcb"),
    '2': ObjectId("654ca59942121c0782131bcc"),
    '3': ObjectId("654ca59942121c0782131bcd"),
    '4': ObjectId("654ca59942121c0782131bce")
  }
}``

**4. List all documents created.**
``db.moviedetails.find()``

**output:**
``[
  {
    _id: ObjectId("654ca59942121c0782131bca"),
    MovieTitle: 'Jurassic Park',
    Type: 'Adventure',
    Director: 'Steven Spielberg',
    ReleaseYear: '1993'
  },
  {
    _id: ObjectId("654ca59942121c0782131bcb"),
    MovieTitle: 'Forrest Gump',
    Type: 'Drama',
    Director: 'Robert Zemeckies',
    ReleaseYear: '1994'
  },
  {
    _id: ObjectId("654ca59942121c0782131bcc"),
    MovieTitle: 'Titanic',
    Type: 'Romance',
    Director: 'James Cameron',
    ReleaseYear: '1997'
  },
  {
    _id: ObjectId("654ca59942121c0782131bcd"),
    MovieTitle: 'The Dark Knight',
    Type: 'Action',
    Director: 'Christopher Nolan',
    ReleaseYear: '2008'
  },
  {
    _id: ObjectId("654ca59942121c0782131bce"),
    MovieTitle: 'Avatar',
    Type: 'Science Fiction',
    Director: 'James Cameron',
    ReleaseYear: '2009'
  }
]``

**5.List James Cameron’s movies.**
``db.moviedetails.find({Director:"James Cameron"},{_id:0,Type:0,Director:0,ReleaseYear:0})``

**output:**
``[ { MovieTitle: 'Titanic' }, { MovieTitle: 'Avatar' } ]``

**6. List  James Cameron’s movies released in 2009.**
   ``db.moviedetails.find({Director:"James Cameron",ReleaseYear:"2009"},{_id:0,Type:0,Director:0,ReleaseYear:0,})``

**output:**
``[ { MovieTitle: 'Avatar' } ]``

**7.Delete the movie which you don’t like.**
``db.moviedetails.deleteOne({MovieTitle:'Forrest Gump'})``

**output:**
``{ acknowledged: true, deletedCount: 1 }``  
``[
  {
    _id: ObjectId("654ca59942121c0782131bca"),
    MovieTitle: 'Jurassic Park',
    Type: 'Adventure',
    Director: 'Steven Spielberg',
    ReleaseYear: '1993'
  },
  {
    _id: ObjectId("654ca59942121c0782131bcc"),
    MovieTitle: 'Titanic',
    Type: 'Romance',
    Director: 'James Cameron',
    ReleaseYear: '1997'
  },
  {
    _id: ObjectId("654ca59942121c0782131bcd"),
    MovieTitle: 'The Dark Knight',
    Type: 'Action',
    Director: 'Christopher Nolan',
    ReleaseYear: '2008'
  },
  {
    _id: ObjectId("654ca59942121c0782131bce"),
    MovieTitle: 'Avatar',
    Type: 'Science Fiction',
    Director: 'James Cameron',
    ReleaseYear: '2009'
  }
]
``

**8. Add the movie which is your favourite.**
 ``db.moviedetails.insertOne({MovieTitle:"Geostorm",Type:"Science fiction",Director:"Dean Devlin",ReleaseYear:"2017"})``

**output:**
``{
  acknowledged: true,
  insertedId: ObjectId("654cb63c2a2f3cee6938d79d")
}``

**9. List movie Directed  by Christopher Nolan in 1994.**
``db.moviesdetails.find({Director:"Christopher Nolan",ReleaseYear:"1994"},{_id:0,Type:0,Director:0,ReleaseYear:0})``

**output:**
``
``

**10.List out the Director’s Name in your document.** 
``db.moviedetails.distinct("Director")``

**output:**
``[
  'Christopher Nolan',
  'Dean Devlin',
  'James Cameron',
  'Steven Spielberg'
]``

# Mondodb
