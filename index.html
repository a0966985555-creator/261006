<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>p5.js 選擇題測驗系統</title>

  <!-- 引入 Google Fonts 預連線機制 -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  
  <!-- 引入指定的英文字型 (Fraunces) 與中文字型 (LXGW WenKai TC 霞鶖文楷) -->
  <link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,100..900;1,9..144,100..900&family=LXGW+WenKai+TC&display=swap" rel="stylesheet">

  <!-- 引入 p5.js 核心庫 -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.9.0/p5.min.js"></script>

  <style>
    /* 清除頁面預設邊距並隱藏滾動條，確保 canvas 滿版顯示 */
    html, body {
      margin: 0;
      padding: 0;
      overflow: hidden;
      background-color: #f0f4f8;
      font-family: 'Fraunces', 'LXGW WenKai TC', serif;
    }
    canvas {
      display: block;
    }
  </style>
</head>
<body>
  <script>
    // -------------------------------------------------------------
    // sketch.js 內容整合
    // -------------------------------------------------------------

    // 定義字型名稱常數
    const FONT_EN = "'Fraunces', 'LXGW WenKai TC', serif";
    const FONT_ZH = "'LXGW WenKai TC', cursive, sans-serif";

    // 定義五題簡易高中英文測驗資料集 (題目, 4個選項, 正確答案索引, 解析)
    let quizData = [
      {
        question: "1. Due to heavy traffic, we had to ______ our trip to the countryside.",
        options: ["A) postpone", "B) accelerate", "C) establish", "D) conquer"],
        answer: 0, // 正確選項索引 (0 表示選項 A)
        explanation: "postpone 意為「延期」。句意：由於交通壅塞，我們不得不延後鄉村之旅。"
      },
      {
        question: "2. The doctor advised him to adopt a healthy diet and exercise ______.",
        options: ["A) rarely", "B) regularly", "C) severely", "D) desperately"],
        answer: 1, // 正確選項索引 (1 表示選項 B)
        explanation: "regularly 意為「規律地」。句意：醫生建議他採取健康飲食並規律運動。"
      },
      {
        question: "3. She has a strong ______ for classical music and plays the violin well.",
        options: ["A) objection", "B) passion", "C) threat", "D) distance"],
        answer: 1, // 正確選項索引 (1 表示選項 B)
        explanation: "passion 意為「熱情」。句意：她對古典音樂有強烈的熱情，且小提琴彈得很好。"
      },
      {
        question: "4. The weather was so cold that the water in the pond had ______.",
        options: ["A) melted", "B) frozen", "C) boiled", "D) floated"],
        answer: 1, // 正確選項索引 (1 表示選項 B)
        explanation: "frozen 意為「結冰」。句意：天氣太冷了，以至於池塘裡的水都結冰了。"
      },
      {
        question: "5. It is essential to ______ water when living in a drought-prone area.",
        options: ["A) consume", "B) pollute", "C) conserve", "D) ignore"],
        answer: 2, // 正確選項索引 (2 表示選項 C)
        explanation: "conserve 意為「節約/保護」。句意：住在易乾旱地區，節約用水非常重要。"
      }
    ];

    // 當前進行到的題號索引 (0 到 4)
    let currentQuestion = 0;
    // 累積答對題數
    let score = 0;
    // 使用者目前選擇的選項 (-1 表示尚未選擇)
    let selectedOption = -1;
    // 紀錄當前題目是否已經回答
    let answered = false;

    // 響應式計算用的尺寸動態變數
    let cardW, cardH, cardX, cardY;
    let isMobile = false;

    // p5.js 初始化設定函式
    function setup() {
      // 建立全螢幕畫布
      createCanvas(windowWidth, windowHeight);
      // 設定文字預設對齊方式 (垂直置中，水平靠左)
      textAlign(LEFT, CENTER);
      // 預設套用英文字型
      textFont(FONT_EN);
    }

    // p5.js 主繪製循環 (每秒約 60 次)
    function draw() {
      // 設定背景色為柔和藍灰色
      background(240, 244, 248);

      // 動態更新響應式尺寸與參數
      updateResponsiveLayout();

      // 判斷是否還有未完成的題目
      if (currentQuestion < quizData.length) {
        // 繪製單題測驗介面
        drawQuizScreen();
      } else {
        // 5 題皆作答完畢，顯示最終成績統計畫面
        drawResultScreen();
      }
    }

    // 動態計算響應式版面尺寸
    function updateResponsiveLayout() {
      // 判斷是否為手機尺寸 (寬度小於 600px 或高度小於 650px)
      isMobile = width < 600 || height < 650;

      // 根據螢幕尺寸動態設定卡片寬高
      cardW = min(width * 0.92, 680);
      cardH = min(height * 0.9, isMobile ? 620 : 540);

      // 設定卡片置中座標
      cardX = width / 2 - cardW / 2;
      cardY = height / 2 - cardH / 2;
    }

    // 繪製單題測驗 UI
    function drawQuizScreen() {
      // 取得當前題目物件
      let q = quizData[currentQuestion];

      // 1. 繪製卡片下方陰影效果
      noStroke();
      fill(210, 215, 225, 120);
      rect(cardX + 6, cardY + 6, cardW, cardH, 16);

      // 2. 繪製白色卡片主體
      fill(255);
      stroke(220, 225, 235);
      strokeWeight(2);
      rect(cardX, cardY, cardW, cardH, 16);

      // 3. 繪製頂部進度條底槽
      let padding = isMobile ? 20 : 35;
      let innerW = cardW - padding * 2;
      noStroke();
      fill(235, 240, 245);
      rect(cardX + padding, cardY + padding, innerW, 8, 4);

      // 4. 繪製藍色答題進度條
      fill(74, 144, 226);
      let progressWidth = map(currentQuestion + 1, 1, quizData.length, 0, innerW);
      rect(cardX + padding, cardY + padding, progressWidth, 8, 4);

      // 5. 顯示當前題號標籤 (使用 Fraunces 英文字型)
      textFont(FONT_EN);
      fill(120);
      textSize(isMobile ? 12 : 14);
      textAlign(LEFT, CENTER);
      text("QUESTION " + (currentQuestion + 1) + " OF " + quizData.length, cardX + padding, cardY + padding + 22);

      // 6. 顯示英文題目文字 (使用 Fraunces 英文字型)
      fill(30);
      textSize(isMobile ? 16 : 19);
      textWrap(WORD);
      text(q.question, cardX + padding, cardY + padding + 60, innerW);

      // 7. 計算第一個選項按鈕起點 Y 座標
      let startY = cardY + padding + (isMobile ? 120 : 135);
      let optH = isMobile ? 48 : 54;
      let optGap = isMobile ? 12 : 16;

      // 迴圈繪製 4 個選項按鈕
      for (let i = 0; i < q.options.length; i++) {
        let optY = startY + i * (optH + optGap);

        // 判斷滑鼠是否懸停於該選項上
        let isHover = mouseX > cardX + padding && mouseX < cardX + cardW - padding &&
                      mouseY > optY && mouseY < optY + optH;

        // 設定預設選項外觀
        fill(250, 252, 255);
        stroke(215, 225, 235);
        strokeWeight(1.5);

        // 已作答狀態下的色彩顯示邏輯
        if (answered) {
          if (i === q.answer) {
            // 答錯或答對時，正確選項統一標示指定背景顏色 #dde5b6 (RGB: 221, 229, 182)
            fill(221, 229, 182);
            stroke(180, 195, 140);
            strokeWeight(2);
          } else if (i === selectedOption && selectedOption !== q.answer) {
            // 若此選項為使用者點選的「錯誤選項」，標示淺紅色底色
            fill(255, 220, 220);
            stroke(230, 150, 150);
            strokeWeight(2);
          }
        } else if (isHover) {
          // 未作答時懸停呈現淺藍高亮
          fill(235, 243, 255);
          stroke(100, 160, 235);
        }

        // 繪製選項圓角矩形按鈕
        rect(cardX + padding, optY, innerW, optH, 10);

        // 繪製選項文字 (使用 Fraunces 英文字型)
        textFont(FONT_EN);
        fill(40);
        textSize(isMobile ? 14 : 16);
        textAlign(LEFT, CENTER);
        text(q.options[i], cardX + padding + 18, optY + optH / 2);
      }

      // 8. 當點選答案後，顯示題目解析與下一題按鈕
      if (answered) {
        // 顯示中文解析 (使用 LXGW WenKai TC 霞鶖文楷字型)
        textFont(FONT_ZH);
        fill(90, 105, 120);
        textSize(isMobile ? 13 : 15);
        textAlign(LEFT, TOP);
        let expY = startY + 4 * (optH + optGap) + (isMobile ? 2 : 10);
        text("解析: " + q.explanation, cardX + padding, expY, innerW);

        // 計算下一題按鈕位置
        let btnW = isMobile ? 120 : 140;
        let btnH = isMobile ? 40 : 45;
        let btnX = cardX + cardW - padding - btnW;
        let btnY = cardY + cardH - padding - btnH;

        // 檢查滑鼠是否懸停在「下一題」按鈕上
        let isBtnHover = mouseX > btnX && mouseX < btnX + btnW &&
                         mouseY > btnY && mouseY < btnY + btnH;

        // 繪製「下一題」按鈕底色
        fill(isBtnHover ? 60 : 74, isBtnHover ? 130 : 144, isBtnHover ? 210 : 226);
        noStroke();
        rect(btnX, btnY, btnW, btnH, 8);

        // 繪製按鈕文字 (使用 LXGW WenKai TC 霞鶖文楷字型)
        fill(255);
        textSize(isMobile ? 14 : 16);
        textAlign(CENTER, CENTER);
        let btnText = (currentQuestion === quizData.length - 1) ? "查看結果" : "下一題 ➔";
        text(btnText, btnX + btnW / 2, btnY + btnH / 2);
      }
    }

    // 繪製最終得分結算畫面
    function drawResultScreen() {
      let padding = isMobile ? 20 : 35;

      // 繪製卡片陰影
      noStroke();
      fill(210, 215, 225, 120);
      rect(cardX + 6, cardY + 6, cardW, cardH, 16);

      // 繪製主要白色背景卡片
      fill(255);
      stroke(220, 225, 235);
      strokeWeight(2);
      rect(cardX, cardY, cardW, cardH, 16);

      // 顯示完成標題 (使用 LXGW WenKai TC 霞鶖文楷字型)
      textFont(FONT_ZH);
      fill(40);
      textSize(isMobile ? 24 : 32);
      textAlign(CENTER, CENTER);
      text("測驗完成！", width / 2, cardY + cardH * 0.2);

      // 顯示答對題數得分 (分數數字使用 Fraunces 英文字型)
      textFont(FONT_EN);
      fill(74, 144, 226);
      textSize(isMobile ? 42 : 56);
      text(score + " / " + quizData.length, width / 2, cardY + cardH * 0.42);

      // 顯示說明文字 (使用 LXGW WenKai TC 霞鶖文楷字型)
      textFont(FONT_ZH);
      fill(100);
      textSize(isMobile ? 16 : 18);
      text("您一共答對了 " + score + " 道題目", width / 2, cardY + cardH * 0.6);

      // 繪製「重新測驗」按鈕
      let btnW = isMobile ? 140 : 160;
      let btnH = isMobile ? 44 : 50;
      let btnX = width / 2 - btnW / 2;
      let btnY = cardY + cardH * 0.73;

      let isBtnHover = mouseX > btnX && mouseX < btnX + btnW &&
                       mouseY > btnY && mouseY < btnY + btnH;

      fill(isBtnHover ? 60 : 74, isBtnHover ? 130 : 144, isBtnHover ? 210 : 226);
      noStroke();
      rect(btnX, btnY, btnW, btnH, 8);

      // 繪製按鈕文字
      fill(255);
      textSize(isMobile ? 15 : 17);
      text("重新測驗", width / 2, btnY + btnH / 2);
    }

    // 處理滑鼠點擊事件邏輯
    function mousePressed() {
      let padding = isMobile ? 20 : 35;

      // 若測驗尚在進行中
      if (currentQuestion < quizData.length) {
        let q = quizData[currentQuestion];
        let startY = cardY + padding + (isMobile ? 120 : 135);
        let optH = isMobile ? 48 : 54;
        let optGap = isMobile ? 12 : 16;

        // 尚未選擇答案時：檢查點擊了哪一個選項
        if (!answered) {
          for (let i = 0; i < q.options.length; i++) {
            let optY = startY + i * (optH + optGap);

            if (mouseX > cardX + padding && mouseX < cardX + cardW - padding &&
                mouseY > optY && mouseY < optY + optH) {

              selectedOption = i;
              answered = true;

              // 答對時累加得分
              if (selectedOption === q.answer) {
                score++;
              }
              break;
            }
          }
        } else {
          // 已選擇答案時：檢查是否點擊「下一題」按鈕
          let btnW = isMobile ? 120 : 140;
          let btnH = isMobile ? 40 : 45;
          let btnX = cardX + cardW - padding - btnW;
          let btnY = cardY + cardH - padding - btnH;

          if (mouseX > btnX && mouseX < btnX + btnW &&
              mouseY > btnY && mouseY < btnY + btnH) {

            // 切換至下一題並重置單題狀態
            currentQuestion++;
            selectedOption = -1;
            answered = false;
          }
        }
      } else {
        // 結算畫面：檢查是否點擊「重新測驗」按鈕
        let btnW = isMobile ? 140 : 160;
        let btnH = isMobile ? 44 : 50;
        let btnX = width / 2 - btnW / 2;
        let btnY = cardY + cardH * 0.73;

        if (mouseX > btnX && mouseX < btnX + btnW &&
            mouseY > btnY && mouseY < btnY + btnH) {

          // 重置全域變數重新開始
          currentQuestion = 0;
          score = 0;
          selectedOption = -1;
          answered = false;
        }
      }
    }

    // 瀏覽器視窗大小調整時觸發，確保畫布自適應全螢幕
    function windowResized() {
      resizeCanvas(windowWidth, windowHeight);
    }
  </script>
</body>
</html>