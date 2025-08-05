# Ivyyy415.github.io
#时念&黎安
html_content = """
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>糖罐子</title>
    <style>
        body { font-family: "Helvetica Neue", sans-serif; background-color: #fffafc; color: #333; padding: 20px; }
        h1 { color: #ff6699; text-align: center; }
        section { margin-bottom: 30px; }
        label { display: block; margin-top: 10px; }
        input, textarea, button { width: 100%; padding: 10px; margin-top: 5px; border: 1px solid #ddd; border-radius: 5px; }
        .task { font-weight: bold; margin-top: 10px; }
    </style>
</head>
<body>
    <h1>🍬 糖罐子 · mini页</h1>

    <section>
        <h2>🌈 今日幸福三件事</h2>
        <textarea rows="5" placeholder="写下今天让你幸福的三件小事吧～"></textarea>
    </section>

    <section>
        <h2>🎯 尾巴任务</h2>
        <div id="random-task" class="task">点下面按钮抽一个小任务！</div>
        <button onclick="generateTask()">🎲 抽一个任务</button>
        <script>
            function generateTask() {
                const tasks = [
                    "给哥哥发一句最肉麻的情话 💌",
                    "偷偷录一段5秒钟的小情话音频 😚",
                    "写一封甜甜的悄悄话信 💕",
                    "给自己一个大大的拥抱 🤗",
                    "去照镜子夸自己三句 ✨"
                ];
                const index = Math.floor(Math.random() * tasks.length);
                document.getElementById("random-task").innerText = tasks[index];
            }
        </script>
    </section>

    <section>
        <h2>✅ 完成记录</h2>
        <textarea rows="5" placeholder="记录你完成任务的感受或过程吧～"></textarea>
    </section>

    <section>
        <h2>⏳ 番茄钟</h2>
        <p>打开你的专注模式，25分钟全力投入～</p>
        <button onclick="startTimer()">🍅 开始番茄钟</button>
        <div id="timer" class="task"></div>
        <script>
            function startTimer() {
                let time = 25 * 60;
                const timer = setInterval(() => {
                    let minutes = Math.floor(time / 60);
                    let seconds = time % 60;
                    document.getElementById("timer").innerText = `${minutes} 分钟 ${seconds < 10 ? '0' : ''}${seconds} 秒`;
                    time--;
                    if (time < 0) {
                        clearInterval(timer);
                        alert("叮铃铃～番茄钟结束啦！去休息一下吧宝贝～");
                    }
                }, 1000);
            }
        </script>
    </section>
</body>
</html>
"""

file_path = "/mnt/data/糖罐子_minipage_网页代码.html"
with open(file_path, "w", encoding="utf-8") as f:
    f.write(html_content)

file_path
