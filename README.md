# ConnorSu_yt-dlp_win_config
My own personal yt-dlp configuration to download ie. YouTube videos
油管下载最清晰视频+音频，多数基本上是AV1+OPUS，下载一个自动en.srt字幕封装成mkv，带章节（如有），带缩略图（如有）：
yt-dlp -f bestvideo+bestaudio --merge-output-format mkv --write-subs --write-auto-subs --embed-subs --convert-subs srt --embed-thumbnail --add-metadata --embed-chapters -o "%(title)s.%(ext)s" 视频链接或列表

油管只下载zh-Hans简体中文字幕，en-US英文字幕
yt-dlp --skip-download --write-subs --write-auto-subs --sub-lang zh-Hans,en-US --convert-subs srt -o "%(title)s.%(ext)s" 视频链接

油管只下载zh-Hans简体中文字幕
yt-dlp --skip-download --write-subs --write-auto-subs --sub-lang zh-Hans --convert-subs srt 视频链接

油管单纯检测有多少字幕，找到之后可以去替换下载字幕里的语言代码
yt-dlp --list-subs 视频链接

P站：yt-dlp --format "bestvideo+bestaudio/best" --merge-output-format mp4 --add-metadata --embed-thumbnail --no-check-certificate --output "%(upload_date)s_%(title)s.%(ext)s" --yes-playlist --download-archive downloaded.txt P站链接

关于处理油管自动生成字幕中重叠的问题，请参考 https://github.com/ConnorSu/subtitle-overlap-fixersu
subtitle-overlap-fixersu 
