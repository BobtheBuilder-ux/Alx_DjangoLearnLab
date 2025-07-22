from bookshelf.models import Book
book = Book.objects.get(title="1984")
book.title = "Nineteen Eighty-Four"
book.save()
# Expected output: (No direct output, but the change is saved)
# To verify:
updated_book = Book.objects.get(pk=book.pk)
print(updated_book.title)
# Expected output: Nineteen Eighty-Four
