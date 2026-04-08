# Aggregations and Annotations in Django ORM 

In Django, sometimes we don’t just want data — we want **calculated results**.

Example:

- Total number of products
- Average price

Django gives us:
- Aggregations
- Annotations


## What is Aggregation?

Aggregation means:
 **Get one single result from many rows**

### Example

Model:
```python
class Product(models.Model):
    name = models.CharField(max_length=100)
    price = models.IntegerField()
```

Code:
```python
from django.db.models import Avg

avg_price = Product.objects.aggregate(Avg('price'))
print(avg_price)
```

Output:
```
{'price__avg': 500}
```

 It calculates **average price of all products**

---

## What is Annotation?

Annotation means:
 **Add calculated value to each row**

### Example

Models:
```python
class Order(models.Model):
    name = models.CharField(max_length=100)

class Item(models.Model):
    order = models.ForeignKey(Order, on_delete=models.CASCADE)
    price = models.IntegerField()
```

Code:
```python
from django.db.models import Sum

orders = Order.objects.annotate(total_price=Sum('item__price'))

for o in orders:
    print(o.name, o.total_price)
```

Output:
```
Order1 1000
Order2 500
```

### Meaning:
 Each order gets its own total price


## Key Difference

| Aggregation | Annotation |
|------------|------------|
| One result | Result per row |
| Returns dictionary | Returns queryset |
| Used for totals | Used for per-object values |

---

## When to Use

Use Aggregation:
- Total users
- Average marks

Use Annotation:
- Total orders per user
- Total price per order


## Final Summary

- Aggregation gives a single result by performing calculations on multiple rows.
  
- Annotation gives result for each row