# tauri-bug-2930
To reproduce https://github.com/tauri-apps/tauri/issues/2930

dist/main_window is a simple main window.

dist/splash_screen is a simple splashscreen.

dist/splash_screen_ng is built by angular.

splash_screen_ng works well. You can check with a static web server, for example `npx http-server dist/splash_screen_ng`.

Steps to reproduce the behavior:

1. cargo tauri build.
2. You can see the main window and splash screen are shown as expected. The js with type=module is OK
3. Modify tauri.conf.json, set splashscreen url to dist/splash_screen_cn
4. "url": "splash_screen/index.html", => "url": "splash_screen_cn/index.html",
5. you can see the splash screen is blank.
