# Zadanie rekrutacyjne – Wtyczka WordPress: Licznik wyświetleń posta

Wtyczka, funkcje:

- zlicza odwiedziny posta raz na sesję użytkownika,
- zapisuje dane w post_meta,
- wyświetla liczbę odwiedzin na końcu treści posta,
- Prezentuje 5 najczęściej oglądanych postów (Narzędzia → Top Posty)

---
Działanie

Wtyczka automatycznie zlicza liczbę odwiedzin każdego posta w WordPressie. Gdy użytkownik wejdzie na stronę pojedynczego wpisu, licznik zwiększa się o 1 – ale tylko raz na sesję (dzięki wykorzystaniu mechanizmu $_SESSION w PHP).

Liczba odwiedzin jest przechowywana jako meta dane wpisu (post_meta) pod kluczem np_post_views, z wykorzystaniem funkcji WordPressa: get_post_meta() i update_post_meta().

Na końcu treści posta, za pomocą filtra the_content, automatycznie dodawana jest informacja o liczbie wyświetleń. Dodatkowo w kokpicie administratora, w zakładce Narzędzia → Top Posty, wyświetlana jest tabela z 5 najczęściej oglądanymi wpisami, wygenerowana za pomocą klasy WP_Query sortującej wyniki według wartości meta_value_num.

---

Instalacja

1. Spakuj folder zadanieRekrutacyjnePHP do archiwum .zip
2. W WordPressie przejdź do Wtyczki → Dodaj nową → Wyślij wtyczkę
3. Wybierz .zip, zainstaluj i kliknij "Włącz"

---


Jak przetestować

1. Przejdź do dowolnego wpisu → licznik odwiedzin zwiększy się raz na sesje (Można zwiększać liczbe wyświetleń otwierajac wpisy w trybie anonimowym wyszukiwarki)
2. Na końcu posta wyświetli się np.: Liczba wyświetleń: 5
