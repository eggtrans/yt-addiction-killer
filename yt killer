// ==UserScript==
// @name         YouTube Warning
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  显示 YouTube 警告
// @exclude      *://www.junyiacademy.org/*
// @exclude      https://www.youtube.com/watch?v=eh3l8I-JT4Q
// @exclude      https://www.youtube.com/watch?v=eh3l8I-JT4Q&sttick=0
// @exclude      https://youtu.be/eh3l8I-JT4Q
// @match        *://www.youtube.com/*
// @grant        none
// @run-at       document-end
// ==/UserScript==


(function() {
    'use strict';

    console.log("YouTube Warning Script Running");

    const targetUrl = "www.youtube.com";

    // 检查是否在 YouTube 页面
    if (window.location.href.includes(targetUrl)) {
        console.log("YouTube detected");

        const warningDiv = document.createElement("div");
        warningDiv.style.position = "fixed";
        warningDiv.style.top = "0";
        warningDiv.style.left = "0";
        warningDiv.style.width = "100%";
        warningDiv.style.height = "100%";
        warningDiv.style.backgroundColor = "black"; // 深色背景
        warningDiv.style.color = "white";
        warningDiv.style.display = "flex";
        warningDiv.style.justifyContent = "center";
        warningDiv.style.alignItems = "center";
        warningDiv.style.zIndex = "10000";
        warningDiv.style.fontSize = "50px"; // 初始字體大小
        warningDiv.style.fontWeight = "bold";
        warningDiv.style.textAlign = "center";
        warningDiv.style.textShadow = "0 0 10px #FFFFFF, 0 0 15px #FFFFFF, 0 0 20px #FFFFFF"; // 減小發光效果
        warningDiv.style.animation = "glow 1.5s infinite alternate, pulse 2s infinite"; // 添加發光和縮放動畫

        // 彩虹旗效果的背景
        warningDiv.style.background = "linear-gradient(135deg, #FF0000, #FF7F00, #FFFF00, #00FF00, #0000FF, #4B0082, #8B00FF)";
        warningDiv.style.backgroundSize = "400% 400%";
        warningDiv.style.animation += ", rainbowBackground 5s ease infinite";

        warningDiv.innerText = "⚠️ 警告：由於 YouTube 已剝奪您過多時間 故禁止访问 YouTube！請專心於學業 ⚠️";

        document.body.appendChild(warningDiv);

        // 播放背景音樂
        const audio = new Audio("https://www.myinstants.com/media/sounds/rick-roll.mp3");
        audio.loop = true; // 使音樂循環播放
        audio.play();

        // 定義動畫效果
        const styleSheet = document.createElement("style");
        styleSheet.type = "text/css";
        styleSheet.innerText = `
    @keyframes glow {
        0% {
            text-shadow: 0 0 10px #FFFFFF, 0 0 15px #FFFFFF, 0 0 20px #FFFFFF;
        }
        100% {
            text-shadow: 0 0 20px #FFFFFF, 0 0 30px #FFFFFF, 0 0 40px #FFFFFF;
        }
    }


    @keyframes rainbowBackground {
        0% {
            background-position: 0% 50%;
        }
        50% {
            background-position: 100% 50%;
        }
        100% {
            background-position: 0% 50%;
        }
    }
`;
        document.head.appendChild(styleSheet);



        document.body.appendChild(warningDiv);
                // Remove the overlay and close the window after 3 seconds
        setTimeout(function() {

            if (window.history.length > 1) {
                window.history.back(); // Go back to the previous page
            } else {
                alert("This tab contains blacklisted content and is attempting to close.");
                // Uncomment the following line if you want to close the tab
                window.close();
            }
        }, 10000); // Display the sign for 3 seconds
    }
})();
