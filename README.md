# 📝 Blog Web Application  

## 🌟 Opis projektu  
Prosty blog napisany w Django z wykorzystaniem wzorca architektonicznego **MVC**. Aplikacja pozwala na:  
- 📄 Przeglądanie listy postów  
- ➕ Dodawanie nowych postów  
- 💅 Wyświetlanie strony z estetycznym stylem CSS  

---

## 🚀 Funkcjonalności  
- 🖥️ **Wyświetlanie listy postów** - dynamiczna lista dodanych przez użytkownika treści  
- ✍️ **Dodawanie nowych postów** - proste formularze w HTML  
- 🎨 **Stylizacja CSS** - minimalistyczny i przejrzysty design  

---

## 📦 Technologie użyte w projekcie  
- **Python 3.12** 🐍  
- **Django 5.1.5** 🌐  
- **HTML5** & **CSS3** 🎨  

---

## 🛠️ Instrukcja instalacji  


1. **Utwórz wirtualne środowisko**:  
   ```bash
   python -m venv venv
   source venv/bin/activate  # Na Windows: venv\Scripts\activate
   ```

2. **Zainstaluj wymagane pakiety**:  
   ```bash
   pip install -r requirements.txt
   ```

3. **Wykonaj migracje bazy danych**:  
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

4. **Uruchom serwer**:  
   ```bash
   python manage.py runserver
   ```

5. **Otwórz w przeglądarce**:  
   Domyślnie aplikacja działa pod adresem:  
   [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

---

## 🔗 Przydatne linki  
- [Dokumentacja Django](https://docs.djangoproject.com/en/stable/)  
- [Bootstrap CSS Framework](https://getbootstrap.com/)  

---

## 🛡️ Licencja  
Projekt udostępniany na licencji MIT.  

---

## ⚠️ Możliwe problemy i sposoby ich rozwiązania

Podczas pracy z projektem mogą wystąpić pewne problemy związane z konfiguracją Django, bazą danych lub frontendem. Poniżej znajdziesz najczęstsze problemy oraz zalecane rozwiązania:

### 1. **Brak pliku `db.sqlite3`**
- **Problem**: Po uruchomieniu aplikacji w Django, jeśli nie ma pliku bazy danych (np. `db.sqlite3`), mogą wystąpić błędy przy próbie uruchomienia aplikacji.
- **Rozwiązanie**: 
   - Upewnij się, że wykonałeś migracje:
   ```bash
   python manage.py migrate
   ```

### 2. **Błąd: `Invalid block tag on line X: 'static'`**
- **Problem**: Przy próbie załadowania strony, Django wyświetla błąd, że nie rozpoznaje tagu `{% static %}`.
- **Rozwiązanie**: 
   - W pliku HTML upewnij się, że załadowano tagi statyczne:
   ```html
   {% load static %}
   ```
   - Jeśli to nie pomoże, sprawdź, czy masz poprawnie skonfigurowany folder `static` w ustawieniach Django (plik `settings.py`).

### 3. **Błąd: `Model class blog.models.Post doesn't declare an explicit app_label`**
- **Problem**: Jeśli aplikacja Django nie jest poprawnie dodana do ustawienia `INSTALLED_APPS`, może wystąpić ten błąd.
- **Rozwiązanie**: 
   - Upewnij się, że w pliku `settings.py` aplikacja `blog` znajduje się w sekcji `INSTALLED_APPS`:
   ```python
   INSTALLED_APPS = [
       ...
       'blog',
       ...
   ]
   ```

### 4. **Nie znaleziono szablonu HTML**  
- **Problem**: Django zgłasza błąd, że nie może znaleźć szablonu HTML.
- **Rozwiązanie**: 
   - Sprawdź, czy szablon HTML znajduje się w odpowiednim katalogu (`blog/templates/blog/`).
   - Jeśli masz problem z ładowaniem statycznych plików CSS, upewnij się, że masz poprawnie ustawiony folder `static` w projekcie oraz odpowiednią konfigurację w pliku `settings.py`:
   ```python
   STATICFILES_DIRS = [
       BASE_DIR / "static",
   ]
   ```

### 5. **Problemy z uprawnieniami użytkowników w panelu administracyjnym**
- **Problem**: Jeśli nie możesz zalogować się do panelu administracyjnego, może być konieczne utworzenie konta admina.
- **Rozwiązanie**:  
   - Stwórz użytkownika administracyjnego:
   ```bash
   python manage.py createsuperuser
   ```
