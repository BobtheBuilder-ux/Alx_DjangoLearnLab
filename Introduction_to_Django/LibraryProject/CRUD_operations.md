# CRUD Operations

## Create

```python
from bookshelf.models import Book
Book.objects.create(title="1984", author="George Orwell", publication_year=1949)
# Expected output: <Book: 1984>
```

## Retrieve

```python
from bookshelf.models import Book
book = Book.objects.get(title="1984")
print(f"Title: {book.title}, Author: {book.author}, Publication Year: {book.publication_year}")
# Expected output: Title: 1984, Author: George Orwell, Publication Year: 1949
```

## Update

```python
from bookshelf.models import Book
book = Book.objects.get(title="1984")
book.title = "Nineteen Eighty-Four"
book.save()
# Expected output: (No direct output, but the change is saved)
# To verify:
updated_book = Book.objects.get(pk=book.pk)
print(updated_book.title)
# Expected output: Nineteen Eighty-Four
```

## Delete

```python
from bookshelf.models import Book
book = Book.objects.get(title="Nineteen Eighty-Four")
book.delete()
# Expected output: (1, {'bookshelf.Book': 1})
# To verify:
Book.objects.all()
# Expected output: <QuerySet []>
