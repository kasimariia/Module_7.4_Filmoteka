import random


class Video:

  def __init__(self, name, year, genre, views):
    self.name = name
    self.year = year
    self.genre = genre
    self.views = views

  def play(self):
    self.views += 1

  def __str__(self):
    return f"{self.name} ({self.year})"

  def __repr__(self):
    return str(self)


class Film(Video):

  def __str__(self):
    return f"{self.name} :: ({self.year})"


class Series(Video):

  def __init__(self, series_number: int, season_number: int, *args, **kwargs):
    super().__init__(*args, **kwargs)
    self.series_number = series_number
    self.season_number = season_number

  def __str__(self):
    return f"{self.name} S:{self.season_number} :: E:{self.series_number}"

  #Після перегляду серіалу інформація про певну серію відображається у вигляді рядка, наприклад: „Сімпсони S01E05” (де після S йде номер сезону в двозначному вигляді, а після E - номер серії, також у двозначному записі).
  # def play(self):
  #   super().play()


film_1 = Film(name='Titanic', year='1997', genre='Drama', views=1200)
film_2 = Film(name='The Shawshank Redemption',
              year=1994,
              genre='Drama',
              views=1500)
film_3 = Film(name='The Lord of the Rings: The Fellowship of the Ring',
              year=2001,
              genre='Adventures',
              views=850)

series_1 = Series(name='Game of Thrones',
                  series_number=2,
                  season_number=3,
                  year=2011,
                  genre='Adventure, Fantasy, Drama',
                  views=15800)
series_2 = Series(name='Squid Game',
                  series_number=3,
                  season_number=4,
                  year=2021,
                  genre='Thriller,Horror, Drama',
                  views=510)
series_3 = Series(name='Spartacus',
                  series_number=1,
                  season_number=3,
                  year=2010,
                  genre='Historical drama',
                  views=615)

library = [film_1, film_2, film_3, series_1, series_2, series_3]

# Play some videos and display information
for i in range(10):
  video = random.choice(library)
  video.play()
  print(f"Playing: {str(video)}")

print()
#фільтрує бібліотека
sorted_films = sorted([v for v in library if isinstance(v, Film)],
                      key=lambda f: f.name)
sorted_series = sorted([v for v in library if isinstance(v, Series)],
                       key=lambda s: s.name)

print('Sorted Films:')
print(sorted_films)

print('sorted series:')
print(sorted_series)

#Створення та відображення найпопулярніших
top_titles = sorted(library, key=lambda v: v.views, reverse=True)[:3]
print("Top Movies & TV Shows of the Day:")
for title in top_titles:
  print(f"{title} - {title.views} views")
