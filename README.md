<!DOCTYPE html>
<html>
<head>
    <title>Mera Music App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            margin: 0;
            padding: 20px;
            color: #333;
        }
        .player {
            background: rgba(255,255,255,0.8);
            border-radius: 15px;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        audio { width: 100%; margin: 20px 0; }
        .song-list { margin-top: 20px; }
        .song-item {
            padding: 10px;
            border-bottom: 1px solid #eee;
            cursor: pointer;
        }
        .song-item:hover { background: #f8f8f8; }
    </style>
</head>
<body>
    <div class="player">
        <h1>🎵 Mera Music Player</h1>
        <audio id="audio" controls></audio>
        
        <div class="song-list" id="playlist">
            <!-- यहां गाने अपने आप लोड होंगे -->
        </div>
    </div>

    <script>
        // ऑडियो फाइल्स की लिस्ट (बाद में बदल सकते हैं)
        const songs = [
            { name: "पहला गाना", file: "audio/song1.mp3" },
            { name: "दूसरा गाना", file: "audio/song2.mp3" }
        ];

        const audio = document.getElementById('audio');
        const playlist = document.getElementById('playlist');

        // प्लेलिस्ट बनाना
        songs.forEach((song, index) => {
            const songItem = document.createElement('div');
            songItem.className = 'song-item';
            songItem.textContent = song.name;
            songItem.onclick = () => {
                audio.src = song.file;
                audio.play();
            };
            playlist.appendChild(songItem);
        });
    </script>
</body>
</html>
