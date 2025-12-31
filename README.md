<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🎮 Free Fire Grupo WhatsApp - Únete a la Comunidad</title>
    <meta name="description" content="Únete al grupo oficial de Free Fire en WhatsApp. Torneos, sorteos y comunidad activa 24/7. ¡Conecta con jugadores de todo el mundo!">
    <meta name="keywords" content="Free Fire, WhatsApp, grupo, gamers, torneos, sorteos, comunidad">
    <meta property="og:title" content="Free Fire Grupo WhatsApp">
    <meta property="og:description" content="Comunidad activa de Free Fire en WhatsApp">
    <meta property="og:image" content="img/preview.jpg">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="style.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Montserrat:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="icon" type="image/x-icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>🎮</text></svg>">
    <script src="base de datos.js"></script>
</head>
  <script>
    class EfectosFreeFire {
    constructor() {
        this.efectosActivos = true;
        this.init();
    }
    
    init() {
        console.log('🎮 Efectos Free Fire Premium iniciados');
        
        // Efectos de carga inicial
        this.iniciarEfectosCarga();
        
        // Efectos de scroll
        this.iniciarEfectosScroll();
        
        // Efectos hover avanzados
        this.iniciarEfectosHover();
        
        // Animaciones de elementos
        this.iniciarAnimaciones();
        
        // Sistema de sonidos
        this.iniciarSistemaSonidos();
        
        // Efectos especiales
        this.iniciarEfectosEspeciales();
    }
    
    // Efectos durante la carga
    iniciarEfectosCarga() {
        // Secuencia de aparición
        const elementos = document.querySelectorAll('.main-container > *');
        elementos.forEach((el, index) => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            
            setTimeout(() => {
                el.style.transition = 'opacity 0.8s ease, transform 0.8s ease';
                el.style.opacity = '1';
                el.style.transform = 'translateY(0)';
            }, 200 + (index * 100));
        });
        
        // Efecto de bienvenida
        setTimeout(() => {
            this.crearEfectoBienvenida();
        }, 1000);
    }
    
    // Efectos al hacer scroll
    iniciarEfectosScroll() {
        let ultimaPosicion = 0;
        let ticking = false;
        
        window.addEventListener('scroll', () => {
            if (!ticking) {
                window.requestAnimationFrame(() => {
                    this.animarElementosScroll();
                    this.efectoParallax();
                    ticking = false;
                });
                ticking = true;
            }
            
            // Efecto de navbar
            const scrollActual = window.pageYOffset;
            const diferencia = scrollActual - ultimaPosicion;
            ultimaPosicion = scrollActual;
            
            if (Math.abs(diferencia) > 5) {
                this.efectoScrollVelocity(diferencia);
            }
        });
        
        // Revelar elementos al scroll
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('reveal');
                }
            });
        }, { threshold: 0.1 });
        
        document.querySelectorAll('.stat-card, .feature-card, .testimonial-card').forEach(el => {
            observer.observe(el);
        });
    }
    
    // Animaciones de scroll
    animarElementosScroll() {
        const scrollY = window.pageYOffset;
        const velocidad = 0.5;
        
        document.querySelectorAll('.stat-card').forEach((card, index) => {
            const offset = scrollY * velocidad - (index * 100);
            card.style.transform = `translateY(${Math.sin(offset * 0.01) * 10}px)`;
        });
    }
    
    // Efecto parallax
    efectoParallax() {
        const scrolled = window.pageYOffset;
        const rate = scrolled * -0.5;
        
        document.querySelectorAll('.feature-icon').forEach(icon => {
            icon.style.transform = `rotate(${rate * 0.1}deg)`;
        });
    }
    
    // Efecto de velocidad de scroll
    efectoScrollVelocity(velocidad) {
        const elementos = document.querySelectorAll('.logo, .stat-card');
        const intensidad = Math.min(Math.abs(velocidad) * 0.1, 10);
        
        elementos.forEach(el => {
            el.style.transform = `translateY(${velocidad > 0 ? intensidad : -intensidad}px)`;
            setTimeout(() => {
                el.style.transform = 'translateY(0)';
            }, 300);
        });
    }
    
    // Efectos hover avanzados
    iniciarEfectosHover() {
        // Efecto magnético en botones
        document.querySelectorAll('.btn-control, .cta-button').forEach(btn => {
            btn.addEventListener('mousemove', (e) => {
                const rect = btn.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                
                const moveX = (x - centerX) / 20;
                const moveY = (y - centerY) / 20;
                
                btn.style.transform = `translate(${moveX}px, ${moveY}px)`;
            });
            
            btn.addEventListener('mouseleave', () => {
                btn.style.transform = 'translate(0, 0)';
            });
        });
        
        // Efecto de seguimiento en cards
        document.querySelectorAll('.stat-card, .feature-card').forEach(card => {
            card.addEventListener('mousemove', (e) => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                
                const rotateY = (x - centerX) / 25;
                const rotateX = (centerY - y) / 25;
                
                card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
            });
            
            card.addEventListener('mouseleave', () => {
                card.style.transform = 'perspective(1000px) rotateX(0) rotateY(0)';
            });
        });
        
        // Efecto de partículas en hover
        document.querySelectorAll('.feature-icon').forEach(icon => {
            icon.addEventListener('mouseenter', (e) => {
                this.crearParticulasIcono(e, icon);
            });
        });
    }
    
    // Animaciones automáticas
    iniciarAnimaciones() {
        // Contador animado
        this.animarContadores();
        
        // Efecto de pulso en elementos importantes
        setInterval(() => {
            document.querySelectorAll('.badge-ultra, .feature-badge').forEach(badge => {
                badge.style.animation = 'none';
                setTimeout(() => {
                    badge.style.animation = 'badgePulse 1.5s infinite';
                }, 10);
            });
        }, 5000);
        
        // Rotación de testimonios
        this.iniciarSliderTestimonios();
        
        // Efecto de texto que escribe
        this.efectoTextoEscribiendose();
    }
    
    // Animación de contadores
    animarContadores() {
        const contadores = document.querySelectorAll('.stat-number');
        
        contadores.forEach(contador => {
            const valorFinal = parseInt(contador.textContent.replace(/,/g, ''));
            let valorActual = 0;
            const incremento = Math.ceil(valorFinal / 100);
            const duracion = 2000;
            const paso = duracion / (valorFinal / incremento);
            
            const timer = setInterval(() => {
                valorActual += incremento;
                if (valorActual >= valorFinal) {
                    valorActual = valorFinal;
                    clearInterval(timer);
                }
                contador.textContent = valorActual.toLocaleString('es-ES');
            }, paso);
        });
    }
    
    // Slider de testimonios automático
    iniciarSliderTestimonios() {
        const testimonios = document.querySelectorAll('.testimonial-card');
        let indiceActual = 0;
        
        setInterval(() => {
            testimonios.forEach((testimonio, index) => {
                testimonio.style.opacity = index === indiceActual ? '1' : '0.5';
                testimonio.style.transform = index === indiceActual ? 'scale(1.05)' : 'scale(0.95)';
            });
            
            indiceActual = (indiceActual + 1) % testimonios.length;
        }, 5000);
    }
    
    // Efecto de texto que se escribe
    efectoTextoEscribiendose() {
        const textos = [
            "Únete a la comunidad más activa de Free Fire",
            "Torneos semanales con grandes premios",
            "Sorteos de diamantes y skins exclusivas",
            "Encuentra compañeros para ranked y casual"
        ];
        
        const elemento = document.querySelector('.cta-subtitle');
        if (!elemento) return;
        
        let textoIndex = 0;
        let charIndex = 0;
        let escribiendo = true;
        
        function escribir() {
            const textoActual = textos[textoIndex];
            
            if (escribiendo) {
                elemento.textContent = textoActual.substring(0, charIndex + 1);
                charIndex++;
                
                if (charIndex === textoActual.length) {
                    escribiendo = false;
                    setTimeout(escribir, 2000);
                } else {
                    setTimeout(escribir, 50);
                }
            } else {
                elemento.textContent = textoActual.substring(0, charIndex - 1);
                charIndex--;
                
                if (charIndex === 0) {
                    escribiendo = true;
                    textoIndex = (textoIndex + 1) % textos.length;
                    setTimeout(escribir, 500);
                } else {
                    setTimeout(escribir, 30);
                }
            }
        }
        
        escribir();
    }
    
    // Sistema de sonidos
    iniciarSistemaSonidos() {
        // Crear contexto de audio
        this.audioContext = null;
        
        // Inicializar solo después de interacción del usuario
        document.addEventListener('click', () => {
            if (!this.audioContext) {
                this.audioContext = new (window.AudioContext || window.webkitAudioContext)();
            }
        }, { once: true });
    }
    
    // Reproducir sonido
    reproducirSonido(tipo, frecuencia = 440, duracion = 0.3) {
        if (!this.audioContext || !this.efectosActivos) return;
        
        try {
            const oscillator = this.audioContext.createOscillator();
            const gainNode = this.audioContext.createGain();
            
            oscillator.connect(gainNode);
            gainNode.connect(this.audioContext.destination);
            
            // Configurar según el tipo
            switch(tipo) {
                case 'click':
                    oscillator.frequency.setValueAtTime(523.25, this.audioContext.currentTime); // Do
                    oscillator.frequency.setValueAtTime(659.25, this.audioContext.currentTime + 0.1); // Mi
                    break;
                case 'hover':
                    oscillator.frequency.setValueAtTime(frequencia, this.audioContext.currentTime);
                    oscillator.frequency.setValueAtTime(frequencia * 1.2, this.audioContext.currentTime + 0.05);
                    break;
                case 'success':
                    oscillator.frequency.setValueAtTime(659.25, this.audioContext.currentTime); // Mi
                    oscillator.frequency.setValueAtTime(783.99, this.audioContext.currentTime + 0.1); // Sol
                    oscillator.frequency.setValueAtTime(1046.50, this.audioContext.currentTime + 0.2); // Do alto
                    break;
            }
            
            gainNode.gain.setValueAtTime(0.1, this.audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.01, this.audioContext.currentTime + duracion);
            
            oscillator.start();
            oscillator.stop(this.audioContext.currentTime + duracion);
        } catch (error) {
            console.log('🔇 Error de audio:', error);
        }
    }
    
    // Efectos especiales
    iniciarEfectosEspeciales() {
        // Efecto de bienvenida
        document.addEventListener('DOMContentLoaded', () => {
            setTimeout(() => {
                this.reproducirSonido('success');
            }, 1500);
        });
        
        // Efecto al hacer clic en botones
        document.querySelectorAll('button, .btn-control').forEach(btn => {
            btn.addEventListener('click', () => {
                this.reproducirSonido('click');
                this.crearOndaClic(btn);
            });
        });
        
        // Efecto al pasar sobre elementos interactivos
        document.querySelectorAll('.feature-card, .stat-card').forEach(card => {
            card.addEventListener('mouseenter', () => {
                this.reproducirSonido('hover', 440 + Math.random() * 100);
            });
        });
        
        // Efecto de notificación periódica
        setInterval(() => {
            if (Math.random() > 0.7) {
                this.mostrarNotificacionSistema();
            }
        }, 30000);
    }
    
    // Crear onda de clic
    crearOndaClic(elemento) {
        const onda = document.createElement('div');
        onda.className = 'onda-clic';
        
        const rect = elemento.getBoundingClientRect();
        onda.style.cssText = `
            position: fixed;
            width: 100px;
            height: 100px;
            border: 3px solid var(--ff-gold);
            border-radius: 50%;
            top: ${rect.top + rect.height/2 - 50}px;
            left: ${rect.left + rect.width/2 - 50}px;
            pointer-events: none;
            z-index: 10000;
            animation: ondaExpand 0.6s ease-out forwards;
        `;
        
        document.body.appendChild(onda);
        
        setTimeout(() => onda.remove(), 600);
    }
    
    // Crear partículas para iconos
    crearParticulasIcono(event, icono) {
        for (let i = 0; i < 8; i++) {
            setTimeout(() => {
                const particula = document.createElement('div');
                const rect = icono.getBoundingClientRect();
                const colores = ['#FF0000', '#FFD700', '#00FF00', '#1E90FF'];
                
                particula.style.cssText = `
                    position: fixed;
                    width: 6px;
                    height: 6px;
                    background: ${colores[Math.floor(Math.random() * colores.length)]};
                    border-radius: 50%;
                    top: ${rect.top + rect.height/2}px;
                    left: ${rect.left + rect.width/2}px;
                    pointer-events: none;
                    z-index: 1000;
                `;
                
                document.body.appendChild(particula);
                
                // Animación
                const angulo = Math.random() * Math.PI * 2;
                const velocidad = 1 + Math.random() * 2;
                const dx = Math.cos(angulo) * velocidad;
                const dy = Math.sin(angulo) * velocidad;
                
                let posX = rect.left + rect.width/2;
                let posY = rect.top + rect.height/2;
                let opacidad = 1;
                
                function animar() {
                    posX += dx;
                    posY += dy;
                    opacidad -= 0.02;
                    
                    particula.style.left = posX + 'px';
                    particula.style.top = posY + 'px';
                    particula.style.opacity = opacidad;
                    
                    if (opacidad > 0) {
                        requestAnimationFrame(animar);
                    } else {
                        particula.remove();
                    }
                }
                
                animar();
            }, i * 50);
        }
    }
    
    // Crear efecto de bienvenida
    crearEfectoBienvenida() {
        // Texto de bienvenida
        const bienvenida = document.createElement('div');
        bienvenida.innerHTML = `
            <div style="
                position: fixed;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                background: rgba(0, 0, 0, 0.9);
                color: white;
                padding: 30px 50px;
                border-radius: 20px;
                border: 3px solid var(--ff-gold);
                text-align: center;
                z-index: 10001;
                font-family: 'Orbitron', sans-serif;
                box-shadow: 0 0 50px rgba(255, 215, 0, 0.5);
                animation: aparecer 0.5s ease-out;
            ">
                <h2 style="color: var(--ff-gold); margin-bottom: 15px;">🎮 BIENVENIDO</h2>
                <p>¡Prepárate para la mejor experiencia Free Fire!</p>
                <button style="
                    background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
                    border: none;
                    color: white;
                    padding: 10px 30px;
                    border-radius: 25px;
                    margin-top: 20px;
                    cursor: pointer;
                    font-family: 'Orbitron', sans-serif;
                    font-weight: 600;
                " onclick="this.parentElement.remove()">
                    ¡ENTRAR!
                </button>
            </div>
        `;
        
        document.body.appendChild(bienvenida);
        
        // Remover después de 3 segundos
        setTimeout(() => {
            if (bienvenida.parentNode) {
                bienvenida.style.animation = 'desaparecer 0.5s ease-out forwards';
                setTimeout(() => bienvenida.remove(), 500);
            }
        }, 3000);
    }
    
    // Mostrar notificación del sistema
    mostrarNotificacionSistema() {
        const notificaciones = [
            "🔥 Nuevo torneo iniciado",
            "🎉 ¡Nuevo jugador se unió!",
            "🏆 Torneo terminado - Revisa ganadores",
            "💎 Sorteo de diamantes en 1 hora",
            "👥 5 jugadores buscando equipo"
        ];
        
        const notificacion = document.createElement('div');
        notificacion.className = 'notificacion-sistema';
        notificacion.innerHTML = `
            <i class="fas fa-bell"></i>
            <span>${notificaciones[Math.floor(Math.random() * notificaciones.length)]}</span>
        `;
        
        document.body.appendChild(notificacion);
        
        // Animación
        setTimeout(() => {
            notificacion.style.right = '20px';
        }, 10);
        
        // Remover
        setTimeout(() => {
            notificacion.style.right = '-300px';
            setTimeout(() => notificacion.remove(), 500);
        }, 5000);
    }
    
    // API pública para otros scripts
    mostrarEfectoPersonalizado(tipo, opciones = {}) {
        switch(tipo) {
            case 'confeti':
                this.crearConfeti(opciones.x || window.innerWidth/2, opciones.y || window.innerHeight/2);
                break;
            case 'explosion':
                this.crearExplosion(opciones.x, opciones.y);
                break;
            case 'textoFlotante':
                this.crearTextoFlotante(opciones.texto, opciones.x, opciones.y);
                break;
        }
    }
    
    crearConfeti(x, y) {
        for(let i = 0; i < 30; i++) {
            setTimeout(() => this.crearParticulaConfeti(x, y), i * 30);
        }
    }
    
    crearParticulaConfeti(x, y) {
        const particula = document.createElement('div');
        const colores = ['#FF0000', '#FFD700', '#00FF00', '#1E90FF', '#8A2BE2'];
        const formas = ['circle', 'square', 'triangle'];
        const forma = formas[Math.floor(Math.random() * formas.length)];
        
        particula.style.cssText = `
            position: fixed;
            width: 10px;
            height: 10px;
            background: ${colores[Math.floor(Math.random() * colores.length)]};
            ${forma === 'circle' ? 'border-radius: 50%;' : ''}
            ${forma === 'triangle' ? `
                background: transparent;
                width: 0;
                height: 0;
                border-left: 5px solid transparent;
                border-right: 5px solid transparent;
                border-bottom: 10px solid ${colores[Math.floor(Math.random() * colores.length)]};
            ` : ''}
            top: ${y}px;
            left: ${x}px;
            pointer-events: none;
            z-index: 10000;
            transform: rotate(${Math.random() * 360}deg);
        `;
        
        document.body.appendChild(particula);
        
        // Animación
        const angulo = Math.random() * Math.PI * 2;
        const velocidad = 2 + Math.random() * 3;
        const dx = Math.cos(angulo) * velocidad;
        const dy = Math.sin(angulo) * velocidad;
        const rotacion = (Math.random() - 0.5) * 10;
        
        let posX = x;
        let posY = y;
        let rot = 0;
        let opacidad = 1;
        
        function animar() {
            posX += dx;
            posY += dy;
            rot += rotacion;
            opacidad -= 0.01;
            
            particula.style.left = posX + 'px';
            particula.style.top = posY + 'px';
            particula.style.transform = `rotate(${rot}deg)`;
            particula.style.opacity = opacidad;
            
            if (opacidad > 0) {
                requestAnimationFrame(animar);
            } else {
                particula.remove();
            }
        }
        
        animar();
    }
}

