#  Django Duration Widget


### When to use?

You can find duration field as below which is not far good for humans to use.

![Duration](/docs/duration.png)



Django duration widget is used for simplfiend Django model's `Duration` field.


### Quick start

1. Install `django-durationwidget` using `pip`

    `pip install django-durationwidget`

2. Add `durationwidget` to your `INSTALLED_APPS` setting like this::

    ```python
    INSTALLED_APPS = [
        ...
        'durationwidget',
    ]
    ```
3. Make sure to set `APP_DIRS` to `True` in settings.py

    ```python
    TEMPLATES = [
        {
            'BACKEND': 'django.template.backends.django.DjangoTemplates',
            'DIRS': [
                os.path.join(BASE_DIR, 'templates'),
                ...
            ],
            'APP_DIRS': True,  # Setup this to True
            'OPTIONS': {
                ...
            },
        },
    ]
    ```

4. Cheer up you are ready to use `TimeDurationWidget` as normal widget as below.

    ```python
    from django import forms
    from durationwidget.widgets import TimeDurationWidget
    
    from .models import YourModel
    
    
    class CustomForm(forms.ModelForm):
        ...
        duration = forms.DurationField(widget=TimeDurationWidget(), required=False)
    
        class Meta:
            model = YourModel
            ...
    
    ```

It will render Duration field as below

![Duration field](/docs/duration_final.png)


## TimeDurationWidget

```python
duration = forms.DurationField(widget=TimeDurationWidget(
    show_days=True, show_hours=True, show_minutes=True, show_seconds=True
), required=False)
```
    
 Following keyword argument can be passed to show/ hide fields in duration widget.
 
 > By default all keyword arguments are set to `True`
 
`show_days` : To display/ hide days field in widget<br/>
`show_hours` : To display/ hide hours field in widget<br/>
`show_minutes` : To display/ hide minutes field in widget<br/>
`show_seconds` : To display/ hide seconds field in widget<br/>