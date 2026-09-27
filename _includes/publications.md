<h2 id="publications" style="margin: 2px 0px 15px;">Publications</h2>

<div class="publications">
<ol class="bibliography" style="padding-left: 0;">

{% for link in site.data.publications.main %}

<li style="list-style: none; margin-bottom: 28px;">

<div class="pub-row"
     style="
       display: flex;
       align-items: center;
       gap: 22px;
       width: 100%;
     ">

  <!-- Paper Image -->
  <div class="pub-image"
       style="
         position: relative;
         flex: 0 0 220px;
         width: 220px;
         display: flex;
         justify-content: center;
         align-items: center;
       ">

    {% if link.image %}

    <img
      src="{{ link.image }}"
      class="teaser img-fluid z-depth-1"
      alt="{{ link.title }}"
      style="
        width: 100%;
        height: 140px;
        object-fit: contain;
        object-position: center;
        border-radius: 4px;
        background: #ffffff;
      "
    >

    {% if link.conference_short %}
    <abbr class="badge"
          style="
            position: absolute;
            top: 6px;
            left: 6px;
            padding: 4px 8px;
            font-size: 11px;
            font-weight: 600;
            text-decoration: none;
          ">
      {{ link.conference_short }}
    </abbr>
    {% endif %}

    {% endif %}

  </div>


  <!-- Paper Information -->
  <div class="pub-info"
       style="
         flex: 1;
         min-width: 0;
       ">

    <!-- Title -->
    <div class="title"
         style="
           font-size: 17px;
           font-weight: 600;
           line-height: 1.35;
           margin-bottom: 5px;
         ">

      {% if link.pdf %}
      <a href="{{ link.pdf }}" target="_blank">
        {{ link.title }}
      </a>
      {% else %}
        {{ link.title }}
      {% endif %}

    </div>


    <!-- Authors -->
    <div class="author"
         style="
           font-size: 14px;
           line-height: 1.5;
           margin-bottom: 3px;
         ">
      {{ link.authors }}
    </div>


    <!-- Venue -->
    <div class="periodical"
         style="
           font-size: 14px;
           line-height: 1.5;
           margin-bottom: 7px;
         ">
      <em>{{ link.conference }}</em>
    </div>


    <!-- Links -->
    <div class="links">

      {% if link.pdf %}
      <a href="{{ link.pdf }}"
         class="btn btn-sm z-depth-0"
         role="button"
         target="_blank"
         style="font-size:12px;">
        PDF
      </a>
      {% endif %}

      {% if link.doi %}
      <a href="{{ link.doi }}"
         class="btn btn-sm z-depth-0"
         role="button"
         target="_blank"
         style="font-size:12px;">
        DOI
      </a>
      {% endif %}

      {% if link.code %}
      <a href="{{ link.code }}"
         class="btn btn-sm z-depth-0"
         role="button"
         target="_blank"
         style="font-size:12px;">
        Code
      </a>
      {% endif %}

      {% if link.page %}
      <a href="{{ link.page }}"
         class="btn btn-sm z-depth-0"
         role="button"
         target="_blank"
         style="font-size:12px;">
        Project Page
      </a>
      {% endif %}

      {% if link.bibtex %}
      <a href="{{ link.bibtex }}"
         class="btn btn-sm z-depth-0"
         role="button"
         target="_blank"
         style="font-size:12px;">
        BibTeX
      </a>
      {% endif %}

      {% if link.notes %}
      <strong>
        <i style="color:#e74d3c; margin-left:5px;">
          {{ link.notes }}
        </i>
      </strong>
      {% endif %}

      {% if link.others %}
        {{ link.others }}
      {% endif %}

    </div>

  </div>

</div>

</li>

{% endfor %}

</ol>
</div>


<style>

/* Mobile layout */
@media (max-width: 768px) {

  .pub-row {
    flex-direction: column !important;
    align-items: flex-start !important;
    gap: 12px !important;
  }

  .pub-image {
    width: 100% !important;
    flex: none !important;
  }

  .pub-image img {
    width: 100% !important;
    height: auto !important;
    max-height: 220px !important;
    object-fit: contain !important;
  }

  .pub-info {
    width: 100% !important;
  }

}

</style>