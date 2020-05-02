# Create Autofill in JetBrains Software
Sometimes, The IDE doesn't support autofill syntax, so we need to add it manually.
in this path:`settings-editor-live-templates`.

## How to do
If I want to achieve this:
```
{% if  %}
{% endif %}
```
I can add:
```
{% if $END$ %}
{% endif %}
```
and name abbreviation with **if**, and expand it with the `tab` key.
