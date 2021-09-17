# README

  Proto SpaceのER図

usersテーブル ||--o{ usersテーブル: owns
prototypesテーブル ||--o{ commentsテーブル : has
commentsテーブル }|--o{ commentsテーブル : does

usersテーブル {
  email    (string型,NOT NULL)
  password (string型,NOT NULL)
  name     (string型,NOT NULL)
  profile  (text型,NOT NULL)
  occupation (text型,NOT NULL)
  position (text型,NOT NULL)
}

prototypesテーブル {
  title(string型,NOT NULL)
  catch_copy(text型,NOT NULL)
  concept(text型,NOT NULL)
  image(ActiveStorageで実装)
  user(references型)
}

commentsテーブル {
  text(text型,NOT NULL)
  user(references型)
  prototype(references型)
}