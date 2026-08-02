---
widget: blank
headless: true
active: true
weight: 20
title: "iNaturalist Observations"
---

These are some of my recent observations from iNaturalist. If you want to see more, follow me there! [austinkoontz11](https://www.inaturalist.org/people/austinkoontz11)

<div class="inat-widget">
  <div class="inat-widget-header">
    <a href="https://www.inaturalist.org/people/austinkoontz11" target="_blank" rel="noopener">
      <img alt="iNaturalist" src="/media/inaturalist-logo.png" />
    </a>
  </div>

  <div id="inat-grid" class="inat-grid">
    <p class="inat-loading">Loading recent observations…</p>
  </div>

  <div class="inat-footer">
    <a href="https://www.inaturalist.org/observations/austinkoontz11" target="_blank" rel="noopener">
      <strong>View austinkoontz11's observations »</strong>
    </a>
  </div>
</div>

<style>
.inat-widget {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  padding: 1rem 0;
  max-width: 100%;
}

.inat-widget-header {
  margin-bottom: 1rem;
}

.inat-widget-header img {
  height: 32px;
  width: auto;
}

.inat-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1.25rem;
  width: 100%;
}

.inat-loading {
  color: #777;
  font-size: 0.9rem;
  grid-column: 1 / -1;
}

.inat-card {
  display: flex;
  flex-direction: column;
  background: #fafafa;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 1px 4px rgba(0,0,0,0.07);
  text-decoration: none;
  color: inherit;
  transition: transform 0.15s ease, box-shadow 0.15s ease;
}

.inat-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.12);
}

.inat-card-image {
  width: 100%;
  aspect-ratio: 1 / 1;
  overflow: hidden;
  background: #eee;
}

.inat-card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.inat-card-body {
  padding: 0.6rem 0.75rem;
  flex: 1;
}

.inat-card-name {
  display: block;
  font-size: 0.9rem;
  font-weight: 600;
  line-height: 1.3;
  margin-bottom: 0.25rem;
}

.inat-card-date {
  color: #777;
  font-size: 0.8rem;
}

.inat-footer {
  margin-top: 1.5rem;
}
</style>

<script>
(function () {
  var grid = document.getElementById('inat-grid');
  if (!grid) return;

  fetch('https://api.inaturalist.org/v1/observations?user_id=austinkoontz11&order_by=observed_on&order=desc&per_page=9&photos=true')
    .then(function (r) { return r.json(); })
    .then(function (data) {
      grid.innerHTML = '';

      if (!data.results || data.results.length === 0) {
        grid.innerHTML = '<p class="inat-loading">No recent observations found.</p>';
        return;
      }

      data.results.forEach(function (obs) {
        var photoUrl = obs.photos && obs.photos[0] && obs.photos[0].url;
        if (!photoUrl) return;
        // Swap iNaturalist's small "square" thumbnail for a sharper "medium" version
        photoUrl = photoUrl.replace('square', 'medium');

        var name = (obs.taxon && (obs.taxon.preferred_common_name || obs.taxon.name)) || 'Unknown species';
        var date = obs.observed_on || '';

        var card = document.createElement('a');
        card.className = 'inat-card';
        card.href = 'https://www.inaturalist.org/observations/' + obs.id;
        card.target = '_blank';
        card.rel = 'noopener';
        card.innerHTML =
          '<div class="inat-card-image"><img src="' + photoUrl + '" alt="' + name + '" loading="lazy" /></div>' +
          '<div class="inat-card-body">' +
            '<span class="inat-card-name">' + name + '</span>' +
            '<span class="inat-card-date">' + date + '</span>' +
          '</div>';
        grid.appendChild(card);
      });
    })
    .catch(function () {
      grid.innerHTML = '<p class="inat-loading">Couldn\'t load observations right now.</p>';
    });
})();
</script>
