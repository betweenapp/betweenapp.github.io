# BETWEEN

<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>between</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:-apple-system,BlinkMacSystemFont,"SF Pro Display",sans-serif;
    background:#090909;
    color:white;
    min-height:100vh;
}

.bg{
    position:fixed;
    inset:0;
    z-index:-1;
    background:
    radial-gradient(circle at top,#3f2a68 0%,transparent 35%),
    radial-gradient(circle at bottom,#1d365f 0%,transparent 35%),
    #090909;
}

.container{
    max-width:430px;
    margin:auto;
    padding:28px 22px 40px;
}

.logo{
    text-align:center;
    letter-spacing:4px;
    opacity:.7;
    margin:20px 0 50px;
}

h1{
    font-size:38px;
    line-height:1.1;
    margin-bottom:16px;
}

.subtitle{
    color:rgba(255,255,255,.65);
    line-height:1.5;
    margin-bottom:32px;
}

.upload-card{
    background:rgba(255,255,255,.05);
    backdrop-filter:blur(30px);
    border:1px solid rgba(255,255,255,.08);
    border-radius:30px;
    padding:24px;
}

.textarea{
    width:100%;
    min-height:220px;
    resize:none;
    border:none;
    outline:none;
    background:rgba(255,255,255,.04);
    border-radius:20px;
    padding:18px;
    color:white;
    font-size:16px;
    line-height:1.5;
}

.textarea::placeholder{
    color:rgba(255,255,255,.35);
}

.or{
    text-align:center;
    margin:18px 0;
    opacity:.4;
}

.upload-btn{
    display:block;
    width:100%;
    padding:18px;
    text-align:center;
    border-radius:20px;
    border:1px solid rgba(255,255,255,.08);
    background:rgba(255,255,255,.04);
    cursor:pointer;
}

.upload-btn:hover{
    background:rgba(255,255,255,.08);
}

input[type=file]{
    display:none;
}

.help{
    margin-top:10px;
    text-align:center;
    font-size:13px;
    color:rgba(255,255,255,.45);
}

.button{
    width:100%;
    margin-top:22px;
    border:none;
    border-radius:22px;
    padding:20px;
    font-size:18px;
    font-weight:600;
    background:white;
    color:black;
    cursor:pointer;
}

.note{
    margin-top:18px;
    text-align:center;
    font-size:13px;
    color:rgba(255,255,255,.45);
}

</style>
</head>

<body>

<div class="bg"></div>

<div class="container">

<div class="logo">
BETWEEN
</div>

<h1>
Загрузите переписку
</h1>

<p class="subtitle">
Вставьте диалог целиком или загрузите скриншоты.
Анализ займёт меньше минуты.
</p>

<div class="upload-card">

<textarea
class="textarea"
placeholder="Вставьте переписку сюда..."
></textarea>

<div class="or">или</div>

<label class="upload-btn">
📸 Загрузить скриншоты
<input type="file" multiple accept="image/*">
</label>

<div class="or">или</div>

<label class="upload-btn">
💬 Импортировать чат WhatsApp / Telegram
<input
id="chatFile"
type="file"
accept=".txt,.zip,.json,.html"
>
</label>

<div id="fileName" class="help">
Файл не выбран
</div>

<button class="button">
Начать анализ
</button>

</div>

<div class="note">
Мы не публикуем и не передаём ваши данные третьим лицам.
</div>

</div>

<script>

const chatFile = document.getElementById('chatFile');
const fileName = document.getElementById('fileName');

chatFile.addEventListener('change', function(){

    if(this.files.length > 0){
        fileName.textContent =
            'Выбран файл: ' + this.files[0].name;
    }

});


</body>
</html>