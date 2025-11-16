---
widget: blank
headless: true
active: true
weight: 30
title: "iNaturalist Observations"
---

These are some of my recent observations from iNaturalist, a platform near and dear to my heart.

<style>
/* Main container */
.inat-widget {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  padding: 1rem 0;
  max-width: 100%;
}

/* Header */
.inat-widget-header {
  margin-bottom: 1rem;
}

/* GRID LAYOUT for observation list */
.inat-widget table {
  width: 100%;
}

/* Replace table layout with CSS grid */
.inat-widget tr {
  display: block !important;
}

.inat-widget tbody {
  display: grid !important;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1.25rem;
  width: 100%;
}

/* Individual observation card */
.inat-observation {
  display: flex !important;
  flex-direction: column;
  background: #fafafa;
  padding: 0.75rem;
  border-radius: 10px;
  box-shadow: 0 1px 4px rgba(0,0,0,0.07);
  height: 100%;
}

/* Image */
.inat-observation-image img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 8px;
}

/* Text block */
.inat-observation-body {
  margin-top: 0.5rem;
  flex: 1;
}

.inat-label {
  color: #666;
  font-size: 0.9rem;
  font-weight: 600;
}

.inat-meta {
  margin-top: 0.35rem;
  color: #777;
  font-size: 0.85rem;
  line-height: 1.3;
}

/* Footer (user info) */
.inat-footer {
  margin-top: 1.5rem;
}

.inat-user {
  display: flex;
  align-items: center;
}

.inat-user-image img {
  width: 48px;
  height: 48px;
  border-radius: 50%;
}

.inat-user-body {
  margin-left: 0.75rem;
}
</style>

<div class="inat-widget">
  <div class="inat-widget-header">
    <a href="https://www.inaturalist.org">
      <img alt="iNaturalist" src="https://www.inaturalist.org/assets/logo-small.gif" />
    </a>
  </div>

  <!-- iNaturalist widget script -->
  <script
    type="text/javascript"
    src="https://www.inaturalist.org/observations/austinkoontz11.widget?layout=large&limit=9&order=desc&order_by=observed_on">
  </script>

  <!-- Footer -->
  <table class="inat-footer">
    <tr class="inat-user">
      <td class="inat-user-image">
        <a href="https://www.inaturalist.org/observations/austinkoontz11">
          <img src="https://static.inaturalist.org/attachments/users/icons/2369873/thumb.jpeg?1685304639" />
        </a>
      </td>
      <td class="inat-user-body">
        <strong>
          <a href="https://www.inaturalist.org/observations/austinkoontz11">
            View austinkoontz11's observations »
          </a>
        </strong>
      </td>
    </tr>
  </table>
</div>
