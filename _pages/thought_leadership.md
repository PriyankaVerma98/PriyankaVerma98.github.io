---
layout: page
permalink: /thought-leadership/
title: Impact
description: Beyond peer-reviewed publications, I strive to translate research into public-facing formats, engage with non-expert audiences, and convene communities around responsible technology design.
nav: true
nav_order: 4
---

<style>
  .impact-section > h2.impact-section-title {
    font-size: 1.5rem;
    font-weight: 500;
    margin-bottom: 1rem;
  }

  .impact-item h3.impact-item-title {
    font-size: 1.15rem;
    font-weight: 500;
    margin-bottom: 0.35rem;
  }

  .impact-item-year {
    font-weight: 100;
    margin-bottom: 0.5rem;
  }

  .impact-item-description {
    font-weight: 400;
  }
</style>

{% for section in site.data.impact.sections %}
  <section class="impact-section{% unless forloop.first %} mt-5{% endunless %}">
    <h2 class="impact-section-title">{{ section.title }}</h2>

    {% for item in section.items %}
      <article class="impact-item mt-4">
        {% if item.image and item.image != '' %}
          <div class="impact-item-image mb-3" style="max-width: 320px;">
            {% include figure.liquid path=item.image class="rounded z-depth-1" %}
          </div>
        {% endif %}

        <h3 class="impact-item-title mb-1">{{ item.title }}</h3>

        {% if item.year and item.year != '' %}
          <p class="impact-item-year mb-2">{{ item.year }}</p>
        {% endif %}

        <div class="impact-item-description mb-0">{{ item.description | markdownify }}</div>
      </article>
    {% endfor %}
  </section>
  {% unless forloop.last %}<hr class="my-5">{% endunless %}
{% endfor %}
