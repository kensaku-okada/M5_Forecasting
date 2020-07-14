# kaggle-m5

ルート直下にdocフォルダを作り、よしなにサンプルデータを格納してください。


# ディレクトリ概要
```
.
├── accuracy
│   ├── M5_Three_shades_of_Dark_Darker_magic #ディレクトリ名のnotebook(旧kernel)を参考に(大部分写経)して
│   │   ├── feature_engineering_for_lag_features.ipynb
│   │   ├── feature_engineering_for_mean_encoding_categorial_values.ipynb
│   │   ├── notebooks
│   │   │   ├── analysis_for_customizing_features.ipynb
│   │   │   ├── analysis_for_lag_features.ipynb
│   │   │   ├── wrmsse.py
│   │   │   ├── wrmsse_RMSE_and_WRMSSE_of_a_submission_useless.ipynb
│   │   │   ├── wrmsse_evaluator-with-extra-features.ipynb
│   │   │   └── wrmsse_fast-clear-wrmsse-18ms_useless.ipynb
│   │   ├── preprocessing_for_base_grid_having_item_properties_and_sales_prices.ipynb
│   │   ├── preprocessing_for_calendar.ipynb
│   │   ├── preprocessing_for_cleaning_base_grid_after_all_pickle_creations.ipynb
│   │   ├── trained_model ＃訓練済みのモデルやnotebookを格納。スコアはフォルダ名に記載
│   │   ├── training_and_validation.ipynb
│   │   └── weights.csv #wrmsseを計算するときの各レベルの各対象の重みを記したファイル。wrmsse基準で学習する際は、ここから適切なweightを抽出する処理を追加する必要がある(wip)
├── uncertainty # undertainty対応時に利用するディレクトリ

├── README.md
├── data # ファイルサイズが大きいのでgithubには上げていない。各自でダウンロードしディレクトリを作り格納する。以下は格納例。
│   ├── M5_Three_shades_of_Dark_Darker_magic
│   │   ├── base_grid_for_darker_magic.pkl
│   │   ├── base_grid_with_calendar_features_for_darker_magic.pkl
│   │   ├── base_grid_with_lag_features_for_28_days.pkl
│   │   ├── base_grid_with_mean_encoded_ids_means_stds_for_darker_magic.pkl
│   │   ├── base_grid_with_sales_price_features_for_darker_magic.pkl
│   │   ├── calendar.csv
│   │   ├── clearned_base_grid_for_darker_magic.pkl
│   │   ├── sales_train_validation.csv
│   │   ├── sample_submission.csv
│   │   └── sell_prices.csv
│   ├── for_Japanese_beginner(with_WRMSSE_in_LGBM))
│   │   ├── calendar.csv
│   │   ├── m5-forecasting-accuracy_features_added_730_days.csv
│   │   ├── m5-forecasting-accuracy_preprocessed_730_days.csv
│   │   ├── m5-forecasting-accuracy_product_detail.csv
│   │   ├── sales_train_validation.csv
│   │   ├── sample_submission.csv
│   │   ├── sell_prices.csv
│   │   └── validation_submission.csv
│   └── m5-forecasting-accuracy.zip
└── doc
    └── M5-Competitors-Guide-Final-10-March-2020.docx
```

# 実行手順
以下の順番でファイルを実行する。ファイル内指定の場所にpickle/binファイルが格納される。(分裂統合による改善の余地あり20200606)
1. preprocessing_for_base_grid_having_item_properties_and_sales_prices.ipynb
1. preprocessing_for_calendar.ipynb
1. preprocessing_for_cleaning_base_grid_after_all_pickle_creations.ipynb
1. feature_engineering_for_lag_features.ipynb
1. feature_engineering_for_lag_features.ipynb
1. training_and_validation.ipynb
    - 学習済みのdumpファイルがすでにある場合はUSE_AUX = Falseとする


最終的に出力されるcsvファイルを提出する。