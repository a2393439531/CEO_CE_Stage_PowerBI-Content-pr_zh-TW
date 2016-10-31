# 單一 web 網頁轉換指南

1.  請移至目標網站， `File -> Save As`
2.  儲存頁面使用它 `github-file-name`
3.  開啟命令提示字元並瀏覽至網頁的資料夾
4.  執行 pandoc 轉換主題 `pandoc -f html -t markdown_github <github-file-name>.html -o <github-file-name>.md`
5.  重新命名 [assets] 資料夾，從 `<github-file-name>_files` 到 `<github-file-name>`。 那里可能會導致警告但點選它還是。
6.  開啟 markdown 檔使用 [notepad + +](https://notepad-plus-plus.org/)。
7.  移除任何不必要的內容，如頁首、 頁尾和提要欄位。
8.  修正 H1 headding 加入雜湊標記和空間之前 H1 標題和移除雙底線。
9.  移除空的範圍內使用的標記搜尋和取代
    
    1.  按 `Ctrl+H` 或從功能表瀏覽 `Search -> Replace`
    2.  請確定這些選項會檢查
        -  換行
        -  規則運算式的搜尋模式︰
        -  搜尋模式:。 符合新行字元
    3.  尋找目標︰ `<span>(.*?)</span>` 取代︰ `\1`
    4.  全部取代

10.  修正該映像連結︰

    1.  Search： `\!\[(.*?)\]\(./<github-file-name>_files/`
    2.  取代： `![\1]\(media/<github-file-name/`
    3.  在 [檔案總管] 中移動映像資料夾至媒體目錄中建立一個萬一不 exisit。
    4.  映像資料夾中移除頁面 （標誌和圖示） 的已移除的區段中的任何非影像項目，例如.js、.css、 php，以及任何未使用的映像。

11.  在您選擇的編輯器中開啟 markdown 檔案。 

12. 從原始網頁 markdown 內容進行比較。 您可能要修正一些其他的資訊，例如讓確定排序的清單正確分開。 可能有少數 `<span>` 需要移除的標記或其他格式設定變更而需要進行。 任何未不會取得轉換的資料表必須也固定。

13.  將任何相關的中繼資料加入至您的主題。

14.  將主題加入至 github 儲存機制 （沒有取得映像資料夾），認可對本機分支。

15.  將分支推送至私用分叉及提取要求提交到主要分支

16.  等候通過驗證，並進行任何修正，視您的主題。 一旦您滿意的登關閉提取要求使用 `#sign-off`。