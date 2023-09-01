---
layout: index
permalink: /mes-projets/
---

<section>
	<article>
		<h2>Mes projets autour de Gamebuino</h2>
        <div class="all-projects">
            {% for groupe in site.data.creations %}
            <div class="year" id="year-{{ groupe.annee }}" >
                <h3>Réalisé(s) en {{groupe.annee}}</h3>
                {% for creation in groupe.projets %}
                <div class="card-project" >
                    <img 
                    src="/assets/img/creations/{{ creation.src-img }}" 
                    class="card-img"
                    alt="{{ creation.alt-img }}" />
                    <div class="card-body" >
                        <h4 class="card-title">{{ creation.title }}</h4>
                        <h5 class="card-subtitle text-muted" >{{ creation.device }} / {{ creation.created-at }}</h5>
                        <p class="card-text">{{ creation.description }}</p>
                        {% if creation.type == 'Workshop' %}<a href="{{ creation.ws-link }}" class="card-link" >Workshop</a>{% elsif creation.type == 'Game' %}<a href="{{ creation.game-link }}" class="card-link" >Jeu</a> - <a href="{{ creation.repository }}" class="card-link" >Dépôt</a>{% elsif creation.type == 'Website' %}<a href="{{ creation.web-link }}" class="card-link" >Site Web</a>{% else %}<a href="{{ creation.repository }}" class="card-link" >Dépôt</a>{% endif %}
                    </div>
                </div>
                {% endfor %}
            </div>
            {% endfor %}
        </div>
	</article>
</section>