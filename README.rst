django-tagify
----------------

A django tag input field using Tagify_ built for Django 2.0.
The tags are stored as a comma-delimited (unless if changed) ``String``.

.. _Tagify: https://github.com/yairEO/tagify/

Usage
===============

1. Models: Use ``TagsField`` to represent a tags field.
2. Forms: Make sure you display ``form.media`` in the html template, for the widget to render correctly.
3. Widget settings: Pass the settings dictionary as follows ``TagsField(widget_settings={...}``.

 * You can specify if 'duplicates' are allowed (boolean).
 * You can specify 'autocomplete' (boolean) - this matches from the whitelist.
 * You can specify 'enforceWhitelist' (boolean).
 * You can specify 'maxTags' (int).
 * You can specify the 'whitelist' (list containing strings).
 * You can specify the 'blacklist' (list containing strings).
 * You can specify the 'delimiter' (string).
 * You can specify the RegEx 'pattern' to validate the input (string).

If you want to allow blank inputs for tags make sure you set ``blank=True`` on ``TagsField``.
If blank inputs are allowed, they will not be filtered by the whitelist.

Note: If you use ``TagsField`` in a Form, then `Form.is_valid()` will automatically verify that its values
conform to those specify in its settings, to prevent malicious behaviour from end users.

Installation
===============

1. Install the module

  .. code-block::

      pip install django-tagify

2. Add ``django_tagify`` to your ``INSTALLED_APPS`` setting in the Django ``settings.py``.

    Example:

    .. code-block:: python

        INSTALLED_APPS = (
            # ...other installed apps
            'django_tagify',
        )
