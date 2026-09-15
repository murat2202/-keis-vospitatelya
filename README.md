<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#2563eb">
<title>Электронный кейс воспитателя</title>
<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Arial, sans-serif;
    background: #f4f7fb;
    color: #172033;
    line-height: 1.5;
}
button,
input {
    font: inherit;
}
.header {
    background: linear-gradient(135deg, #2563eb, #4f46e5);
    color: white;
    padding: 55px 20px 75px;
}
.header-inner {
    max-width: 1150px;
    margin: auto;
}
.badge {
    display: inline-block;
    background: rgba(255,255,255,.16);
    border: 1px solid rgba(255,255,255,.25);
    padding: 7px 13px;
    border-radius: 30px;
    font-size: 14px;
    margin-bottom: 18px;
}
.header h1 {
    font-size: 42px;
    margin-bottom: 12px;
}
.header p {
    font-size: 18px;
    opacity: .92;
    max-width: 650px;
}
.container {
    max-width: 1150px;
    margin: -35px auto 50px;
    padding: 0 20px;
    position: relative;
}
.search-box {
    background: white;
    padding: 18px;
    border-radius: 18px;
    box-shadow: 0 10px 35px rgba(30, 55, 90, .12);
    margin-bottom: 30px;
}
.search {
    width: 100%;
    border: 1px solid #dbe2ea;
    border-radius: 12px;
    padding: 15px 18px;
    outline: none;
    font-size: 16px;
}
.search:focus {
    border-color: #2563eb;
    box-shadow: 0 0 0 3px rgba(37,99,235,.1);
}
.section-title {
    font-size: 25px;
    margin-bottom: 18px;
}
.categories {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 18px;
}
.card {
    background: white;
    border-radius: 18px;
    padding: 22px;
    cursor: pointer;
    border: 1px solid #e7ebf0;
    transition: .2s ease;
    box-shadow: 0 5px 18px rgba(30,55,90,.05);
}
.card:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 30px rgba(30,55,90,.12);
    border-color: #cdd9ee;
}
.icon {
    width: 52px;
    height: 52px;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #eff6ff;
    font-size: 27px;
    margin-bottom: 15px;
}
.card h3 {
    font-size: 17px;
    margin-bottom: 6px;
}
.card p {
    color: #6b7280;
    font-size: 14px;
}
.info-block {
    margin-top: 35px;
    background: white;
    border-radius: 20px;
    padding: 28px;
    border: 1px solid #e7ebf0;
}
.info-block h2 {
    margin-bottom: 10px;
}
.info-block p {
    color: #626b7a;
}
.qr-box {
    margin-top: 35px;
    background: linear-gradient(135deg, #eef5ff, #f5f3ff);
    border-radius: 20px;
    padding: 30px;
    text-align: center;
}
.qr-placeholder {
    background: white;
    width: 170px;
    height: 170px;
    border-radius: 16px;
    margin: 20px auto;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px dashed #b7c6df;
    color: #718096;
    font-size: 14px;
}
.footer {
    text-align: center;
    padding: 35px 20px;
    color: #7b8493;
    font-size: 14px;
}
.modal {
    display: none;
    position: fixed;
    z-index: 100;
    inset: 0;
    background: rgba(15,23,42,.55);
    padding: 20px;
    overflow-y: auto;
}
.modal.active {
    display: flex;
    align-items: center;
    justify-content: center;
}
.modal-content {
    background: white;
    width: 100%;
    max-width: 650px;
    border-radius: 22px;
    padding: 28px;
    box-shadow: 0 25px 70px rgba(0,0,0,.25);
    position: relative;
    animation: show .2s ease;
}
@keyframes show {
    from {
        opacity: 0;
        transform: translateY(10px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
.close {
    position: absolute;
    right: 18px;
    top: 14px;
    border: 0;
    background: #f1f3f6;
    width: 38px;
    height: 38px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 20px;
}
.modal-title {
    font-size: 25px;
    margin-bottom: 20px;
    padding-right: 40px;
}
.documents {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
.document {
    display: flex;
    align-items: center;
    gap: 13px;
    padding: 14px;
    border: 1px solid #e6eaf0;
    border-radius: 13px;
    background: #fafbfc;
}
.document-icon {
    font-size: 22px;
}
.document-info {
    flex: 1;
}
.document-name {
    font-weight: 600;
    font-size: 15px;
}
.document-type {
    color: #8a93a2;
    font-size: 12px;
}
.open-btn {
    border: 0;
    background: #2563eb;
    color: white;
    padding: 8px 12px;
    border-radius: 9px;
    cursor: pointer;
    font-size: 13px;
}
.open-btn:hover {
    background: #1d4ed8;
}
.no-results {
    display: none;
    text-align: center;
    background: white;
    border-radius: 18px;
    padding: 35px;
    color: #727b8b;
}
@media (max-width: 850px) {
    .categories {
        grid-template-columns: repeat(2, 1fr);
    }
    .header h1 {
        font-size: 34px;
    }
}
@media (max-width: 560px) {
    .header {
        padding: 40px 18px 65px;
    }
    .header h1 {
        font-size: 29px;
    }
    .header p {
        font-size: 16px;
    }
    .container {
        padding: 0 14px;
    }
    .categories {
        grid-template-columns: 1fr;
    }
    .card {
        padding: 19px;
    }
    .info-block,
    .qr-box {
        padding: 22px;
    }
    .document {
        align-items: flex-start;
    }
    .open-btn {
        padding: 7px 9px;
    }
}
</style>
</head>
<body>
<header class="header">
    <div class="header-inner">
        <div class="badge">📚 Электронная документация</div>
    <h1>Электронный кейс воспитателя</h1>
    <p>
        Вся необходимая документация, планы, инструкции,
        памятки и образцы — в одном удобном месте.
    </p>
</div>
</header>
<main class="container">
<div class="search-box">
    <input
        type="text"
        id="search"
        class="search"
        placeholder="🔎 Найти документ или раздел..."
    >
</div>
<h2 class="section-title">Разделы кейса</h2>
<div class="categories" id="categories">
    <div class="card"
         data-name="Нормативные документы"
         onclick="openCategory('Нормативные документы', 0)">
        <div class="icon">⚖️</div>
        <h3>Нормативные документы</h3>
        <p>ФГОС, ФОП, законы, приказы и локальные акты</p>
    </div>
    <div class="card"
         data-name="Документация воспитателя"
         onclick="openCategory('Документация воспитателя', 1)">
        <div class="icon">📋</div>
        <h3>Документация воспитателя</h3>
        <p>Основные документы и рабочие материалы</p>
    </div>
    <div class="card"
         data-name="Планирование"
         onclick="openCategory('Планирование', 2)">
        <div class="icon">🗓️</div>
        <h3>Планирование</h3>
        <p>Годовые, перспективные и календарные планы</p>
    </div>
    <div class="card"
         data-name="Отчётность"
         onclick="openCategory('Отчётность', 3)">
        <div class="icon">📊</div>
        <h3>Отчётность</h3>
        <p>Отчёты, аналитика и мониторинг</p>
    </div>
    <div class="card"
         data-name="Работа с родителями"
         onclick="openCategory('Работа с родителями', 4)">
        <div class="icon">👨‍👩‍👧</div>
        <h3>Работа с родителями</h3>
        <p>Планы, памятки и протоколы собраний</p>
    </div>
    <div class="card"
         data-name="Инструкции и памятки"
         onclick="openCategory('Инструкции и памятки', 5)">
        <div class="icon">📖</div>
        <h3>Инструкции и памятки</h3>
        <p>Полезные инструкции и алгоритмы действий</p>
    </div>
    <div class="card"
         data-name="Охрана труда и безопасность"
         onclick="openCategory('Охрана труда и безопасность', 6)">
        <div class="icon">🛡️</div>
        <h3>Охрана труда и безопасность</h3>
        <p>Безопасность детей, пожарная безопасность и ОТ</p>
    </div>
    <div class="card"
         data-name="Медицинская документация"
         onclick="openCategory('Медицинская документация', 7)">
        <div class="icon">🩺</div>
        <h3>Медицинская документация</h3>
        <p>Режим дня, наблюдения и рабочие формы</p>
    </div>
    <div class="card"
         data-name="Образцы заполнения"
         onclick="openCategory('Образцы заполнения', 8)">
        <div class="icon">✍️</div>
        <h3>Образцы заполнения</h3>
        <p>Готовые примеры оформления документов</p>
    </div>
    <div class="card"
         data-name="Архив"
         onclick="openCategory('Архив', 9)">
        <div class="icon">🗄️</div>
        <h3>Архив</h3>
        <p>Документы прошлых периодов</p>
    </div>
</div>
<div class="no-results" id="noResults">
    Ничего не найдено. Попробуйте изменить запрос.
</div>
<section class="info-block">
    <h2>💡 Как пользоваться кейсом?</h2>
    <p>
        Выберите необходимый раздел выше. Внутри находятся документы,
        которые можно будет открыть или скачать. Для быстрого доступа
        к кейсу можно разместить QR-код на информационном стенде
        или в кабинете воспитателя.
    </p>
</section>
<section class="qr-box">
    <h2>📱 Быстрый доступ по QR-коду</h2>
    <div class="qr-placeholder">
        QR-код сайта<br>
        будет размещён здесь
    </div>
    <p>
        Наведите камеру телефона на QR-код,
        чтобы сразу открыть электронный кейс.
    </p>
</section>
</main>
<footer class="footer">
    Электронный кейс воспитателя • 2026
</footer>
<div class="modal" id="modal" onclick="closeOutside(event)">
    <div class="modal-content">
    <button class="close" onclick="closeModal()">×</button>
    <div class="modal-title" id="modalTitle"></div>
    <div class="documents" id="documents"></div>
</div>
</div>
<script>
const categories = [
    {
        name: "Нормативные документы",
        docs: [
            ["ФГОС и ФОП.pdf", "PDF"],
            ["Законодательство.pdf", "PDF"],
            ["Приказы и распоряжения.pdf", "PDF"],
            ["Локальные акты ДОУ.pdf", "PDF"]
        ]
    },
    {
        name: "Документация воспитателя",
        docs: [
            ["Должностная инструкция.pdf", "PDF"],
            ["Права и обязанности.pdf", "PDF"],
            ["Журнал работы.docx", "DOCX"],
            ["План самообразования.docx", "DOCX"]
        ]
    },
    {
        name: "Планирование",
        docs: [
            ["Годовой план.docx", "DOCX"],
            ["Перспективное планирование.docx", "DOCX"],
            ["Календарный план.docx", "DOCX"],
            ["Индивидуальный план работы.docx", "DOCX"]
        ]
    },
    {
        name: "Отчётность",
        docs: [
            ["Отчёт о проделанной работе.docx", "DOCX"],
            ["Аналитическая справка.docx", "DOCX"],
            ["Мониторинг.xlsx", "XLSX"]
        ]
    },
    {
        name: "Работа с родителями",
        docs: [
            ["План работы с родителями.docx", "DOCX"],
            ["Памятки для родителей.pdf", "PDF"],
            ["Протоколы родительских собраний.docx", "DOCX"]
        ]
    },
    {
        name: "Инструкции и памятки",
        docs: [
            ["Инструкция по безопасности.pdf", "PDF"],
            ["Памятка воспитателю.pdf", "PDF"],
            ["Алгоритмы действий.pdf", "PDF"]
        ]
    },
    {
        name: "Охрана труда и безопасность",
        docs: [
            ["Инструкции по охране труда.pdf", "PDF"],
            ["Пожарная безопасность.pdf", "PDF"],
            ["Безопасность детей.pdf", "PDF"]
        ]
    },
    {
        name: "Медицинская документация",
        docs: [
            ["Режим дня.pdf", "PDF"],
            ["Листы наблюдений.xlsx", "XLSX"],
            ["Образцы журналов.docx", "DOCX"]
        ]
    },
    {
        name: "Образцы заполнения",
        docs: [
            ["Образец плана.docx", "DOCX"],
            ["Образец отчёта.docx", "DOCX"],
            ["Образец журнала.docx", "DOCX"]
        ]
    },
    {
        name: "Архив",
        docs: [
            ["Документы 2025–2026.zip", "ZIP"],
            ["Старые приказы.pdf", "PDF"]
        ]
    }
];
function openCategory(title, index) {
    const modal = document.getElementById("modal");
    const modalTitle = document.getElementById("modalTitle");
    const documents = document.getElementById("documents");
    modalTitle.textContent = title;
    documents.innerHTML = "";
    categories[index].docs.forEach(doc => {
        const item = document.createElement("div");
        item.className = "document";
        let icon = "📄";
        if (doc[1] === "PDF") icon = "📕";
        if (doc[1] === "DOCX") icon = "📝";
        if (doc[1] === "XLSX") icon = "📊";
        if (doc[1] === "ZIP") icon = "🗜️";
        item.innerHTML = `
            <div class="document-icon">${icon}</div>
            <div class="document-info">
                <div class="document-name">${doc[0]}</div>
                <div class="document-type">${doc[1]} • электронный документ</div>
            </div>
            <button class="open-btn"
                    onclick="openDocument('${doc[0]}')">
                Открыть
            </button>
        `;
        documents.appendChild(item);
    });
    modal.classList.add("active");
}
function openDocument(name) {
    alert(
        "Документ «" + name +
        "» пока является демонстрационным.\n\n" +
        "После загрузки настоящего файла сюда будет добавлена ссылка на его открытие."
    );
}
function closeModal() {
    document.getElementById("modal").classList.remove("active");
}
function closeOutside(event) {
    if (event.target.id === "modal") {
        closeModal();
    }
}
document.addEventListener("keydown", function(event) {
    if (event.key === "Escape") {
        closeModal();
    }
});
const search = document.getElementById("search");
const cards = document.querySelectorAll(".card");
const noResults = document.getElementById("noResults");
search.addEventListener("input", function() {
    const query = this.value.toLowerCase().trim();
    let visible = 0;
    cards.forEach(card => {
        const text = card.textContent.toLowerCase();
        if (text.includes(query)) {
            card.style.display = "";
            visible++;
        } else {
            card.style.display = "none";
        }
    });
    noResults.style.display = visible === 0 ? "block" : "none";
});
</script>
</body>
</html>