// Inicializar efectos cuando cargue la página
document.addEventListener('DOMContentLoaded', () => {
    window.efectosFF = new EfectosFreeFire();
    console.log('✨ Efectos premium activados');
});

// Agregar estilos CSS para animaciones
const estilosEfectos = document.createElement('style');
estilosEfectos.textContent = `
    @keyframes ondaExpand {
        0% {
            transform: scale(0.1);
            opacity: 1;
            border-width: 3px;
        }
        100% {
            transform: scale(3);
            opacity: 0;
            border-width: 1px;
        }
    }
    
    @keyframes aparecer {
        from {
            opacity: 0;
            transform: translate(-50%, -50%) scale(0.8);
        }
        to {
            opacity: 1;
            transform: translate(-50%, -50%) scale(1);
        }
    }
    
    @keyframes desaparecer {
        from {
            opacity: 1;
            transform: translate(-50%, -50%) scale(1);
        }
        to {
            opacity: 0;
            transform: translate(-50%, -50%) scale(0.8);
        }
    }
    
    .notificacion-sistema {
        position: fixed;
        top: 20px;
        right: -300px;
        background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
        color: white;
        padding: 15px 25px;
        border-radius: 10px;
        display: flex;
        align-items: center;
        gap: 15px;
        z-index: 10000;
        transition: right 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        box-shadow: 0 5px 20px rgba(0,0,0,0.3);
        border-left: 5px solid var(--ff-gold);
    }
    
    .notificacion-sistema i {
        font-size: 1.2rem;
    }
    
    .reveal {
        animation: revealUp 0.8s ease forwards;
    }
    
    @keyframes revealUp {
        from {
            opacity: 0;
            transform: translateY(50px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
    
    .onda-clic {
        pointer-events: none;
    }
`;
document.head.appendChild(estilosEfectos);


  </script>
  <style>
    * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    /* Colores Free Fire */
    --ff-red: #FF0000;
    --ff-orange: #FF4500;
    --ff-gold: #FFD700;
    --ff-green: #00FF00;
    --ff-blue: #1E90FF;
    --ff-purple: #8A2BE2;
    
    /* Tema oscuro */
    --bg-dark: #0a0a1a;
    --bg-darker: #050510;
    --card-bg: rgba(20, 20, 40, 0.8);
    --card-border: rgba(255, 69, 0, 0.3);
    
    /* Sombras */
    --shadow-glow: 0 0 30px rgba(255, 69, 0, 0.4);
    --shadow-card: 0 10px 30px rgba(0, 0, 0, 0.5);
    --shadow-text: 2px 2px 4px rgba(0, 0, 0, 0.8);
    
    /* Transiciones */
    --transition-fast: 0.3s ease;
    --transition-medium: 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    --transition-slow: 0.8s ease;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: 'Montserrat', sans-serif;
    background: linear-gradient(135deg, var(--bg-darker), #1a1a2e, #16213e);
    color: white;
    min-height: 100vh;
    position: relative;
    overflow-x: hidden;
    background-attachment: fixed;
}

