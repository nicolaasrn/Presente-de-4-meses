<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Presente para Sofia</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"></script>
    <style>
       body {

            font-family: 'Arial', sans-serif;
            background-color: #fff;
            color: #9370db; /* Roxo */
            background-repeat: repeat;
            background-size: 5%;
            background-position: center;
            background-attachment: fixed;
            overflow-x: hidden;
        }

        .container {
    max-width: 800px;
    margin: -2cm auto 50px;  /* Ajustado para -2cm na margem superior */
    padding: 20px;
    position: relative; 
    z-index: 10;  
}



        h1, h2 {
            text-align: center;
            color: #20b2aa; /* Verde Água */
        }

        .timeline {
            position: relative;
            list-style: none;
        }

        .timeline li {
            margin-bottom: 30px;
        }

        .event {
            padding: 10px 20px;
            background-color: #1E90FF; /* Azul */
            display: inline-block;
            border-radius: 8px;
            margin-left: 60px;
            color: #ffffff; /* Branco */
            margin-left: calc(60px + 3cm); /* Adiciona 3cm à margem esquerda existente de 60px */
        }

        /* Título das seções em negrito */
        .event strong {
            font-weight: bold;
        }

        /* Intercalando as cores de fundo das seções */
        .timeline li:nth-child(odd) .event {
            background-color: #1E90FF; /* Azul */
        }

        .timeline li:nth-child(even) .event {
            background-color: #9370db; /* Roxo */
        }

        .event img, .event video {
            vertical-align: top;
            margin: 5px;
            max-width: 150px;
            border-radius: 8px;
            transition: transform 0.4s;
        }

        .event img:hover, .event video:hover {
            transform: scale(1.1);
        }

        .event video {
            max-height: 150px;
        }

        /* Centralizar a imagem na seção Moda & Compras */
        .event.centered img {
            display: block;
            margin: 5px auto;
        }

        /* Animação de entrada */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hidden {
            animation: fadeIn 2s forwards;
            visibility: hidden;
        }

        /* Estilo do Quiz */
        .quiz-container {
            text-align: center;
            margin-top: 30px;
        }

        .question {
            font-weight: bold;
            margin-bottom: 10px;
        }

        .options {
            list-style: none;
            padding: 0;
        }

        .options li {
            margin-bottom: 5px;
        }

        /* Adicionando estilos para os radio buttons */
        .options input[type="radio"] {
            display: none;
        }

        .options label {
            display: block;
            padding: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
            cursor: pointer;
        }

        .options input[type="radio"]:checked + label {
            background-color: #ddd;
}

.heart {
    position: absolute;
    width: 50px;
    height: 50px;
    background-color: pink;
    clip-path: polygon(
        50% 80%,
        100% 40%,
        100% 20%,
        50% 0%,
        0% 20%,
        0% 40%
    );
    opacity: 0.7;
    z-index: -1;
}

.highlight-text {
    background-color: rgba(255, 255, 255, 0.7); /* Branco com 70% de transparência */
    padding: 10px;
    border-radius: 8px;
    margin: 20px 0;
    color: #20b2aa; /* Verde Água */
    text-align: center; /* Alinhar o texto no centro */
}

.text-section p {
    color: #20b2aa; /* Verde Água */
    font-size: 20px;
}

#playMusicButton {
    display: block;
    margin: 2cm auto 1cm; /* Isso irá mover o botão 2cm para baixo */
}

#map {
    width: 100%;
    height: 400px;
}

/* Adicionando estilo para o layout da carta e da poesia */
.text-wrapper {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap; /* Caso os conteúdos sejam grandes e precisem ser envolvidos em linhas separadas */
    gap: 2rem;
}


/* Estilizando a poesia */
.poetry {
    font-style: italic;
    font-size: 20px; 
    text-align: center; /* Alinhar a poesia ao centro */
    margin: 0; /* Remover a margem padrão do parágrafo */
}

.text-content {
    background-color: rgba(255, 255, 255, 0.7); /* Branco com 70% de transparência */
    padding: 10px;
    border-radius: 8px;
    margin: 20px 0;
}


    </style>
</head>

<body>
    <audio id="backgroundMusic" controls loop style="display:none;">
    <source src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\oltremare.mp3.mp3" type="audio/mpeg">
    Seu navegador não suporta o elemento de áudio.
    </audio>

    <div class="container">
    <button id="playMusicButton" onclick="playMusic()">Clique para tocar música</button>

    <!-- Seção da Carta -->
    <div class="text-section text-content"> <!-- Aqui! -->
    <h1 class="highlight-text">Uma carta para Sofia</h1>
    <p>Querida Sofia,</p>
        
<p>Em cada batimento do meu coração, encontro um eco do nosso amor – um ritmo que dança entre nós, tecendo a melodia de uma canção que apenas nós dois conhecemos. Ao olhar para trás, para os momentos que compartilhamos, sinto uma emoção tão profunda que palavras mal conseguem descrever. No entanto, vou tentar.
<br>
<br>
Quatro meses podem parecer efêmeros no relógio do universo, mas no nosso pequeno e intenso canto de existência, já construímos uma eternidade. Você, com sua feminilidade graciosa e poética, se tornou a melodia que sempre quis ouvir, mas nunca soube que existia. E quão arrebatador é esse encanto que emana de ti e que desejo que se perpetue através dos tempos.
<br>
<br>
Desde o instante em que nossos olhos se cruzaram, senti uma conexão que transcende o tempo e o espaço. Cada sorriso seu se transformou em uma estrela no céu da minha vida, iluminando os meus dias mais sombrios e me guiando através das tempestades. Nos seus abraços, encontrei refúgio; nas suas palavras, encontrei sabedoria; e nos seus beijos, descobri o verdadeiro sabor do amor.
<br>
<br>
Seu apoio nas minhas decisões, sua mão estendida nas horas de incerteza, tudo isso não só me fortalece, mas também molda o homem que estou me tornando. Em você, encontrei não apenas um amor, mas também um farol, uma parceira que ilumina e orienta, mesmo nas noites mais escuras. Você me inspira a ser melhor, a sonhar mais alto e a amar com todo o meu ser. Contigo, descobri o que significa ter um verdadeiro parceiro de vida, alguém que está ao meu lado, não importa o que aconteça, alguém que me entende até mesmo quando eu não consigo encontrar as palavras certas.
<br>
<br>
E em meio a essa profundidade, não posso deixar de sorrir ao pensar nas nossas conversas despretensiosas, onde o mundo externo desaparece e somos apenas nós, jogando conversa fora e compartilhando risadas genuínas. E ah, as brincadeiras e piadas! Pequenos fragmentos de alegria que, somados, criam uma tapeçaria de momentos felizes. Quando estamos juntos, o mundo parece desaparecer, e somos apenas nós dois, compartilhando sonhos, esperanças e risadas. E quando estamos separados, te carrego comigo, em cada pensamento e desejo, como uma lembrança etérea que aquece a minha alma. Em nossas conversas noturnas, entre risos e segredos compartilhados, sinto a verdadeira essência da intimidade – uma conexão que vai além da carne e do sangue, tocando a própria alma.
<br>
<br>
Mas, meu amor, isso é só o começo. Sinto no meu âmago que estamos no limiar de uma trajetória inesquecível. Quatro meses é o prelúdio da sinfonia que iremos compor juntos, da vida que iremos tecer, e da família que, juntos, sonhamos construir. Porque é contigo que quero compartilhar cada amanhecer e cada pôr do sol, cada riso e cada lágrima, cada sucesso e cada fracasso. Nós, Sofia, somos um time. E times enfrentam, juntos, qualquer desafio que surja no horizonte. Independentemente do que o futuro nos reserva, quero que saiba que, contigo ao meu lado, me sinto pronto para qualquer jornada.
<br>
<br>
Com todo o amor e profundidade que estas palavras podem carregar,
<br>
<br>
Nícolas </p>
    </div>


    <!-- Seção da Poesia -->
    <div class="text-section text-content"> <!-- E aqui! -->
        <h1 class="highlight-text">Poesia para Sofia</h1>
        <p class="poetry">
                    Em quatro meses, no dançar do tempo, achamos nossa canção,<br>
                    Tua feminilidade, qual melodia, ressoa em meu coração.<br>
                    Desejo, Sofia, que este encanto não tenha fim,<br>
                    Que a graça e poesia em ti, se perpetue assim.<br>
                    <br>
                    Ao teu lado, nas decisões que escolhemos traçar,<br>
                    Vejo teu apoio firme, a me guiar, a me abraçar.<br>
                    Tua mão, quando estendo a minha em busca de direção,<br>
                    É mais que um toque, é mapa, é solução.<br>
                    <br>
                    Nosso diálogo despretensioso, é melodia do luar,<br>
                    Entre risadas e palavras, nosso mundo a se formar.<br>
                    E as brincadeiras e piadas, ah, elas têm lugar,<br>
                    Como estrelas cintilantes, nosso céu a iluminar.<br>
                    <br>
                    Juntos, somos uma equipe, um par sem igual,<br>
                    Desafiando tempestades, nosso amor é um vendaval.<br>
                    Porque Sofia, em ti eu vejo mais que um rosto,<br>
                    Vejo um time, um futuro, nosso ninho, nosso posto.<br>
                    <br>
                    Este é apenas o prelúdio, a abertura de um grande ato,<br>
                    Sonho com os anos, com a família, com nosso pacto.<br>
                    Em cada amanhecer, cada pôr do sol a vislumbrar,<br>
                    Desejo-te a meu lado, eternamente a caminhar.<br>

                </p>
        </div>

    <h2 class="highlight-text">Nosso tempo juntos...</h2>
         <ul class="timeline">
            <li>
                <div class="event hidden">
                    <strong>24/04/2023 - Começamos a namorar</strong><br>
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\namoro_2.jpeg.jpg" alt="Descrição da imagem 1a">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\namoro_1.jpeg.jpg" alt="Descrição da imagem 1b">
                </div>
            </li>
            <li>
                <div class="event hidden">
                    <strong>Xadrez - Nossas incontáveis partidas</strong><br>
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\xadrez_2.jpeg.jpg" alt="Descrição da imagem 2a">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\xadrez_1.jpeg.jpg" alt="Descrição da imagem 2b">
                </div>
            </li>
            <li>
                <div class="event hidden">
                    <strong>Cozinhando - Criando memórias deliciosas</strong><br>
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\jantar_1.jpeg.jpg" alt="Descrição da imagem 3a">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\jantar_2.jpeg.jpg" alt="Descrição da imagem 3b">
                    <video controls>
                        <source src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\jantar_3.mp4" type="video/mp4">
                    </video>
                </div>
            </li>
            <li>
                <div class="event hidden">
                    <strong>Viagens - Explorando o mundo juntos</strong><br>
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\viagem_1.jpeg.jpg" alt="Descrição da imagem 4a">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\viagem_2.jpeg.jpg" alt="Descrição da imagem 4b">
                </div>
            </li>
            <li>
                <div class="event hidden centered">
                    <strong>Moda & Compras - Apreciando seu estilo</strong><br>
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\compras.jpeg.jpg" alt="Descrição da imagem 5d">
                </div>
            </li>
            <li>
                <div class="event hidden">
                    <strong>Comida Japonesa - Nossos jantares favoritos</strong><br>
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\japa_1.jpeg.jpg" alt="Descrição da imagem 6a">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\japa_2.jpeg.jpg" alt="Descrição da imagem 6b">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\japa_3.jpeg.jpg" alt="Descrição da imagem 6c">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\japa_4.jpeg.jpg" alt="Descrição da imagem 6d">
                </div>
            </li>
            <li>
                <div class="event hidden">
                    <strong>Momentos felizes juntos - Celebrando nosso amor</strong><br>
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes.jpeg.jpg" alt="Descrição da imagem 7a">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_2.jpeg.jpg" alt="Descrição da imagem 7b">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_3.jpeg.jpg" alt="Descrição da imagem 7c">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_4.jpeg.jpg" alt="Descrição da imagem 7d">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_5.jpeg.jpg" alt="Descrição da imagem 7e">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_6.jpeg.jpg" alt="Descrição da imagem 7f">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_7.jpeg.jpg" alt="Descrição da imagem 7g">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_8.jpeg.jpg" alt="Descrição da imagem 7h">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_9.jpeg.jpg" alt="Descrição da imagem 7i">
                    <img src="C:\Users\nroch\OneDrive\Área de Trabalho\Surpresa 4 meses\felizes_10.jpeg.jpg" alt="Descrição da imagem 7j">
                </div>
            </li>

            <!-- Adicionando o quiz no final -->
            <li>
                <div class="quiz-container">
                    <h2>O quão bem nos conhecemos?</h2>
                    <div class="question">1. Onde foi nosso primeiro encontro?</div>
<ul class="options">
    <li><input type="radio" name="q1" id="q1a" data-answer="false"><label for="q1a">Restaurante Italiano</label></li>
    <li><input type="radio" name="q1" id="q1b" data-answer="true"><label for="q1b">Pizzaria Mr Texas</label></li>
    <li><input type="radio" name="q1" id="q1c" data-answer="false"><label for="q1c">Parque da cidade</label></li>
    <li><input type="radio" name="q1" id="q1d" data-answer="false"><label for="q1d">Cafeteria local</label></li>
</ul>

<div class="question">2. Qual comida eu sempre peço no restaurante?</div>
<ul class="options">
    <li><input type="radio" name="q2" id="q2a" data-answer="false"><label for="q2a">Frango assado</label></li>
    <li><input type="radio" name="q2" id="q2b" data-answer="false"><label for="q2b">Pizza</label></li>
    <li><input type="radio" name="q2" id="q2c" data-answer="true"><label for="q2c">Churrasco</label></li>
    <li><input type="radio" name="q2" id="q2d" data-answer="false"><label for="q2d">Sushi</label></li>
</ul>

<div class="question">3. Onde eu sonho em morar?</div>
<ul class="options">
    <li><input type="radio" name="q3" id="q3a" data-answer="false"><label for="q3a">Montanhas</label></li>
    <li><input type="radio" name="q3" id="q3b" data-answer="true"><label for="q3b">Praia</label></li>
    <li><input type="radio" name="q3" id="q3c" data-answer="false"><label for="q3c">Campos</label></li>
    <li><input type="radio" name="q3" id="q3d" data-answer="false"><label for="q3d">Cidade grande</label></li>
</ul>

<div class="question">4. Qual é o meu curso?</div>
<ul class="options">
    <li><input type="radio" name="q4" id="q4a" data-answer="true"><label for="q4a">Defesa Cibernética</label></li>
    <li><input type="radio" name="q4" id="q4b" data-answer="false"><label for="q4b">Moda</label></li>
    <li><input type="radio" name="q4" id="q4c" data-answer="false"><label for="q4c">Direito</label></li>
    <li><input type="radio" name="q4" id="q4d" data-answer="false"><label for="q4d">Medicina</label></li>
</ul>

<div class="question">5. Onde eu pedi você em namoro?</div>
<ul class="options">
    <li><input type="radio" name="q5" id="q5a" data-answer="false"><label for="q5a">Restaurante</label></li>
    <li><input type="radio" name="q5" id="q5b" data-answer="false"><label for="q5b">Na sua casa</label></li>
    <li><input type="radio" name="q5" id="q5c" data-answer="true"><label for="q5c">No quiosque do condomínio</label></li>
    <li><input type="radio" name="q5" id="q5d" data-answer="false"><label for="q5d">Na praia</label></li>
</ul>

                    <button onclick="checkAnswers()">Verificar Respostas</button>
                </div>
            </li>
        </ul>
        <h2 class="highlight-text" style="margin-top: 1cm;">Nossas viagens</h2>

        <div id="map" style="margin-top: 1cm;"></div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
    createHearts();
    setTimeout(revealEvent, 1000);
    initMap();
    loadMarkers();
});

let map;  // Variável global para o mapa

const events = document.querySelectorAll('.event');
let index = 0;

function revealEvent() {
    if (index < events.length) {
        events[index].style.visibility = 'visible';
        index++;
        setTimeout(revealEvent, 1500); 
    }
}

function checkAnswers() {
    const options = document.querySelectorAll('.options input[type="radio"]');
    let correctCount = 0;

    options.forEach(opt => {
        if(opt.checked && opt.getAttribute('data-answer') === 'true') {
            opt.nextElementSibling.style.backgroundColor = '#00FF00';  // Verde para correto
            correctCount++;
        } else if (opt.checked) {
            opt.nextElementSibling.style.backgroundColor = '#FF0000';  // Vermelho para incorreto
        }
    });

    alert(`Você acertou ${correctCount} de 5 perguntas!`);
}

function createHearts() {
    const heartCount = 270;

    for (let i = 0; i < heartCount; i++) {
        const heart = document.createElement('div');
        heart.className = 'heart';
        
        const posX = Math.random() * window.innerWidth;
        const posY = Math.random() * (document.documentElement.scrollHeight + 35);
        
        heart.style.left = posX + 'px';
        heart.style.top = posY + 'px';
        
        document.body.appendChild(heart);
    }
}

function playMusic() {
    const music = document.getElementById("backgroundMusic");
    if (music.paused) {
        music.play();
    } else {
        music.pause();
    }
}

function initMap() {
    map = L.map('map').setView([20, 0], 2);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        maxZoom: 19
    }).addTo(map);
    
    map.on('click', addMarker);
}

function addMarker(event) {
    const marker = L.marker([event.latlng.lat, event.latlng.lng], {
        title: "Clique para remover"
    }).addTo(map).on('click', removeMarker);
    
    updateLocalStorage(event.latlng.lat, event.latlng.lng);
}

function loadMarkers() {
    const savedMarkers = JSON.parse(localStorage.getItem('markers'));
    
    if(savedMarkers) {
        savedMarkers.forEach(coord => {
            if(coord[0] && coord[1]) {
                L.marker([coord[0], coord[1]], {title: "Clique para remover"}).addTo(map).on('click', removeMarker);
            }
        });
    }
}

function removeMarker(event) {
    const markerToRemove = event.target;
    map.removeLayer(markerToRemove);

    const savedMarkers = JSON.parse(localStorage.getItem('markers'));
    const index = savedMarkers.findIndex(m => 
        m[0] === markerToRemove.getLatLng().lat && m[1] === markerToRemove.getLatLng().lng
    );
    
    if(index !== -1) {
        savedMarkers.splice(index, 1);
        localStorage.setItem('markers', JSON.stringify(savedMarkers));
    }
}

function updateLocalStorage(lat, lng) {
    let savedMarkers = JSON.parse(localStorage.getItem('markers'));
    if(!savedMarkers) {
        savedMarkers = [];
    }
    savedMarkers.push([lat, lng]);
    localStorage.setItem('markers', JSON.stringify(savedMarkers));
}





    </script>
    </div>
</body>

</html>
