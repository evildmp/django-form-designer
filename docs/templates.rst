#########
Templates
#########

Form template
=============

A form's template is set in its ``form_template_name``.

If none is provided, ``form_designer.settings.DEFAULT_FORM_TEMPLATE`` will be
used (whch itself defaults to ``html/formdefinition/forms/as_p.html``).

When a form renders, it renders to the ``html/formdefinition/detail.html``
template. This *includes* ``form_template_name``, and *extends*
``html/formdefinition/base.html``.

In the case of a django CMS plugin, it renders to
``html/formdefinition/plugin_detail.html``.

Base template
=============

Unless you're using django CMS plugins to deliver your forms, you'll need to
override ``html/formdefinition/detail.html`` so that the forms Django Form
Designer publishes match your site's page structure and appearance.

Heading levels
==============

The provided ``detail.html`` and ``plugin_detail`` templates place the form's
``title`` in an HTML heading.

This defaults to ``<h2>``. However, if the context variable
``body_heading_level`` (i.e., a level for headings in the body of the page,
rather than those reserved for page titles and other purposes) is set, it will
use that.

A convenient way to do this is to use ``{% with body_heading_level=2 %}`` and
``{% endwith %}`` around the main body section of your site's base template.'