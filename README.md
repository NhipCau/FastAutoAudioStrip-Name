# FastAutoAudioStrip-Name
Created using Colab - Automatic audio splitting &amp; automatic file name assignment (ultra-fast version) A tool that detects silence from WAV files bounced in ProTools, splits them into lines, and automatically names files.  Created to improve the efficiency of game audio production and prevent mistakes.
［Eng] JP follows after Eng
Created using Colab - Automatic audio splitting & automatic file name assignment (ultra-fast version) 
1. Detect silence in WAV files 
2. Remove silence and split audio 
3. File name assignment from xlsx, automatic assignment and file saving 

A tool that detects silence from WAV files bounced in ProTools, splits them into lines, and automatically names files.

Created to improve the efficiency of game audio production and prevent mistakes.

[Settings]
# ===== Settings =====
input_audio_path = "/content/drive/MyDrive/Colab Notebooks/sample_voice.wav" # Input WAV file (full path)
excel_path = "/content/drive/MyDrive/Colab Notebooks/sample_list.xlsx" # Excel file (full path)
output_dir = "/content/drive/MyDrive/Colab Notebooks/output_wavs" # Output directory (full path)
target_sample_rate = 48000 # Sample rate (Hz)
vad_aggressiveness = 3 # VAD aggressiveness (0-3)
What is #vad_aggressiveness? : 0 → Breaths are also considered as "voice" / 3 → Breaths and pauses are considered as "silence" and may be split into two chunks / 1 or 2 is a good balance, so if you want to "reduce false positives" use 2, if you want to "pick up as much voice as possible" use 1
silence_thresh = -55 # dB threshold for determining silence (-60db for complete silence, needs to be adjusted if there is background noise)
min_silence_len_ms = 1700 # Minimum silence length (milliseconds) Pre-set number of seconds of silence - pre/post buffer seconds
pre_buffer_sec = 1.5 # Pre-buffer (seconds)
post_buffer_sec = 1.5 # Post-buffer (seconds)

filename_column_index = 1 # Column to get filename from (column A = 0, column B = 1, ...)
filename_start_row = 4 # Start row to get filename from (row 1 = 0, row 2 = 1, ...)

［JP]
Colab を使用して作成・自動音声分割＆ファイル名自動割当「超高速版」
１．WAVファイル内の無音検出
２．無音を削除して音声を分割
３．Xlsxからファイル名付与し自動保割当＆ファイル保存

ProToolsなどでBounce済のWAVファイルから、無音検出し、セリフごとに分割、自動でファイル名をつけるツール
ゲーム音響制作現場の効率化かつミスを防ぐために作成
【設定可能事項】
# ===== 設定 =====
input_audio_path = "/content/drive/MyDrive/Colab Notebooks/sample_voice.wav"       # 入力WAVファイル（完全パス）
excel_path = "/content/drive/MyDrive/Colab Notebooks/sample_list.xlsx"             # Excelファイル（完全パス）
output_dir = "/content/drive/MyDrive/Colab Notebooks/output_wavs"                  # 出力ディレクトリ（完全パス）

target_sample_rate = 48000                  # サンプルレート（Hz）
vad_aggressiveness = 3                      # VADの攻撃性（0〜3）
#vad_aggressivenessとは？：0 → 息継ぎも含めて「音声」と判定／　3 → 息継ぎや間は「無音」と判定し、2つのチャンクに分割される可能性あり／  1 または 2 がバランスが良く、「誤検出を減らしたい」場合は 2、「できるだけ多くの音声を拾いたい」場合は 1

silence_thresh = -55                        # 無音とみなすdB閾値(完全無音は-60db,背景ノイズがある場合は要調整)
min_silence_len_ms = 1700                   # 最小サイレンス長（ミリ秒）事前に設定されている無音秒数-前後バッファ秒
pre_buffer_sec = 1.5                        # 前バッファ（秒）
post_buffer_sec = 1.5                       # 後バッファ（秒）

filename_column_index = 1                   # ファイル名を取得する列（A列=0, B列=1, ...）
filename_start_row = 4                      # ファイル名を取得する開始行（1行目=0, 2行目=1, ...）

