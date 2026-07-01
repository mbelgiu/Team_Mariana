---
layout: page
permalink: /publications/
title: publications
description: selected papers, preprints, and group outputs.
nav: true
nav_order: 3
---

<!-- _pages/publications.md -->

<aside class="scholar-profile" aria-label="Google Scholar citation summary">
  <div class="scholar-profile__heading">
    <h2>Cited by</h2>
  </div>

  <button class="scholar-profile__view" type="button" data-scholar-modal-open>VIEW ALL</button>

  <div class="scholar-profile__main">
    <table class="scholar-citations" aria-label="Citation metrics">
      <thead>
        <tr>
          <th scope="col"></th>
          <th scope="col">All</th>
          <th scope="col">Since 2021</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">Citations</th>
          <td>12304</td>
          <td>9615</td>
        </tr>
        <tr>
          <th scope="row">h-index</th>
          <td>27</td>
          <td>23</td>
        </tr>
        <tr>
          <th scope="row">i10-index</th>
          <td>42</td>
          <td>35</td>
        </tr>
      </tbody>
    </table>

    <div class="scholar-chart scholar-chart--preview" aria-label="Citation history from 2019 to 2026">
      <div class="scholar-chart__plot" aria-hidden="true">
        <div class="scholar-chart__grid"></div>
        <div class="scholar-chart__bars">
          <div class="scholar-chart__bar" style="--height: 32%"><span class="scholar-chart__year">2019</span><span class="scholar-chart__value">704</span></div>
          <div class="scholar-chart__bar" style="--height: 47%"><span class="scholar-chart__year">2020</span><span class="scholar-chart__value">1030</span></div>
          <div class="scholar-chart__bar" style="--height: 58%"><span class="scholar-chart__year">2021</span><span class="scholar-chart__value">1270</span></div>
          <div class="scholar-chart__bar" style="--height: 66%"><span class="scholar-chart__year">2022</span><span class="scholar-chart__value">1450</span></div>
          <div class="scholar-chart__bar" style="--height: 74%"><span class="scholar-chart__year">2023</span><span class="scholar-chart__value">1620</span></div>
          <div class="scholar-chart__bar" style="--height: 86%"><span class="scholar-chart__year">2024</span><span class="scholar-chart__value">1892</span></div>
          <div class="scholar-chart__bar" style="--height: 99%"><span class="scholar-chart__year">2025</span><span class="scholar-chart__value">2188</span></div>
          <div class="scholar-chart__bar" style="--height: 56%"><span class="scholar-chart__year">2026</span><span class="scholar-chart__value">1230</span></div>
        </div>
        <div class="scholar-chart__axis">
          <span>2200</span>
          <span>1650</span>
          <span>1100</span>
          <span>550</span>
          <span>0</span>
        </div>
      </div>
    </div>
  </div>

  <div class="scholar-access" aria-label="Public access">
    <div class="scholar-access__title">Public access</div>
    <div class="scholar-access__content">
      <div class="scholar-access__counts">
        <span class="scholar-access__closed">2 articles not available</span>
        <span class="scholar-access__open">29 articles available</span>
      </div>
      <div class="scholar-access__bar" aria-hidden="true">
        <span class="scholar-access__bar-closed"></span>
        <span class="scholar-access__bar-open"></span>
      </div>
      <p>Based on funding mandates</p>
    </div>
  </div>
</aside>

<div class="scholar-modal" role="dialog" aria-modal="true" aria-labelledby="scholar-modal-title" hidden data-scholar-modal>
  <div class="scholar-modal__panel" role="document">
    <div class="scholar-modal__header">
      <button class="scholar-modal__close" type="button" aria-label="Close citation chart" data-scholar-modal-close></button>
      <h2 id="scholar-modal-title">Citations per year</h2>
    </div>
    <div class="scholar-modal__body">
      <div class="scholar-modal__chart-scroll">
        <div class="scholar-chart scholar-chart--modal" aria-label="Enlarged citation history from 2019 to 2026">
          <div class="scholar-chart__plot" aria-hidden="true">
            <div class="scholar-chart__grid"></div>
            <div class="scholar-chart__bars">
              <div class="scholar-chart__bar" style="--height: 32%"><span class="scholar-chart__year">2019</span><span class="scholar-chart__value">704</span></div>
              <div class="scholar-chart__bar" style="--height: 47%"><span class="scholar-chart__year">2020</span><span class="scholar-chart__value">1030</span></div>
              <div class="scholar-chart__bar" style="--height: 58%"><span class="scholar-chart__year">2021</span><span class="scholar-chart__value">1270</span></div>
              <div class="scholar-chart__bar" style="--height: 66%"><span class="scholar-chart__year">2022</span><span class="scholar-chart__value">1450</span></div>
              <div class="scholar-chart__bar" style="--height: 74%"><span class="scholar-chart__year">2023</span><span class="scholar-chart__value">1620</span></div>
              <div class="scholar-chart__bar" style="--height: 86%"><span class="scholar-chart__year">2024</span><span class="scholar-chart__value">1892</span></div>
              <div class="scholar-chart__bar" style="--height: 99%"><span class="scholar-chart__year">2025</span><span class="scholar-chart__value">2188</span></div>
              <div class="scholar-chart__bar" style="--height: 56%"><span class="scholar-chart__year">2026</span><span class="scholar-chart__value">1230</span></div>
            </div>
            <div class="scholar-chart__axis">
              <span>2200</span>
              <span>1650</span>
              <span>1100</span>
              <span>550</span>
              <span>0</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<script>
  (() => {
    const modal = document.querySelector("[data-scholar-modal]");
    const openButton = document.querySelector("[data-scholar-modal-open]");
    const closeButton = document.querySelector("[data-scholar-modal-close]");

    if (!modal || !openButton || !closeButton) return;

    const openModal = () => {
      modal.hidden = false;
      modal.classList.add("is-open");
      document.body.classList.add("scholar-modal-open");
      closeButton.focus();
    };

    const closeModal = () => {
      modal.classList.remove("is-open");
      modal.hidden = true;
      document.body.classList.remove("scholar-modal-open");
      openButton.focus();
    };

    openButton.addEventListener("click", openModal);
    closeButton.addEventListener("click", closeModal);

    modal.addEventListener("click", (event) => {
      if (event.target === modal) {
        closeModal();
      }
    });

    document.addEventListener("keydown", (event) => {
      if (event.key === "Escape" && modal.classList.contains("is-open")) {
        closeModal();
      }
    });
  })();
</script>

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>
