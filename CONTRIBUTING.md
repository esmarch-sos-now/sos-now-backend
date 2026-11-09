# Quy trình làm việc

```
feat/xxx ──PR──▶ dev ──PR──▶ main
```

- `main`: bản ổn định, sau này dùng để deploy. Chỉ nhận PR từ `dev`.
- `dev`: nhánh tích hợp (nhánh mặc định). Chỉ nhận PR.
- Không push thẳng vào `main` hoặc `dev`.

## Làm một tính năng mới

```bash
git checkout dev
git pull
git checkout -b feat/ten-tinh-nang
# ... code, commit ...
git push -u origin feat/ten-tinh-nang
gh pr create --base dev
```

Sau khi CI xanh, merge PR vào `dev`.

## Đưa lên main

```bash
gh pr create --base main --head dev --title "Release: ..."
```

## Đặt tên nhánh

- `feat/...` tính năng mới
- `fix/...` sửa lỗi
- `chore/...` cấu hình, dọn dẹp
- `docs/...` tài liệu
