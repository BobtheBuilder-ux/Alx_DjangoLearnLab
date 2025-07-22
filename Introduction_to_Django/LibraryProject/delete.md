from bookshelf.models import Book
book = Book.objects.get(title="Nineteen Eighty-Four")
book.delete()
# Expected output: (1, {'bookshelf.Book': 1})
# To verify:
Book.objects.all()
# Expected output: <QuerySet []>
