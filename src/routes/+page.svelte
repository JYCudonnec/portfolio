<script>
	const profile = {
		nom: "Jean-Yves CUDONNEC",
		titre: "Développeur Full-Stack",
		email: "jycudonnec@gmail.com",
		telephone: "+33 6 03 96 82 05",
		localisation: "LANNION (22), France",
		photo: "/images/profile.jpg",
		presentation: "JavaScript • React • Vue.js • Node.js • WordPress",
		linkedin: "https://www.linkedin.com/in/jean-yves-cudonnec/"
	};

	let showHeader = false;
	let showSections = false;
	let currentPage = null;

	function expandCard() {
		showHeader = true;
		// Afficher les sections avec un délai après la header bar
		setTimeout(() => {
			showSections = true;
		}, 400);
	}

	function openSection(sectionName) {
		currentPage = sectionName;
		// Remettre le scroll en haut après l'animation d'ouverture
		setTimeout(() => {
			const fullPage = document.querySelector('.full-page.visible');
			if (fullPage) {
				fullPage.scrollTop = 0;
			}
		}, 100);
	}

	function closePage() {
		currentPage = null;
	}

	function goHome() {
		currentPage = null;
	}
</script>

<div class="container">
	<!-- Header bar -->
	<div class="header-bar" class:visible={showHeader}>
		<div class="header-photo" class:visible={showHeader} on:click={goHome}>
			<img src={profile.photo} alt={profile.nom} />
		</div>
		<div class="header-name">
			<h1>{profile.nom}</h1>
			<p class="header-title">{profile.titre}</p>
		</div>
	</div>

	<!-- Sections principales -->
	<div class="main-sections">
		<section class="section apropos" class:visible={showSections} on:click={() => openSection('apropos')}>
			<div class="section-content">
				<h2>A propos de moi</h2>
				<div class="section-body">
					<p>Présentation • Expériences • Formations • Centres d'intérêt</p>
				</div>
			</div>
		</section>
		
		<section class="section competences" class:visible={showSections} on:click={() => openSection('competences')}>
			<div class="section-content">
				<h2>Mes Compétences</h2>
				<div class="section-body">
					<p>Expertises • Technologies • Soft Skills</p>
				</div>
			</div>
		</section>
		
		<section class="section realisations" class:visible={showSections} on:click={() => openSection('realisations')}>
			<div class="section-content">
				<h2>Quelques Réalisations</h2>
				<div class="section-body">
					<p>Sélection de sites sur lesquels j'ai travaillé</p>
				</div>
			</div>
		</section>
		
		<section class="section autres" class:visible={showSections} on:click={() => openSection('autres')}>
			<div class="section-content">
				<h2>CV & Contact</h2>
				<div class="section-body">
					<p>Télécharger mon CV • Me contacter • Réseaux sociaux</p>
				</div>
			</div>
		</section>
	</div>

	<!-- Pages détaillées -->
	<div class="full-page apropos-page" class:visible={currentPage === 'apropos'}>
		<div class="page-header">
			<h1>A propos de moi</h1>
		</div>
		<div class="page-body">
			<div class="content-section intro-section">
				<p class="presentation-text">J'ai <strong>39 ans</strong> et suis <strong>Développeur Web</strong> depuis près de <strong>5 ans</strong>. J'ai une expertise solide en <strong>WordPress</strong>, mais pas seulement. Mon expérience inclut la création de <strong>sites sécurisés et performants</strong>, ainsi que la mise en place de <strong>boutiques en ligne</strong>, le développement de <strong>plugins personnalisés</strong> et d'<strong>applications web sur-mesure</strong>.</p>
			</div>
			
			<div class="content-section experience-section">
				<h2>Expériences Professionnelles</h2>
				<div class="experience-grid">
					<div class="experience-item">
						<h3>Développeur Web Full-Stack</h3>
						<p class="location">Full-Remote (2020 - 2025)</p>
						<p>Développement d'applications web modernes avec <strong>WordPress</strong>, <strong>React</strong>, <strong>Vue.js</strong> et <strong>Node.js</strong>. Conception et débeloppement de sites, création de thèmes et plugins personnalisés, intégration de maquettes complexes, optimisation SEO et performance.</p>
					</div>
					<div class="experience-item">
						<h3>Assistant d'éducation</h3>
						<p class="location">Lycée Auguste Pavie - Guingamp (2012 - 2018)</p>
						<p>Encadrement des élèves (assiduité, résultats scolaires, discipline, aide aux devoirs), liaison équipe pédagogique/parents, secrétaire jurys de bac. <br><strong>Compétences transversales:</strong> pédagogie, écoute, responsabilités</p>
					</div>
					<div class="experience-item">
						<h3>Chargé de recherche / Technicien de laboratoire</h3>
						<p class="location">UCO-BN - Guingamp (2008 - 2009)</p>
						<p>Génie génétique et analyse biomédicale, connaissance et pratique des techniques de laboratoires<br><strong>Compétences transversales: </strong>recherche bibiographique, rigueur et minutie, rédaction de rapport</p>
					</div>
				</div>
			</div>
			
			<div class="content-section experience-section">
				<h2>Formation</h2>
				<div class="experience-grid">
					<div class="experience-item">
						<h3>DU Développeur d'Applications Web</h3>
						<p class="location">IUT Lannion (2020)</p>
					</div>
					<div class="experience-item">
						<h3>Ingénieur en Biologie</h3>
						<p class="location">CNAM en distanciel (2012 - 2016)</p>
					</div>
					<div class="experience-item">
						<h3>Licence en Biologie</h3>
						<p class="location">UCO Guingamp (2006 - 2009)</p>
					</div>
					<div class="experience-item">
						<h3>PCEM1</h3>
						<p class="location">UBO Brest (2004 - 2006)</p>
					</div>
					<div class="experience-item">
						<h3>Bac S option Maths</h3>
						<p class="location">Lycée Félix Le Dantec, Lannion (2004)</p>
					</div>
				</div>
			</div>

			<div class="content-section interests-section">
				<h2>Centres d'intérêt</h2>
				<div class="interests-grid">
					<div class="interest-item">
						<div class="interest-header">
							<div class="interest-icon">
								<img src="/images/guitar-icon.png" alt="Guitar icon" />
							</div>
							<h3>Musique & Concerts</h3>
						</div>
						<p>Collectionneur de décibels et adepte de gros sons</p>
					</div>
					<div class="interest-item">
						<div class="interest-header">
							<div class="interest-icon">
								<img src="/images/canivtt-icon.png" alt="Cani-VTT" />
							</div>
							<h3>Rando & Cani-cross</h3>
						</div>
						<p>Aventures en nature avec mon compagnon à quatre pattes</p>
					</div>
					<div class="interest-item">
						<div class="interest-header">
							<div class="interest-icon">
								<img src="/images/gaming-icon.png" alt="Gaming" />
							</div>
							<h3>Gaming</h3>
						</div>
						<p>Explorateur de mondes virtuels et pourfendeur de boss depuis 1995</p>
					</div>
				</div>
			</div>
			
			<!-- <div class="content-section timeline-section">
				<h2>Mon parcours</h2>
				<div class="timeline">
					<div class="timeline-item">
						<div class="timeline-marker"></div>
						<div class="timeline-content">
							<div class="timeline-date">2024</div>
							<h3>Développeur Full-Stack</h3>
							<p>Développement d'applications web modernes avec React, Node.js et bases de données</p>
						</div>
					</div>
					
					<div class="timeline-item">
						<div class="timeline-marker"></div>
						<div class="timeline-content">
							<div class="timeline-date">2022</div>
							<h3>Spécialisation E-commerce</h3>
							<p>Création de boutiques en ligne performantes et sécurisées avec WooCommerce et solutions custom</p>
						</div>
					</div>
					
					<div class="timeline-item">
						<div class="timeline-marker"></div>
						<div class="timeline-content">
							<div class="timeline-date">2020</div>
							<h3>Expert WordPress</h3>
							<p>Développement de plugins personnalisés et thèmes sur-mesure pour clients professionnels</p>
						</div>
					</div>
					
					<div class="timeline-item">
						<div class="timeline-marker"></div>
						<div class="timeline-content">
							<div class="timeline-date">2019</div>
							<h3>Début en Développement Web</h3>
							<p>Formation intensive et premiers projets en HTML, CSS, JavaScript et PHP</p>
						</div>
					</div>
					
					<div class="timeline-item">
						<div class="timeline-marker"></div>
						<div class="timeline-content">
							<div class="timeline-date">Avant 2019</div>
							<h3>Reconversion Professionnelle</h3>
							<p>Décision de me reconvertir dans le développement web après une carrière dans un autre domaine</p>
						</div>
					</div>
				</div>
			</div> -->
		</div>
	</div>

	<div class="full-page competences-page" class:visible={currentPage === 'competences'}>
		<div class="page-header">
			<h1>Mes Compétences</h1>
		</div>
		<div class="page-body">
			
			<div class="content-section experience-section">
				<h2>Expertise & Missions</h2>
				<div class="experience-grid">
					<div class="experience-item">
						<h3>Développement WordPress</h3>
						<p><strong>Expertise</strong> en développement de thèmes custom, création de plugins sur-mesure et optimisation SEO, pour des solutions robustes et évolutives.</p>
					</div>
					<div class="experience-item">
						<h3>Missions Freelance</h3>
						<p>Accompagnement de <strong>PME et startups</strong> dans leur transformation digitale : refonte de sites, développement d'applications métier et conseil en architecture technique.</p>
					</div>
					<div class="experience-item">
						<h3>TMA & Maintenance</h3>
						<p><strong>Tierce Maintenance Applicative</strong> : maintenance corrective et évolutive, développement de fonctionnalités métier et migration d'outils analytics.</p>
					</div>
					<div class="experience-item">
						<h3>Intégration Maquettes</h3>
						<p>Transformation de <strong>mockups Figma/Adobe XD</strong> en interfaces responsive. Respect pixel-perfect, optimisation cross-browser et analyse technique des cahiers des charges.</p>
					</div>
					<div class="experience-item">
						<h3>Applications Web Modernes</h3>
						<p>Développement d'<strong>applications SPA</strong> avec React et Vue.js, intégration d'APIs REST, gestion d'état avancée et déploiement sur infrastructures cloud modernes.</p>
					</div>
					<div class="experience-item">
						<h3>Optimisation & Performance</h3>
						<p><strong>Audit et optimisation</strong> de sites existants : amélioration des performances, migration vers technologies modernes, mise en conformité RGPD et accessibilité web.</p>
					</div>
				</div>
			</div>

			<div class="content-section">
				<h2>Technologies & Outils</h2>
				<div class="skills-grid">
					<!-- Langages -->
					<span class="skill-badge language">JavaScript</span>
					<span class="skill-badge language">TypeScript</span>
					<span class="skill-badge language">PHP</span>
					<span class="skill-badge language">Python</span>
					<span class="skill-badge language">HTML</span>
					<span class="skill-badge language">CSS</span>
					<span class="skill-badge language">SQL</span>
					<div class="skills-break"></div>
					
					<!-- Frameworks -->
					<span class="skill-badge framework">React</span>
					<span class="skill-badge framework">React Native</span>
					<span class="skill-badge framework">Vue.js</span>
					<span class="skill-badge framework">Laravel</span>
					<span class="skill-badge framework">PhpSlim</span>
					<div class="skills-break"></div>
					
					<!-- CMS -->
					<span class="skill-badge cms">WordPress</span>
					<span class="skill-badge cms">Sanity</span>
					<div class="skills-break"></div>
					
					<!-- Outils -->
					<span class="skill-badge tool">Git</span>
					<span class="skill-badge tool">Docker</span>
					<span class="skill-badge tool">VS Code</span>
					<span class="skill-badge tool">Postman</span>
					<span class="skill-badge tool">MAMP</span>
					<span class="skill-badge tool">Filezilla</span>
					<span class="skill-badge tool">Procreate</span>
					<div class="skills-break"></div>
					
					<!-- IA & Machine Learning -->
					<span class="skill-badge ai">GitHub Copilot</span>
					<span class="skill-badge ai">Prompt Engineering</span>
					<span class="skill-badge ai">IA Générative</span>
					<span class="skill-badge ai">ChatGPT</span>
					<span class="skill-badge ai">Claude AI</span>
					<span class="skill-badge ai">Gemini</span>
				</div>
			</div>
			
			<div class="content-section">
				<h2>Soft Skills</h2>
				<div class="skills-grid">
					<span class="skill-badge soft">Capacité d'analyse</span>
					<span class="skill-badge soft">Autonomie</span>
					<span class="skill-badge soft">Formation continue</span>
					<span class="skill-badge soft">Créativité</span>
					<span class="skill-badge soft">Travail en équipe</span>
					<span class="skill-badge soft">Adaptabilité</span>
					<span class="skill-badge soft">Réactivité</span>
					<span class="skill-badge soft">Curiosité technique</span>
				</div>
			</div>
		</div>
	</div>

	<div class="full-page realisations-page" class:visible={currentPage === 'realisations'}>
		<div class="page-header">
			<h1>Quelques Réalisations</h1>
		</div>
		<div class="page-body">
			<div class="projects-grid">
				<div class="project-item">
					<div class="project-visual">
						<div class="project-logo">
							<img src="/images/breizhmetal.svg" alt="Breizh Metal Logo" />
						</div>
						<div class="project-screenshot">
							<img src="/images/breizhmetal_screen.png" alt="Breizh Metal Screenshot" />
						</div>
					</div>
					<div class="project-content">
						<h3>Breizh Metal</h3>
						<p class="project-subtitle">Portail de la scène metal bretonne</p>
						<div class="project-tech">
							<span class="tech-tag">CMS Headless Sanity</span>
							<span class="tech-tag">Vue.js</span>
							<span class="tech-tag">Conception & Design</span>
							<span class="tech-tag">Optimisation SEO</span>
						</div>
						<a href="https://breizhmetal.bzh" target="_blank" rel="noopener noreferrer" class="project-link">Visiter le site →</a>
					</div>
				</div>

				<div class="project-item">
					<div class="project-visual">
						<div class="project-logo">
							<img src="/images/hikamp_logo.png" alt="Hikamp Logo" />
						</div>
						<div class="project-screenshot">
							<img src="/images/hikamp_screen.png" alt="Hikamp Screenshot" />
						</div>
					</div>
					<div class="project-content">
						<h3>Hikamp</h3>
						<p class="project-subtitle">Site web spécialisé dans les randonnées</p>
						<div class="project-tech">
							<span class="tech-tag">WordPress</span>
							<span class="tech-tag">Plugin custom d'analyse GPX</span>
							<span class="tech-tag">Boutique WooCommerce</span>
						</div>
						<a href="https://www.hikamp.com" target="_blank" rel="noopener noreferrer" class="project-link">Visiter le site →</a>
					</div>
				</div>

				<div class="project-item">
					<div class="project-visual">
						<div class="project-logo">
							<img src="/images/parcoursmetiers_logo.png" alt="ParcoursMetiers Logo" />
						</div>
						<div class="project-screenshot">
							<img src="/images/parcoursmetiers_screen.png" alt="ParcoursMetiers Screenshot" />
						</div>
					</div>
					<div class="project-content">
						<h3>ParcoursMetiers</h3>
						<p class="project-subtitle">Trouve le métier ou la formation qui te plaît</p>
						<div class="project-tech">
							<span class="tech-tag">Laravel</span>
							<span class="tech-tag">TMA</span>
							<span class="tech-tag">Maintenance évolutive</span>
						</div>
						<a href="https://www.parcoursmetiers.tv" target="_blank" rel="noopener noreferrer" class="project-link">Visiter le site →</a>
					</div>
				</div>

				<div class="project-item">
					<div class="project-visual">
						<div class="project-logo">
							<img src="/images/neuroprofiler_logo.png" alt="Neuroprofiler Logo" />
						</div>
						<div class="project-screenshot">
							<img src="/images/neuroprofiler_screen.png" alt="Neuroprofiler Screenshot" />
						</div>
					</div>
					<div class="project-content">
						<h3>Neuroprofiler</h3>
						<p class="project-subtitle">Site de conseils en investissement</p>
						<div class="project-tech">
							<span class="tech-tag">WordPress</span>
							<span class="tech-tag">Thème personnalisé</span>
							<span class="tech-tag">Gestion multilangues</span>
						</div>
						<a href="https://neuroprofiler.com" target="_blank" rel="noopener noreferrer" class="project-link">Visiter le site →</a>
					</div>
				</div>

				<div class="project-item">
					<div class="project-visual">
						<div class="project-logo">
							<img src="/images/hellfest_logo.png" alt="Hellfest RO Logo" />
						</div>
						<div class="project-screenshot">
							<img src="/images/HellfestRO_screen.png" alt="Hellfest RO Screenshot" />
						</div>
					</div>
					<div class="project-content">
						<h3>Hellfest RO</h3>
						<p class="project-subtitle">Assistant de préparation de Running-Order</p>
						<div class="project-tech">
							<span class="tech-tag">React</span>
							<span class="tech-tag">Système de favoris</span>
							<span class="tech-tag">Authentification Discourse</span>
						</div>
						<a href="https://devinfafara.github.io/running-order/#/" target="_blank" rel="noopener noreferrer" class="project-link">Visiter le site →</a>
					</div>
				</div>

				<div class="project-item">
					<div class="project-visual">
						<div class="project-logo">
							<img src="/images/b2ai_logo.png" alt="B2ai Logo" />
						</div>
						<div class="project-screenshot">
							<img src="/images/b2ai_screen.png" alt="B2ai Screenshot" />
						</div>
					</div>
					<div class="project-content">
						<h3>B2ai</h3>
						<p class="project-subtitle">Systèmes connectés pour bâtiments intelligents</p>
						<div class="project-tech">
							<span class="tech-tag">WordPress</span>
							<span class="tech-tag">Intégration de maquettes</span>
							<span class="tech-tag">Thème personnalisé</span>
						</div>
						<a href="https://b2ai.fr" target="_blank" rel="noopener noreferrer" class="project-link">Visiter le site →</a>
					</div>
				</div>
			</div>
		</div>
	</div>

	<div class="full-page autres-page" class:visible={currentPage === 'autres'}>
		<div class="page-header">
			<h1>CV & Contact</h1>
		</div>
		<div class="page-body">
			<div class="content-section availability-section">
				<h2>Disponibilité</h2>
				<div class="availability-status">
					<div class="status-indicator available"></div>
					<div class="status-text">
						<h3>Actuellement disponible</h3>
						<p>Je suis <strong>ouvert aux nouvelles opportunités</strong>. N'hésitez pas à me contacter pour discuter de vos projets !</p>
					</div>
				</div>
			</div>
			
			<div class="content-section contact-section">
				<h2>Me contacter</h2>
				<div class="contact-grid">
					<div class="contact-item">
						<div class="contact-icon">✉️</div>
						<div class="contact-info">
							<a href="mailto:jycudonnec@gmail.com">jycudonnec@gmail.com</a>
						</div>
					</div>
					<div class="contact-item">
						<div class="contact-icon">📞</div>
						<div class="contact-info">
							<a href="tel:+33603968205">+33 6 03 96 82 05</a>
						</div>
					</div>
					<div class="contact-item">
						<div class="contact-icon linkedin-icon">
							<svg viewBox="0 0 24 24" fill="currentColor">
								<path d="M20.5 2h-17A1.5 1.5 0 002 3.5v17A1.5 1.5 0 003.5 22h17a1.5 1.5 0 001.5-1.5v-17A1.5 1.5 0 0020.5 2zM8 19H5v-9h3zM6.5 8.25A1.75 1.75 0 118.3 6.5a1.78 1.78 0 01-1.8 1.75zM19 19h-3v-4.74c0-1.42-.6-1.93-1.38-1.93A1.74 1.74 0 0013 14.19a.66.66 0 000 .14V19h-3v-9h2.9v1.3a3.11 3.11 0 012.7-1.4c1.55 0 3.36.86 3.36 3.66z"></path>
							</svg>
						</div>
						<div class="contact-info">
							<a href="https://www.linkedin.com/in/jean-yves-cudonnec/" target="_blank" rel="noopener noreferrer">Voir mon profil</a>
						</div>
					</div>
				</div>
			</div>
			
			<div class="content-section cv-section">
				<h2>Mon CV</h2>
				<div class="cv-container">
					<div class="cv-preview">
						<div class="cv-thumbnail">
							<img src="/images/CV_JYC_dw.pdf" alt="Aperçu CV" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex'">
							<div class="cv-placeholder">
								<div class="cv-icon">📄</div>
								<p>CV - Jean-Yves CUDONNEC</p>
							</div>
						</div>
						<div class="cv-actions">
							<a href="/images/CV_JYC_dw.pdf" target="_blank" class="cv-button view-cv">
								👁️ Visualiser
							</a>
							<a href="/images/CV_JYC_dw.pdf" download="CV_Jean-Yves_CUDONNEC.pdf" class="cv-button download-cv">
								⬇️ Télécharger
							</a>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>

	<div class="carte-visite" class:hidden={showSections}>
		<div class="profile-image">
			<img src={profile.photo} alt={profile.nom} />
		</div>
		
		<div class="profile-info">
			<h1 class="profile-name">{profile.nom}</h1>
			<h2 class="profile-title">{profile.titre}</h2>
			<p class="profile-description">{profile.presentation}</p>
			<span class="profile-info-item">📍 {profile.localisation}</span>
			<a href="mailto:{profile.email}" class="profile-info-item">
				✉️ {profile.email}
			</a>
			<a href="tel:{profile.telephone}" class="profile-info-item">
				📞 {profile.telephone}
			</a>

			<button class="expand-btn" on:click={expandCard}>
				En savoir plus
			</button>
		</div>
	</div>

	<!-- Bouton retour fixe -->
	{#if currentPage}
		<button class="back-button" on:click={closePage}>
			←
		</button>
	{/if}
</div>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
		min-height: 100vh;
		overflow-x: hidden;
	}

	/* Masquer le contenu en mode paysage et afficher un message */
	@media screen and (max-width: 768px) and (orientation: landscape) {
		.container {
			display: none;
		}
		
		:global(body)::after {
			content: "Veuillez tourner votre appareil en mode portrait pour une meilleure expérience";
			display: flex;
			align-items: center;
			justify-content: center;
			position: fixed;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
			color: white;
			font-size: 1.2rem;
			text-align: center;
			padding: 2rem;
			box-sizing: border-box;
			z-index: 9999;
		}
	}

	.container {
		min-height: 100vh;
		height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 1rem;
		overflow: hidden;
		box-sizing: border-box;
	}

	.carte-visite {
		max-width: 420px;
		width: 100%;
		background: rgba(255, 255, 255, 0.95);
		backdrop-filter: blur(20px);
		border-radius: 24px;
		padding: 2rem 2rem;
		text-align: center;
		box-shadow: 
			0 32px 64px rgba(0, 0, 0, 0.2),
			0 16px 32px rgba(0, 0, 0, 0.1);
		border: 1px solid rgba(255, 255, 255, 0.3);
		transition: transform 0.3s ease;
	}

	.carte-visite:hover {
		transform: translateY(-8px);
	}

	.carte-visite.hidden {
		opacity: 0;
		pointer-events: none;
		transition: opacity 0.3s ease;
	}

	.profile-image {
		margin-bottom: 1.5rem;
	}

	.profile-image img {
		width: 100px;
		height: 100px;
		border-radius: 50%;
		object-fit: cover;
		border: 4px solid #667eea;
		box-shadow: 0 8px 32px rgba(102, 126, 234, 0.3);
		transition: transform 0.3s ease;
	}

	.profile-image img:hover {
		transform: scale(1.05);
	}

	.profile-name {
		font-size: 1.75rem;
		font-weight: 700;
		margin: 0 0 0.25rem;
		color: #2d3748;
		letter-spacing: -0.025em;
	}

	.profile-title {
		font-size: 1.1rem;
		font-weight: 500;
		margin: 0 0 1rem;
		color: #667eea;
	}

	.profile-description {
		font-size: 0.95rem;
		line-height: 1.5;
		margin: 0 0 0.75rem;
		color: #4a5568;
	}

	.profile-info-item {
		display: block;
		color: #4a5568;
		text-decoration: none;
		font-size: 0.9rem;
		font-weight: 500;
		transition: all 0.2s ease;
		padding: 0rem;
		border-radius: 8px;
	}

	.profile-info-item:hover {
		background: rgba(102, 126, 234, 0.1);
		color: #667eea;
		transform: translateX(4px);
	}

	.social-links {
		display: flex;
		gap: 1rem;
		justify-content: center;
	}

	.social-link {
		background: #667eea;
		color: white;
		text-decoration: none;
		padding: 0.75rem 1.5rem;
		border-radius: 50px;
		font-size: 0.9rem;
		font-weight: 600;
		transition: all 0.2s ease;
		box-shadow: 0 4px 16px rgba(102, 126, 234, 0.3);
	}

	.social-link:hover {
		background: #5a67d8;
		transform: translateY(-2px);
		box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);
	}

	/* Bouton En savoir plus */
	.expand-btn {
		background: linear-gradient(135deg, #667eea, #764ba2);
		color: white;
		border: none;
		padding: 1rem 2rem;
		border-radius: 50px;
		font-size: 1rem;
		font-weight: 600;
		cursor: pointer;
		transition: all 0.3s ease;
		margin-top: 1rem;
		width: 100%;
	}

	.expand-btn:hover {
		transform: translateY(-2px);
		box-shadow: 0 12px 35px rgba(102, 126, 234, 0.4);
	}

	/* Header bar */
	.header-bar {
		position: fixed;
		top: -80px;
		left: 0;
		right: 0;
		height: 60px;
		background: rgba(255, 255, 255, 0.95);
		backdrop-filter: blur(10px);
		border-bottom: 1px solid rgba(0, 0, 0, 0.1);
		display: flex;
		align-items: center;
		padding: 0 20px;
		z-index: 5000;
		box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
		transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
		opacity: 0;
	}

	.header-bar.visible {
		top: 0;
		opacity: 1;
	}

	.header-photo {
		width: 70px;
		height: 70px;
		border-radius: 50%;
		overflow: hidden;
		position: absolute;
		top: -100px;
		left: 0;
		border: 4px solid rgba(255, 255, 255, 0.95);
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
		transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
		opacity: 0;
	}

	.header-photo.visible {
		top: 0;
		opacity: 1;
	}

	.header-photo {
		cursor: pointer;
		transition: transform 0.2s ease;
	}

	.header-photo:hover {
		transform: scale(1.05);
	}

	.header-photo img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.header-name {
		flex: 1;
		text-align: center;
		margin-left: 70px;
		padding-right: 70px;
	}

	.header-name h1 {
		margin: 0 0 2px 0;
		font-size: 1.1rem;
		color: #2d3748;
		font-weight: 600;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
		line-height: 1.2;
	}

	.header-name .header-title {
		margin: 0;
		font-size: 0.85rem;
		color: #666;
		font-weight: 400;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
		line-height: 1.1;
	}

	/* Sections principales */
	.main-sections {
		position: fixed;
		top: 60px;
		left: 0;
		right: 0;
		bottom: 0;
		z-index: 999;
		display: flex;
		flex-direction: column;
		pointer-events: none;
		overflow: hidden;
	}

	.section {
		flex: 1;
		width: 100%;
		background: rgba(255, 255, 255, 0.98);
		border-bottom: 1px solid rgba(0, 0, 0, 0.1);
		padding: 2rem;
		transform: translateX(-100%);
		visibility: hidden;
		transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1), visibility 0s 0.8s;
		overflow: hidden;
		display: flex;
		align-items: center;
		justify-content: flex-start;
		pointer-events: auto;
		cursor: pointer;
		position: relative;
	}

	.section:hover {
		background: rgba(255, 255, 255, 0.98);
		transform: translateX(10px);
		box-shadow: -5px 0 20px rgba(102, 126, 234, 0.3);
	}

	.section:hover .section-content h2 {
		color: #667eea;
		transform: translateX(10px);
	}

	.section:hover::before {
		content: '';
		position: absolute;
		left: 0;
		top: 0;
		bottom: 0;
		width: 4px;
		background: linear-gradient(135deg, #667eea, #764ba2);
		opacity: 1;
	}

	.section::before {
		content: '';
		position: absolute;
		left: 0;
		top: 0;
		bottom: 0;
		width: 4px;
		background: linear-gradient(135deg, #667eea, #764ba2);
		opacity: 0;
		transition: opacity 0.3s ease;
	}

	.section.visible {
		transform: translateX(0);
		visibility: visible;
		transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1), visibility 0s;
	}

	.section.apropos.visible {
		transition-delay: 0.1s;
	}

	.section.competences.visible {
		transition-delay: 0.2s;
	}

	.section.realisations.visible {
		transition-delay: 0.3s;
	}

	.section.autres.visible {
		transition-delay: 0.4s;
	}

	.section-content {
		width: 100%;
	}

	.section-content h2 {
		margin: 0 0 1rem 0;
		color: #2d3748;
		font-size: 1.5rem;
		font-weight: 600;
		border-bottom: 2px solid #667eea;
		padding-bottom: 0.5rem;
		transition: all 0.3s ease;
	}

	.section-body {
		color: #4a5568;
		line-height: 1.6;
		font-size: 1rem;
	}

	/* Pages détaillées plein écran */
	.full-page {
		position: fixed;
		top: 60px;
		left: 0;
		right: 0;
		bottom: 0;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		z-index: 1500;
		transform: translateX(100%);
		visibility: hidden;
		transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1), visibility 0s 0.8s;
		overflow-y: auto;
		pointer-events: none;
	}

	.full-page.visible {
		transform: translateX(0);
		visibility: visible;
		transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
		pointer-events: auto;
	}

	.page-header {
		background: rgba(255, 255, 255, 0.95);
		backdrop-filter: blur(10px);
		border-bottom: 1px solid rgba(0, 0, 0, 0.1);
		padding: 1rem 2rem;
		display: flex;
		align-items: center;
		justify-content: center;
		position: sticky;
		top: -60px;
		z-index: 100;
		margin-bottom: 20px;
	}



	.page-header h1 {
		color: #2d3748;
		margin: 0;
		font-size: 1.5rem;
		font-weight: 600;
		flex: 1;
		text-align: center;
	}

	.page-body {
		padding: 0 0 5rem 0;
		max-width: 1200px;
		margin: 0 auto;
	}

	.content-section {
		background: rgba(255, 255, 255, 0.95);
		backdrop-filter: blur(20px);
		border-radius: 0.5rem;
		padding: 1rem;
		margin-bottom: 1.5rem;
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
		border: 0px solid rgba(255, 255, 255, 0.3);
	}

	.content-section h2 {
		color: #2d3748;
		margin: 0 0 1rem 0;
		font-size: 1.5rem;
		font-weight: 600;
		border-bottom: 2px solid #667eea;
		padding-bottom: 0.5rem;
	}

	.content-section p {
		color: #4a5568;
		line-height: 1.6;
		margin: 0;
	}

	.content-section ul {
		color: #4a5568;
		line-height: 1.8;
		margin: 0;
		padding-left: 1.5rem;
	}

	.content-section li {
		margin-bottom: 0.5rem;
	}

	/* Styles spécifiques pour la page A propos */
	.intro-section {
		margin-bottom: 2rem;
	}

	.presentation-text {
		font-size: 0.95rem;
		color: #4a5568;
		line-height: 1.6;
		margin: 0;
	}

	.presentation-text strong {
		color: #667eea;
		font-weight: 600;
	}

	/* Centres d'intérêt */
	.interests-section h2 {
		text-align: center;
		margin-bottom: 2rem;
	}

	.interests-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 1.5rem;
		max-width: 900px;
		margin: 0 auto;
	}

	.interest-item {
		text-align: center;
		padding: 0.5rem;
		background: rgba(255, 255, 255, 0.6);
		border-radius: 12px;
		transition: transform 0.2s ease, box-shadow 0.2s ease;
		border: 1px solid rgba(102, 126, 234, 0.1);
	}

	.interest-item:hover {
		transform: translateY(-5px);
		box-shadow: 0 8px 25px rgba(102, 126, 234, 0.15);
	}

	.interest-icon {
		margin-bottom: 0.2rem;
		display: flex;
		justify-content: center;
		align-items: center;
		height: 120px;
	}

	.interest-icon img {
		width: 96px;
		height: 96px;
		object-fit: contain;
	}

	.interest-item h3 {
		color: #2d3748;
		font-size: 1.2rem;
		font-weight: 600;
		margin: 0 0 0.5rem 0;
	}

	.interest-item p {
		color: #4a5568;
		line-height: 1.5;
		margin: 0;
		font-size: 0.95rem;
	}

	/* Sur desktop, garder l'affichage vertical */
	.interest-header {
		display: contents;
	}

	/* Section Expérience */
	.experience-section h2 {
		text-align: center;
		margin-bottom: 2rem;
	}

	.experience-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		gap: 1.5rem;
		max-width: 1000px;
		margin: 0 auto;
	}

	.experience-item {
		text-align: left;
		padding: 1.8rem;
		background: rgba(255, 255, 255, 0.7);
		border-radius: 12px;
		transition: transform 0.2s ease, box-shadow 0.2s ease;
		border: 1px solid rgba(102, 126, 234, 0.15);
		border-left: 4px solid #667eea;
	}

	.experience-item:hover {
		transform: translateY(-5px);
		box-shadow: 0 8px 25px rgba(102, 126, 234, 0.2);
		border-left-color: #764ba2;
	}



	.experience-item h3 {
		color: #2d3748;
		font-size: 1.3rem;
		font-weight: 600;
		margin: 0 0 1rem 0;
		border-bottom: 2px solid rgba(102, 126, 234, 0.2);
		padding-bottom: 0.5rem;
		margin-top: 0;
	}

	.experience-item p {
		color: #4a5568;
		line-height: 1.6;
		margin: 0;
		font-size: 0.95rem;
	}

	.experience-item p strong {
		color: #667eea;
		font-weight: 600;
	}

	/* Grille des projets */
	.projects-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 1.5rem;
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem 0.5rem 5rem 0.5rem;
	}

	.project-item {
		background: rgba(255, 255, 255, 0.95);
		border-radius: 16px;
		overflow: hidden;
		transition: transform 0.3s ease, box-shadow 0.3s ease;
		border: 1px solid rgba(102, 126, 234, 0.1);
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
	}

	.project-item:hover {
		transform: translateY(-8px);
		box-shadow: 0 12px 32px rgba(102, 126, 234, 0.2);
	}

	.project-visual {
		position: relative;
		height: 200px;
		background: linear-gradient(135deg, #f7fafc, #edf2f7);
		overflow: hidden;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.project-logo {
		position: absolute;
		top: 1rem;
		left: 1rem;
		z-index: 2;
		background: white;
		padding: 0.5rem;
		border-radius: 8px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
		width: 60px;
		height: 60px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.project-logo img {
		width: 40px;
		height: 40px;
		object-fit: contain;
	}

	.project-screenshot {
		width: 100%;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
		opacity: 0.8;
	}

	.project-screenshot img {
		width: 90%;
		max-height: 85%;
		object-fit: cover;
		border-radius: 8px;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
	}

	.project-content {
		padding: 1.5rem;
	}

	.project-content h3 {
		color: #2d3748;
		font-size: 1.4rem;
		font-weight: 600;
		margin: 0 0 0.5rem 0;
	}

	.project-subtitle {
		color: #667eea;
		font-size: 0.95rem;
		font-weight: 500;
		margin: 0 0 1rem 0;
		line-height: 1.4;
	}

	.project-tech {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem;
	}

	.tech-tag {
		background: rgba(102, 126, 234, 0.1);
		color: #667eea;
		padding: 0.25rem 0.75rem;
		border-radius: 20px;
		font-size: 0.85rem;
		font-weight: 500;
		border: 1px solid rgba(102, 126, 234, 0.2);
	}

	.project-link {
		display: inline-block;
		margin-top: 1rem;
		color: #667eea;
		text-decoration: none;
		font-size: 0.9rem;
		font-weight: 600;
		padding: 0.5rem 1rem;
		border: 2px solid #667eea;
		border-radius: 25px;
		transition: all 0.3s ease;
		background: rgba(102, 126, 234, 0.05);
	}

	.project-link:hover {
		background: #667eea;
		color: white;
		transform: translateY(-2px);
		box-shadow: 0 4px 12px rgba(102, 126, 234, 0.3);
	}

	/* Grilles de compétences */
	.skills-grid {
		display: flex;
		flex-wrap: wrap;
		gap: 0.75rem;
		margin-top: 1rem;
	}

	.skills-break {
		flex-basis: 100%;
		height: 0;
	}

	.skill-badge {
		color: white;
		padding: 0.5rem 1rem;
		border-radius: 25px;
		font-size: 0.9rem;
		font-weight: 600;
		transition: all 0.3s ease;
		cursor: default;
	}

	/* Langages - Jaune */
	.skill-badge.language {
		background: linear-gradient(135deg, #f6ad55, #ed8936);
		box-shadow: 0 2px 8px rgba(246, 173, 85, 0.3);
	}

	.skill-badge.language:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 15px rgba(246, 173, 85, 0.4);
	}

	/* Frameworks - Vert */
	.skill-badge.framework {
		background: linear-gradient(135deg, #48bb78, #38a169);
		box-shadow: 0 2px 8px rgba(72, 187, 120, 0.3);
	}

	.skill-badge.framework:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 15px rgba(72, 187, 120, 0.4);
	}

	/* Outils - Rouge */
	.skill-badge.tool {
		background: linear-gradient(135deg, #e53e3e, #c53030);
		box-shadow: 0 2px 8px rgba(229, 62, 62, 0.3);
	}

	.skill-badge.tool:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 15px rgba(229, 62, 62, 0.4);
	}

	/* IA - Violet */
	.skill-badge.ai {
		background: linear-gradient(135deg, #9f7aea, #805ad5);
		box-shadow: 0 2px 8px rgba(159, 122, 234, 0.3);
	}

	.skill-badge.ai:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 15px rgba(159, 122, 234, 0.4);
	}

	/* CMS - Bleu clair */
	.skill-badge.cms {
		background: linear-gradient(135deg, #63b3ed, #4299e1);
		box-shadow: 0 2px 8px rgba(99, 179, 237, 0.3);
	}

	.skill-badge.cms:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 15px rgba(99, 179, 237, 0.4);
	}

	/* Soft Skills - Gris */
	.skill-badge.soft {
		background: linear-gradient(135deg, #718096, #4a5568);
		box-shadow: 0 2px 8px rgba(113, 128, 150, 0.3);
	}

	.skill-badge.soft:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 15px rgba(113, 128, 150, 0.4);
	}

	/* Frise chronologique */
	.timeline-section h2 {
		text-align: center;
		margin-bottom: 2rem;
	}

	.timeline {
		position: relative;
		max-width: 900px;
		margin: 0 auto;
		padding-left: 2rem;
	}

	.timeline::before {
		content: '';
		position: absolute;
		left: 20px;
		top: 0;
		bottom: 0;
		width: 3px;
		background: linear-gradient(135deg, #667eea, #764ba2);
		border-radius: 2px;
	}

	.timeline-item {
		position: relative;
		margin-bottom: 2rem;
		display: flex;
		align-items: flex-start;
	}

	.timeline-marker {
		position: absolute;
		left: -28px;
		top: 8px;
		width: 16px;
		height: 16px;
		background: #667eea;
		border: 3px solid white;
		border-radius: 50%;
		box-shadow: 0 2px 8px rgba(102, 126, 234, 0.3);
		z-index: 10;
	}

	.timeline-content {
		flex: 1;
		background: rgba(255, 255, 255, 0.8);
		padding: 1.2rem 1.5rem;
		border-radius: 10px;
		box-shadow: 0 3px 12px rgba(0, 0, 0, 0.08);
		border-left: 3px solid #667eea;
		margin-left: 2rem;
		transition: transform 0.2s ease, box-shadow 0.2s ease;
	}

	.timeline-content:hover {
		transform: translateX(5px);
		box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
	}

	.timeline-date {
		color: #667eea;
		font-weight: 700;
		font-size: 1rem;
		margin-bottom: 0.5rem;
	}

	.timeline-content h3 {
		color: #2d3748;
		font-size: 1.3rem;
		font-weight: 600;
		margin: 0 0 0.8rem 0;
	}

	.timeline-content p {
		color: #4a5568;
		line-height: 1.6;
		margin: 0;
		font-size: 1rem;
	}

	.timeline-location {
		color: #667eea !important;
		font-weight: 600 !important;
		font-style: italic;
		margin-bottom: 0.5rem !important;
	}

	.period {
		color: #667eea;
		font-weight: 500;
		font-size: 0.9rem;
	}

	.location {
		color: #667eea;
		font-weight: 600;
		font-style: italic;
		margin-bottom: 0.5rem;
		font-size: 0.9rem;
	}



	/* Bouton retour fixe */
	.back-button {
		position: fixed;
		bottom: 2rem;
		left: 50%;
		transform: translateX(-50%);
		background: rgba(0, 0, 0, 0.7);
		color: white;
		border: none;
		padding: 1rem;
		border-radius: 50%;
		font-size: 1.5rem;
		cursor: pointer;
		display: flex;
		align-items: center;
		justify-content: center;
		width: 3.5rem;
		height: 3.5rem;
		z-index: 10000;
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
		backdrop-filter: blur(10px);
		transition: background-color 0.3s ease, box-shadow 0.3s ease;
	}

	.back-button:hover {
		background: rgba(0, 0, 0, 0.9);
		box-shadow: 0 6px 25px rgba(0, 0, 0, 0.5);
	}

	@media (max-width: 480px) {
		* {
			box-sizing: border-box;
		}

		body, html {
			overflow-x: hidden;
		}

		.container {
			padding: 0.25rem;
			max-width: 100vw;
			overflow: hidden;
		}

		.section-content h2 {
			font-size: 1.2rem;
		}
		
		.carte-visite {
			padding: 1.5rem 1rem;
			max-width: calc(100vw - 0.5rem);
			margin: 0 auto;
		}

		.profile-name {
			font-size: 1.5rem;
		}

		.profile-title {
			font-size: 1rem;
		}

		.profile-image img {
			width: 80px;
			height: 80px;
		}

		.social-links {
			flex-direction: column;
			gap: 0.75rem;
		}

		/* Optimisation projets mobile */
		.projects-grid {
			grid-template-columns: 1fr;
			gap: 1rem;
			padding: 0.25rem 0.25rem 6rem 0.25rem;
		}

		.project-item {
			margin: 0;
		}

		.project-visual {
			height: 150px;
		}

		.project-logo {
			width: 50px;
			height: 50px;
			top: 0.5rem;
			left: 0.5rem;
		}

		.project-logo img {
			width: 30px;
			height: 30px;
		}

		.project-content {
			padding: 1rem;
		}

		.project-content h3 {
			font-size: 1.2rem;
		}

		.tech-tag {
			font-size: 0.75rem;
			padding: 0.2rem 0.5rem;
		}

		/* Corrections pour les pages et sections */
		.section-page, .full-page {
			width: 100vw;
			height: 100vh;
			max-width: 100%;
			overflow-x: hidden;
		}

		.page-body {
			padding: 0.5rem 0.5rem 6rem 0.5rem;
			max-width: 100%;
			overflow-x: hidden;
		}

		.content-section {
			padding: 0.5rem;
			margin-bottom: 1rem;
			max-width: 100%;
		}
		
		.section-content {
			padding: 0.5rem;
			max-width: 100%;
		}

		/* Optimisation timeline mobile */
		.timeline {
			padding-left: 1rem;
		}
		
		.timeline::before {
			left: 10px;
		}
		
		.timeline-marker {
			left: -18px;
			width: 12px;
			height: 12px;
		}
		
		.timeline-content {
			padding: 0.8rem 1rem;
			margin-left: 1.2rem;
		}
		
		.timeline-content h3 {
			font-size: 1.1rem;
		}
		
		/* Optimisation grilles mobile */
		.experience-grid {
			gap: 0.8rem;
		}
		
		.experience-item {
			padding: 1rem;
		}
		
		.experience-item h3 {
			font-size: 1.1rem;
		}
		
		.interests-grid {
			gap: 0.8rem;
		}
		
		.interest-item {
			padding: 0.75rem;
			display: flex;
			flex-direction: column;
			text-align: left;
		}
		
		.interest-header {
			display: flex;
			align-items: center;
			gap: 0.5rem;
			margin-bottom: 0.5rem;
		}
		
		.interest-item h3 {
			font-size: 0.95rem;
			margin: 0;
		}
		
		.interest-icon {
			height: auto;
			margin-bottom: 0;
			flex-shrink: 0;
		}
		
		.interest-icon img {
			width: 1.8rem;
			height: 1.8rem;
		}
		
		/* Corrections pour les textes longs */
		.section-content p, .timeline-content p {
			word-wrap: break-word;
			overflow-wrap: break-word;
			font-size: 0.9rem;
			line-height: 1.4;
		}

		/* Simplification des contacts sur mobile */
		.contact-grid {
			grid-template-columns: 1fr;
			gap: 0.75rem;
		}

		.contact-item {
			padding: 0.75rem;
			flex-direction: row;
			text-align: left;
			gap: 0.75rem;
		}

		.contact-icon {
			font-size: 1.8rem;
			margin-bottom: 0;
		}

		.linkedin-icon {
			width: 1.8rem;
			height: 1.8rem;
		}
	}

	/* Styles pour la page CV & Contact */
	.cv-section h2 {
		text-align: center;
		margin-bottom: 2rem;
	}

	.cv-container {
		max-width: 500px;
		margin: 0 auto;
	}

	.cv-preview {
		padding: 2rem;
		text-align: center;
	}

	.cv-thumbnail {
		margin-bottom: 1.5rem;
		position: relative;
	}

	.cv-thumbnail img {
		width: 100%;
		max-width: 300px;
		height: auto;
		border-radius: 8px;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
	}

	.cv-placeholder {
		display: none;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 100%;
		max-width: 300px;
		height: 400px;
		background: linear-gradient(135deg, #f7fafc, #edf2f7);
		border: 2px dashed #cbd5e0;
		border-radius: 8px;
		margin: 0 auto;
	}

	.cv-icon {
		font-size: 4rem;
		margin-bottom: 1rem;
		color: #667eea;
	}

	.cv-placeholder p {
		color: #4a5568;
		font-weight: 600;
		margin: 0;
	}

	.cv-actions {
		display: flex;
		gap: 1rem;
		justify-content: center;
		flex-wrap: wrap;
	}

	.cv-button {
		display: inline-flex;
		align-items: center;
		gap: 0.5rem;
		padding: 0.75rem 1.5rem;
		border-radius: 25px;
		font-weight: 600;
		text-decoration: none;
		transition: all 0.3s ease;
		border: 2px solid transparent;
	}

	.view-cv {
		background: rgba(102, 126, 234, 0.1);
		color: #667eea;
		border-color: #667eea;
	}

	.view-cv:hover {
		background: #667eea;
		color: white;
		transform: translateY(-2px);
		box-shadow: 0 4px 12px rgba(102, 126, 234, 0.3);
	}

	.download-cv {
		background: linear-gradient(135deg, #667eea, #764ba2);
		color: white;
		box-shadow: 0 2px 8px rgba(102, 126, 234, 0.3);
	}

	.download-cv:hover {
		transform: translateY(-2px);
		box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);
	}

	/* Section Contact */
	.contact-section h2 {
		text-align: center;
		margin-bottom: 2rem;
	}

	.contact-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 1.5rem;
		max-width: 800px;
		margin: 0 auto;
	}

	.contact-item {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
		gap: 0.75rem;
		padding: 1.5rem;
		background: rgba(255, 255, 255, 0.7);
		border-radius: 12px;
		transition: transform 0.2s ease, box-shadow 0.2s ease;
		border: 1px solid rgba(102, 126, 234, 0.15);
	}

	.contact-item:hover {
		transform: translateY(-3px);
		box-shadow: 0 6px 20px rgba(102, 126, 234, 0.15);
	}

	.contact-icon {
		font-size: 2.5rem;
		flex-shrink: 0;
		margin-bottom: 0.5rem;
	}

	.linkedin-icon {
		width: 2.5rem;
		height: 2.5rem;
		color: #0077b5;
		transition: color 0.3s ease, transform 0.3s ease;
	}

	.linkedin-icon:hover {
		color: #005885;
		transform: scale(1.1);
	}

	.linkedin-icon svg {
		width: 100%;
		height: 100%;
	}

	.contact-info h3 {
		margin: 0 0 0.25rem 0;
		color: #2d3748;
		font-size: 1rem;
		font-weight: 600;
	}

	.contact-info a, .contact-info p {
		margin: 0;
		color: #667eea;
		text-decoration: none;
		font-weight: 500;
		transition: color 0.2s ease;
	}

	.contact-info a:hover {
		color: #764ba2;
		text-decoration: underline;
	}

	.contact-info p {
		color: #4a5568;
	}

	/* Section Disponibilité */
	.availability-section h2 {
		text-align: center;
		margin-bottom: 2rem;
	}

	.availability-status {
		display: flex;
		align-items: center;
		gap: 1rem;
		max-width: 600px;
		margin: 0 auto;
		padding: 2rem;
		background: rgba(255, 255, 255, 0.8);
		border-radius: 12px;
		border: 1px solid rgba(72, 187, 120, 0.3);
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1);
	}

	.status-indicator {
		width: 20px;
		height: 20px;
		border-radius: 50%;
		flex-shrink: 0;
		position: relative;
	}

	.status-indicator.available {
		background: #48bb78;
		box-shadow: 0 0 0 4px rgba(72, 187, 120, 0.2);
		animation: pulse 2s infinite;
	}

	@keyframes pulse {
		0% {
			box-shadow: 0 0 0 0 rgba(72, 187, 120, 0.4);
		}
		70% {
			box-shadow: 0 0 0 10px rgba(72, 187, 120, 0);
		}
		100% {
			box-shadow: 0 0 0 0 rgba(72, 187, 120, 0);
		}
	}

	.status-text h3 {
		margin: 0 0 0.5rem 0;
		color: #2d3748;
		font-size: 1.3rem;
		font-weight: 600;
	}

	.status-text p {
		margin: 0;
		color: #4a5568;
		line-height: 1.6;
	}

	.status-text strong {
		color: #48bb78;
		font-weight: 600;
	}

	/* Media query pour les très petits écrans (iPhone SE, etc.) */
	@media (max-width: 375px) {
		.carte-visite {
			padding: 1rem 0.75rem;
			max-width: calc(100vw - 1rem);
		}

		.profile-name {
			font-size: 1.3rem;
		}

		.projects-grid {
			padding: 0 0 7rem 0;
			gap: 0.5rem;
		}

		.project-item {
			margin: 0;
		}

		.cv-actions {
			flex-direction: column;
		}

		.contact-grid {
			grid-template-columns: 1fr;
			gap: 1rem;
		}

		.contact-item {
			padding: 1rem;
			flex-direction: row;
			text-align: left;
			gap: 1rem;
		}

		.contact-icon {
			font-size: 2rem;
			margin-bottom: 0;
		}

		.linkedin-icon {
			width: 2rem;
			height: 2rem;
		}

		.availability-status {
			flex-direction: column;
			text-align: center;
			gap: 1rem;
		}

		.cv-preview {
			padding: 1rem;
		}
	}
</style>
