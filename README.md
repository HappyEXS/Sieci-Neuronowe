# Mini porjekty w ramach zajęć z przedmiotu Sztuczne Sieci Neuronowe

Realizowane w zespole z Dominik Łopatecki

## Projekt 1 - wielowarstwowy regresor

Zadanie polega na przewidywaniu liczby wypożyczonych rowerów/hulajnóg w danym mieście. Do dyspozycji mamy informacje historyczne na temat tego, ile pojazdów zostało wypożyczonych o danej godzinie danego dnia, jakie były wtedy warunki atmosferyczne, czy był to zwykły dzień pracy czy wolny itp. Interesuje mnie wartość ostatniej kolumny ze zbioru data.csv, czyli cnt - to jest sumaryczna liczba wypożyczeń. Dodatkowo ta suma jest rozbita na liczbę wypożyczeń użytkowników zarejestrowanych (registered) i niezarejestrowanych (casual). Jeżeli ktoś chce to może stworzyć osobny model per grupa użytkowników, co może poprawić wyniki. Na koniec proszę zwrócić sumaryczną liczbę wypożyczeń, czyli przewidywane registered + przewidywane casual lub przewidywane cnt.

## Projekt 2 - rozbudowana rekresja/klasyfikacja

Załóżmy, że chcemy kupić mieszkanie. Do dyspozycji mamy 100 000 dolarów, możemy też wziąć kredyt na kolejne 250 tysięcy, co da nam w sumie budżet w wysokości 350 000 dolarów. Stwórzmy model który pomoże nam przewidzieć, czy mieszkanie o pewnych, zadanych parametrach, możemy kupić za własne pieniądze (cheap), z kredytem (average), czy jest poza naszym zasięgiem (expensive).

W oparciu o dostępne atrybuty zbuduj model, który pomoże oszacować, czy dana nieruchomość należy do klasy cheap, average czy expensive. Do dyspozycji mają Państwo dane treningowe (train_data.csv) z oryginalnymi cenami nieruchomości (SalePrice), oraz, tak jak ostatnio, zbiór testowy (test_data.csv).

## Projekt 3 - sieci konwolucyjne - klasyfikacja obrazów

ym razem zadanie polega na stworzeniu klasyfikatora obrazków działającego na 50 klasach z różnymi przedmiotami/zwierzętami itp. Do dyspozycji mają Państwo zbiór treningowy podzielony na odpowiednie podfoldery z klasami oraz zbiór testowy - bez podziału. Zbiór treningowy jest przygotowany w taki sposób by można go było łatwo załadować za pomocą klasy torchvision.ImageFolder wywołując np:
trainset = ImageFolder("data/train/", transform=train_transform)
Wówczas wszystkie przykłady zostaną przypisane do odpowiedniej klasy w zależności od tego w jakim podfolderze się znajdowały.
Jako że dane są bardzo duże to umieściłem je na OneDrive:
(train.zip i test_all.zip)

## Projekt 4 - modele generatywne (VAE) - generowanie obrazów

Tym razem zadanie będzie polegało na stworzeniu modelu generatywnego który generował będzie nowe obrazki przedstawiające znaki drogowe. Do wyboru mają Państwo dowolny model generatywny (VAE, GAN, GLOW, VAEGAN, czy modele dyfuzyjne (o ile mają Państwo za dużo GPU)). Zbiór danych udostępniony jest przez onedrive (trafic_32.zip) i ma taką samą strukturę jak poprzednio (zgodną z domyślnymi ustawieniami ImageFolderu). Znaki podzielone są na klasy, które jak najbardziej mogą Państwo wykorzystywać do generowania próbek. Tym razem zamiast predykcji proszę o zwrócenie mi kodu z implementacją eksperymentów i przykładowe 1000 wygenerowanych za pomocą Państwa metody próbek.

## Projekt 5 - sieci sekwecyjne (LSTM) - klasyfikacja utworów (sekwencji) o różnych rozmiarach

ewien słuchacz szkoły muzycznej ma w sobie niesamowity talent. Jednak przed jej ukończeniem wstrzymuje go jeden przedmiot - "Kompozytorzy muzyki klasycznej". Słuchacz ten, mając dość niepowodzeń w zdawaniu tego tematu, zwraca się do Was o pomoc.

Zadanie polega na stworzeniu modelu rekurencyjnego, który będzie przewidywał kompozytora danego utworu klasycznego w oparciu o jego zapis w formie sekwencji akordów. Akordy znormalizowane zostały do klucza C-dur lub a-moll, w zależności od skali utworu (durowa/molowa).
Dane przygotowane są w postaci pickle (https://docs.python.org/3/library/pickle.html), w których znajduje się lista krotek z sekwencjami i odpowiadającymi im klasami (kompozytorami), odpowiednio: {0: 'bach', 1: 'beethoven', 2: 'debussy', 3: 'scarlatti', 4: 'victoria'}. Dane treningowe znajdują się w pliku train.pkl. W pliku test_no_target.pkl znajdują się testowe sekwencje, dla których predykcje mają Państwo przewidzieć.

Uwaga, utwory mogą mieć różne długości. Do stworzenia batchy dla przykładów różnej długości proszę wykorzystać omówiony na zajęciach padding i trenować z wykorzystaniem spaddowanych tensorów lub spakowanych sekwencji (PackedSequence).

## Projekt 6 - coming soon