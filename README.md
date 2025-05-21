# PREVINE-FIT
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-TF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PrevineFit - Apresentação Interativa da Oferta</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Visualization & Content Choices:
        - Report Info: Product Name "PrevineFit" -> Goal: Introduce -> Presentation: Prominent Title -> Interaction: Static -> Justification: Clear branding.
        - Report Info: Problem of Evasion -> Goal: Contextualize -> Presentation: Dedicated text section -> Interaction: Static -> Justification: Set the stage for the solution.
        - Report Info: What is PrevineFit (AI tool) -> Goal: Explain Solution -> Presentation: Descriptive text, key features highlighted -> Interaction: Static -> Justification: Core product explanation.
        - Report Info: Target Audience (Daiane) -> Goal: Personalize -> Presentation: Persona description section -> Interaction: Static -> Justification: Connect with the intended user.
        - Report Info: Benefits (Reduce Evasion, Improve Experience, Efficiency) -> Goal: Showcase Value -> Presentation: Icon-accompanied list -> Interaction: Static, clear visual separation -> Justification: Easy-to-scan value proposition.
        - Report Info: Objections (Cost, Efficiency, Tech Resistance) & Solutions -> Goal: Address Concerns -> Presentation: Interactive accordion/expandable cards for each objection/solution pair -> Interaction: Click to reveal -> Justification: Allows users to explore concerns they have without cluttering the page.
        - Report Info: Urgency (Financial Harm, Special Offers) -> Goal: Drive Action -> Presentation: Highlighted list/cards for reasons to act now and special offers -> Interaction: Static, visually emphasized -> Justification: Motivate immediate interest.
        - Report Info: Missing Cost -> Goal: Acknowledge -> Presentation: Note in "Next Steps" that pricing is TBD -> Interaction: Static -> Justification: Transparency.
        - Library/Method: HTML/CSS/Tailwind for layout and text. Vanilla JS for navigation and accordion. No charts needed.
        -->
    <style>
        body {
            font-family: 'Inter', sans-serif; /* Using Inter as a professional and clean font */
        }
        /* Custom scroll behavior */
        html {
            scroll-behavior: smooth;
        }
        /* Active link styling */
        .nav-link.active {
            font-weight: 600;
            color: #4f46e5; /* Indigo-600 */
            border-bottom: 2px solid #4f46e5;
        }
        .section-title {
            font-size: 2.25rem; /* text-4xl */
            font-weight: 700; /* font-bold */
            color: #374151; /* text-gray-700 */
            margin-bottom: 1.5rem; /* mb-6 */
            text-align: center;
        }
        .card {
            background-color: white;
            border-radius: 0.75rem; /* rounded-xl */
            padding: 1.5rem; /* p-6 */
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05); /* shadow-lg */
            transition: transform 0.3s ease-in-out;
        }
        .card:hover {
            transform: translateY(-5px);
        }
        .accordion-button::after {
            content: '\\25BC'; /* Down arrow */
            float: right;
            transition: transform 0.2s ease-in-out;
        }
        .accordion-button.open::after {
            transform: rotate(180deg); /* Up arrow */
        }
        .stat-card {
            background-color: #e0e7ff; /* indigo-100 */
            border-left: 5px solid #4f46e5; /* indigo-600 */
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
</head>
<body class="bg-gray-50 text-gray-800 antialiased">

    <header class="bg-white shadow-md sticky top-0 z-50">
        <nav class="container mx-auto px-6 py-3 flex flex-wrap justify-between items-center">
            <a href="#inicio" class="text-2xl font-bold text-indigo-600">PrevineFit</a>
            <button id="nav-toggle" class="md:hidden block text-indigo-600 focus:outline-none">
                <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
                    <path fill-rule="evenodd" d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"/>
                </svg>
            </button>
            <div id="nav-content" class="w-full md:flex md:items-center md:w-auto hidden md:block">
                <ul class="md:flex md:justify-between text-base text-gray-700 pt-4 md:pt-0">
                    <li><a class="nav-link md:p-4 py-3 px-0 block border-b-2 border-transparent hover:border-indigo-500" href="#problema">O Problema</a></li>
                    <li><a class="nav-link md:p-4 py-3 px-0 block border-b-2 border-transparent hover:border-indigo-500" href="#solucao">A Solução</a></li>
                    <li><a class="nav-link md:p-4 py-3 px-0 block border-b-2 border-transparent hover:border-indigo-500" href="#para-quem">Para Quem?</a></li>
                    <li><a class="nav-link md:p-4 py-3 px-0 block border-b-2 border-transparent hover:border-indigo-500" href="#beneficios">Benefícios</a></li>
                    <li><a class="nav-link md:p-4 py-3 px-0 block border-b-2 border-transparent hover:border-indigo-500" href="#desafios">Desafios</a></li>
                    <li><a class="nav-link md:p-4 py-3 px-0 block border-b-2 border-transparent hover:border-indigo-500" href="#urgencia">Por Que Agora?</a></li>
                    <li><a class="nav-link md:p-4 py-3 px-0 block border-b-2 border-transparent hover:border-indigo-500" href="#contato">Contato</a></li>
                </ul>
            </div>
        </nav>
    </header>

    <main class="container mx-auto px-6 py-12">

        <section id="inicio" class="min-h-[80vh] flex flex-col justify-center items-center text-center py-12">
            <h1 class="text-5xl md:text-6xl font-extrabold text-indigo-700 mb-6 leading-tight">
                Previne<span class="text-blue-500">Fit</span>:
            </h1>
            <p class="text-2xl md:text-3xl text-gray-600 mb-8 max-w-3xl">
                Sua academia com <span class="font-semibold text-indigo-600">menos evasão</span> e <span class="font-semibold text-indigo-600">mais retenção</span> através da Inteligência Artificial.
            </p>
            <p class="text-lg text-gray-500 mb-10 max-w-2xl">
                Descubra como nossa ferramenta inovadora pode prever cancelamentos e ajudar sua academia a prosperar.
            </p>
            <a href="#solucao" class="bg-indigo-600 hover:bg-indigo-700 text-white font-semibold py-3 px-8 rounded-lg text-lg shadow-lg transition duration-300 transform hover:scale-105">
                Conheça a Solução
            </a>
        </section>

        <section id="problema" class="py-16 bg-white rounded-xl shadow-xl my-12 p-8 md:p-12">
            <h2 class="section-title">O Desafio da Evasão em Academias</h2>
            <p class="text-lg text-gray-700 mb-6 text-center max-w-3xl mx-auto">
                A alta taxa de evasão de alunos é um dos maiores obstáculos para o crescimento e a estabilidade financeira das academias. Perder clientes não significa apenas uma redução na receita, mas também impacta o moral da equipe e a reputação do negócio.
            </p>
            <div class="grid md:grid-cols-2 gap-8 items-center">
                <div class="text-center md:text-left">
                    <h3 class="text-2xl font-semibold text-indigo-700 mb-3">Impactos da Evasão:</h3>
                    <ul class="list-none space-y-3 text-gray-600">
                        <li class="flex items-start"><span class="text-red-500 mr-2 text-xl font-bold">✗</span> Perda de Receita Recorrente</li>
                        <li class="flex items-start"><span class="text-red-500 mr-2 text-xl font-bold">✗</span> Custos Elevados para Aquisição de Novos Clientes</li>
                        <li class="flex items-start"><span class="text-red-500 mr-2 text-xl font-bold">✗</span> Dificuldade em Planejamento Financeiro a Longo Prazo</li>
                        <li class="flex items-start"><span class="text-red-500 mr-2 text-xl font-bold">✗</span> Desmotivação da Equipe e Alunos Remanescentes</li>
                    </ul>
                </div>
                <div class="flex justify-center">
                    <div class="p-6 bg-red-50 rounded-lg shadow-md text-center max-w-sm">
                        <span class="text-6xl text-red-500">📉</span>
                        <p class="text-xl font-semibold text-red-700 mt-4">A evasão silenciosamente drena os recursos da sua academia.</p>
                        <p class="text-sm text-red-600 mt-2">É hora de agir antes que seja tarde demais.</p>
                    </div>
                </div>
            </div>
            <p class="text-lg text-gray-700 mt-10 text-center max-w-3xl mx-auto">
                Entender os motivos e antecipar quem está prestes a sair é crucial. É aqui que o PrevineFit entra em ação.
            </p>
        </section>

        <section id="solucao" class="py-16 p-8 md:p-12">
            <h2 class="section-title">A Solução Inteligente: PrevineFit</h2>
            <p class="text-lg text-gray-700 mb-10 text-center max-w-3xl mx-auto">
                O PrevineFit é uma ferramenta inovadora que utiliza o poder da Inteligência Artificial para analisar dados dos seus alunos e identificar padrões que indicam um risco de cancelamento. Com informações precisas, você pode agir proativamente para reter seus clientes.
            </p>
            <div class="grid md:grid-cols-3 gap-8">
                <div class="card text-center">
                    <span class="text-5xl text-indigo-600 mb-4 block">🔮</span>
                    <h3 class="text-xl font-semibold text-gray-800 mb-2">Previsão Preditiva</h3>
                    <p class="text-gray-600">Nossa IA analisa frequência, tipo de plano, interações e outros fatores para prever quem está em risco de evasão.</p>
                </div>
                <div class="card text-center">
                    <span class="text-5xl text-indigo-600 mb-4 block">🎯</span>
                    <h3 class="text-xl font-semibold text-gray-800 mb-2">Ações Proativas</h3>
                    <p class="text-gray-600">Receba alertas e insights para intervir no momento certo, oferecendo suporte personalizado e melhorando a experiência do aluno.</p>
                </div>
                <div class="card text-center">
                    <span class="text-5xl text-indigo-600 mb-4 block">📊</span>
                    <h3 class="text-xl font-semibold text-gray-800 mb-2">Gestão Eficiente</h3>
                    <p class="text-gray-600">Otimize seus esforços de retenção, focando nos alunos que mais precisam de atenção, e melhore a saúde financeira da sua academia.</p>
                </div>
            </div>
        </section>

        <section id="para-quem" class="py-16 bg-indigo-50 rounded-xl shadow-xl my-12 p-8 md:p-12">
            <h2 class="section-title">Para Quem é o PrevineFit?</h2>
            <p class="text-lg text-gray-700 mb-10 text-center max-w-3xl mx-auto">
                O PrevineFit foi desenhado especialmente para gestores de academias que, como você, buscam soluções práticas e inovadoras para os desafios do dia a dia, especialmente a retenção de clientes.
            </p>
            <div class="bg-white p-8 rounded-lg shadow-lg max-w-2xl mx-auto flex flex-col md:flex-row items-center gap-6">
                <div class="flex-shrink-0">
                    <div class="w-32 h-32 rounded-full bg-indigo-500 text-white flex items-center justify-center text-5xl font-bold shadow-md">
                        D
                    </div>
                </div>
                <div>
                    <h3 class="text-2xl font-bold text-indigo-700 mb-2">Conheça Daiane: Sua Parceira Ideal</h3>
                    <p class="text-gray-600 mb-1"><span class="font-semibold">Idade:</span> 32 anos</p>
                    <p class="text-gray-600 mb-1"><span class="font-semibold">Função:</span> Gestora da Academia Força Local</p>
                    <p class="text-gray-600 mb-1"><span class="font-semibold">Experiência:</span> 7 anos liderando a academia</p>
                    <p class="text-gray-600 mt-3 italic">"Busco constantemente soluções que otimizem a gestão e, principalmente, que me ajudem a manter meus alunos satisfeitos e engajados. A retenção é chave para o nosso sucesso."</p>
                </div>
            </div>
             <p class="text-lg text-gray-700 mt-10 text-center max-w-3xl mx-auto">
                Se você se identifica com os desafios da Daiane e busca uma forma inteligente de combater a evasão, o PrevineFit é para você.
            </p>
        </section>

        <section id="beneficios" class="py-16 p-8 md:p-12">
            <h2 class="section-title">Benefícios Claros para Sua Academia</h2>
            <p class="text-lg text-gray-700 mb-10 text-center max-w-3xl mx-auto">
                Ao implementar o PrevineFit, sua academia colherá vantagens significativas que vão além da simples redução de cancelamentos.
            </p>
            <div class="grid md:grid-cols-1 lg:grid-cols-2 gap-8">
                <div class="card stat-card p-6">
                    <div class="flex items-center mb-3">
                        <span class="text-3xl text-indigo-600 mr-3">💰</span>
                        <h3 class="text-xl font-semibold text-indigo-800">Redução Direta da Evasão</h3>
                    </div>
                    <p class="text-gray-700">O benefício principal e mais imediato. Menos cancelamentos significam maior receita e estabilidade financeira para sua academia.</p>
                </div>
                <div class="card stat-card p-6">
                    <div class="flex items-center mb-3">
                        <span class="text-3xl text-indigo-600 mr-3">😊</span>
                        <h3 class="text-xl font-semibold text-indigo-800">Melhora na Experiência do Aluno</h3>
                    </div>
                    <p class="text-gray-700">Ao identificar alunos em risco, você pode oferecer um atendimento mais personalizado, entendendo suas necessidades e aumentando sua satisfação.</p>
                </div>
                <div class="card stat-card p-6">
                    <div class="flex items-center mb-3">
                        <span class="text-3xl text-indigo-600 mr-3">⚙️</span>
                        <h3 class="text-xl font-semibold text-indigo-800">Maior Eficiência na Gestão</h3>
                    </div>
                    <p class="text-gray-700">Concentre seus esforços de retenção de forma mais inteligente, otimizando tempo e recursos da sua equipe.</p>
                </div>
                <div class="card stat-card p-6">
                    <div class="flex items-center mb-3">
                        <span class="text-3xl text-indigo-600 mr-3">📈</span>
                        <h3 class="text-xl font-semibold text-indigo-800">Decisões Baseadas em Dados</h3>
                    </div>
                    <p class="text-gray-700">Tenha acesso a insights valiosos sobre o comportamento dos seus alunos, permitindo um planejamento estratégico mais eficaz.</p>
                </div>
            </div>
        </section>

        <section id="desafios" class="py-16 bg-gray-100 rounded-xl shadow-xl my-12 p-8 md:p-12">
            <h2 class="section-title">Superando Desafios Comuns</h2>
            <p class="text-lg text-gray-700 mb-10 text-center max-w-3xl mx-auto">
                Entendemos que a adoção de novas tecnologias pode gerar dúvidas. O PrevineFit foi pensado para ser uma solução acessível e eficaz, quebrando barreiras comuns.
            </p>
            <div class="space-y-4 max-w-3xl mx-auto" id="accordion-container">
                <div class="accordion-item bg-white rounded-lg shadow-md">
                    <button class="accordion-button w-full text-left p-5 font-semibold text-lg text-indigo-700 focus:outline-none flex justify-between items-center">
                        Preocupações sobre o custo da solução?
                    </button>
                    <div class="accordion-content overflow-hidden max-h-0 transition-max-height duration-500 ease-in-out">
                        <p class="p-5 text-gray-600">
                            <strong>Nossa Resposta:</strong> Oferecemos planos acessíveis e flexíveis, pensados especialmente para academias de diferentes portes, incluindo as menores. O retorno sobre o investimento com a redução da evasão compensa rapidamente o custo da ferramenta.
                        </p>
                    </div>
                </div>
                <div class="accordion-item bg-white rounded-lg shadow-md">
                    <button class="accordion-button w-full text-left p-5 font-semibold text-lg text-indigo-700 focus:outline-none flex justify-between items-center">
                        Dúvidas sobre a eficiência do modelo preditivo?
                    </button>
                    <div class="accordion-content overflow-hidden max-h-0 transition-max-height duration-500 ease-in-out">
                        <p class="p-5 text-gray-600">
                            <strong>Nossa Resposta:</strong> Nosso modelo de IA é baseado em algoritmos robustos e constantemente aprimorado. Apresentamos resultados concretos e podemos compartilhar casos de sucesso que demonstram a eficácia do PrevineFit em reduzir a evasão.
                        </p>
                    </div>
                </div>
                <div class="accordion-item bg-white rounded-lg shadow-md">
                    <button class="accordion-button w-full text-left p-5 font-semibold text-lg text-indigo-700 focus:outline-none flex justify-between items-center">
                        Resistência ao uso de novas tecnologias pela equipe?
                    </button>
                    <div class="accordion-content overflow-hidden max-h-0 transition-max-height duration-500 ease-in-out">
                        <p class="p-5 text-gray-600">
                            <strong>Nossa Resposta:</strong> Garantimos que o PrevineFit seja uma ferramenta simples, intuitiva e de fácil utilização. Oferecemos treinamento inicial completo e suporte contínuo para assegurar que sua equipe se sinta confortável e confiante ao usar a plataforma.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <section id="urgencia" class="py-16 p-8 md:p-12">
            <h2 class="section-title">Por Que Agir Agora?</h2>
            <p class="text-lg text-gray-700 mb-6 text-center max-w-3xl mx-auto">
                A evasão de alunos é um problema que corrói os lucros e a estabilidade da sua academia dia após dia. Adiar a solução significa continuar perdendo receita e oportunidades de crescimento.
            </p>
            <div class="bg-amber-50 border-l-4 border-amber-500 p-6 rounded-md shadow-lg max-w-3xl mx-auto mb-10">
                <div class="flex">
                    <div class="flex-shrink-0">
                        <span class="text-2xl">⚠️</span>
                    </div>
                    <div class="ml-3">
                        <p class="text-lg font-semibold text-amber-700">
                            Cada dia sem uma estratégia eficaz de retenção é um dia em que sua academia pode estar perdendo clientes valiosos para a concorrência ou para o desânimo.
                        </p>
                    </div>
                </div>
            </div>

            <h3 class="text-2xl font-semibold text-gray-700 mb-6 text-center">Torne Sua Oferta Ainda Mais Atraente Conosco:</h3>
            <div class="grid md:grid-cols-3 gap-6">
                <div class="card text-center bg-green-50 border-green-500 border-l-4">
                    <span class="text-4xl text-green-600 mb-3 block">🎁</span>
                    <h4 class="text-lg font-semibold text-green-800 mb-1">Teste Gratuito</h4>
                    <p class="text-gray-600 text-sm">Experimente o PrevineFit por tempo limitado e veja os resultados por si mesmo, sem compromisso.</p>
                </div>
                <div class="card text-center bg-green-50 border-green-500 border-l-4">
                    <span class="text-4xl text-green-600 mb-3 block">🎓</span>
                    <h4 class="text-lg font-semibold text-green-800 mb-1">Treinamento Inicial</h4>
                    <p class="text-gray-600 text-sm">Capacitamos sua equipe para extrair o máximo da ferramenta desde o primeiro dia.</p>
                </div>
                <div class="card text-center bg-green-50 border-green-500 border-l-4">
                    <span class="text-4xl text-green-600 mb-3 block">🤝</span>
                    <h4 class="text-lg font-semibold text-green-800 mb-1">Suporte Personalizado</h4>
                    <p class="text-gray-600 text-sm">Conte com nosso apoio e ofertas especiais para academias da sua região.</p>
                </div>
            </div>
        </section>

        <section id="contato" class="py-16 bg-indigo-700 text-white rounded-xl shadow-xl my-12 p-8 md:p-12">
            <h2 class="text-4xl font-bold mb-6 text-center">Pronto para Transformar Sua Academia?</h2>
            <p class="text-lg text-indigo-100 mb-10 text-center max-w-3xl mx-auto">
                Dê o próximo passo para reduzir a evasão e fortalecer o relacionamento com seus alunos. Entre em contato conosco para uma demonstração personalizada do PrevineFit.
            </p>
            <div class="text-center">
                <a href="mailto:contato@previnefit.com.br?subject=Interesse no PrevineFit" class="bg-white hover:bg-gray-100 text-indigo-700 font-semibold py-3 px-8 rounded-lg text-lg shadow-lg transition duration-300 transform hover:scale-105 inline-block">
                    Solicitar Demonstração
                </a>
                <p class="text-indigo-200 text-sm mt-6">
                    (Informações sobre planos e custos serão detalhadas durante a demonstração ou em contato posterior.)
                </p>
            </div>
        </section>
    </main>

    <footer class="bg-gray-800 text-gray-300 text-center py-8">
        <p>&copy; <span id="currentYear"></span> PrevineFit. Todos os direitos reservados.</p>
        <p class="text-sm">Uma solução inovadora para academias.</p>
    </footer>

    <script>
        // Mobile Nav Toggle
        const navToggle = document.getElementById('nav-toggle');
        const navContent = document.getElementById('nav-content');
        navToggle.addEventListener('click', () => {
            navContent.classList.toggle('hidden');
        });

        // Close mobile nav on link click
        document.querySelectorAll('#nav-content a').forEach(link => {
            link.addEventListener('click', () => {
                if (!navContent.classList.contains('hidden') && window.innerWidth < 768) {
                     navContent.classList.add('hidden');
                }
            });
        });

        // Accordion
        const accordionContainer = document.getElementById('accordion-container');
        if (accordionContainer) {
            const accordionButtons = accordionContainer.querySelectorAll('.accordion-button');
            accordionButtons.forEach(button => {
                button.addEventListener('click', () => {
                    const content = button.nextElementSibling;
                    button.classList.toggle('open');
                    if (content.style.maxHeight) {
                        content.style.maxHeight = null;
                    } else {
                        content.style.maxHeight = content.scrollHeight + "px";
                    }
                    // Close other accordions
                    accordionButtons.forEach(otherButton => {
                        if (otherButton !== button) {
                            otherButton.classList.remove('open');
                            otherButton.nextElementSibling.style.maxHeight = null;
                        }
                    });
                });
            });
        }

        // Active Nav Link Styling on Scroll
        const sections = document.querySelectorAll('section[id]');
        const navLinks = document.querySelectorAll('.nav-link');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (pageYOffset >= (sectionTop - sectionHeight / 3)) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === current) {
                    link.classList.add('active');
                }
            });
             // Handle initial load for #inicio
            if (window.pageYOffset < sections[0].offsetTop) {
                 const homeLink = document.querySelector('.nav-link[href="#inicio"]'); // Assuming you add a home link
                 if(homeLink) homeLink.classList.add('active');
            }
        });
        
        // Set current year in footer
        document.getElementById('currentYear').textContent = new Date().getFullYear();

    </script>
</body>
</html>
