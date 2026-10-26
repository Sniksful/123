# 123
examples/xiaomi-mitv-mssp1/debloat.txt
https://github.com/Gathin23/cleanyourtv xiaomi-mitv-mssp1
# Stock-home recommendation feeds
com.google.android.tvrecommendations
com.google.android.leanbacklauncher.recommendations

# --- Verified extras (same unit, second pass 2026-10-25) ---
# All packages in this section were also disabled with pm disable-user --user 0 on a live
# MSSP1 / PI.5925, then reboot-checked with an empty logcat -b crash afterwards. Nothing had
# to be re-enabled. Read each note before applying: two entries change system behaviour.

# Error-report and feedback uploaders (pure telemetry, nothing user-facing)
com.google.android.feedback
com.google.android.tv.bugreportsender

# Partner auto-installer: pushes sponsored apps through Play on fresh accounts
android.autoinstalls.config.xiaomi.amelie

# Heavy screensavers. REASSIGN THE SCREENSAVER FIRST (e.g. the launcher's ClockDream via
# `settings put secure screensaver_components`, or tools/theme.sh) — otherwise the screensaver
# setting dangles until reassigned. Ambient Mode is also what shows the stock backdrop loop.
com.google.android.backdrop
com.mitv.dream

# Xiaomi "TV Manager" rocket-cleaner app
com.xiaomi.mitv.tvmanager

# Preinstalled Google apps that reinstall freely from Play whenever wanted
com.google.android.play.games
com.google.android.videos
org.chromium.webview_shell
com.android.printspooler

# Xiaomi media leftovers and accessibility suite. The gallery doubles as the photo screensaver,
# so keep com.mitv.gallery enabled if you want Photos screensaver instead of reassigning it.
com.xiaomi.mimusic2
com.mitv.gallery
com.google.android.marvin.talkback
python3 -m venv tools/venv && tools/venv/bin/pip install -r tools/requirements.txt
export TV_HOST=192.168.0.105
tools/venv/bin/python -I tools/tv.py --probe
tools/disable.sh examples/xiaomi-mitv-mssp1/debloat.txt
TV_HOST=192.168.0.105 launcher/build-and-install.sh
