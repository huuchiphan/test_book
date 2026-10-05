# Góc học tập của Chi — blog Quarto

Khung blog cá nhân viết bằng Quarto. Nội dung dùng Markdown và công thức toán LaTeX; mỗi bài viết nằm trong một tệp `.qmd`.

## 1. Cài công cụ

- Cài Quarto: https://quarto.org/docs/get-started/
- Cài GitHub Desktop: https://desktop.github.com/
- (Tuỳ chọn) cài VS Code để soạn bài thoải mái hơn.

## 2. Xem blog trên máy

Mở thư mục `blog-hoc-tap` trong VS Code. Trong Terminal tại thư mục đó, chạy:

```sh
quarto preview
```

Quarto sẽ dựng bản xem trước và mở trình duyệt. Nhấn `Ctrl+C` để dừng.

## 3. Viết một bài mới

Tạo tệp mới trong `posts`, ví dụ `posts/luat-so-lon.qmd`:

```markdown
---
title: "Luật số lớn"
date: "2026-10-06"
categories: [toán, xác suất-thống-kê]
---

Khi số phép thử $n$ tăng lên, trung bình mẫu tiến gần đến kỳ vọng:

$$
\bar X_n = \frac{1}{n}\sum_{i=1}^{n}X_i
\xrightarrow{p} \mathbb{E}[X].
$$
```

Dùng `$...$` cho công thức trong câu và `$$...$$` cho công thức tách riêng. LaTeX được hiển thị bằng KaTeX trong trang web.

## 4. Đưa blog lên GitHub Pages

1. Đăng nhập GitHub và tạo repository mới, ví dụ `goc-hoc-tap`.
2. Trong GitHub Desktop chọn **File → Add local repository**, rồi chọn thư mục này. Nếu GitHub Desktop báo chưa có repository, chọn **Create a repository** và đặt thư mục local là `blog-hoc-tap`.
3. Commit các tệp và chọn **Publish repository** để đẩy lên GitHub.
4. Trên GitHub, mở **Settings → Pages**. Chọn **GitHub Actions** làm nguồn xuất bản.
5. Mỗi lần commit và push lên nhánh `main`, workflow sẽ dựng rồi cập nhật blog. Lần đầu có thể mất vài phút; địa chỉ thường có dạng `https://TEN-GITHUB.github.io/goc-hoc-tap/`.

Repository công khai thường cần thiết để dùng GitHub Pages miễn phí. Chỉ đăng nội dung bạn muốn chia sẻ công khai. Nếu muốn giữ ghi chép riêng tư, vẫn có thể viết và xem blog trên máy, hoặc chọn dịch vụ lưu trữ khác có hỗ trợ trang riêng tư.

## Cấu trúc thư mục

- `_quarto.yml`: cấu hình giao diện, điều hướng và công thức.
- `index.qmd`: trang chủ.
- `posts/`: bài viết.
- `about.qmd`: trang giới thiệu.
- `.github/workflows/publish.yml`: tự dựng và xuất bản sau mỗi lần push.