body::before {
    content: '';
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: 
        radial-gradient(circle at 20% 50%, rgba(255, 69, 0, 0.1) 0%, transparent 50%),
        radial-gradient(circle at 80% 20%, rgba(255, 215, 0, 0.1) 0%, transparent 50%),
        radial-gradient(circle at 40% 80%, rgba(30, 144, 255, 0.1) 0%, transparent 50%);
    z-index: -2;
}

/* Partículas de fondo */
#particles-js {
    position: fixed;
    width: 100%;
    height: 100%;
    z-index: -1;
}

/* Borde de neón */
.neon-border {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 0;
    border: 2px solid transparent;
    border-image: linear-gradient(45deg, var(--ff-red), var(--ff-orange), var(--ff-gold), var(--ff-green), var(--ff-blue)) 1;
    animation: neonGlow 3s ease-in-out infinite alternate;
}

@keyframes neonGlow {
    0% { opacity: 0.3; }
    100% { opacity: 0.7; }
}

/* Contenedor principal */
.main-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
    position: relative;
    z-index: 1;
}

/* HEADER PRINCIPAL */
.main-header {
    text-align: center;
    margin-bottom: 40px;
    animation: slideDown 1s ease;
}

.logo-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
    margin-bottom: 30px;
}

.logo {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 80px;
    height: 80px;
    background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
    border-radius: 50%;
    font-size: 2.5rem;
    color: white;
    position: relative;
    animation: logoPulse 2s infinite;
}

