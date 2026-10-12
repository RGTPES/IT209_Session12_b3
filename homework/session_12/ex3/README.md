# Bài tập 3 - Session 12: Tách biệt luồng CI/CD đa môi trường (Staging & Production) với GitHub Environments

## Cấu trúc thư mục nộp bài
```text
homework/session_12/ex3/
├── .github/
│   └── workflows/
│       └── cd-multi-env.yml          # Kịch bản GitHub Actions Workflow
├── cd-multi-env.yml                  # Bản sao trực tiếp file workflow
├── screenshot_production_approval.jpg # Ảnh chụp màn hình cửa sổ phê duyệt Production
├── BAOCAO_BAI3.md                    # Báo cáo chi tiết các bước thực hiện & giải thích
└── README.md                         # Hướng dẫn tổng quan
```

## Tóm tắt nội dung kịch bản Workflow
- **File:** [cd-multi-env.yml](file:///d:/IT209/Session12_b3/homework/session_12/ex3/cd-multi-env.yml) (hoặc [.github/workflows/cd-multi-env.yml](file:///d:/IT209/Session12_b3/.github/workflows/cd-multi-env.yml))
- **Job `deploy-staging`:**
  - Nhánh kích hoạt: `develop` (`if: github.ref == 'refs/heads/develop'`)
  - Environment: `staging`
  - URL: `https://staging.example.com`
- **Job `deploy-prod`:**
  - Nhánh kích hoạt: `main` (`if: github.ref == 'refs/heads/main'`)
  - Environment: `production`
  - URL: `https://api.prod.example.com`
  - Quy tắc bảo vệ: Cấu hình `Required reviewers` trên GitHub Settings yêu cầu phê duyệt thủ công trước khi chạy.

Chi tiết hướng dẫn cấu hình và ảnh minh họa vui lòng xem tại: [BAOCAO_BAI3.md](file:///d:/IT209/Session12_b3/homework/session_12/ex3/BAOCAO_BAI3.md)
