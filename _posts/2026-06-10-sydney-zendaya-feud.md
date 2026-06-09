---
layout: default
---
<!DOCTYPE html>
<html lang="en-US" prefix="og: https://ogp.me/ns#">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
    
    <!-- Dynamic Title from Front Matter -->
    <title>{{ page.title | default: site.title }}</title>
    
    <!-- SEO Meta Tags -->
    <meta name="description" content="{{ page.excerpt | strip_html | truncate: 160 }}">
    
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700;900&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Include CSS (Disarankan dipindah ke assets/css/style.css) -->
    <style>
        /* ... PASTE SEMUA CSS DARI KODE ASLI DI SINI ... */
        /* Saya tidak menyalin ulang CSS-nya di sini agar tidak terlalu panjang, 
           silakan copy blok <style>...</style> dari kode asli Anda ke sini */
    </style>
</head>
<body>
    <!-- Custom Cursor -->
    <div class="cursor"></div>
    <div class="cursor-follower"></div>

    <!-- Reading Progress Bar -->
    <div class="progress-bar" id="progressBar"></div>

    <!-- Background Animation -->
    <div class="bg-animation"></div>
    <div class="particles" id="particles"></div>

    <!-- Navigation -->
    <nav id="navbar">
        <div class="logo">{{ site.title | default: "CELEBRITY TOP 1" }}</div>
        <ul class="nav-links">
            <li><a href="/">Home</a></li>
            <li><a href="#article">Article</a></li>
            <li><a href="#gallery">Gallery</a></li>
            <li><a href="#timeline">Timeline</a></li>
            <li><a href="#comments">Comments</a></li>
        </ul>
    </nav>

    <!-- Social Share -->
    <div class="social-share">
        <a href="https://wa.me/?text={{ page.url | absolute_url }}" class="share-btn" title="Share on WhatsApp"><i class="fab fa-whatsapp"></i></a>
        <a href="https://twitter.com/intent/tweet?text={{ page.title }}&url={{ page.url | absolute_url }}" class="share-btn" title="Share on Twitter"><i class="fab fa-twitter"></i></a>
        <a href="#" class="share-btn" title="Share on Instagram"><i class="fab fa-instagram"></i></a>
        <a href="#" class="share-btn" title="Share on Facebook"><i class="fab fa-facebook-f"></i></a>
    </div>

    <!-- Hero Section (Dynamic Content) -->
    <section class="hero" id="home">
        <div class="hero-content">
            <div class="hero-text">
                <span class="category-tag"><i class="fas fa-fire"></i> {{ page.category | default: "Breaking News" }}</span>
                
                <!-- Dynamic Title -->
                <h1 class="hero-title">{{ page.title }}</h1>
                
                <!-- Dynamic Excerpt/Subtitle -->
                <p class="hero-subtitle">
                    {{ page.excerpt | strip_html | truncate: 200 }}
                </p>
                
                <div class="hero-meta">
                    <span><i class="far fa-calendar"></i> {{ page.date | date: "%B %d, %Y" }}</span>
                    <span><i class="far fa-clock"></i> {{ page.read_time | default: "5 min read" }}</span>
                    <span><i class="far fa-eye"></i> {% if page.views %}{{ page.views }}{% else %}125K{% endif %} views</span>
                    <span><i class="far fa-heart"></i> {% if page.likes %}{{ page.likes }}{% else %}8.5K{% endif %} likes</span>
                </div>
            </div>
            
            <div class="hero-images">
                <!-- Dynamic Images from Front Matter -->
                <div class="hero-image-main" onclick="openLightbox(this)">
                    <img src="{{ page.hero_image_1 | default: 'https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhCBuQhJxBr5Ui3AnOQnMHZ04uq0ZHj0EqpJHKtE6UGiTGz1ZMWUS4dCQore1apsMKx7zRDMf_EBV6uQ_1PX1n4oCcSNPyErpvo1g9lH_2x8z8iZocIDubXlVlOT2ymq2YUf_RxiLcz-5CnUmsiiSiUldSc1va_vVx_ojGRZJsk6D5CKK1ij2QEqcW2btY/s1600/zen.webp' }}" alt="{{ page.title }}">
                </div>
                <div class="hero-image-secondary" onclick="openLightbox(this)">
                    <img src="{{ page.hero_image_2 | default: 'https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg1vxHKZORDS2EUzvieNF0KSVKpNHmNkIOfXaaktJ8tzbLAqVKU4U5wrUvvSsWNSXgSqWEQrshdQqzlsM57JLuO2x2UsJMQOIUi8cy1CcIP4PgsxjEcppI7ft_Xwjwpzg3jTP4817ShXOYsqpnKMzWHhTnKU2abpybkJgJ7axxo9l_34bFhe6jiWhwmjZE/s1600/zend.webp' }}" alt="Secondary Image">
                </div>
                <div class="floating-badge">
                    <h3>{{ page.badge_title | default: "EUPHORIA" }}</h3>
                    <p>{{ page.badge_subtitle | default: "Season 3" }}</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Article Content (Dynamic from Markdown Body) -->
    <article class="article-container" id="article">
        {{ content }}
        
        <!-- Stats Section (Static or Dynamic) -->
        <div class="stats-section scroll-reveal">
            <div class="stat-item">
                <div class="stat-number" data-target="3">0</div>
                <div class="stat-label">Seasons</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" data-target="2026">0</div>
                <div class="stat-label">Release Year</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" data-target="125">0</div>
                <div class="stat-label">K+ Views</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">∞</div>
                <div class="stat-label">Speculation</div>
            </div>
        </div>
    </article>

    <!-- Timeline Section (Hardcoded for this specific post, or make dynamic via Data Files) -->
    <section class="article-container" id="timeline">
        <h2 class="section-title scroll-reveal">Controversy Timeline</h2>
        
        <div class="timeline">
            <div class="timeline-item scroll-reveal">
                <div class="timeline-content">
                    <div class="timeline-date"><i class="far fa-calendar-alt"></i> November 2025</div>
                    <p class="timeline-text">Daily Mail reports bitter feud between Sweeney and Zendaya stemming from political differences.</p>
                </div>
                <div class="timeline-dot"></div>
            </div>
            <!-- Tambahkan item timeline lain sesuai kebutuhan -->
             <div class="timeline-item scroll-reveal">
                <div class="timeline-content">
                    <div class="timeline-date"><i class="far fa-calendar-alt"></i> June 2026</div>
                    <p class="timeline-text">Sweeney shares BTS photos without Zendaya, reigniting feud speculation.</p>
                </div>
                <div class="timeline-dot"></div>
            </div>
        </div>
    </section>

    <!-- Related Articles (Dynamic Jekyll Loop) -->
    <section class="article-container related-section">
        <h2 class="section-title scroll-reveal">Related Articles</h2>
        <div class="related-grid">
            {% for post in site.posts limit: 3 %}
                {% unless post.url == page.url %}
                <div class="related-card scroll-reveal">
                    <a href="{{ post.url }}" style="text-decoration: none; color: inherit;">
                        <div class="related-image">🎬</div>
                        <div class="related-content">
                            <div class="related-category">{{ post.category | default: "Entertainment" }}</div>
                            <h3 class="related-title">{{ post.title }}</h3>
                            <div class="related-meta"><i class="far fa-clock"></i> {{ post.date | date: "%b %d, %Y" }}</div>
                        </div>
                    </a>
                </div>
                {% endunless %}
            {% endfor %}
        </div>
    </section>

    <!-- Comments Section -->
    <section class="article-container comments-section" id="comments">
        <h2 class="section-title scroll-reveal">Comments</h2>
        
        <div class="comment-form scroll-reveal">
            <textarea class="comment-input" placeholder="Write your comment here..."></textarea>
            <button class="comment-btn"><i class="fas fa-paper-plane"></i> Post Comment</button>
        </div>

        <div class="comment-list">
            <!-- Contoh Komentar Statis -->
            <div class="comment-item scroll-reveal">
                <div class="comment-avatar">👤</div>
                <div class="comment-content">
                    <div class="comment-header">
                        <span class="comment-name">Sarah Johnson</span>
                        <span class="comment-time">2 hours ago</span>
                    </div>
                    <p class="comment-text">Wow, this is really surprising! I didn't expect there to be tension like this between them. Hope everything is okay. 🙏</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>{{ site.title | default: "CELEBRITY TOP 1" }}</h3>
                <p>Your trusted source for the latest news about celebrity culture, entertainment, and Hollywood stars.</p>
                <div class="footer-social">
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <a href="/"><i class="fas fa-chevron-right"></i> Home</a>
                <a href="#article"><i class="fas fa-chevron-right"></i> Article</a>
                <a href="#gallery"><i class="fas fa-chevron-right"></i> Gallery</a>
            </div>
            <div class="footer-section">
                <h3>Contact Us</h3>
                <p><i class="fas fa-envelope"></i> info@celebritytop1.com</p>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; {{ site.time | date: "%Y" }} {{ site.title | default: "Celebrity Top 1" }}. All rights reserved.</p>
        </div>
    </footer>

    <!-- Back to Top Button -->
    <div class="back-to-top" id="backToTop">
        <i class="fas fa-arrow-up"></i>
    </div>

    <!-- Lightbox -->
    <div class="lightbox" id="lightbox">
        <div class="lightbox-close" onclick="closeLightbox()"><i class="fas fa-times"></i></div>
        <img class="lightbox-img" id="lightboxImg" src="" alt="">
    </div>

    <!-- JavaScript -->
    <script>
        // ... PASTE SEMUA JAVASCRIPT DARI KODE ASLI DI SINI ...
        // Pastikan script loader dihapus atau dimodifikasi karena Jekyll tidak selalu butuh loader eksternal
        
        // Loader fix for Jekyll
        window.addEventListener('load', () => {
            // Jika ada elemen loader, hidden kan. Jika tidak, abaikan.
            const loader = document.getElementById('loader');
            if(loader) loader.classList.add('hidden');
        });

        // Create Particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            if(!particlesContainer) return;
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 15 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particlesContainer.appendChild(particle);
            }
        }
        createParticles();

        // Reading Progress Bar
        window.addEventListener('scroll', () => {
            const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
            const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrolled = (winScroll / height) * 100;
            const progressBar = document.getElementById('progressBar');
            if(progressBar) progressBar.style.width = scrolled + '%';
        });

        // Scroll Reveal Animation
        const observerOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -100px 0px"
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.scroll-reveal').forEach((el) => observer.observe(el));

        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Navbar Scroll Effect
        window.addEventListener('scroll', () => {
            const nav = document.getElementById('navbar');
            if (window.scrollY > 100) {
                nav.classList.add('scrolled');
            } else {
                nav.classList.remove('scrolled');
            }
        });

        // Back to Top Button
        const backToTopBtn = document.getElementById('backToTop');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 500) {
                backToTopBtn.classList.add('visible');
            } else {
                backToTopBtn.classList.remove('visible');
            }
        });

        if(backToTopBtn) {
            backToTopBtn.addEventListener('click', () => {
                window.scrollTo({
                    top: 0,
                    behavior: 'smooth'
                });
            });
        }

        // Counter Animation for Stats
        const animateCounter = (element, target, duration = 2000) => {
            let start = 0;
            const increment = target / (duration / 16);
            
            const timer = setInterval(() => {
                start += increment;
                if (start >= target) {
                    element.textContent = target;
                    clearInterval(timer);
                } else {
                    element.textContent = Math.floor(start);
                }
            }, 16);
        };

        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const statNumbers = entry.target.querySelectorAll('.stat-number[data-target]');
                    statNumbers.forEach(stat => {
                        const value = parseInt(stat.getAttribute('data-target'));
                        animateCounter(stat, value);
                    });
                    statsObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });

        const statsSection = document.querySelector('.stats-section');
        if (statsSection) {
            statsObserver.observe(statsSection);
        }

        // Parallax Effect for Hero Images
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallaxElements = document.querySelectorAll('.hero-image-main, .hero-image-secondary');
            
            parallaxElements.forEach((el, index) => {
                const speed = index === 0 ? 0.5 : 0.3;
                el.style.transform = `translateY(${scrolled * speed}px)`;
            });
        });

        // Lightbox
        function openLightbox(element) {
            const img = element.querySelector('img');
            const lightbox = document.getElementById('lightbox');
            const lightboxImg = document.getElementById('lightboxImg');
            if(img && lightbox && lightboxImg) {
                lightboxImg.src = img.src;
                lightbox.classList.add('active');
                document.body.style.overflow = 'hidden';
            }
        }

        function closeLightbox() {
            const lightbox = document.getElementById('lightbox');
            if(lightbox) {
                lightbox.classList.remove('active');
                document.body.style.overflow = 'auto';
            }
        }

        const lightboxEl = document.getElementById('lightbox');
        if(lightboxEl) {
            lightboxEl.addEventListener('click', (e) => {
                if (e.target.id === 'lightbox') {
                    closeLightbox();
                }
            });
        }

        // Custom Cursor
        const cursor = document.querySelector('.cursor');
        const cursorFollower = document.querySelector('.cursor-follower');

        if(cursor && cursorFollower) {
            document.addEventListener('mousemove', (e) => {
                cursor.style.left = e.clientX + 'px';
                cursor.style.top = e.clientY + 'px';
                
                setTimeout(() => {
                    cursorFollower.style.left = e.clientX - 10 + 'px';
                    cursorFollower.style.top = e.clientY - 10 + 'px';
                }, 100);
            });

            document.querySelectorAll('a, button, .gallery-item, .hero-image-main, .hero-image-secondary').forEach(el => {
                el.addEventListener('mouseenter', () => {
                    cursor.style.transform = 'scale(1.5)';
                    cursorFollower.style.transform = 'scale(1.5)';
                });
                el.addEventListener('mouseleave', () => {
                    cursor.style.transform = 'scale(1)';
                    cursorFollower.style.transform = 'scale(1)';
                });
            });
        }

        // Comment Form
        const commentBtn = document.querySelector('.comment-btn');
        if(commentBtn) {
            commentBtn.addEventListener('click', () => {
                const commentInput = document.querySelector('.comment-input');
                if (commentInput.value.trim() !== '') {
                    alert('Comment posted successfully! ✨');
                    commentInput.value = '';
                } else {
                    alert('Please write a comment first!');
                }
            });
        }

        // Add hover effect to timeline items
        document.querySelectorAll('.timeline-item').forEach(item => {
            item.addEventListener('mouseenter', () => {
                const dot = item.querySelector('.timeline-dot');
                if(dot) dot.style.transform = 'translateX(-50%) scale(1.3)';
            });
            item.addEventListener('mouseleave', () => {
                const dot = item.querySelector('.timeline-dot');
                if(dot) dot.style.transform = 'translateX(-50%) scale(1)';
            });
        });

        // Keyboard shortcut for lightbox
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') {
                closeLightbox();
            }
        });
    </script>
</body>
</html>