.logo::after {
    content: '';
    position: absolute;
    top: -5px;
    left: -5px;
    right: -5px;
    bottom: -5px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
    z-index: -1;
    filter: blur(10px);
    opacity: 0.5;
}

.logo-text {
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    font-size: 1.8rem;
    margin-left: 5px;
}

.titulo {
    text-align: center;
    margin-bottom: 10px;
}

.titulo-texto {
    display: block;
    font-family: 'Orbitron', sans-serif;
    font-size: 2.5rem;
    font-weight: 700;
    background: linear-gradient(45deg, var(--ff-gold), #FFFFFF, var(--ff-gold));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    letter-spacing: 2px;
    text-transform: uppercase;
    animation: textShine 3s ease-in-out infinite alternate;
}

.titulo-sub {
    display: block;
    font-family: 'Orbitron', sans-serif;
    font-size: 3.5rem;
    font-weight: 900;
    color: var(--ff-red);
    text-shadow: 
        0 0 10px var(--ff-red),
        0 0 20px var(--ff-orange),
        0 0 30px var(--ff-red);
    letter-spacing: 3px;
    margin-top: 5px;
    animation: fireText 2s ease-in-out infinite alternate;
}

.badge-ultra {
    display: inline-block;
    background: linear-gradient(45deg, var(--ff-red), var(--ff-orange));
    color: white;
    padding: 8px 20px;
    border-radius: 25px;
    font-family: 'Orbitron', sans-serif;
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 1px;
    text-transform: uppercase;
    animation: badgePulse 1.5s infinite;
    position: relative;
    overflow: hidden;
}

.badge-ultra::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(45deg, transparent 30%, rgba(255, 255, 255, 0.3) 50%, transparent 70%);
    animation: shine 2s infinite linear;
}

/* ESTADÍSTICAS */
.stats-container {
    margin: 40px 0;
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin-top: 30px;
}

.stat-card {
    background: var(--card-bg);
    border: 2px solid var(--card-border);
    border-radius: 15px;
    padding: 25px;
    display: flex;
    align-items: center;
    gap: 20px;
    transition: var(--transition-medium);
    backdrop-filter: blur(10px);
    position: relative;
    overflow: hidden;
}

.stat-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
    transition: var(--transition-slow);
}

.stat-card:hover::before {
    left: 100%;
}

.stat-card:hover {
    transform: translateY(-10px);
    box-shadow: var(--shadow-glow);
    border-color: var(--ff-gold);
}

.stat-icon {
    width: 60px;
    height: 60px;
    background: linear-gradient(135deg, var(--ff-orange), var(--ff-gold));
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.8rem;
    color: white;
    flex-shrink: 0;
}

.stat-content h3 {
    font-family: 'Orbitron', sans-serif;
    font-size: 0.9rem;
    color: var(--ff-gold);
    margin-bottom: 5px;
    letter-spacing: 1px;
    text-transform: uppercase;
}

.stat-number {
    font-family: 'Orbitron', sans-serif;
    font-size: 2.2rem;
    font-weight: 700;
    color: white;
    margin: 5px 0;
    text-shadow: var(--shadow-text);
}

.stat-trend {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 0.85rem;
    color: rgba(255, 255, 255, 0.8);
}

/* VIDEO SECTION */
.video-section {
    margin: 60px 0;
}

.section-header {
    text-align: center;
    margin-bottom: 40px;
}

.section-header h2 {
    font-family: 'Orbitron', sans-serif;
    font-size: 2rem;
    color: var(--ff-gold);
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 15px;
}

.section-header p {
    color: rgba(255, 255, 255, 0.8);
    font-size: 1.1rem;
}

.video-wrapper {
    position: relative;
    max-width: 800px;
    margin: 0 auto;
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 
        0 0 50px rgba(255, 69, 0, 0.3),
        0 20px 50px rgba(0, 0, 0, 0.5);
    border: 3px solid var(--ff-orange);
}

video {
    width: 100%;
    display: block;
    border-radius: 17px;
}

.video-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(45deg, rgba(0,0,0,0.3), transparent);
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: var(--transition-fast);
}

.video-wrapper:hover .video-overlay {
    opacity: 1;
}

.play-btn {
    width: 70px;
    height: 70px;
    background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2rem;
    color: white;
    cursor: pointer;
    transition: var(--transition-medium);
    transform: scale(0.9);
}

.video-wrapper:hover .play-btn {
    transform: scale(1);
}

.video-controls {
    display: flex;
    justify-content: center;
    gap: 15px;
    margin-top: 25px;
}

.btn-control {
    background: rgba(255, 69, 0, 0.2);
    border: 2px solid var(--ff-orange);
    color: white;
    padding: 12px 25px;
    border-radius: 25px;
    font-family: 'Orbitron', sans-serif;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition-fast);
    display: flex;
    align-items: center;
    gap: 10px;
}

.btn-control.active,
.btn-control:hover {
    background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
    transform: translateY(-3px);
    box-shadow: var(--shadow-glow);
}

/* CTA SECTION */
.cta-section {
    margin: 80px 0;
    text-align: center;
}

