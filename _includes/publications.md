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
      <a href="{{ link.pdf }}"
         class="pub-btn"
         target="_blank">
        PDF
      </a>
      {% endif %}

      {% if link.doi %}
      <a href="{{ link.doi }}"
         class="pub-btn"
         target="_blank">
        DOI
      </a>
      {% endif %}

      {% if link.code %}
      <a href="{{ link.code }}"
         class="pub-btn"
         target="_blank">
        Code
      </a>
      {% endif %}

      {% if link.page %}
      <a href="{{ link.page }}"
         class="pub-btn"
         target="_blank">
        Project Page
      </a>
      {% endif %}

      {% if link.bibtex %}
      <a href="{{ link.bibtex }}"
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

/* ===========================
   Publication container
   =========================== */

.pub-list {
  padding-left: 0 !important;
  margin-left: 0 !important;
}

.pub-item {
  list-style: none !important;
  margin-bottom: 24px;
  padding: 0;
}


/* ===========================
   Row
   =========================== */

.pub-row {
  display: flex;
  align-items: center;
  width: 100%;
  gap: 18px;
}


/* ===========================
   Image
   =========================== */

.pub-image-wrapper {
  position: relative;

  /*
   * Reduce the proportion occupied
   * by the teaser image.
   */
  flex: 0 0 245px;
  width: 245px;
  height: 150px;

  display: flex;
  align-items: center;
  justify-content: center;
}


/*
 * Important:
 * contain = complete figure,
 * no cropping.
 */
.pub-teaser {
  display: block;

  width: 100%;
  height: 100%;

  object-fit: contain;
  object-position: center;

  background: #ffffff;

  border-radius: 5px;

  box-shadow:
    0 2px 6px rgba(0, 0, 0, 0.18);
}


/* ===========================
   Venue Badge
   =========================== */

.pub-badge {
  position: absolute;

  top: 6px;
  left: 6px;

  z-index: 10;

  display: inline-block;

  padding: 3px 8px;

  background: #268bd2;
  color: #ffffff !important;

  font-size: 11px;
  font-weight: 600;
  line-height: 1.35;

  border-radius: 4px;

  white-space: nowrap;

  box-shadow:
    0 1px 3px rgba(0, 0, 0, 0.18);
}


/* ===========================
   Paper information
   =========================== */

.pub-info {
  flex: 1;
  min-width: 0;
}


.pub-title {
  font-size: 17px;
  font-weight: 600;

  line-height: 1.4;

  margin-bottom: 5px;
}


.pub-title a {
  text-decoration: none;
}


.pub-authors {
  font-size: 14px;
  line-height: 1.5;

  margin-bottom: 3px;
}


.pub-venue {
  font-size: 14px;
  line-height: 1.5;

  margin-bottom: 8px;
}


/* ===========================
   Links
   =========================== */

.pub-links {
  display: flex;

  align-items: center;
  flex-wrap: wrap;

  gap: 6px;
}


/*
 * Important:
 * inherit current theme color.
 *
 * This works in both light
 * and dark themes.
 */
.pub-btn {
  display: inline-block;

  padding: 3px 10px;

  color: inherit !important;
  background: transparent !important;

  border: 1px solid currentColor;

  border-radius: 2px;

  font-size: 12px;
  line-height: 1.35;

  text-decoration: none !important;

  opacity: 0.9;

  transition:
    background-color 0.15s ease,
    opacity 0.15s ease;
}


.pub-btn:hover {
  /*
   * Do not switch to fixed black/white.
   * Therefore dark theme stays readable.
   */
  color: inherit !important;

  background-color:
    rgba(128, 128, 128, 0.15) !important;

  opacity: 1;

  text-decoration: none !important;
}


/* Spotlight / Oral / etc. */
.pub-note {
  color: #e74d3c;

  font-size: 13px;
  font-style: italic;
  font-weight: 600;

  margin-left: 3px;
}


/* ===========================
   Medium screen
   =========================== */

@media (max-width: 1000px) {

  .pub-image-wrapper {
    flex: 0 0 220px;

    width: 220px;
    height: 140px;
  }

  .pub-row {
    gap: 16px;
  }

  .pub-title {
    font-size: 16px;
  }

}


/* ===========================
   Mobile
   =========================== */

@media (max-width: 768px) {

  .pub-row {
    flex-direction: column;
    align-items: flex-start;

    gap: 12px;
  }


  .pub-image-wrapper {
    flex: none;

    width: 100%;
    height: auto;
  }


  .pub-teaser {
    width: 100%;
    height: auto;

    max-height: 230px;

    object-fit: contain;
  }


  .pub-info {
    width: 100%;
  }


  .pub-title {
    font-size: 16px;
  }


  .pub-authors,
  .pub-venue {
    font-size: 14px;
  }

}

</style>