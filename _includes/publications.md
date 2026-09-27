<h2 id="publications" style="margin: 2px 0px 15px;">Publications</h2>

<div class="publications">

<ol class="bibliography pub-list">

{% for link in site.data.publications.main %}

<li class="pub-item">

  <div class="pub-row">

    <!-- ==================== -->
    <!-- Paper Teaser Image   -->
    <!-- ==================== -->
    <div class="pub-image-wrapper">

      {% if link.image %}

      <img
        src="{{ link.image }}"
        class="pub-teaser"
        alt="{{ link.title }}"
      >

      <!-- Conference / Journal Badge -->
      {% if link.conference_short %}
      <span class="pub-badge">
        {{ link.conference_short }}
      </span>
      {% endif %}

      {% endif %}

    </div>


    <!-- ==================== -->
    <!-- Paper Information    -->
    <!-- ==================== -->
    <div class="pub-info">

      <!-- Title -->
      <div class="pub-title">

        {% if link.pdf %}
        <a href="{{ link.pdf }}" target="_blank">
          {{ link.title }}
        </a>
        {% else %}
          {{ link.title }}
        {% endif %}

      </div>


      <!-- Authors -->
      <div class="pub-authors">
        {{ link.authors }}
      </div>


      <!-- Conference / Journal -->
      <div class="pub-venue">
        <em>{{ link.conference }}</em>
      </div>


      <!-- Links -->
      <div class="pub-links">

        {% if link.pdf %}
        <a
          href="{{ link.pdf }}"
          class="pub-btn"
          target="_blank">
          PDF
        </a>
        {% endif %}


        {% if link.doi %}
        <a
          href="{{ link.doi }}"
          class="pub-btn"
          target="_blank">
          DOI
        </a>
        {% endif %}


        {% if link.code %}
        <a
          href="{{ link.code }}"
          class="pub-btn"
          target="_blank">
          Code
        </a>
        {% endif %}


        {% if link.page %}
        <a
          href="{{ link.page }}"
          class="pub-btn"
          target="_blank">
          Project Page
        </a>
        {% endif %}


        {% if link.bibtex %}
        <a
          href="{{ link.bibtex }}"
          class="pub-btn"
          target="_blank">
          BibTeX
        </a>
        {% endif %}


        {% if link.notes %}
        <span class="pub-note">
          {{ link.notes }}
        </span>
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

/* =========================================================
   Publication List
   ========================================================= */

.pub-list {
  padding-left: 0 !important;
  margin-left: 0 !important;
}


.pub-item {
  list-style: none !important;
  margin-bottom: 28px;
  padding: 0;
}


/* =========================================================
   Main Row
   ========================================================= */

.pub-row {
  display: flex;
  align-items: center;

  width: 100%;

  gap: 28px;
}


/* =========================================================
   Paper Image
   ========================================================= */

.pub-image-wrapper {
  position: relative;

  flex: 0 0 330px;
  width: 330px;

  height: 210px;

  display: flex;
  align-items: center;
  justify-content: center;

  overflow: visible;
}


/* Actual teaser image */
.pub-teaser {

  width: 100%;
  height: 100%;

  object-fit: contain;
  object-position: center;

  background-color: #ffffff;

  border-radius: 5px;

  box-shadow:
    0 3px 8px rgba(0, 0, 0, 0.20);

}


/* =========================================================
   Conference / Journal Badge
   ========================================================= */

.pub-badge {

  position: absolute;

  top: 8px;
  left: 8px;

  z-index: 10;

  display: inline-block;

  padding: 4px 9px;

  background-color: #268bd2;
  color: #ffffff !important;

  font-size: 12px;
  font-weight: 600;

  line-height: 1.3;

  border-radius: 4px;

  text-decoration: none !important;

  white-space: nowrap;

  box-shadow:
    0 1px 4px rgba(0, 0, 0, 0.18);
}


/* =========================================================
   Paper Information
   ========================================================= */

.pub-info {

  flex: 1;

  min-width: 0;

  padding-right: 5px;

}


/* Paper title */
.pub-title {

  font-size: 18px;

  font-weight: 600;

  line-height: 1.4;

  margin-bottom: 7px;

}


.pub-title a {

  text-decoration: none;

}


/* Authors */
.pub-authors {

  font-size: 15px;

  line-height: 1.55;

  margin-bottom: 4px;

}


/* Conference / Journal */
.pub-venue {

  font-size: 15px;

  line-height: 1.5;

  margin-bottom: 10px;

}


/* =========================================================
   Buttons
   ========================================================= */

.pub-links {

  display: flex;

  align-items: center;

  flex-wrap: wrap;

  gap: 5px;

}


.pub-btn {

  display: inline-block;

  padding: 3px 11px;

  border: 1px solid #222;

  color: #111 !important;

  background: transparent;

  font-size: 12px;

  line-height: 1.4;

  text-decoration: none !important;

  transition: all 0.15s ease;

}


.pub-btn:hover {

  background: #222;

  color: #ffffff !important;

  text-decoration: none;

}


/* Notes, e.g. Spotlight */
.pub-note {

  color: #e74d3c;

  font-size: 13px;

  font-style: italic;

  font-weight: 600;

  margin-left: 5px;

}


/* =========================================================
   Tablet
   ========================================================= */

@media (max-width: 1000px) {

  .pub-image-wrapper {

    flex: 0 0 280px;

    width: 280px;

    height: 180px;

  }


  .pub-row {

    gap: 22px;

  }


  .pub-title {

    font-size: 17px;

  }

}


/* =========================================================
   Mobile
   ========================================================= */

@media (max-width: 768px) {

  .pub-row {

    flex-direction: column;

    align-items: flex-start;

    gap: 14px;

  }


  .pub-image-wrapper {

    flex: none;

    width: 100%;

    height: auto;

  }


  .pub-teaser {

    width: 100%;

    height: auto;

    max-height: 260px;

    object-fit: contain;

  }


  .pub-info {

    width: 100%;

    padding-right: 0;

  }


  .pub-title {

    font-size: 17px;

  }


  .pub-authors,
  .pub-venue {

    font-size: 14px;

  }

}

</style>