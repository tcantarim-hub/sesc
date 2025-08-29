<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resultados SESC Porto Seguro 1° Semestre</title>
    <!-- Tailwind CSS CDN for styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f4f8;
            color: #1f2937;
        }
        .tab-content {
            display: none;
        }
        .tab-content.active {
            display: block;
        }
        .tab-button.active {
            border-bottom: 3px solid #F6BE00;
            color: #004C99;
            font-weight: 700;
        }
        .card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .card:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        /* Pie chart for Receitas (63.82%) */
        .pie-chart-receitas {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: conic-gradient(#004C99 0% 63.82%, #D0D0CE 63.82% 100%);
        }
        /* Pie chart for Credenciamento (94.98%) */
        .pie-chart-credenciamento {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: conic-gradient(#C8102E 0% 94.98%, #D0D0CE 94.98% 100%);
        }
        /* Animation for the progress bar */
        @keyframes fill-progress {
            from { width: 0; }
            to { width: 107.67%; }
        }
        .animated-progress-bar {
            width: 0;
            animation: fill-progress 2s ease-out forwards;
        }
        /* The modal (background) */
        .modal {
            display: none;
            position: fixed;
            z-index: 100;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.4);
            backdrop-filter: blur(5px);
        }
        /* Modal Content/Box */
        .modal-content {
            background-color: #fefefe;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            max-width: 600px;
            border-radius: 1rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        /* The Close Button */
        .close-button {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }
        .close-button:hover,
        .close-button:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
        .timeline-item {
            position: relative;
            padding-left: 2rem;
            border-left: 3px solid #cbd5e1;
            margin-left: 10px;
            padding-bottom: 2rem;
        }
        .timeline-point {
            position: absolute;
            left: -13px;
            top: 0;
            width: 26px;
            height: 26px;
            background-color: #F6BE00;
            border-radius: 50%;
            border: 3px solid #fff;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: #004C99;
        }
        .timeline-item:last-child {
            border-left: none;
        }
    </style>
</head>
<body class="p-4 md:p-8">
    
    <!-- Main Header Section -->
    <header class="text-center mb-12">
        <img src="https://www2.sesc.com.br/wps/wcm/connect/10777ce7-b080-4966-a36c-2f9611681283/logo_Sesc_Horizontal_cores.png?MOD=AJPERES&CACHEID=10777ce7-b080-4966-a36c-2f9611681283" alt="Logomarca do Sesc" class="mx-auto w-32 md:w-48 mb-4">
        <h1 class="text-4xl md:text-5xl font-extrabold text-[#004C99] mb-2">
            Resultados do 1° Semestre ✨
        </h1>
        <p class="text-lg md:text-xl font-medium text-gray-600">
            Acompanhe os resultados do Centro de Atividades Sesc Porto Seguro.
        </p>
    </header>

    <!-- Tab Navigation -->
    <nav class="flex justify-center mb-8 border-b-2 border-gray-200">
        <button id="tab-orcamento-btn" class="tab-button active py-4 px-6 md:px-12 text-lg md:text-xl font-medium text-gray-500 hover:text-[#004C99] transition-colors duration-300">
            Orçamento
        </button>
        <button id="tab-social-btn" class="tab-button py-4 px-6 md:px-12 text-lg md:text-xl font-medium text-gray-500 hover:text-[#004C99] transition-colors duration-300">
            Produção Social
        </button>
        <button id="tab-perfil-btn" class="tab-button py-4 px-6 md:px-12 text-lg md:text-xl font-medium text-gray-500 hover:text-[#004C99] transition-colors duration-300">
            Perfil da Unidade
        </button>
        <button id="tab-investimentos-btn" class="tab-button py-4 px-6 md:px-12 text-lg md:text-xl font-medium text-gray-500 hover:text-[#004C99] transition-colors duration-300">
            Investimentos
        </button>
    </nav>

    <!-- Tab Content Container -->
    <div class="bg-white p-6 md:p-10 rounded-2xl shadow-xl">
        
        <!-- Orçamento Tab Content -->
        <div id="tab-orcamento" class="tab-content active">

            <!-- Overall Summary Section - Despesas -->
            <section class="mb-12">
                <h2 class="text-2xl md:text-3xl font-bold text-[#004C99] mb-6 text-center">Balanço Geral das Despesas</h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 text-center">
                    <div class="bg-[#EBF5FF] p-6 rounded-xl shadow-inner card">
                        <p class="text-sm font-semibold text-[#004C99]">Total Orçado</p>
                        <p class="text-2xl md:text-3xl font-bold text-[#004C99] mt-2">R$ 14.7M</p>
                    </div>
                    <div class="bg-gray-100 p-6 rounded-xl shadow-inner card">
                        <p class="text-sm font-semibold text-gray-600">Realizado Acumulado</p>
                        <p class="text-2xl md:text-3xl font-bold text-gray-800 mt-2">R$ 7.7M</p>
                    </div>
                    <div class="bg-[#FFF7E3] p-6 rounded-xl shadow-inner card">
                        <p class="text-sm font-semibold text-[#F6BE00]">Disponível Final</p>
                        <p class="text-2xl md:text-3xl font-bold text-[#F6BE00] mt-2">R$ 7.0M</p>
                    </div>
                </div>
                <p class="text-center text-gray-500 mt-4 text-sm md:text-base">
                    O orçamento de despesas foi executado em **52.19%** até o momento.
                </p>
                <div class="mt-8 bg-gray-100 p-6 rounded-xl border border-gray-300">
                    <h4 class="font-bold text-lg mb-4 text-center">Execução Orçamentária das Despesas</h4>
                    <div class="flex items-end justify-between space-x-4 h-48">
                        <div class="w-1/3 bg-[#004C99] rounded-lg flex flex-col justify-end" style="height: 100%;">
                            <span class="text-xs text-center text-white font-bold p-1">100%</span>
                        </div>
                        <div class="w-1/3 bg-gray-500 rounded-lg flex flex-col justify-end" style="height: 52.19%;">
                            <span class="text-xs text-center text-white font-bold p-1">52.19%</span>
                        </div>
                        <div class="w-1/3 bg-[#F6BE00] rounded-lg flex flex-col justify-end" style="height: 47.81%;">
                            <span class="text-xs text-center text-white font-bold p-1">47.81%</span>
                        </div>
                    </div>
                    <div class="flex justify-between mt-2 text-sm text-center font-semibold">
                        <span class="w-1/3 text-[#004C99]">Orçado</span>
                        <span class="w-1/3 text-gray-600">Realizado</span>
                        <span class="w-1/3 text-[#F6BE00]">Disponível</span>
                    </div>
                </div>
            </section>
            
            <!-- Overall Summary Section - Receitas -->
            <section>
                <h2 class="text-2xl md:text-3xl font-bold text-[#004C99] mb-6 text-center">Balanço Geral das Receitas</h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 text-center">
                    <div class="bg-[#EBF5FF] p-6 rounded-xl shadow-inner card">
                        <p class="text-sm font-semibold text-[#004C99]">Total Orçado</p>
                        <p class="text-2xl md:text-3xl font-bold text-[#004C99] mt-2">R$ 1.86M</p>
                    </div>
                    <div class="bg-gray-100 p-6 rounded-xl shadow-inner card">
                        <p class="text-sm font-semibold text-gray-600">Realizado Acumulado</p>
                        <p class="text-2xl md:text-3xl font-bold text-gray-800 mt-2">R$ 1.19M</p>
                    </div>
                    <div class="bg-[#FFF7E3] p-6 rounded-xl shadow-inner card">
                        <p class="text-sm font-semibold text-[#C8102E]">Disponível a Realizar</p>
                        <p class="text-2xl md:text-3xl font-bold text-[#C8102E] mt-2">R$ 0.67M</p>
                    </div>
                </div>
                <p class="text-center text-gray-500 mt-4 text-sm md:text-base">
                    A receita foi realizada em **63.82%** do total orçado.
                </p>
                 <div class="mt-8 bg-gray-100 p-6 rounded-xl border border-gray-300 flex flex-col items-center">
                    <h4 class="font-bold text-lg mb-4 text-center">Realização da Receita</h4>
                    <div class="pie-chart-receitas relative flex items-center justify-center text-xl font-bold text-white">
                        <span class="absolute">63.82%</span>
                    </div>
                    <div class="flex justify-center gap-4 mt-4">
                        <div class="flex items-center">
                            <span class="w-3 h-3 bg-[#004C99] rounded-full mr-2"></span>
                            <p class="text-sm">Realizado (63.82%)</p>
                        </div>
                        <div class="flex items-center">
                            <span class="w-3 h-3 bg-gray-300 rounded-full mr-2"></span>
                            <p class="text-sm">Falta Realizar (36.18%)</p>
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- Aonde a Grana Sobrou? (Despesas) -->
            <section class="mb-12">
                <h3 class="text-xl md:text-2xl font-bold text-[#F6BE00] mb-6 flex items-center justify-center lg:justify-start">
                    <span class="mr-2">💰</span> Aonde a Grana Sobrou? (Despesas)
                </h3>
                 <p class="text-sm text-gray-500 mb-4">
                    Oportunidades de redirecionar recursos para outras áreas estratégicas.
                </p>
                <div class="space-y-6">
                    <div class="card bg-[#FFF7E3] p-6 rounded-2xl shadow-md border border-[#F6BE00]">
                        <p class="font-bold text-[#004C99]">Superávit de R$ 928.911,54</p>
                        <p class="text-sm text-gray-500 mt-1"><span class="font-bold text-base text-[#004C99]">Centro de Custo: Apoio à Prog Final</span></p>
                        <p class="text-sm text-gray-500">Conta: Outros Serviços de Terceiros</p>
                        <button onclick="showInsight('apoio-superavit')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Destaque ✨</button>
                    </div>
                    <div class="card bg-[#FFF7E3] p-6 rounded-2xl shadow-md border border-[#F6BE00]">
                        <p class="font-bold text-[#004C99]">Superávit de R$ 393.774,42</p>
                        <p class="text-sm text-gray-500 mt-1"><span class="font-bold text-base text-[#004C99]">Centro de Custo: Manutenção da Unidade</span></p>
                        <p class="text-sm text-gray-500">Conta: Outros Serviços de Terceiros</p>
                        <button onclick="showInsight('manutencao-superavit')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Destaque ✨</button>
                    </div>
                </div>
            </section>

            <!-- Oportunidades de Otimização (Despesas) -->
            <section>
                <h3 class="text-xl md:text-2xl font-bold text-[#C8102E] mb-6 flex items-center justify-center lg:justify-start">
                    <span class="mr-2">💡</span> Oportunidades de Otimização (Despesas)
                </h3>
                <p class="text-sm text-gray-500 mb-4">
                    Estas áreas exigem atenção para alinhar os gastos com o planejamento.
                </p>
                <div class="space-y-6">
                    <div class="card bg-[#FFF0F2] p-6 rounded-2xl shadow-md border border-[#C8102E]">
                        <p class="font-bold text-[#C8102E]">Analisar gastos em R$ 250.000,00</p>
                        <p class="text-sm text-gray-500 mt-1"><span class="font-bold text-base text-[#C8102E]">Centro de Custo: Música</span></p>
                        <p class="text-sm text-gray-500">Conta: Outros Serviços de Terceiros</p>
                        <button onclick="showInsight('musica-despesa')" class="mt-4 px-4 py-2 bg-[#F6BE00] text-[#004C99] rounded-full font-bold shadow-md hover:bg-[#FFD966] transition-colors duration-300">Gerar Análise ✨</button>
                    </div>
                    <div class="card bg-[#FFF0F2] p-6 rounded-2xl shadow-md border border-[#C8102E]">
                        <p class="font-bold text-[#C8102E]">Revisar orçamento de R$ 47.052,79</p>
                        <p class="text-sm text-gray-500 mt-1"><span class="font-bold text-base text-[#C8102E]">Centro de Custo: Manutenção da Unidade</span></p>
                        <p class="text-sm text-gray-500">Conta: Locação de Mão de Obra</p>
                        <button onclick="showInsight('manutencao-despesa')" class="mt-4 px-4 py-2 bg-[#F6BE00] text-[#004C99] rounded-full font-bold shadow-md hover:bg-[#FFD966] transition-colors duration-300">Gerar Análise ✨</button>
                    </div>
                </div>
            </section>

        </div>

        <!-- Produção Social Tab Content -->
        <div id="tab-social" class="tab-content">
            <!-- Panorama Global Section -->
            <section class="mb-12">
                <h2 class="text-2xl md:text-3xl font-bold text-[#004C99] mb-6 text-center">Panorama Global da Produção Social</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 text-center">
                    <div class="bg-[#EBF5FF] p-6 rounded-2xl shadow-xl border border-[#004C99] card">
                        <p class="text-sm font-semibold text-[#004C99]">Pessoas Atendidas (Previsto)</p>
                        <p class="text-3xl md:text-4xl font-bold text-[#004C99] mt-2">51.295</p>
                        <p class="text-sm text-gray-500 mt-2">O número total planejado para as atividades.</p>
                    </div>
                    <div class="bg-gray-100 p-6 rounded-2xl shadow-xl border border-gray-300 card">
                        <p class="text-sm font-semibold text-gray-600">Pessoas Atendidas (Realizado)</p>
                        <p class="text-3xl md:text-4xl font-bold text-gray-800 mt-2">55.228</p>
                        <p class="text-sm text-gray-500 mt-2">O número total de pessoas que participaram.</p>
                    </div>
                    <div class="bg-[#FFF7E3] p-6 rounded-2xl shadow-xl border border-[#F6BE00] card">
                        <p class="text-sm font-semibold text-[#F6BE00]">Cumprimento da Meta</p>
                        <p class="text-3xl md:text-4xl font-bold text-[#F6BE00] mt-2">107.67%</p>
                        <p class="text-sm text-gray-500 mt-2">No geral, superamos a nossa meta de atendimento!</p>
                    </div>
                </div>
                <!-- Animated Progress Bar for Global Fulfillment -->
                <div class="mt-8 bg-gray-100 p-6 rounded-xl border border-gray-300">
                    <h4 class="font-bold text-lg mb-4 text-center">Cumprimento da Meta de Pessoas Atendidas</h4>
                    <div class="relative pt-1">
                        <div class="overflow-hidden h-6 text-xs flex rounded bg-gray-200">
                            <div class="animated-progress-bar shadow-none flex flex-col text-center whitespace-nowrap text-white justify-center bg-[#F6BE00]"></div>
                        </div>
                        <div class="flex justify-between mt-2 text-sm font-semibold">
                            <span>0%</span>
                            <span>100%</span>
                            <span class="absolute left-1/2 -translate-x-1/2 text-gray-500 font-bold">Meta</span>
                            <span class="absolute" style="left: 107.67%;">107.67%</span>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Credenciamento Section -->
            <section class="mb-12">
                <h2 class="text-2xl md:text-3xl font-bold text-[#F6BE00] mb-6 text-center">💳 Resultados do Credenciamento</h2>
                <p class="text-center text-gray-500 text-lg mb-6">
                    Atingimos **94,98%** da nossa meta de credenciamento pleno para o período.
                </p>
                <div class="flex flex-col items-center gap-6">
                    <div class="pie-chart-credenciamento relative flex items-center justify-center text-xl font-bold text-[#004C99]">
                        <span class="absolute">94.98%</span>
                    </div>
                    <div class="flex justify-center gap-4 mt-4">
                        <div class="flex items-center">
                            <span class="w-3 h-3 bg-[#C8102E] rounded-full mr-2"></span>
                            <p class="text-sm">Realizado (94.98%)</p>
                        </div>
                        <div class="flex items-center">
                            <span class="w-3 h-3 bg-gray-300 rounded-full mr-2"></span>
                            <p class="text-sm">Falta Realizar (5.02%)</p>
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- Success Projects Section -->
            <section class="mb-12">
                <h2 class="text-2xl md:text-3xl font-bold text-[#F6BE00] mb-6 text-center">🎉 Atividades de Sucesso! (acima de 110%)</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="card bg-[#FFF7E3] p-6 rounded-2xl shadow-md border border-[#F6BE00] text-center">
                        <p class="text-4xl mb-4">🎶</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">Música</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Apresentações</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">292,55% da presença prevista!</p>
                        <button onclick="showSocialInsight('musica')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Destaque ✨</button>
                    </div>
                    <div class="card bg-[#FFF7E3] p-6 rounded-2xl shadow-md border border-[#F6BE00] text-center">
                        <p class="text-4xl mb-4">🤸</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">Recreação</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Multipráticas Recreativas</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">149,29% da presença prevista!</p>
                         <button onclick="showSocialInsight('recreacao')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Destaque ✨</button>
                    </div>
                    <div class="card bg-[#FFF7E3] p-6 rounded-2xl shadow-md border border-[#F6BE00] text-center">
                        <p class="text-4xl mb-4">👥</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">Valorização Social</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Ações Formativas</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">194,92% das pessoas atendidas!</p>
                         <button onclick="showSocialInsight('valorizacao')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Destaque ✨</button>
                    </div>
                    <div class="card bg-[#FFF7E3] p-6 rounded-2xl shadow-md border border-[#F6BE00] text-center">
                        <p class="text-4xl mb-4">🏖️</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">Recreação - Colônias</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Colônias Recreativas</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">Dobramos o número de eventos!</p>
                         <button onclick="showSocialInsight('colonias')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Destaque ✨</button>
                    </div>
                </div>
            </section>

            <!-- Ideal Projects Section -->
            <section class="mb-12">
                <h2 class="text-2xl md:text-3xl font-bold text-[#004C99] mb-6 text-center">🎯 Metas na Medida Certa! (90% a 110%)</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="card bg-[#EBF5FF] p-6 rounded-2xl shadow-md border border-[#004C99] text-center">
                        <p class="text-4xl mb-4">🎓</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">Educação Infantil</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Creche</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">103,33% de matrículas!</p>
                    </div>
                    <div class="card bg-[#EBF5FF] p-6 rounded-2xl shadow-md border border-[#004C99] text-center">
                        <p class="text-4xl mb-4">📚</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">Ensino Fundamental</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Anos Finais</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">97% de matrículas!</p>
                    </div>
                    <div class="card bg-[#EBF5FF] p-6 rounded-2xl shadow-md border border-[#004C99] text-center">
                        <p class="text-4xl mb-4">🏋️</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">Saúde</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Sessão Diagnóstica</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">101,26% da presença!</p>
                    </div>
                    <div class="card bg-[#EBF5FF] p-6 rounded-2xl shadow-md border border-[#004C99] text-center">
                        <p class="text-4xl mb-4">🥳</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">Recreação</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Festas</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">94,33% da presença prevista!</p>
                    </div>
                    <div class="card bg-[#EBF5FF] p-6 rounded-2xl shadow-md border border-[#004C99] text-center">
                        <p class="text-4xl mb-4">🎓</p>
                        <p class="font-bold text-[#004C99] text-xl md:text-2xl">EJA</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Séries/Etapas</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">100% de pessoas atendidas!</p>
                    </div>
                </div>
            </section>


            <!-- Deficit Projects Section -->
            <section>
                <h2 class="text-2xl md:text-3xl font-bold text-[#C8102E] mb-6 text-center">🚨 Onde Precisamos de Atenção (abaixo de 90%)</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="card bg-[#FFF0F2] p-6 rounded-2xl shadow-md border border-[#C8102E] text-center">
                        <p class="text-4xl mb-4">🎭</p>
                        <p class="font-bold text-[#C8102E] text-xl md:text-2xl">Artes Cênicas</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Apresentações</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">50% das apresentações</p>
                        <button onclick="showSocialInsight('artes-cenicas')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Análise ✨</button>
                    </div>
                    <div class="card bg-[#FFF0F2] p-6 rounded-2xl shadow-md border border-[#C8102E] text-center">
                        <p class="text-4xl mb-4">🦷</p>
                        <p class="font-bold text-[#C8102E] text-xl md:text-2xl">Saúde Bucal</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Proced. Comp.</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">29,36% dos procedimentos</p>
                         <button onclick="showSocialInsight('saude-bucal')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Análise ✨</button>
                    </div>
                    <div class="card bg-[#FFF0F2] p-6 rounded-2xl shadow-md border border-[#C8102E] text-center">
                        <p class="text-4xl mb-4">🏆</p>
                        <p class="font-bold text-[#C8102E] text-xl md:text-2xl">DFE - Competições</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Competições Fisico-Esportivas</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">12,04% da presença</p>
                         <button onclick="showSocialInsight('dfe')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Análise ✨</button>
                    </div>
                    <div class="card bg-[#FFF0F2] p-6 rounded-2xl shadow-md border border-[#C8102E] text-center">
                        <p class="text-4xl mb-4">📖</p>
                        <p class="font-bold text-[#C8102E] text-xl md:text-2xl">Biblioteca</p>
                        <p class="text-sm text-gray-500 mt-2">Modalidade: Acesso a Recursos</p>
                        <p class="text-lg font-bold text-[#C8102E] mt-2">49,92% das pessoas atendidas</p>
                         <button onclick="showSocialInsight('biblioteca')" class="mt-4 px-4 py-2 bg-[#004C99] text-white rounded-full font-bold shadow-md hover:bg-blue-800 transition-colors duration-300">Gerar Análise ✨</button>
                    </div>
                </div>
            </section>

        </div>

        <!-- Perfil da Unidade Tab Content -->
        <div id="tab-perfil" class="tab-content">
            <h2 class="text-2xl md:text-3xl font-bold text-[#004C99] mb-6 text-center">Perfil da Unidade Sesc Porto Seguro</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <!-- Colaboradores Section -->
                <div class="p-6 bg-gray-100 rounded-xl shadow-md flex flex-col items-center justify-center">
                    <h3 class="font-bold text-lg text-gray-800 mb-4">Colaboradores</h3>
                    <div class="w-full max-w-xs">
                        <div class="relative pt-1">
                            <div class="flex mb-2 items-center justify-between">
                                <div>
                                    <span class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded-full text-[#C8102E] bg-pink-200">
                                        Mulheres (58)
                                    </span>
                                </div>
                                <div class="text-right">
                                    <span class="text-xs font-semibold inline-block text-gray-600">
                                        60.4%
                                    </span>
                                </div>
                            </div>
                            <div class="overflow-hidden h-4 flex rounded-full bg-pink-200">
                                <div style="width:60.4%" class="shadow-none flex flex-col text-center whitespace-nowrap text-white justify-center bg-[#C8102E]"></div>
                            </div>
                        </div>
                        <div class="relative pt-1 mt-4">
                            <div class="flex mb-2 items-center justify-between">
                                <div>
                                    <span class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded-full text-[#004C99] bg-blue-200">
                                        Homens (38)
                                    </span>
                                </div>
                                <div class="text-right">
                                    <span class="text-xs font-semibold inline-block text-gray-600">
                                        39.6%
                                    </span>
                                </div>
                            </div>
                            <div class="overflow-hidden h-4 flex rounded-full bg-blue-200">
                                <div style="width:39.6%" class="shadow-none flex flex-col text-center whitespace-nowrap text-white justify-center bg-[#004C99]"></div>
                            </div>
                        </div>
                    </div>
                    <p class="text-gray-600 mt-6 text-center text-sm">
                        Total de 96 colaboradores dedicados à missão do Sesc.
                    </p>
                </div>
                <!-- Estrutura da Unidade Section -->
                <div class="p-6 bg-gray-100 rounded-xl shadow-md">
                    <h3 class="font-bold text-lg text-gray-800 mb-4 text-center">Estrutura da Unidade</h3>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="p-4 bg-white rounded-lg shadow-sm card">
                            <p class="text-2xl mb-2 text-[#004C99]">🎨</p>
                            <p class="font-bold text-[#004C99]">Módulo Cultura</p>
                            <ul class="list-disc list-inside mt-1 text-xs text-gray-500">
                                <li>Cineteatro (190 lugares)</li>
                                <li>Café-teatro</li>
                                <li>Biblioteca</li>
                                <li>Foyer para exposições</li>
                            </ul>
                        </div>
                        <div class="p-4 bg-white rounded-lg shadow-sm card">
                            <p class="text-2xl mb-2 text-[#004C99]">💪</p>
                            <p class="font-bold text-[#004C99]">Módulo Convivência</p>
                            <ul class="list-disc list-inside mt-1 text-xs text-gray-500">
                                <li>Academia</li>
                                <li>Sala de pilates e dança</li>
                                <li>Cozinha didática</li>
                                <li>Sala de habilidades manuais</li>
                                <li>Sala de corte e costura</li>
                            </ul>
                        </div>
                        <div class="p-4 bg-white rounded-lg shadow-sm card">
                            <p class="text-2xl mb-2 text-[#004C99]">📚</p>
                            <p class="font-bold text-[#004C99]">Módulo Educacional</p>
                            <ul class="list-disc list-inside mt-1 text-xs text-gray-500">
                                <li>Salas de aula (educação infantil e fundamental)</li>
                                <li>Biblioteca escolar</li>
                                <li>Refeitório e pátios</li>
                                <li>Laboratórios e sala de AEE</li>
                            </ul>
                        </div>
                        <div class="p-4 bg-white rounded-lg shadow-sm card">
                            <p class="text-2xl mb-2 text-[#004C99]">🏊‍♂️</p>
                            <p class="font-bold text-[#004C99]">Área de Lazer</p>
                            <ul class="list-disc list-inside mt-1 text-xs text-gray-500">
                                <li>Piscina infantil e semi-olímpica</li>
                                <li>Campo de grama sintética</li>
                                <li>Quadra poliesportiva coberta</li>
                                <li>Playground, lanchonete e quiosques</li>
                            </ul>
                        </div>
                        <div class="p-4 bg-white rounded-lg shadow-sm card col-span-1 md:col-span-2">
                            <p class="text-2xl mb-2 text-[#004C99]">💼</p>
                            <p class="font-bold text-[#004C99]">Módulo Administrativo</p>
                            <ul class="list-disc list-inside mt-1 text-xs text-gray-500">
                                <li>2 consultórios odontológicos</li>
                                <li>Central de Relacionamento</li>
                                <li>Sala de avaliação física</li>
                                <li>Área de administração</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- New section for testimonials -->
            <section class="mt-12">
                <h2 class="text-2xl md:text-3xl font-bold text-[#F6BE00] mb-6 text-center">💬 O que dizem sobre nós?</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Testimonial 1 -->
                    <div class="p-6 bg-white rounded-2xl shadow-md border border-gray-200 card flex flex-col items-center text-center">
                        <p class="text-5xl mb-4">😊</p>
                        <p class="text-xl text-gray-500 font-serif leading-relaxed">
                            "A Unidade do Sesc Porto Seguro é um exemplo de excelência. A equipe é sempre muito atenciosa e a qualidade dos serviços oferecidos é notável."
                        </p>
                        <p class="mt-4 text-sm font-semibold text-gray-800">- Um cliente satisfeito</p>
                    </div>
                    <!-- Testimonial 2 -->
                    <div class="p-6 bg-white rounded-2xl shadow-md border border-gray-200 card flex flex-col items-center text-center">
                        <p class="text-5xl mb-4">🥳</p>
                        <p class="text-xl text-gray-500 font-serif leading-relaxed">
                            "Adorei a diversidade de atividades. Encontrei opções incríveis para a minha família na área de lazer e na cultura, o que enriqueceu muito nossos momentos de folga."
                        </p>
                        <p class="mt-4 text-sm font-semibold text-gray-800">- Um frequentador assíduo</p>
                    </div>
                    <!-- Testimonial 3 -->
                    <div class="p-6 bg-white rounded-2xl shadow-md border border-gray-200 card flex flex-col items-center text-center">
                        <p class="text-5xl mb-4">❤️</p>
                        <p class="text-xl text-gray-500 font-serif leading-relaxed">
                            "É ótimo ver a paixão e o cuidado com que os colaboradores se dedicam ao trabalho. Fico feliz em fazer parte de uma comunidade tão acolhedora e inspiradora."
                        </p>
                        <p class="mt-4 text-sm font-semibold text-gray-800">- Um associado</p>
                    </div>
                </div>
            </section>
        </div>

        <!-- Investimentos Tab Content -->
        <div id="tab-investimentos" class="tab-content">
            <h2 class="text-2xl md:text-3xl font-bold text-[#004C99] mb-6 text-center">Investimentos e Melhorias em 2025</h2>
            <div class="relative max-w-2xl mx-auto">
                <div class="space-y-12">
                    <div class="timeline-item">
                        <div class="timeline-point text-white bg-[#004C99] drop-shadow-lg">1</div>
                        <div class="p-6 bg-white rounded-lg shadow-md border border-gray-200 ml-4 card">
                            <p class="font-bold text-lg text-[#004C99] mb-2">Novo mobiliário para educação infantil</p>
                            <p class="text-sm text-gray-600">Investimento para modernizar e oferecer mais conforto e segurança para as crianças.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-point text-white bg-[#004C99] drop-shadow-lg">2</div>
                        <div class="p-6 bg-white rounded-lg shadow-md border border-gray-200 ml-4 card">
                            <p class="font-bold text-lg text-[#004C99] mb-2">Novos equipamentos para a academia</p>
                            <p class="text-sm text-gray-600">Melhoria para os frequentadores, com equipamentos modernos e de alta performance.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-point text-white bg-[#004C99] drop-shadow-lg">3</div>
                        <div class="p-6 bg-white rounded-lg shadow-md border border-gray-200 ml-4 card">
                            <p class="font-bold text-lg text-[#004C99] mb-2">Aquisição do Playground</p>
                            <p class="text-sm text-gray-600">Novo espaço para o lazer das crianças, promovendo diversão e desenvolvimento físico.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-point text-white bg-[#004C99] drop-shadow-lg">4</div>
                        <div class="p-6 bg-white rounded-lg shadow-md border border-gray-200 ml-4 card">
                            <p class="font-bold text-lg text-[#004C99] mb-2">Novos equipamentos para nutrição</p>
                            <p class="text-sm text-gray-600">Aprimoramento do serviço, com foco em qualidade e eficiência para os alunos.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-point text-white bg-[#004C99] drop-shadow-lg">5</div>
                        <div class="p-6 bg-white rounded-lg shadow-md border border-gray-200 ml-4 card">
                            <p class="font-bold text-lg text-[#004C99] mb-2">Reforma do pátio da escola</p>
                            <p class="text-sm text-gray-600">Ambiente renovado para o convívio e atividades recreativas dos estudantes.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-point text-white bg-[#004C99] drop-shadow-lg">6</div>
                        <div class="p-6 bg-white rounded-lg shadow-md border border-gray-200 ml-4 card">
                            <p class="font-bold text-lg text-[#004C99] mb-2">Aquisição de novos equipamentos para o teatro</p>
                            <p class="text-sm text-gray-600">Modernização do Cineteatro para oferecer eventos culturais de alta qualidade.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-point text-white bg-[#004C99] drop-shadow-lg">7</div>
                        <div class="p-6 bg-white rounded-lg shadow-md border border-gray-200 ml-4 card">
                            <p class="font-bold text-lg text-[#004C99] mb-2">Novos equipos para a odontologia</p>
                            <p class="text-sm text-gray-600">Equipamentos de ponta para os consultórios, garantindo mais qualidade nos atendimentos.</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-point text-white bg-[#004C99] drop-shadow-lg">8</div>
                        <div class="p-6 bg-white rounded-lg shadow-md border border-gray-200 ml-4 card">
                            <p class="font-bold text-lg text-[#004C99] mb-2">Efetivação dos instrutores de CVS</p>
                            <p class="text-sm text-gray-600">Fortalecimento da equipe de instrutores, garantindo a continuidade e a qualidade dos serviços.</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="flex flex-col items-center justify-center text-center mt-12 px-4">
                <img src="https://placehold.co/400x400/D0D0CE/FFFFFF?text=QR+Code+para+Pesquisa" alt="QR Code para pesquisa" class="w-48 h-48 mb-6">
                <p class="text-gray-600 text-lg md:text-xl max-w-lg mx-auto">
                    Agora é sua vez, dê sua opinião e participe da construção do projeto de melhorias do Sesc Porto Seguro.
                </p>
            </div>
        </div>

    </div>

    <!-- The Modal -->
    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close-button">&times;</span>
            <h3 id="modal-title" class="text-2xl font-bold text-[#004C99] mb-4 text-center"></h3>
            <div id="modal-body" class="text-gray-700">
                <p id="gemini-response" class="text-sm"></p>
            </div>
            <div id="loading" class="text-center mt-4 hidden">
                <div class="animate-spin rounded-full h-8 w-8 border-b-2 border-gray-900 mx-auto"></div>
                <p class="text-gray-500 mt-2">Gerando insights com o Gemini...</p>
            </div>
        </div>
    </div>
    
    <!-- Footer with a playful message -->
    <footer class="text-center mt-12 text-gray-500 text-sm">
        <p>Análise de Dados feita com amor e alguns cliques. 😊</p>
    </footer>

    <script>
        // Modal logic
        var modal = document.getElementById("myModal");
        var span = document.getElementsByClassName("close-button")[0];
        
        span.onclick = function() {
          modal.style.display = "none";
        }
        
        window.onclick = function(event) {
          if (event.target == modal) {
            modal.style.display = "none";
          }
        }
        
        // API call and display logic for Orçamento tab
        async function showInsight(context) {
            modal.style.display = "block";
            document.getElementById('modal-title').innerText = "Análise Gerada pelo Gemini";
            const geminiResponseElem = document.getElementById('gemini-response');
            const loadingElem = document.getElementById('loading');
            geminiResponseElem.innerText = "";
            loadingElem.style.display = "block";

            let prompt;
            let title;

            switch (context) {
                case 'musica-despesa':
                    prompt = "Gere uma breve análise construtiva (50 palavras) para o Centro de Custo 'Música' que teve um déficit de R$ 250.000,00 na conta 'Outros Serviços de Terceiros'. Sugira o que pode ter causado o gasto elevado.";
                    title = "Oportunidades no Orçamento de Música";
                    break;
                case 'manutencao-despesa':
                    prompt = "Crie uma análise e sugestão de melhoria (50 palavras) para o Centro de Custo 'Manutenção da Unidade' que teve um déficit de R$ 47.052,79 na conta 'Locação de Mão de Obra'.";
                    title = "Oportunidades no Orçamento de Manutenção";
                    break;
                case 'apoio-superavit':
                    prompt = "Crie um breve texto de celebração e destaque (50 palavras) para o superávit de R$ 928.911,54 no Centro de Custo 'Apoio à Prog Final'. Mencione que o valor pode ser realocado para outras áreas.";
                    title = "Destaque de Sucesso Financeiro";
                    break;
                case 'manutencao-superavit':
                    prompt = "Crie um breve texto de celebração e destaque (50 palavras) para o superávit de R$ 393.774,42 no Centro de Custo 'Manutenção da Unidade'. Mencione que o valor pode ser realocado para outras áreas.";
                    title = "Destaque de Sucesso Financeiro";
                    break;
                default:
                    prompt = "Análise não disponível para este item.";
                    title = "Erro";
            }
            
            document.getElementById('modal-title').innerText = title;

            // Simulating API call with hardcoded responses
            const responses = {
                'musica-despesa': "O alto déficit em 'Música' pode ser resultado de custos inesperados com logística e contratação de artistas. Uma melhoria seria renegociar contratos ou buscar parcerias estratégicas para reduzir despesas fixas. Planejar com antecedência ajuda a evitar surpresas.",
                'manutencao-despesa': "O déficit na manutenção pode indicar a necessidade de uma análise mais profunda dos contratos de terceirização. É vital comparar propostas de diferentes fornecedores e auditar o escopo dos serviços, garantindo que o valor pago esteja alinhado ao serviço prestado. Otimizar é a palavra-chave.",
                'apoio-superavit': "Que ótima notícia! 🎉 O superávit de R$ 928 mil em 'Apoio à Programação Final' mostra uma gestão eficiente. Esse valor pode ser realocado para impulsionar projetos que precisam de mais investimento, como a divulgação de novos eventos ou a compra de equipamentos.",
                'manutencao-superavit': "O superávit de R$ 393 mil em 'Manutenção da Unidade' demonstra uma gestão de custos exemplar! Esse saldo pode ser usado para melhorias estruturais, como a modernização de espaços ou a implementação de tecnologias de economia de energia, agregando valor à unidade.",
                'default': "Análise não disponível para este item."
            };
            
            await new Promise(r => setTimeout(r, 1000)); // Simulate loading time
            geminiResponseElem.innerText = responses[context] || responses['default'];
            loadingElem.style.display = "none";
        }
        
        // API call and display logic for Produção Social tab
        async function showSocialInsight(context) {
            modal.style.display = "block";
            document.getElementById('modal-title').innerText = "Análise Gerada pelo Gemini";
            const geminiResponseElem = document.getElementById('gemini-response');
            const loadingElem = document.getElementById('loading');
            geminiResponseElem.innerText = "";
            loadingElem.style.display = "block";

            let prompt;
            let title;

            switch (context) {
                case 'musica':
                    prompt = "Gere uma mensagem curta e animada (30 palavras) para celebrar o sucesso da atividade 'Música - Apresentações' que superou 292,55% da presença prevista. Use emojis.";
                    title = "O sucesso da Música!";
                    break;
                case 'recreacao':
                    prompt = "Gere uma mensagem curta e animada (30 palavras) para celebrar o sucesso da atividade 'Recreação - Multipráticas Recreativas' que superou 149,29% da presença prevista. Use emojis.";
                    title = "Recreação em Alta!";
                    break;
                case 'valorizacao':
                    prompt = "Gere uma mensagem curta e animada (30 palavras) para celebrar o sucesso da atividade 'Valorização Social - Ações Formativas' que superou 194,92% das pessoas atendidas. Use emojis.";
                    title = "Valorização Social Brilhando!";
                    break;
                case 'colonias':
                    prompt = "Gere uma mensagem curta e animada (30 palavras) para celebrar o sucesso da atividade 'Recreação - Colônias Recreativas' que dobrou o número de eventos. Use emojis.";
                    title = "Sucesso nas Colônias!";
                    break;
                case 'artes-cenicas':
                    prompt = "Gere uma breve análise (50 palavras) sobre a baixa realização de 'Artes Cênicas - Apresentações' (50% do previsto). Sugira formas de aumentar a divulgação para atrair mais público.";
                    title = "Oportunidades em Artes Cênicas";
                    break;
                case 'saude-bucal':
                    prompt = "Gere uma breve análise (50 palavras) sobre a baixa realização de 'Saúde Bucal - Procedimentos Complementares' (29,36% do previsto). Sugira ideias para aumentar a procura pelos procedimentos.";
                    title = "Oportunidades em Saúde Bucal";
                    break;
                case 'dfe':
                    prompt = "Gere uma breve análise (50 palavras) sobre a baixa realização de 'DFE - Competições Físico-Esportivas' (12,04% de presença). Sugira estratégias para impulsionar a participação.";
                    title = "Oportunidades no DFE";
                    break;
                case 'biblioteca':
                    prompt = "Gere uma breve análise (50 palavras) sobre a baixa realização de 'Biblioteca - Acesso a Recursos' (49,92% das pessoas atendidas). Sugira ações para atrair mais público.";
                    title = "Oportunidades na Biblioteca";
                    break;
                default:
                    prompt = "Análise não disponível para este item.";
                    title = "Erro";
            }
            
            document.getElementById('modal-title').innerText = title;

            // Simulating API call with hardcoded responses
            const responses = {
                'musica': "Uau! A música do Sesc Porto Seguro está bombando! 🎶 Superamos a meta de público em quase 300%. Sinal de que a curadoria está no caminho certo. Continuem assim! ✨",
                'recreacao': "Recorde de diversão! 🎉 As atividades de recreação superaram 149% das expectativas. Isso mostra o quanto o público adora as nossas propostas lúdicas. Vamos manter a energia lá em cima! ✨",
                'valorizacao': "Que impacto! ✨ Ações formativas de valorização social atenderam quase o dobro de pessoas. Isso reforça a importância do nosso trabalho e o engajamento da comunidade em temas relevantes! Vamos com tudo! 💪",
                'colonias': "As colônias recreativas foram um sucesso! ☀️ Dobramos o número de eventos, mostrando que o planejamento e a demanda andam de mãos dadas. Mais diversão para todos! �",
                'artes-cenicas': "A baixa realização em 'Artes Cênicas' pode ter sido influenciada por uma divulgação limitada. Uma estratégia seria explorar parcerias com escolas e coletivos locais, além de usar as redes sociais para criar campanhas interativas que gerem expectativa e envolvam o público.",
                'saude-bucal': "Para aumentar a procura por procedimentos de saúde bucal, o Sesc pode criar campanhas de conscientização visualmente atrativas, destacando a importância da prevenção. Oferecer pacotes promocionais ou sessões de diagnóstico gratuitas pode ser um bom gatilho para atrair novos pacientes e gerar receita.",
                'dfe': "Para impulsionar a participação em competições do DFE, o Sesc pode investir em uma divulgação mais forte, tanto online quanto em locais estratégicos. A criação de ligas ou torneios com premiações atrativas também tende a aumentar o engajamento e a presença de público.",
                'biblioteca': "Para atrair mais pessoas à biblioteca, o Sesc pode modernizar o espaço, tornando-o mais acolhedor com áreas de leitura confortáveis. Além disso, eventos como clubes do livro e workshops de escrita criativa podem atrair um novo público e aumentar a frequência.",
                'default': "Análise não disponível para este item."
            };
            
            await new Promise(r => setTimeout(r, 1000)); // Simulate loading time
            geminiResponseElem.innerText = responses[context] || responses['default'];
            loadingElem.style.display = "none";
        }
        
        // Tab navigation logic
        document.addEventListener('DOMContentLoaded', () => {
            const tabs = document.querySelectorAll('.tab-button');
            const contents = document.querySelectorAll('.tab-content');
            const defaultTab = 'tab-orcamento';

            function activateTab(tabId) {
                tabs.forEach(t => t.classList.remove('active'));
                contents.forEach(c => c.classList.remove('active'));

                const targetTabBtn = document.getElementById(tabId + '-btn');
                const targetContent = document.getElementById(tabId);
                
                if (targetTabBtn && targetContent) {
                    targetTabBtn.classList.add('active');
                    targetContent.classList.add('active');
                }
            }

            tabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    const targetId = tab.id.replace('-btn', '');
                    activateTab(targetId);
                });
            });

            // Activate default tab on load
            activateTab(defaultTab);
        });
    </script>
</body>
</html>
```�
