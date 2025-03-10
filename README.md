// Seleciona todas as imagens
const imgs = document.querySelectorAll('img');

imgs.forEach(img => {
    const picture = document.createElement('picture');
    
    // Cria o <source> para o formato AVIF
    const sourceAvif = document.createElement('source');
    sourceAvif.setAttribute('srcset', img.src.replace('.jpg', '.avif'));
    sourceAvif.setAttribute('type', 'image/avif');
    picture.appendChild(sourceAvif);
    
    // Cria o <source> para o formato WebP
    const sourceWebp = document.createElement('source');
    sourceWebp.setAttribute('srcset', img.src.replace('.jpg', '.webp'));
    sourceWebp.setAttribute('type', 'image/webp');
    picture.appendChild(sourceWebp);
    
    // Cria o <img> dentro do <picture>
    picture.appendChild(img.cloneNode());

    // Substitui a imagem original pelo <picture>
    img.replaceWith(picture);
});
