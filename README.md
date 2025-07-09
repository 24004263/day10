# Create an `Expense` model that stores amount, description, category (choices), and expense_date. Category could be Food, Travel, Bills.
# admin.py:
```
from django.contrib import admin
from .models import Expense

admin.site.register(Expense)
```
# models.py:
```
from django.db import models

class Expense(models.Model):
    CATEGORY_CHOICES = [
        ('Food', 'Food'),
        ('Travel', 'Travel'),
        ('Bills', 'Bills'),
    ]

    amount = models.DecimalField(max_digits=10, decimal_places=2)
    description = models.TextField()
    category = models.CharField(max_length=20, choices=CATEGORY_CHOICES)
    expense_date = models.DateField()

    def __str__(self):
        return f"{self.category} - ₹{self.amount}"
```
# output:
![Screenshot 2025-07-09 112908](https://github.com/user-attachments/assets/b61d1d07-f303-4bd9-bc89-030c461b9c8b)
