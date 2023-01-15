---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Analogue Pocket
---

The [Analogue Pocket](https://www.analogue.co/pocket) is a multi-video-game-system portable handheld designed and built by [Analogue](https://www.analogue.co).

## Test

<div class="row row-cols-1 row-cols-md-3 g-4">
  <div class="col">
    <div class="card bg-light h-100">
      <img src="{{ "/assets/images/platforms/a500.png" | relative_url }}" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Amiga 500 <span class="badge bg-secondary">Computer</span></h5>
        <h6 class="card-subtitle mb-2 text-muted">Mazamars312</h6>
        <p class="card-text">Amiga 500 Core</p>
      </div>
      <div class="card-footer text-muted">
        <div class="d-flex justify-content-between align-items-center">
          <div class="btn-toolbar" role="toolbar">
            <div class="btn-group me-2">
              <a href="#" class="btn btn-sm btn-dark"><i class="bi-github" role="img" aria-label="GitHub"></i></a>
            </div>
            <div class="btn-group">
              <div class="dropdown">
                <a class="btn btn-sm btn-danger dropdown-toggle" href="#" role="button" id="dropdownMenuLink" data-bs-toggle="dropdown" aria-expanded="false"><i class="bi-heart-fill" role="img" aria-label="Sponsor"></i>
                </a>
                <ul class="dropdown-menu" aria-labelledby="dropdownMenuLink">
                  <li><a class="dropdown-item" href="#">Action</a></li>
                  <li><a class="dropdown-item" href="#">Another action</a></li>
                  <li><a class="dropdown-item" href="#">Something else here</a></li>
                </ul>
              </div>
            </div>
          </div>
          <small class="text-muted">0.0.6 • Dec 10, 2022</small>
        </div>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card bg-light h-100">
      <img src="{{ "/assets/images/platforms/arduboy.png" | relative_url }}" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Arduboy <span class="badge bg-secondary">Handheld</span></h5>
        <h6 class="card-subtitle mb-2 text-muted">agg23</h6>
        <p class="card-text">A small, portable Arduino console.</p>
      </div>
      <div class="card-footer">
        <div class="d-flex justify-content-between align-items-center">
          <div class="btn-toolbar" role="toolbar">
            <div class="btn-group me-2">
              <a href="#" class="btn btn-sm btn-dark"><i class="bi-github" role="img" aria-label="GitHub"></i></a>
            </div>
            <div class="btn-group">
              <div class="dropdown">
                <a class="btn btn-sm btn-danger dropdown-toggle" href="#" role="button" id="dropdownMenuLink" data-bs-toggle="dropdown" aria-expanded="false"><i class="bi-heart-fill" role="img" aria-label="Sponsor"></i>
                </a>
                <ul class="dropdown-menu" aria-labelledby="dropdownMenuLink">
                  <li><a class="dropdown-item" href="#">Action</a></li>
                  <li><a class="dropdown-item" href="#">Another action</a></li>
                  <li><a class="dropdown-item" href="#">Something else here</a></li>
                </ul>
              </div>
            </div>
          </div>
          <small class="text-muted">0.9.0 • Sep 3, 2022</small>
        </div>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card bg-light h-100">
      <img src="{{ "/assets/images/platforms/asteroids.png" | relative_url }}" class="card-img-top" alt="...">
      <div class="card-body">
        <h5 class="card-title">Asteroids <span class="badge bg-secondary">Arcade</span></h5>
        <h6 class="card-subtitle mb-2 text-muted">ericlewis</h6>
        <p class="card-text">Atari's Asteroids released in 1979.</p>
      </div>
      <div class="card-footer text-muted">
        <div class="d-flex justify-content-between align-items-center">
          <div class="btn-toolbar" role="toolbar">
            <div class="btn-group me-2">
              <a href="#" class="btn btn-sm btn-dark"><i class="bi-github" role="img" aria-label="GitHub"></i></a>
            </div>
            <div class="btn-group">
              <div class="dropdown">
                <a class="btn btn-sm btn-danger dropdown-toggle" href="#" role="button" id="dropdownMenuLink" data-bs-toggle="dropdown" aria-expanded="false"><i class="bi-heart-fill" role="img" aria-label="Sponsor"></i>
                </a>
                <ul class="dropdown-menu" aria-labelledby="dropdownMenuLink">
                  <li><a class="dropdown-item" href="#">Action</a></li>
                  <li><a class="dropdown-item" href="#">Another action</a></li>
                  <li><a class="dropdown-item" href="#">Something else here</a></li>
                </ul>
              </div>
            </div>
          </div>
          <small class="text-muted">1.0.1 • Oct 11, 2022</small>
        </div>
      </div>
    </div>
  </div>
</div>

## Cores

<div class="mb-5">
  <table class="datatable table table-striped" style="width:100%">
    <thead>
      <tr>
        <th>Name</th>
        <th>Platform</th>
        <th>Category</th>
        <th>Author</th>
        <th>Version</th>
        <th>Date</th>
        <th>API</th>
      </tr>
    </thead>
    <tbody>
      {% for developer in site.data.cores -%}
        {% for core in developer.cores -%}
          {%- if core.prerelease %}
            {% assign metadata = core.prerelease %}
          {%- else %}
            {%- assign metadata = core.release %}
          {%- endif %}
          <tr>
            <td><a href="https://github.com/{{ developer.username }}/{{ core.repository }}">{{ core.display_name }}</a></td>
            <td>{{ metadata.platform.name }}</td>
            <td>{{ metadata.platform.category }}</td>
            <td><a href="https://github.com/{{ developer.username }}">{{ developer.username }}</a></td>
            <td data-order="{{ metadata.tag_name | remove_first: "v" }}">
              <a href="https://github.com/{{ developer.username }}/{{ core.repository }}/releases/latest">{{ metadata.tag_name }}</a>
            </td>
            <td data-order="{{ metadata.release_date | date: "%s" }}">
              {{ metadata.release_date | date: "%b %-d, %Y" }}
            </td>
            <td class="check" data-order="1">&#10003;</td>
          </tr>
        {% endfor -%}
      {% endfor -%}
      {% for developer in site.data.other -%}
        {% for core in developer.cores -%}
          <tr>
            <td><a href="{{ core.repository_url }}">{{ core.display_name }}</a></td>
            <td>{{ core.platform }}</td>
            <td>{{ core.category }}</td>
            <td><a href="https://github.com/{{ developer.username }}">{{ developer.username }}</a></td>
            <td data-order="{{ core.version }}">
              <a href="{{ core.release_url }}">{{ core.version }}</a>
            </td>
            <td data-order="{{ core.release_date | date: "%s" }}">
              {{ core.release_date | date: "%b %-d, %Y" }}
            </td>
            <td data-order="0"></td>
          </tr>
        {% endfor -%}
      {% endfor -%}
    </tbody>
  </table>
</div>

<script type="text/javascript" src="{{ "/assets/js/script.js" | relative_url }}"></script>
