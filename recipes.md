---
layout: default
title: Recipes
permalink: /recipes/index.html
---
<div class="index">
<header><h1>{{ page.title }}</h1></header>
{% assign recipes_grouped = site.recipes | group_by: "category" | sort: "name" %}{% for group in recipes_grouped %}
<section>
<header><h1>{{ group.name | capitalize }}</h1></header>
{% assign recipes = group.items | sort: "title" %}{% for recipe in recipes %}
<article class="h-recipe">
<p><a href="{{ recipe.url | prepend: site.baseurl }}" class="p-name">{{ recipe.title }}</a></p>
</article>
{% endfor %}
</section>
{% endfor %}
</div>