.cta-container {
    background: linear-gradient(135deg, rgba(255, 69, 0, 0.1), rgba(255, 215, 0, 0.1));
    border: 2px solid var(--ff-orange);
    border-radius: 25px;
    padding: 50px 30px;
    position: relative;
    overflow: hidden;
}

.cta-container::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(45deg, transparent 30%, rgba(255, 215, 0, 0.1) 50%, transparent 70%);
    animation: shine 3s infinite linear;
    z-index: 0;
}

.cta-container > * {
    position: relative;
    z-index: 1;
}

.cta-subtitle {
    font-size: 1.2rem;
    color: var(--ff-gold);
    margin: 15px 0 40px;
    font-weight: 600;
}

.cta-button-wrapper {
    max-width: 500px;
    margin: 0 auto;
}

.cta-button {
    display: block;
    text-decoration: none;
    background: linear-gradient(135deg, #25D366, #128C7E);
    border-radius: 20px;
    padding: 5px;
    position: relative;
    overflow: hidden;
    transition: var(--transition-medium);
    margin-bottom: 30px;
}

.cta-button:hover {
    transform: translateY(-10px) scale(1.05);
    box-shadow: 
        0 20px 40px rgba(37, 211, 102, 0.4),
        0 0 30px rgba(37, 211, 102, 0.6);
}

.cta-button::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(45deg, transparent 30%, rgba(255, 255, 255, 0.3) 50%, transparent 70%);
    animation: shine 2s infinite linear;
}

.button-content {
    background: rgba(0, 0, 0, 0.9);
    border-radius: 15px;
    padding: 25px 30px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    position: relative;
    z-index: 1;
}

.button-icon {
    width: 60px;
    height: 60px;
    background: #25D366;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2.5rem;
    color: white;
    flex-shrink: 0;
    animation: iconPulse 2s infinite;
}

.button-text {
    flex-grow: 1;
    text-align: left;
}

.button-main {
    display: block;
    font-family: 'Orbitron', sans-serif;
    font-size: 1.5rem;
    font-weight: 700;
    color: white;
    margin-bottom: 5px;
}

.button-sub {
    display: block;
    font-size: 0.9rem;
    color: #25D366;
    font-weight: 600;
}

.button-arrow {
    width: 50px;
    height: 50px;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    color: white;
    transition: var(--transition-fast);
}

.cta-button:hover .button-arrow {
    background: #25D366;
    transform: translateX(5px);
}

.button-particles {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 0;
}

.cta-stats {
    display: flex;
    justify-content: center;
    gap: 40px;
    flex-wrap: wrap;
}

.cta-stats .stat {
    display: flex;
    align-items: center;
    gap: 10px;
    color: rgba(255, 255, 255, 0.9);
    font-size: 0.95rem;
}

.cta-stats .stat i {
    color: var(--ff-gold);
    font-size: 1.2rem;
}

/* FEATURES SECTION */
.features-section {
    margin: 80px 0;
}

.features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 30px;
    margin-top: 40px;
}

.feature-card {
    background: var(--card-bg);
    border: 2px solid var(--card-border);
    border-radius: 20px;
    padding: 30px;
    text-align: center;
    transition: var(--transition-medium);
    backdrop-filter: blur(10px);
    position: relative;
    overflow: hidden;
}

.feature-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 5px;
    background: linear-gradient(90deg, var(--ff-red), var(--ff-orange), var(--ff-gold));
}

.feature-card:hover {
    transform: translateY(-15px);
    box-shadow: var(--shadow-glow);
    border-color: var(--ff-gold);
}

.feature-icon {
    width: 80px;
    height: 80px;
    background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2.5rem;
    color: white;
    margin: 0 auto 25px;
    position: relative;
}

.feature-icon::after {
    content: '';
    position: absolute;
    top: -5px;
    left: -5px;
    right: -5px;
    bottom: -5px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
    z-index: -1;
    filter: blur(10px);
    opacity: 0.5;
}

.feature-card h3 {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.3rem;
    color: var(--ff-gold);
    margin-bottom: 15px;
}

.feature-card p {
    color: rgba(255, 255, 255, 0.8);
    line-height: 1.6;
    margin-bottom: 20px;
}

.feature-badge {
    display: inline-block;
    background: linear-gradient(45deg, var(--ff-blue), var(--ff-purple));
    color: white;
    padding: 8px 20px;
    border-radius: 20px;
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.5px;
}

/* TESTIMONIOS */
.testimonials-section {
    margin: 80px 0;
}

.testimonials-slider {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    margin-top: 40px;
}

.testimonial-card {
    background: var(--card-bg);
    border: 2px solid var(--card-border);
    border-radius: 20px;
    padding: 30px;
    transition: var(--transition-medium);
    backdrop-filter: blur(10px);
}

.testimonial-card:hover {
    transform: translateY(-10px);
    box-shadow: var(--shadow-glow);
    border-color: var(--ff-gold);
}

.testimonial-header {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 20px;
}

.testimonial-avatar {
    width: 70px;
    height: 70px;
    border-radius: 50%;
    border: 3px solid var(--ff-orange);
    background: linear-gradient(135deg, var(--ff-red), var(--ff-orange));
    padding: 3px;
}

.testimonial-info h4 {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.1rem;
    color: var(--ff-gold);
    margin-bottom: 5px;
}

.rating {
    color: var(--ff-gold);
    font-size: 0.9rem;
}

.testimonial-text {
    color: rgba(255, 255, 255, 0.9);
    line-height: 1.6;
    font-style: italic;
    margin-bottom: 20px;
    padding-left: 20px;
    border-left: 3px solid var(--ff-orange);
}

.testimonial-rank {
    display: inline-block;
    background: linear-gradient(45deg, var(--ff-blue), var(--ff-purple));
    color: white;
    padding: 8px 20px;
    border-radius: 20px;
    font-size: 0.85rem;
    font-weight: 600;
}

/* FAQ */
.faq-section {
    margin: 80px 0;
}

.faq-container {
    max-width: 800px;
    margin: 40px auto 0;
}

.faq-item {
    margin-bottom: 15px;
    border: 2px solid var(--card-border);
    border-radius: 15px;
    overflow: hidden;
    background: var(--card-bg);
    backdrop-filter: blur(10px);
}

.faq-question {
    width: 100%;
    background: transparent;
    border: none;
    color: white;
    padding: 25px 30px;
    text-align: left;
    font-family: 'Montserrat', sans-serif;
    font-size: 1.1rem;
    font-weight: 600;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: var(--transition-fast);
}

.faq-question:hover {
    background: rgba(255, 69, 0, 0.1);
}

.faq-question i {
    color: var(--ff-gold);
    transition: var(--transition-fast);
}

.faq-answer {
    max-height: 0;
    overflow: hidden;
    transition: var(--transition-medium);
    padding: 0 30px;
}

.faq-answer.active {
    max-height: 200px;
    padding: 0 30px 25px;
}

.faq-answer p {
    color: rgba(255, 255, 255, 0.9);
    line-height: 1.6;
}

