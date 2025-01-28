let score = 0; // 初始化分数
const scoreElement = document.getElementById('score'); // 分数显示
const catImage = document.getElementById('cat'); // 图片
const restartButton = document.getElementById('restart'); // 重置按钮

// 切换图片并计分
function toggleCat() {
    if (catImage.src.includes('ZI6fQfB.png')) {
        catImage.src = 'https://i.imgur.com/w93B5IL.png'; // 张嘴图片
    } else {
        catImage.src = 'https://i.imgur.com/ZI6fQfB.png'; // 闭嘴图片
    }
    score++;
    scoreElement.textContent = score;
}

// 重置游戏
function resetGame() {
    score = 0;
    scoreElement.textContent = score;
    catImage.src = 'https://i.imgur.com/ZI6fQfB.png'; // 重置为闭嘴图片
}

// 添加事件监听
catImage.addEventListener('click', toggleCat);
restartButton.addEventListener('click', resetGame);
const popSound = new Audio('https://www.myinstants.com/media/sounds/pop-cat.mp3'); // 使用在线音效文件

// 修改 toggleCat 函数，添加播放音效
function toggleCat() {
    popSound.play(); // 播放音效
    if (catImage.src.includes('ZI6fQfB.png')) {
        catImage.src = 'https://i.imgur.com/w93B5IL.png'; // 张嘴图片
    } else {
        catImage.src = 'https://i.imgur.com/ZI6fQfB.png'; // 闭嘴图片
    }
    score++;
    scoreElement.textContent = score;
}
