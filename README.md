# 安裝環境
1. 使用 [Anaconda](https://www.anaconda.com/download) 安裝 `Python 3.8.15` 並安裝`Jupyter Notebook`.
2. 安裝 `tensorflow-gpu 2.9.1` 進行模型訓練以及建立所需之訓練和測試集.

# 文件結構

- **CSVs**: 用於訓練和測試的資料集資料夾.
- **Dan-train.ipynb**: Dan 資料集的模型訓練.
- **Kyu-train.ipynb**: Kyu 資料集的模型訓練.
- **PlayStyle_IMAGE_train.ipynb**: Playstyle 資料集的模型訓練.
- **建立playstyle圖檔.ipynb**: 將Playstyle訓練、測試資料轉換為自創圖像.
- **建立Public.ipynb**: 使用模型進行預測.
- **建立Private.ipynb**: 使用模型進行預測.
- **model_dan.h5**: Dan 資料集的模訓練型.
- **model_kyu.h5**: Kyu 資料集的模訓練型.
- **model_Playstyle_image.h5**: Playstyle 資料集的模訓練型.
- **private_submission_template.csv**: Public 與 Private 的資料集預測結果.

# 資料前處理 Dan、Kyu

- 1.先將原始檔(`.csv`) 放進資料夾 (舉Dan為例)
    - 訓練集:`CSVs\dan_train.csv`
    - public測試集:`CSVs\dan_test_public.csv`
    - private測試集`CSVs\dan_test_private.csv`
- 2.分別使用以下程式碼來進行訓練 (舉Dan為例)
    - 訓練集:`Dan-train.ipynb`
    - public測試集:`建立Public.ipynb`
    - private測試集:`建立Private.ipynb`

# 資料前處理 Playstyle

- 1.先將原始檔(`.csv`) 放進資料夾
    - 訓練集:`CSVs\play_style_train.csv`
    - public測試集:`CSVs\play_style_test_public.csv`
    - private測試集`CSVs\play_style_test_private.csv`
- 2.使用以下程式碼將原始檔(`.csv`) 轉換成(`.png`) 該檔案會對應`.csv` 內的資訊
    - 訓練集:`建立playstyle圖檔.ipynb` (第一個儲存格)
    - public測試集:`建立playstyle圖檔.ipynb` (第二個儲存格)
    - private測試集`建立playstyle圖檔.ipynb` (第三個儲存格)
- 3.使用以下程式碼來進行訓練
    - 訓練集:`PlayStyle_IMAGE_train.ipynb`
    - public測試集:`建立Public.ipynb`
    - private測試集:`建立Private.ipynb`

# 訓練方式 (舉Dan為例)

- 1.開啟`Dan-train.ipynb`
- 2.從第`1`個儲存格開始執行程式，至第`5`格為止
- 3.在第`6`個儲存格開始建立模型
- 4.在第`7`個儲存格建立學習率調度並設置model checkpoint 來存最高一筆的`val_accuracy`
- 5.在第`8`個儲存格開始訓練模型
- 6.在第`9`以及`10`儲存格查看訓練後的`loss` `val_loss` `accuracy` `val_accuracy` 曲線圖

# 測試方式 (舉Dan為例)

- 1.開啟`建立Public.ipynb`或是`建立Private.ipynb`
- 2.從第`1`個儲存格開始執行程式，至第`3`格為止
- 3.在第`4`個儲存格引入model checkpoint 並寫入(`.csv`)的格式，並將驗證後的答案存入`private_submission_template.csv`