/* FOOTER */
.main-footer {
    margin-top: 80px;
    padding-top: 60px;
    border-top: 2px solid var(--card-border);
    background: linear-gradient(to bottom, transparent, rgba(20, 20, 40, 0.5));
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 40px;
    margin-bottom: 40px;
}

.footer-logo .logo {
    display: flex;
    align-items: center;
    gap: 15px;
    font-family: 'Orbitron', sans-serif;
    font-size: 1.5rem;
    color: var(--ff-gold);
    margin-bottom: 15px;
}

.footer-tagline {
    color: rgba(255, 255, 255, 0.8);
    font-size: 1.1rem;
}

.link-group h4 {
    font-family: 'Orbitron', sans-serif;
    color: var(--ff-gold);
    margin-bottom: 20px;
    font-size: 1.1rem;
}

.link-group a {
    display: flex;
    align-items: center;
    gap: 10px;
    color: rgba(255, 255, 255, 0.8);
    text-decoration: none;
    margin-bottom: 12px;
    transition: var(--transition-fast);
}

.link-group a:hover {
    color: var(--ff-gold);
    transform: translateX(5px);
}

.link-group a i {
    width: 20px;
    text-align: center;
}

.footer-bottom {
    text-align: center;
    padding: 30px 0;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    color: rgba(255, 255, 255, 0.6);
    font-size: 0.9rem;
}

.footer-stats {
    display: flex;
    justify-content: center;
    gap: 30px;
    margin-top: 15px;
    flex-wrap: wrap;
}

.footer-stats span {
    display: flex;
    align-items: center;
    gap: 8px;
}

