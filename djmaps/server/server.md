# djmaps/server folder

Contains various Django generated files for djmaps.

## settings.py

Contains settings for the Django web app framework including the django apps which are installed and the middleware whcih is installed.  Settings file is generated by Django, and there shouldn't be any settings we need to manually alter.

## urls.py

Only contains one list, urlpatterns, where URLs are routed to views.  Currently contains URL configurations for maps, crimePred, and admin.

## wsgi.py

Exposes the WSGI callable as a module-level variable named ``application``.