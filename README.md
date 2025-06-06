# SW_projekt

Podzieliłem obraz na 4 części:  
- górna część jezdni  
- tory tramwajowe  
- dolna część jezdni  
- chodnik


Do wykrycia nowego obiektu do zidentyfikowania wykorzystałem funkcję structural_similarity() z biblioteki skimage.metrics. Wykorzystałem obraz tła, na którym nie było pojazdów i ludzi. Na każdym z czterech obrazów ustawiłem linię składającą się z kilku małych prostokątów, gdzie każdy z nich sprawdzał podobieństwo ze statycznym obrazem tła. W ten sposób w programie rozpoczynał się proces identyfikacji obiektu w obszarze, w którym wystąpiła różnica względem tła.  

Do detekcji ruchu wykorzystałem algorytm mieszanin Gaussowskich, z którego uzyskiwałem dobrze widoczne kształty poruszających się obiektów. Na ich podstawie wyznaczałem bounding boxes i na podstawie ich cech dodawałem nowo wykryty obiekt do licznika.  

Wykrywając tramwaj na torach, konieczne było zablokowanie zliczania na górnej części jezdni.  

Dodałem dla każdego z obiektów okno czasowe oraz liczbę wolnych klatek, aby precyzyjniej zliczać kilka obiektów występujących jeden po drugim.  

