# Thử thách 1 Titanic (Tuần 02 - Thực hành)

Dự đoán hành khách sống sót trên Titanic bằng mạng MLP đơn giản với PyTorch.

## Cấu trúc

```
Tham gia thử thách 1 Titanic/
├── titanic_pytorch_s2.ipynb      # Notebook đầy đủ 11 bước: load → EDA → preprocessing → MLP → tuning → submission
├── data/
│   ├── train.csv                 # 891 hành khách (có nhãn Survived)
│   └── test.csv                  # 418 hành khách (dùng để dự đoán)
├── experiments/
│   └── titanic_mlp_v1/
│       ├── best_model.pt         # Model tốt nhất sau tuning
│       ├── params.json           # Cấu hình thí nghiệm + cấu hình tốt nhất
│       ├── tuning_results.csv    # Kết quả 3 cấu hình tuning
│       └── images/               # Biểu đồ từ notebook
└── submission.csv                # Kết quả nộp Kaggle (418 dòng)
```

## Cách chạy

Chạy notebook từ chính thư mục này để đường dẫn `data/` hoạt động.
Trên Kaggle, notebook tự động dùng `/kaggle/input/competitions/titanic`.

Tất cả tham số nằm trong từ điển `params` ở cell "Cấu hình kịch bản".

## Kết quả

| Cấu hình | hidden1 | hidden2 | Val accuracy |
|---|---:|---:|---:|
| small | 16 | 8 | 0.8246 |
| **medium (best)** | **32** | **16** | **0.8284** |
| large | 64 | 32 | 0.8246 |

`submission.csv` gồm 2 cột `PassengerId, Survived` theo đúng định dạng Kaggle.

## Nguồn dữ liệu

Bản public của cuộc thi Titanic (Kaggle): `train.csv` (891 dòng) và `test.csv` (418 dòng),
tải từ các dataset công khai trên Kaggle để có thể chạy lại tại local.