/* ANIMACIONES */
@keyframes slideDown {
    from {
        opacity: 0;
        transform: translateY(-30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes logoPulse {
    0%, 100% {
        transform: scale(1);
        box-shadow: 0 0 20px rgba(255, 69, 0, 0.5);
    }
    50% {
        transform: scale(1.05);
        box-shadow: 0 0 30px rgba(255, 69, 0, 0.8);
    }
}

@keyframes textShine {
    0% {
        background-position: 0% 50%;
    }
    100% {
        background-position: 100% 50%;
    }
}

@keyframes fireText {
    0% {
        text-shadow: 
            0 0 10px var(--ff-red),
            0 0 20px var(--ff-orange),
            0 0 30px var(--ff-red);
    }
    100% {
        text-shadow: 
            0 0 15px var(--ff-red),
            0 0 30px var(--ff-orange),
            0 0 45px var(--ff-red);
    }
}

@keyframes badgePulse {
    0%, 100% {
        box-shadow: 0 0 10px rgba(255, 69, 0, 0.5);
    }
    50% {
        box-shadow: 0 0 20px rgba(255, 69, 0, 0.8);
    }
}

@keyframes shine {
    0% {
        transform: translateX(-100%) rotate(45deg);
    }
    100% {
        transform: translateX(100%) rotate(45deg);
    }
}

@keyframes iconPulse {
    0%, 100% {
        transform: scale(1);
        box-shadow: 0 0 20px rgba(37, 211, 102, 0.5);
    }
    50% {
        transform: scale(1.1);
        box-shadow: 0 0 30px rgba(37, 211, 102, 0.8);
    }
}

/* RESPONSIVE */
@media (max-width: 768px) {
    .main-container {
        padding: 15px;
    }
    
    .titulo-texto {
        font-size: 1.8rem;
    }
    
    .titulo-sub {
        font-size: 2.5rem;
    }
    
    .section-header h2 {
        font-size: 1.5rem;
        flex-direction: column;
        gap: 10px;
    }
    
    .button-content {
        flex-direction: column;
        text-align: center;
        gap: 15px;
    }
    
    .button-text {
        text-align: center;
    }
    
    .features-grid,
    .testimonials-slider {
        grid-template-columns: 1fr;
    }
    
    .footer-content {
        grid-template-columns: 1fr;
        text-align: center;
    }
    
    .link-group a {
        justify-content: center;
    }
}

@media (max-width: 480px) {
    .titulo-texto {
        font-size: 1.5rem;
    }
    
    .titulo-sub {
        font-size: 2rem;
    }
    
    .stat-card {
        flex-direction: column;
        text-align: center;
        gap: 15px;
    }
    
    .cta-stats {
        flex-direction: column;
        gap: 20px;
    }
    
    .video-controls {
        flex-direction: column;
        align-items: center;
    }
    
    .btn-control {
        width: 100%;
        max-width: 250px;
        justify-content: center;
    }
}

/* Efectos adicionales para el contador */
#contador-jugadores {
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    background: linear-gradient(45deg, var(--ff-gold), #FFFFFF, var(--ff-gold));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    animation: textShine 2s ease-in-out infinite;
    position: relative;
    display: inline-block;
}

#contador-jugadores::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--ff-gold), transparent);
    animation: linePulse 2s infinite;
}

@keyframes linePulse {
    0%, 100% {
        opacity: 0.5;
        transform: scaleX(0.8);
    }
    50% {
        opacity: 1;
        transform: scaleX(1);
    }
}

/* Scrollbar personalizada */
::-webkit-scrollbar {
    width: 10px;
}

::-webkit-scrollbar-track {
    background: rgba(20, 20, 40, 0.5);
}

::-webkit-scrollbar-thumb {
    background: linear-gradient(var(--ff-red), var(--ff-orange));
    border-radius: 5px;
}

::-webkit-scrollbar-thumb:hover {
    background: linear-gradient(var(--ff-orange), var(--ff-gold));
}

/* Selección de texto */
::selection {
    background: var(--ff-orange);
    color: white;
}

  </style>
<body>
    <div id="particles-js"></div>
    
    <!-- Efecto de neón alrededor -->
    <div class="neon-border"></div>
    
    <!-- Contenedor principal -->
    <div class="main-container">
        <!-- Logo y título -->
        <header class="main-header">
            <div class="logo-container">
                <div class="logo">
                    <i class="fas fa-fire"></i>
                    <span class="logo-text">FF</span>
                </div>
                <h1 class="titulo">
                    <span class="titulo-texto">GRUPO WHATSAPP</span>
                    <span class="titulo-sub">FREE FIRE</span>
                </h1>
                <div class="badge-ultra">ULTRA ACTIVO</div>
            </div>
        </header>

        <!-- Estadísticas en tiempo real -->
        <section class="stats-container">
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="stat-content">
                        <h3>JUGADORES</h3>
                        <div class="stat-number" id="contador-jugadores">Cargando...</div>
                        <div class="stat-trend">
                            <i class="fas fa-chart-line"></i>
                            <span>+12 hoy</span>
                        </div>
                    </div>
                </div>
                
                <div class="stat-card">
                    <div class="stat-icon">
                        <i class="fas fa-trophy"></i>
                    </div>
                    <div class="stat-content">
                        <h3>TORNEOS</h3>
                        <div class="stat-number">47</div>
                        <div class="stat-trend">
                            <i class="fas fa-calendar"></i>
                            <span>Próximo: Hoy 20:00</span>
                        </div>
                    </div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon">
                        <i class="fas fa-gift"></i>
                    </div>
                    <div class="stat-content">
                        <h3>PREMIOS</h3>
                        <div class="stat-number">1,250+</div>
                        <div class="stat-trend">
                            <i class="fas fa-diamond"></i>
                            <span>Diamantes & Skin</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Video destacado -->
        <section class="video-section">
            <div class="section-header">
                <h2><i class="fas fa-play-circle"></i> MOMENTOS ÉPICOS</h2>
                <p>Descubre las mejores jugadas de nuestra comunidad</p>
            </div>
            <div class="video-container">
                <div class="video-wrapper">
                    <video controls loop autoplay muted playsinline>
                        <source src="vid/Brazilian_Freestyle_🇧🇷🔥(480p).mp4" type="video/mp4">
                        Tu navegador no soporta videos HTML5
                    </video>
                    <div class="video-overlay">
                        <div class="play-btn">
                            <i class="fas fa-play"></i>
                        </div>
                    </div>
                </div>
                <div class="video-controls">
                    <button class="btn-control active"><i class="fas fa-fire"></i> Épico</button>
                    <button class="btn-control"><i class="fas fa-trophy"></i> Torneos</button>
                    <button class="btn-control"><i class="fas fa-star"></i> Destacados</button>
                </div>
            </div>
        </section>

        <!-- Botón principal -->
        <section class="cta-section">
            <div class="cta-container">
                <h2><i class="fab fa-whatsapp"></i> ¡ÚNETE AHORA!</h2>
                <p class="cta-subtitle">Conecta con +500 jugadores activos diariamente</p>
                
                <div class="cta-button-wrapper">
                    <a href="https://chat.whatsapp.com/LWIJKYpo686V32sqmNAAd" 
                       target="_blank" 
                       rel="noopener noreferrer" 
                       class="cta-button">
                        <div class="button-content">
                            <div class="button-icon">
                                <i class="fab fa-whatsapp"></i>
                            </div>
                            <div class="button-text">
                                <span class="button-main">ENTRAR AL GRUPO</span>
                                <span class="button-sub">¡Click aquí para unirte!</span>
                            </div>
                            <div class="button-arrow">
                                <i class="fas fa-arrow-right"></i>
                            </div>
                        </div>
                        <div class="button-particles"></div>
                    </a>
                    
                    <div class="cta-stats">
                        <div class="stat">
                            <i class="fas fa-bolt"></i>
                            <span>Último ingreso: <strong>Hace 2 min</strong></span>
                        </div>
                        <div class="stat">
                            <i class="fas fa-shield-alt"></i>
                            <span>Grupo verificado ✓</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Características -->
        <section class="features-section">
            <div class="section-header">
                <h2><i class="fas fa-star"></i> ¿POR QUÉ UNIRTE?</h2>
                <p>Todo lo que ofrece nuestra comunidad</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-gamepad"></i>
                    </div>
                    <h3>Juega en Equipo</h3>
                    <p>Encuentra compañeros para ranked, casual y torneos. Nunca juegues solo otra vez.</p>
                    <div class="feature-badge">+300 equipos</div>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-coins"></i>
                    </div>
                    <h3>Sorteos Diarios</h3>
                    <p>Participa en sorteos de diamantes, skins exclusivas y pases de elite totalmente gratis.</p>
                    <div class="feature-badge">1,250+ premios</div>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3>Mejora tu Skill</h3>
                    <p>Aprende estrategias, tácticas y tips de jugadores profesionales de Free Fire.</p>
                    <div class="feature-badge">Guías expertas</div>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-comments"></i>
                    </div>
                    <h3>Comunidad Activa</h3>
                    <p>Chat activo 24/7 con jugadores de toda Latinoamérica. Siempre hay alguien en línea.</p>
                    <div class="feature-badge">24/7 online</div>
                </div>
            </div>
        </section>

        <!-- Testimonios -->
        <section class="testimonials-section">
            <div class="section-header">
                <h2><i class="fas fa-comment-dots"></i> OPINIONES DE JUGADORES</h2>
                <p>Lo que dicen nuestros miembros</p>
            </div>
            
            <div class="testimonials-slider">
                <div class="testimonial-card">
                    <div class="testimonial-header">
                        <img src="https://api.dicebear.com/7.x/avataaars/svg?seed=FreeFire1" alt="Jugador 1" class="testimonial-avatar">
                        <div class="testimonial-info">
                            <h4>Carlos "ProShot"</h4>
                            <div class="rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                            </div>
                        </div>
                    </div>
                    <p class="testimonial-text">"Gracias al grupo encontré mi equipo para torneos. ¡Ganamos 3 campeonatos este mes y muchos diamantes!"</p>
                    <div class="testimonial-rank">Rango: Heroico</div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-header">
                        <img src="https://api.dicebear.com/7.x/avataaars/svg?seed=FreeFire2" alt="Jugador 2" class="testimonial-avatar">
                        <div class="testimonial-info">
                            <h4>Ana "DiamondQueen"</h4>
                            <div class="rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star-half-alt"></i>
                            </div>
                        </div>
                    </div>
                    <p class="testimonial-text">"Me gané 500 diamantes en un sorteo y aprendí estrategias que me hicieron subir de platino a diamante."</p>
                    <div class="testimonial-rank">Rango: Diamante III</div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-header">
                        <img src="https://api.dicebear.com/7.x/avataaars/svg?seed=FreeFire3" alt="Jugador 3" class="testimonial-avatar">
                        <div class="testimonial-info">
                            <h4>Miguel "SniperPro"</h4>
                            <div class="rating">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                            </div>
                        </div>
                    </div>
                    <p class="testimonial-text">"La mejor comunidad de Free Fire. Siempre hay alguien para jugar y el ambiente es increíble."</p>
                    <div class="testimonial-rank">Rango: Gran Maestro</div>
                </div>
            </div>
        </section>

        <!-- FAQ -->
        <section class="faq-section">
            <div class="section-header">
                <h2><i class="fas fa-question-circle"></i> PREGUNTAS FRECUENTES</h2>
                <p>Todo lo que necesitas saber</p>
            </div>
            
            <div class="faq-container">
                <div class="faq-item">
                    <button class="faq-question">
                        <span>¿El grupo es gratuito?</span>
                        <i class="fas fa-chevron-down"></i>
                    </button>
                    <div class="faq-answer">
                        <p>Sí, completamente gratuito. No cobramos por ingresar ni por participar en torneos y sorteos.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <button class="faq-question">
                        <span>¿Necesito ser buen jugador para entrar?</span>
                        <i class="fas fa-chevron-down"></i>
                    </button>
                    <div class="faq-answer">
                        <p>¡No! Aceptamos jugadores de todos los niveles, desde principiantes hasta profesionales.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <button class="faq-question">
                        <span>¿Con qué frecuencia hay torneos?</span>
                        <i class="fas fa-chevron-down"></i>
                    </button>
                    <div class="faq-answer">
                        <p>Organizamos torneos semanales y eventos especiales cada mes con grandes premios.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <button class="faq-question">
                        <span>¿Hay reglas en el grupo?</span>
                        <i class="fas fa-chevron-down"></i>
                    </button>
                    <div class="faq-answer">
                        <p>Sí, mantenemos un ambiente respetuoso. Prohibimos spam, insultos y comportamientos tóxicos.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="main-footer">
            <div class="footer-content">
                <div class="footer-logo">
                    <div class="logo">
                        <i class="fas fa-fire"></i>
                        <span>Free Fire WhatsApp</span>
                    </div>
                    <p class="footer-tagline">La comunidad más activa de Free Fire</p>
                </div>
                
                <div class="footer-links">
                    <div class="link-group">
                        <h4>Comunidad</h4>
                        <a href="#"><i class="fas fa-users"></i> Jugadores Online</a>
                        <a href="#"><i class="fas fa-trophy"></i> Torneos</a>
                        <a href="#"><i class="fas fa-gift"></i> Sorteos</a>
                    </div>
                    
                    <div class="link-group">
                        <h4>Recursos</h4>
                        <a href="#"><i class="fas fa-book"></i> Guías</a>
                        <a href="#"><i class="fas fa-video"></i> Gameplays</a>
                        <a href="#"><i class="fas fa-chart-bar"></i> Estadísticas</a>
                    </div>
                    
                    <div class="link-group">
                        <h4>Conéctate</h4>
                        <a href="#"><i class="fab fa-discord"></i> Discord</a>
                        <a href="#"><i class="fab fa-youtube"></i> YouTube</a>
                        <a href="#"><i class="fab fa-tiktok"></i> TikTok</a>
                    </div>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>© 2024 Free Fire WhatsApp Community. No afiliado oficialmente con Garena.</p>
                <div class="footer-stats">
                    <span><i class="fas fa-eye"></i> <span id="visitas-totales">1,250</span> visitas hoy</span>
                    <span><i class="fas fa-user-clock"></i> Actualizado hace 2 min</span>
                </div>
            </div>
        </footer>
    </div>

    <!-- Scripts -->
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script src="java.js"></script>
    <script src="efectos.js"></script>
    
    <!-- Script de inicialización -->
    <script>
        // Inicializar efectos avanzados
        document.addEventListener('DOMContentLoaded', function() {
            console.log('🎮 Free Fire Community - Inicializando...');
            
            // Inicializar partículas de fondo
            if (typeof particlesJS !== 'undefined') {
                particlesJS('particles-js', {
                    particles: {
                        number: { value: 80, density: { enable: true, value_area: 800 } },
                        color: { value: ["#FF0000", "#FFD700", "#00FF00"] },
                        shape: { type: "circle" },
                        opacity: { value: 0.5, random: true },
                        size: { value: 3, random: true },
                        line_linked: {
                            enable: true,
                            distance: 150,
                            color: "#FFD700",
                            opacity: 0.2,
                            width: 1
                        },
                        move: {
                            enable: true,
                            speed: 2,
                            direction: "none",
                            random: true,
                            straight: false,
                            out_mode: "out",
                            bounce: false
                        }
                    },
                    interactivity: {
                        detect_on: "canvas",
                        events: {
                            onhover: { enable: true, mode: "repulse" },
                            onclick: { enable: true, mode: "push" }
                        }
                    }
                });
            }
            
            // FAQ interactivo
            const faqQuestions = document.querySelectorAll('.faq-question');
            faqQuestions.forEach(question => {
                question.addEventListener('click', () => {
                    const answer = question.nextElementSibling;
                    const icon = question.querySelector('i');
                    
                    answer.classList.toggle('active');
                    icon.classList.toggle('fa-chevron-down');
                    icon.classList.toggle('fa-chevron-up');
                });
            });
            
            // Simular estadísticas dinámicas
            setInterval(() => {
                const contador = document.getElementById('contador-jugadores');
                if (contador && window.contadorFF) {
                    contador.textContent = window.contadorFF.contadorActual.toLocaleString('es-ES');
                }
                
                // Actualizar visitas
                const visitas = document.getElementById('visitas-totales');
                if (visitas) {
                    const actual = parseInt(visitas.textContent.replace(/,/g, ''));
                    visitas.textContent = (actual + Math.floor(Math.random() * 3)).toLocaleString('es-ES');
                }
            }, 30000);
            
            console.log('✅ Página completamente cargada y optimizada');
        });
        
        // Efecto de confeti al hacer clic en el botón principal
        document.querySelector('.cta-button').addEventListener('click', function(e) {
            if (!this.href.includes('whatsapp')) return;
            
            // Crear confeti
            for(let i = 0; i < 50; i++) {
                setTimeout(() => crearConfeti(e.clientX, e.clientY), i * 20);
            }
            
            // Sonido de confirmación
            try {
                const audioContext = new (window.AudioContext || window.webkitAudioContext)();
                const oscillator = audioContext.createOscillator();
                const gainNode = audioContext.createGain();
                
                oscillator.connect(gainNode);
                gainNode.connect(audioContext.destination);
                
                oscillator.frequency.setValueAtTime(523.25, audioContext.currentTime);
                oscillator.frequency.setValueAtTime(659.25, audioContext.currentTime + 0.1);
                oscillator.frequency.setValueAtTime(783.99, audioContext.currentTime + 0.2);
                
                gainNode.gain.setValueAtTime(0.1, audioContext.currentTime);
                gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.5);
                
                oscillator.start();
                oscillator.stop(audioContext.currentTime + 0.5);
            } catch (error) {
                console.log('🔇 Audio no disponible');
            }
        });
        
        function crearConfeti(x, y) {
            const confeti = document.createElement('div');
            confeti.style.cssText = `
                position: fixed;
                width: 10px;
                height: 10px;
                background: ${['#FF0000', '#FFD700', '#00FF00', '#1E90FF'][Math.floor(Math.random() * 4)]};
                border-radius: ${Math.random() > 0.5 ? '50%' : '2px'};
                pointer-events: none;
                z-index: 10000;
                top: ${y}px;
                left: ${x}px;
                transform: rotate(${Math.random() * 360}deg);
            `;
            
            document.body.appendChild(confeti);
            
            // Animación
            const angulo = Math.random() * Math.PI * 2;
            const velocidad = 2 + Math.random() * 4;
            const dx = Math.cos(angulo) * velocidad;
            const dy = Math.sin(angulo) * velocidad;
            const rotacion = (Math.random() - 0.5) * 10;
            
            let posX = x;
            let posY = y;
            let rot = 0;
            let gravedad = 0.1;
            let velocidadY = -Math.random() * 5;
            let opacidad = 1;
            
            function animar() {
                posX += dx;
                posY += velocidadY;
                rot += rotacion;
                velocidadY += gravedad;
                opacidad -= 0.01;
                
                confeti.style.left = posX + 'px';
                confeti.style.top = posY + 'px';
                confeti.style.transform = `rotate(${rot}deg)`;
                confeti.style.opacity = opacidad;
                
                if (opacidad > 0) {
                    requestAnimationFrame(animar);
                } else {
                    confeti.remove();
                }
            }
            
            animar();
        }
    </script>
</body>
</html>
