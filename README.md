<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>お会計電卓</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body { font-family: sans-serif; padding: 20px; background: #111; color: #fff; }
    input, button { font-size: 1.2em; margin: 5px 0; width: 100%; }
    .result { margin-top: 20px; font-size: 1.4em; }
  </style>
</head>
<body>
  <h1>お会計電卓</h1>
  <label>合計金額（円）</label><input type="number" id="total" />
  <label>人数</label><input type="number" id="people" />
  <button onclick="calc()">計算する</button>
  <div class="result" id="result"></div>

  <script>
    function calc() {
      const total = parseFloat(document.getElementById('total').value);
      const people = parseInt(document.getElementById('people').value);
      if (isNaN(total) || isNaN(people) || people <= 0) {
        document.getElementById('result').innerText = '正しい数値を入力してください';
        return;
      }
      const per = Math.ceil(total / people);
      document.getElementById('result').innerText = `一人あたり ${per} 円です`;
    }
  </script>
</body>
</html>