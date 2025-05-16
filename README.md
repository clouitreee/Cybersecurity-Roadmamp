<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hoja de Ruta Autodidacta en Ciberseguridad</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f2f5;
            color: #333;
        }
        .slide-container {
            max-width: 900px;
            margin: 20px auto;
            padding: 0;
            background-color: #fff;
            box-shadow: 0 0 15px rgba(0,0,0,0.1);
            border-radius: 8px;
            overflow: hidden;
        }
        .slide {
            padding: 30px 40px;
            border-bottom: 1px solid #e0e0e0;
            min-height: calc(100vh - 120px); /* Aproximar altura de diapositiva */
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        .slide:last-child {
            border-bottom: none;
        }

        /* Estilos generales para títulos */
        h1, h2, h3 {
            color: #1a237e; /* Azul oscuro principal por defecto */
        }
        h1.slide-title-main { /* Título de la primera diapositiva */
            font-size: 2.8em;
            color: #0d47a1; 
            text-align: center;
            margin-bottom: 5px;
            border-bottom: 3px solid #ff6f00; /* Naranja acento más grueso */
            padding-bottom: 15px;
        }
        .slide-subtitle-main {
            font-size: 1.2em;
            color: #555;
            text-align: center;
            margin-bottom: 30px;
        }
        h2 { /* Títulos de cada diapositiva */
            font-size: 2.2em; /* Ligeramente más grande */
            margin-top: 20px;
            margin-bottom: 20px; /* Más espacio */
            color: #283593; 
            display: flex; /* Para alinear icono y texto */
            align-items: center; /* Para alinear icono y texto */
        }
        h3 { /* Subtítulos dentro de las diapositivas */
            font-size: 1.6em; /* Ligeramente más grande */
            margin-top: 18px;
            margin-bottom: 12px;
            color: #3949ab;
        }
        p, ul, li {
            font-size: 1.1em;
            line-height: 1.7;
            margin-bottom: 10px;
        }
        ul {
            list-style-type: none; /* Quitar bullets por defecto para control custom */
            padding-left: 0;
        }
        ul li {
            padding-left: 25px; /* Espacio para bullet custom o icono */
            position: relative; /* Para posicionar bullet custom */
            margin-bottom: 8px;
        }
        ul li::before { /* Bullet custom */
            content: '➤'; /* Puedes usar '•', '➤', etc. o un SVG */
            position: absolute;
            left: 0;
            color: #ff6f00; /* Color de acento para bullets */
            font-size: 1.2em;
        }

        strong {
            color: #ef6c00; /* Naranja acento más intenso para destacar */
            font-weight: bold;
        }
        a {
            color: #1e88e5; 
            text-decoration: none;
            font-weight: 500; /* Enlaces un poco más notorios */
        }
        a:hover {
            text-decoration: underline;
            color: #005cb2;
        }
        .project {
            background-color: #e3f2fd; 
            padding: 20px; /* Más padding */
            border-radius: 8px; /* Más redondeado */
            margin-top: 20px;
            border: 1px solid #bbdefb;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }
        .project strong {
            color: #0d47a1;
        }

        /* Placeholder para iconos y logos */
        .icon-placeholder, .logo-placeholder {
            display: inline-flex; /* Para alinear con texto verticalmente */
            align-items: center;
            padding: 6px 12px;
            border: 1px dashed #90a4ae; /* Gris azulado */
            background-color: #eceff1; /* Gris muy claro */
            color: #546e7a; /* Gris azulado oscuro */
            font-style: italic;
            font-size: 0.95em;
            margin-right: 10px;
            border-radius: 4px;
            vertical-align: middle; /* Mejor alineación con texto */
        }
        h2 .icon-placeholder { /* Iconos en títulos h2 */
            font-size: 0.7em; /* Más pequeños en relación al h2 */
            padding: 8px 10px;
        }

        /* Temas específicos por diapositiva */
        /* Slide 1: Título - Fondo abstracto (simulado con color) */
        .slide-theme-title {
            background-color: #f4f6f8; /* Un gris muy claro como base para "abstracto" */
            /* Para una imagen de fondo real: background-image: url('path/to/tech-abstract.jpg'); background-size: cover; */
        }
        .slide-theme-title h1.slide-title-main { color: #0d47a1; border-bottom-color: #ff8f00; }
        .slide-theme-title .slide-subtitle-main strong { color: #ff8f00; }

        /* Slide 2: Introducción */
        .slide-theme-intro h2 { color: #1565c0; } /* Azul más brillante para introducción */
        .slide-theme-intro strong { color: #f57c00; }

        /* Slide 3: Tool Stack - Fondo con textura sutil (simulado con color) */
        .slide-theme-tools {
            background-color: #e8f5e9; /* Verde muy pálido como "textura sutil" */
        }
        .slide-theme-tools h3 { color: #2e7d32; } /* Títulos de categoría en verde oscuro */

        /* Slide 4: Fundamentos */
        .slide-theme-foundations h2 { color: #303f9f; } /* Azul índigo más oscuro, profesional */
        .slide-theme-foundations strong { color: #c62828; } /* Rojo oscuro para puntos clave */

        /* Slide 5: Linux y Scripting */
        .slide-theme-linux h2 { color: #388e3c; } /* Verde vibrante para Linux */
        .slide-theme-linux h3 { color: #4caf50; }
        .slide-theme-linux strong { color: #1b5e20; } /* Verde muy oscuro para acento */

        /* Slide 6: Seguridad Ofensiva */
        .slide-theme-offensive { background-color: #37474f; color: #eceff1; } /* Fondo oscuro, texto claro */
        .slide-theme-offensive h2 { color: #d32f2f; } /* Rojo para ofensiva */
        .slide-theme-offensive h3 { color: #e57373; } /* Rojo claro */
        .slide-theme-offensive strong { color: #ffb300; } /* Ámbar para acento en tema oscuro */
        .slide-theme-offensive a { color: #80cbc4; } /* Teal claro para enlaces */
        .slide-theme-offensive a:hover { color: #4db6ac; }
        .slide-theme-offensive ul li::before { color: #d32f2f; }
        .slide-theme-offensive .project { background-color: #455a64; border-color: #546e7a; color: #eceff1;}
        .slide-theme-offensive .project strong { color: #ffb300;}


        /* Slide 7: Seguridad Defensiva */
        .slide-theme-defensive h2 { color: #0277bd; } /* Azul cian para defensa */
        .slide-theme-defensive strong { color: #004c8c; }
        .slide-theme-defensive ul li::before { color: #0277bd; }
        .slide-theme-defensive .project { background-color: #e1f5fe; border-color: #b3e5fc;}


        /* Slide 8: Especializaciones */
        .slide-theme-specializations h2 { color: #6a1b9a; } /* Púrpura para especializaciones */
        .slide-theme-specializations strong { color: #4a148c; }
        .slide-theme-specializations ul li::before { color: #6a1b9a; }


        /* Slide 9: Investigación */
        .slide-theme-research h2 { color: #00695c; } /* Teal oscuro para investigación */
        .slide-theme-research strong { color: #004d40; }


        /* Slide 10: Soft Skills */
        .slide-theme-softskills { background-color: #fffde7; } /* Amarillo pálido, cálido */
        .slide-theme-softskills h2 { color: #fbc02d; } /* Amarillo/Dorado */
        .slide-theme-softskills strong { color: #f57f17; } /* Naranja oscuro */


        /* Slide 11: Preparación Empleo */
        .slide-theme-jobs h2 { color: #558b2f; } /* Verde oliva, profesional y motivador */
        .slide-theme-jobs strong { color: #33691e; }

        /* Slide 12: Cronograma - Estilo más visual para la lista */
        .slide-theme-timeline ul li {
            background-color: #f1f8e9;
            padding: 10px 15px 10px 35px; /* Más padding interno */
            border-left: 5px solid; /* Barra de color */
            margin-bottom: 12px;
            border-radius: 0 4px 4px 0;
        }
        .slide-theme-timeline ul li:nth-child(odd) { border-left-color: #7cb342; } /* Alternar colores */
        .slide-theme-timeline ul li:nth-child(even) { border-left-color: #c0ca33; }
        .slide-theme-timeline ul li::before { content: counter(list-item) '. '; counter-increment: list-item; left: 10px; font-weight: bold; color: #333; }


        /* Slide 13: Conclusión */
        .slide-theme-conclusion h2 { color: #ad1457; } /* Rosa oscuro/Magenta para conclusión */
        .slide-theme-conclusion strong { color: #880e4f; }


        /* Slide 14: Recursos Adicionales */
        .slide-theme-resources h3 { color: #4e342e; } /* Marrón oscuro para títulos de sección */


        /* Estilos específicos para impresión a PDF */
        @media print {
            body {
                background-color: #fff;
                font-size: 11pt; /* Ajustar tamaño para PDF */
            }
            .slide-container {
                box-shadow: none;
                margin: 0;
                max-width: 100%;
                border-radius: 0;
            }
            .slide {
                padding: 18mm 12mm; /* Márgenes A4 ajustados */
                border-bottom: none; 
                page-break-after: always; 
                min-height: 0; 
            }
            .slide:last-child {
                page-break-after: avoid;
            }
            h1, h2, h3, p, ul, li, a, strong { /* Forzar negro para mejor impresión, excepto si se quiere mantener un color específico */
                color: #000 !important; 
            }
            strong { font-weight: bold !important; }
            a { text-decoration: underline !important; }
            .icon-placeholder, .logo-placeholder { border-color: #000 !important; background-color: #eee !important; color: #000 !important;}
            ul li::before { color: #000 !important; } /* Bullets a negro */
            .slide-theme-offensive { background-color: #fff !important; color: #000 !important; } /* Resetear fondos oscuros para impresión */
            .slide-theme-offensive a { color: #000 !important; }
            .slide-theme-offensive .project { background-color: #f0f0f0 !important; border-color: #ccc !important; color: #000 !important;}
            .slide-theme-timeline ul li { background-color: #f9f9f9 !important; }
            .slide-theme-timeline ul li:nth-child(odd) { border-left-color: #666 !important; }
            .slide-theme-timeline ul li:nth-child(even) { border-left-color: #999 !important; }

        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
</head>
<body>
    <div class="slide-container">
        <div class="slide slide-theme-title">
            <h1 class="slide-title-main">Hoja de Ruta Autodidacta en Ciberseguridad</h1>
            <p class="slide-subtitle-main"><strong>De Principiante a Profesional Preparado • 0€ (o muy bajo coste) • Aproximadamente 12-18 Meses (a tiempo parcial)</strong></p>
        </div>

        <div class="slide slide-theme-intro">
            <h2><span class="icon-placeholder">[ICONO: Camino/Mapa]</span>Diapositiva 2: Introducción – Tu Viaje en Ciberseguridad</h2>
            <p>¡Bienvenido/a a tu aventura en el mundo de la ciberseguridad! Esta hoja de ruta está diseñada para guiarte en tu aprendizaje autodidacta, aprovechando al máximo los recursos gratuitos disponibles. El curso de Google que estás realizando es una base fantástica, y esta guía te ayudará a profundizar y ampliar tus conocimientos y habilidades prácticas.</p>
            <h3>Propósito de esta guía:</h3>
            <ul>
                <li>Ofrecer una estructura clara para tu autoestudio.</li>
                <li>Identificar áreas clave de conocimiento en ciberseguridad.</li>
                <li>Proporcionar recursos gratuitos y de alta calidad.</li>
                <li>Suggerir proyectos prácticos para consolidar el aprendizaje.</li>
            </ul>
            <h3>Recuerda:</h3>
            <ul>
                <li><strong>Flexibilidad:</strong> Adapta esta guía a tus intereses y ritmo de aprendizaje.</li>
                <li><strong>Práctica Constante:</strong> La ciberseguridad es un campo eminentemente práctico. ¡Aplica lo que aprendes!</li>
                <li><strong>Curiosidad:</strong> ¡Nunca dejes de hacer preguntas y explorar!</li>
            </ul>
        </div>

        <div class="slide slide-theme-tools">
            <h2><span class="icon-placeholder">[ICONO: Herramientas]</span>Diapositiva 3: Tool Stack Esencial (Gratuito)</h2>
            <p>Para empezar, necesitarás algunas herramientas. La mayoría son gratuitas y de código abierto:</p>
            <h3><span class="logo-placeholder">[LOGO: VirtualBox]</span>Virtualización:</h3>
            <ul>
                <li><strong>VirtualBox:</strong> (Oracle) Gratuito y multiplataforma.</li>
                <li><strong>VMware Workstation Player:</strong> Gratuito para uso personal.</li>
            </ul>
            <h3><span class="logo-placeholder">[LOGO: Kali Linux]</span>Sistemas Operativos para Prácticas:</h3>
            <ul>
                <li><strong>Kali Linux:</strong> Distribución Linux para pentesting y auditoría de seguridad.</li>
                <li><strong>Parrot OS Security:</strong> Alternativa a Kali Linux.</li>
                <li><strong>Windows:</strong> Necesitarás una instancia para practicar hardening y análisis.</li>
            </ul>
            <h3><span class="logo-placeholder">[LOGO: Wireshark]</span>Herramientas de Red:</h3>
            <ul>
                <li><strong>Wireshark:</strong> Analizador de protocolos de red.</li>
                <li><strong>Nmap:</strong> Escáner de puertos y descubridor de redes.</li>
            </ul>
            <h3><span class="logo-placeholder">[LOGO: TryHackMe]</span>Plataformas de Práctica Online:</h3>
            <ul>
                <li><strong>TryHackMe:</strong> Salas de aprendizaje y desafíos. <a href="https://tryhackme.com" target="_blank">tryhackme.com</a></li>
                <li><strong>Hack The Box:</strong> Máquinas vulnerables. <a href="https://hackthebox.com" target="_blank">hackthebox.com</a></li>
                <li><strong>OWASP Juice Shop:</strong> App web insegura. <a href="https://owasp.org/www-project-juice-shop/" target="_blank">owasp.org/www-project-juice-shop/</a></li>
            </ul>
            <h3>Navegadores Web:</h3>
            <ul>
                <li>Firefox, Chrome (con sus herramientas de desarrollador).</li>
            </ul>
            <h3>Editores de Código/Texto:</h3>
            <ul>
                <li>VS Code, Sublime Text.</li>
            </ul>
            <h3>Organización:</h3>
            <ul>
                <li>Lector de RSS (Feedly), Notas (Notion, Obsidian).</li>
            </ul>
        </div>

        <div class="slide slide-theme-foundations">
            <h2><span class="icon-placeholder">[ICONO: Cimientos]</span>Diapositiva 4: Fase 1: Fundamentos Sólidos (Aprox. 4-6 Semanas)</h2>
            <p><strong>Tema:</strong> Conceptos Clave de TI y Ciberseguridad. Es crucial construir sobre una base firme.</p>
            <h3>Objetivos:</h3>
            <ul>
                <li>Comprender modelos de red (OSI, TCP/IP), protocolos (DNS, HTTP/S, FTP, SSH).</li>
                <li>Entender Sistemas Operativos (Linux y Windows): procesos, memoria, archivos, permisos.</li>
                <li>Asimilar conceptos de ciberseguridad: Triada CIA, amenazas, vulnerabilidades, riesgos, controles.</li>
            </ul>
            <h3>Recursos Gratuitos:</h3>
            <ul>
                <li><strong>Redes:</strong>
                    <ul>
                        <li><strong>Professor Messer's CompTIA Network+ (YouTube):</strong> <a href="https://www.professormesser.com/network-plus/n10-008/n10-008-training-course/" target="_blank">professormesser.com</a> (Inglés)</li>
                        <li><strong>Khan Academy - Internet:</strong> <a href="https://www.khanacademy.org/computing/computers-and-internet" target="_blank">khanacademy.org</a></li>
                        <li><strong>Eli the Computer Guy (YouTube):</strong> <a href="https://www.youtube.com/user/elithecomputerguy" target="_blank">youtube.com/user/elithecomputerguy</a> (Inglés)</li>
                        <li><strong>Cisco Packet Tracer:</strong> <a href="https://www.netacad.com/courses/packet-tracer" target="_blank">netacad.com</a></li>
                    </ul>
                </li>
                <li><strong>Sistemas Operativos:</strong>
                    <ul>
                        <li><strong>Linux Journey:</strong> <a href="https://linuxjourney.com" target="_blank">linuxjourney.com</a> (Inglés)</li>
                        <li><strong>OverTheWire - Bandit:</strong> <a href="https://overthewire.org/wargames/bandit/" target="_blank">overthewire.org/wargames/bandit/</a> (Inglés)</li>
                        <li><strong>Microsoft Learn:</strong> <a href="https://learn.microsoft.com/" target="_blank">learn.microsoft.com/</a></li>
                    </ul>
                </li>
                <li><strong>Ciberseguridad Básica:</strong>
                    <ul>
                        <li><strong>Cybrary.it:</strong> <a href="https://www.cybrary.it" target="_blank">cybrary.it</a> (Inglés)</li>
                        <li><strong>NIST Cybersecurity Framework:</strong> <a href="https://www.nist.gov/cyberframework" target="_blank">nist.gov/cyberframework</a> (Inglés)</li>
                        <li><strong>YouTube - "Introducción a la Ciberseguridad"</strong></li>
                    </ul>
                </li>
            </ul>
            <div class="project">
                <strong>Mini-Proyecto:</strong>
                <ul>
                    <li>Configura una red virtual simple con dos VMs (Kali atacante, Windows/Linux víctima).</li>
                    <li>Documenta la configuración y verifica conectividad.</li>
                </ul>
            </div>
        </div>

        <div class="slide slide-theme-linux">
            <h2><span class="icon-placeholder">[ICONO: Tux Pingüino]</span><span class="icon-placeholder">[ICONO: Código < >]</span>Diapositiva 5: Fase 2: Dominando Linux y Scripting (Aprox. 6-8 Semanas)</h2>
            <p><strong>Tema:</strong> Linux es el SO predilecto en ciberseguridad. Scripting automatiza tareas.</p>
            <h3>Objetivos:</h3>
            <ul>
                <li>Dominar línea de comandos Linux: navegación, gestión de archivos, usuarios, permisos, procesos.</li>
                <li>Aprender scripting básico en Bash.</li>
                <li>Fundamentos de Python para ciberseguridad (redes, parseo, automatización).</li>
            </ul>
            <h3>Recursos Gratuitos:</h3>
            <ul>
                <li><strong>Linux:</strong>
                    <ul>
                        <li><strong>TryHackMe - Linux Fundamentals:</strong> <a href="https://tryhackme.com/path/outline/linux-fundamentals" target="_blank">tryhackme.com</a></li>
                        <li><strong>LinuxCommand.org:</strong> <a href="http://linuxcommand.org" target="_blank">linuxcommand.org</a></li>
                        <li><strong>Ryan's Tutorials - Linux:</strong> <a href="https://ryanstutorials.net/linuxtutorial/" target="_blank">ryanstutorials.net</a></li>
                        <li><strong>YouTube "La PingüiNera":</strong> <a href="https://www.youtube.com/@LaPinguinera" target="_blank">youtube.com/c/Lapinguinera</a></li>
                    </ul>
                </li>
                <li><strong>Bash Scripting:</strong>
                    <ul>
                        <li><strong>Learn Shell:</strong> <a href="https://www.learnshell.org/" target="_blank">learnshell.org</a></li>
                        <li><strong>The Bash Guide:</strong> <a href="https://tldp.org/LDP/Bash-Beginners-Guide/html/" target="_blank">tldp.org</a></li>
                        <li><strong>YouTube - "Curso de Bash Scripting"</strong></li>
                    </ul>
                </li>
                <li><strong>Python para Ciberseguridad:</strong>
                    <ul>
                        <li><strong>Python.org - Tutorial:</strong> <a href="https://docs.python.org/es/3/tutorial/" target="_blank">python.org</a></li>
                        <li><strong>Automate the Boring Stuff:</strong> <a href="https://automatetheboringstuff.com/" target="_blank">automatetheboringstuff.com</a></li>
                        <li><strong>FreeCodeCamp (YouTube):</strong> <a href="https://www.youtube.com/c/Freecodecamp" target="_blank">youtube.com/c/Freecodecamp</a></li>
                        <li><strong>HackerSploit (YouTube) - Python for Pentesters:</strong> <a href="https://www.youtube.com/playlist?list=PLBf0hzazHTGM_dncTqO9l-0zUQWb6heK-" target="_blank">youtube.com/c/HackerSploit</a></li>
                    </ul>
                </li>
            </ul>
            <div class="project">
                <strong>Proyecto:</strong>
                <ul>
                    <li>Script en Python: toma IPs/dominios, escanea puertos comunes con `nmap`, parsea y muestra resultados.</li>
                </ul>
            </div>
        </div>

        <div class="slide slide-theme-offensive">
            <h2><span class="icon-placeholder">[ICONO: Sombrero Blanco/Lupa]</span>Diapositiva 6: Fase 3: Seguridad Ofensiva – El Arte del Hacking Ético (Aprox. 8-10 Semanas)</h2>
            <p><strong>Tema:</strong> Aprende cómo piensan y actúan los atacantes para defender mejor. (¡Ética y legalmente!).</p>
            <h3>Objetivos:</h3>
            <ul>
                <li>Fases de pentest: reconocimiento, escaneo, enumeración, explotación, post-explotación, reporte.</li>
                <li>Uso básico: Nmap (avanzado), Metasploit, Burp Suite Community.</li>
                <li>Vulnerabilidades comunes (OWASP Top 10 web, red, sistemas).</li>
            </ul>
            <h3>Recursos Gratuitos:</h3>
            <ul>
                <li><strong>Plataformas de Práctica:</strong>
                    <ul>
                        <li><strong>TryHackMe:</strong> Rutas "Jr Penetration Tester", "Offensive Pentesting". <a href="https://tryhackme.com" target="_blank">tryhackme.com</a></li>
                        <li><strong>Hack The Box:</strong> Labs "Starting Point", máquinas retiradas. <a href="https://www.hackthebox.com" target="_blank">hackthebox.com</a></li>
                        <li><strong>VulnHub.com:</strong> VMs vulnerables. <a href="https://www.vulnhub.com/" target="_blank">vulnhub.com</a></li>
                    </ul>
                </li>
                <li><strong>Guías y Documentación:</strong>
                    <ul>
                        <li><strong>OWASP Top 10:</strong> <a href="https://owasp.org/www-project-top-ten/" target="_blank">owasp.org/www-project-top-ten/</a></li>
                        <li><strong>OWASP WSTG:</strong> <a href="https://owasp.org/www-project-web-security-testing-guide/" target="_blank">owasp.org/www-project-web-security-testing-guide/</a></li>
                        <li><strong>Metasploit Unleashed:</strong> <a href="https://www.offensive-security.com/metasploit-unleashed/" target="_blank">offensive-security.com</a></li>
                    </ul>
                </li>
                <li><strong>Canales YouTube (Inglés):</strong> John Hammond, HackerSploit, IppSec, The Cyber Mentor.</li>
                <li><strong>Canales YouTube (Español):</strong> s4vitar, David Bombal en Español.</li>
            </ul>
            <div class="project">
                <strong>Proyecto:</strong>
                <ul>
                    <li>Pentest completo a máquina de TryHackMe/VulnHub (fácil/medio).</li>
                    <li>Documenta todo el proceso. <strong>¡Excelente para tu portfolio!</strong></li>
                </ul>
            </div>
        </div>

        <div class="slide slide-theme-defensive">
            <h2><span class="icon-placeholder">[ICONO: Escudo/Candado]</span>Diapositiva 7: Fase 4: Seguridad Defensiva – Protegiendo los Activos (Aprox. 8-10 Semanas)</h2>
            <p><strong>Tema:</strong> No todo es atacar; aprender a defender es igualmente crucial.</p>
            <h3>Objetivos:</h3>
            <ul>
                <li>Hardening de sistemas (Linux, Windows).</li>
                <li>Firewalls (iptables, UFW, Win Firewall) e IDS/IPS (Snort, Suricata - conceptual).</li>
                <li>Análisis de logs básico.</li>
                <li>Introducción a SIEM (Wazuh, Security Onion - exploración).</li>
                <li>Fundamentos de respuesta a incidentes.</li>
            </ul>
            <h3>Recursos Gratuitos:</h3>
            <ul>
                <li><strong>Hardening:</strong> CIS Benchmarks, Microsoft Security Baselines.</li>
                <li><strong>Herramientas Defensivas:</strong> Wazuh, Security Onion, Snort, Suricata, LetsDefend.io, Blue Team Labs Online.</li>
                <li><strong>Canales YouTube (Inglés):</strong> Black Hills Information Security, 13Cubed.</li>
            </ul>
            <div class="project">
                <strong>Proyecto:</strong>
                <ul>
                    <li>Configura Wazuh en VM. Integra logs de otra VM.</li>
                    <li>Simula actividades "maliciosas", analiza alertas y documenta.</li>
                </ul>
            </div>
        </div>

        <div class="slide slide-theme-specializations">
            <h2><span class="icon-placeholder">[ICONO: Árbol de Ramas]</span>Diapositiva 8: Fase 5: Especializaciones y Temas Avanzados (Continuo)</h2>
            <p>Con base sólida, explora áreas específicas. Elige 1-2 para profundizar.</p>
            <h3>Posibles Especializaciones:</h3>
            <ul>
                <li><span class="icon-placeholder">[ICONO: Cripto]</span><strong>Criptografía Aplicada:</strong> CryptoHack.org, Christof Paar (YouTube).</li>
                <li><span class="icon-placeholder">[ICONO: WebSec]</span><strong>Seguridad Web Avanzada:</strong> PortSwigger Web Security Academy, OWASP.org.</li>
                <li><span class="icon-placeholder">[ICONO: Nube]</span><strong>Seguridad en la Nube:</strong> Docs AWS/Azure/GCP, Cloud Security Alliance (CSA).</li>
                <li><span class="icon-placeholder">[ICONO: Malware]</span><strong>Análisis de Malware Básico:</strong> MalwareUnicorn, REMnux.</li>
                <li><span class="icon-placeholder">[ICONO: Forense]</span><strong>Forense Digital:</strong> SANS Posters, Autopsy.</li>
                <li><span class="icon-placeholder">[ICONO: Móvil]</span><strong>Seguridad Móvil.</strong></li>
                <li><span class="icon-placeholder">[ICONO: IoT]</span><strong>Seguridad en IoT.</strong></li>
            </ul>
            <div class="project">
                <strong>Proyecto (Ejemplos):</strong>
                <ul>
                    <li><strong>Seguridad Web:</strong> Script para explotar XSS/SQLi en Juice Shop.</li>
                    <li><strong>Análisis Malware:</strong> Analiza muestra en VM aislada, documenta comportamiento.</li>
                </ul>
            </div>
        </div>

        <div class="slide slide-theme-research">
            <h2><span class="icon-placeholder">[ICONO: Lupa/Libro]</span>Diapositiva 9: Fase 6: Investigación y Contribución (Continuo)</h2>
            <p>La ciberseguridad evoluciona. Mantenerse actualizado es clave.</p>
            <h3>Objetivos:</h3>
            <ul>
                <li>Leer noticias, blogs, reportes de vulnerabilidades.</li>
                <li>Leer whitepapers y artículos de investigación.</li>
                <li>Participar en CTFs (Capture The Flag).</li>
                <li>Contribuir a proyectos open-source.</li>
            </ul>
            <h3>Recursos:</h3>
            <ul>
                <li><strong>Noticias/Blogs:</strong> The Hacker News, Bleeping Computer, Threatpost, Krebs on Security.</li>
                <li><strong>Investigación:</strong> SANS Reading Room, arXiv (cs.CR, cs.LG), USENIX.</li>
                <li><strong>CTFs:</strong> CTFtime.org, PicoCTF, OverTheWire.</li>
                <li><strong>Comunidades:</strong> Reddit (r/cybersecurity, r/netsec), foros.</li>
            </ul>
            <h3>Actividad Continua:</h3>
            <ul>
                <li>Dedica horas semanales a leer. Resuelve CTFs regularmente.</li>
            </ul>
        </div>

        <div class="slide slide-theme-softskills">
            <h2><span class="icon-placeholder">[ICONO: Red Personas]</span><span class="icon-placeholder">[ICONO: Diálogo]</span>Diapositiva 10: Fase 7: Soft Skills y Networking (Continuo)</h2>
            <p>Habilidades técnicas son importantes, pero soft skills y networking te llevarán lejos.</p>
            <h3>Objetivos:</h3>
            <ul>
                <li><strong>Comunicación:</strong> Explicar conceptos técnicos claramente (verbal/escrito).</li>
                <li><strong>Documentación:</strong> Profesional para proyectos, hallazgos, procedimientos.</li>
                <li><strong>Trabajo en Equipo.</strong></li>
                <li><strong>Networking:</strong> Conectar con estudiantes y profesionales.</li>
            </ul>
            <h3>Recursos y Actividades:</h3>
            <ul>
                <li><strong>Documentación:</strong> Blog personal o GitHub con proyectos.</li>
                <li><strong>Presentación:</strong> Practica explicando. Toastmasters (<a href="https://www.toastmasters.org" target="_blank">toastmasters.org</a>).</li>
                <li><strong>Networking:</strong> LinkedIn, comunidades online (Discord, foros), eventos (webinars, BSides).</li>
            </ul>
            <h3>Actividad Continua:</h3>
            <ul>
                <li>Documenta cada proyecto. Explica un concepto nuevo semanalmente. Participa en comunidades.</li>
            </ul>
        </div>

        <div class="slide slide-theme-jobs">
            <h2><span class="icon-placeholder">[ICONO: Maletín]</span><span class="icon-placeholder">[ICONO: CV]</span>Diapositiva 11: Fase 8: Preparación para la Búsqueda de Empleo (Aprox. 4 Semanas)</h2>
            <p><strong>Tema:</strong> Es hora de mostrar lo aprendido y buscar tu primera oportunidad.</p>
            <h3>Objetivos:</h3>
            <ul>
                <li><strong>Portfolio:</strong> GitHub con proyectos, scripts, write-ups.</li>
                <li><strong>CV/Currículum:</strong> Destacar habilidades y proyectos.</li>
                <li><strong>Entrevistas:</strong> Preparar preguntas técnicas y de comportamiento (STAR).</li>
                <li><strong>Investigación de Roles:</strong> Analista SOC Nivel 1, Técnico Seguridad Jr., Jr. Pentester.</li>
            </ul>
            <h3>Recursos:</h3>
            <ul>
                <li><strong>Portfolio:</strong> <a href="https://github.com" target="_blank">GitHub</a>.</li>
                <li><strong>CV/Entrevistas:</strong> YouTube "Cybersecurity interview questions", blogs, LinkedIn.</li>
                <li><strong>Plataformas Empleo:</strong> LinkedIn, Indeed, Glassdoor.</li>
            </ul>
            <div class="project">
                <strong>Proyecto Final (Portfolio):</strong>
                <ul>
                    <li>Mínimo 3-5 proyectos sólidos y bien documentados en GitHub.</li>
                    <li>CV claro y conciso. Prepara "elevator pitch".</li>
                </ul>
            </div>
        </div>

        <div class="slide slide-theme-timeline">
            <h2><span class="icon-placeholder">[ICONO: Calendario/Gráfico]</span>Diapositiva 12: Cronograma General (Ejemplo Visual)</h2>
            <p><em>(Esta lista simula una línea de tiempo o gráfico de Gantt)</em></p>
            <ul style="list-style-type: none; counter-reset: list-item;">
                <li><strong>Fase 1: Fundamentos Sólidos</strong> (4-6 Semanas)</li>
                <li><strong>Fase 2: Dominando Linux y Scripting</strong> (6-8 Semanas)</li>
                <li><strong>Fase 3: Seguridad Ofensiva – Hacking Ético</strong> (8-10 Semanas)</li>
                <li><strong>Fase 4: Seguridad Defensiva – Protección</strong> (8-10 Semanas)</li>
                <li><strong>Fase 5: Especializaciones</strong> (Continuo, según interés)</li>
                <li><strong>Fase 6: Investigación y Contribución</strong> (Continuo)</li>
                <li><strong>Fase 7: Soft Skills y Networking</strong> (Continuo)</li>
                <li><strong>Fase 8: Preparación Empleo</strong> (4 Semanas dedicadas)</li>
            </ul>
            <p><strong>Duración Total Estimada: 12-18 Meses (muy flexible, dedicación a tiempo parcial)</strong></p>
        </div>

        <div class="slide slide-theme-conclusion">
            <h2><span class="icon-placeholder">[ICONO: Meta/Cohete]</span>Diapositiva 13: Conclusión y Próximos Pasos</h2>
            <p><span class="icon-placeholder"></span></p>
            <p>¡Has llegado al final de esta hoja de ruta, pero es solo el comienzo de tu carrera en ciberseguridad!</p>
            <ul>
                <li><strong>Perseverancia:</strong> Habrá momentos desafiantes, la constancia es clave.</li>
                <li><strong>Curiosidad Insaciable:</strong> El panorama cambia a diario. Mantén viva tu curiosidad.</li>
                <li><strong>Comunidad:</strong> Apóyate en las comunidades online. No estás solo/a.</li>
                <li><strong>Ética:</strong> Actúa siempre de forma ética y responsable.</li>
            </ul>
            <p><strong>¡Mucha suerte en tu emocionante viaje por la ciberseguridad!</strong></p>
            <p><em>[Espacio para tus datos de contacto o perfil de LinkedIn]</em></p>
        </div>

        <div class="slide slide-theme-resources">
            <h2><span class="icon-placeholder">[ICONO: Libro Abierto/Comunidad]</span>Diapositiva 14: Recursos Adicionales y Comunidades (Español)</h2>
            <h3><span class="logo-placeholder">[LOGO: Foro]</span>Comunidades y Foros:</h3>
            <ul>
                <li><strong>Foro de Ciberseguridad (Hacking Ético y Seguridad Informática):</strong> Busca foros activos.</li>
                <li><strong>Grupos de Telegram/Discord:</strong> "FluProject", "Adastra", comunidades CTF.</li>
                <li><strong>Reddit:</strong> r/esCiberseguridad, r/hacking_es.</li>
            </ul>
            <h3><span class="logo-placeholder">[LOGO: Podcast]</span>Podcasts en Español:</h3>
            <ul>
                <li><strong>"Desde la Barra del Bar"</strong></li>
                <li><strong>"Ciberseguridad con Cerveza"</strong></li>
                <li><strong>"Hacking Etico y Ciberseguridad"</strong> (Busca similares)</li>
            </ul>
            <h3><span class="logo-placeholder">[LOGO: YouTube]</span>Canales de YouTube Adicionales (Español):</h3>
            <ul>
                <li><strong>FluProject:</strong> <a href="https://www.youtube.com/@FluProject" target="_blank">youtube.com/c/FluProject</a></li>
                <li><strong>Maligno Alonso:</strong> <a href="https://www.youtube.com/@MalignoAlonso" target="_blank">youtube.com/user/MalignoAlonso</a> (Blog y charlas)</li>
                <li><strong>Rootkito:</strong> <a href="https://www.youtube.com/@Rootkito" target="_blank">youtube.com/c/Rootkito</a></li>
            </ul>
        </div>

    </div>
</body>
</html>
