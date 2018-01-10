# Coding best practices & review

1. Avoid implicit logic in source code for easy understand and maintain
e.g:
```python
def function_test(locations):
    #locations = [{"city": "Saigon", "ID" : 100, "Country" : "Vietnam"}]
    cities = []
    for i in range(len(locations)):
        location = locations[i]
        try:
            city = location["city"]
            if city not in cities:
                cities.append(city)
        except KeyError as ex:
            print(ex)
            #<----- missing continue here
```
