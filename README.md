# Ginvify — website prototype

Prototype trang web cho **Ginvify**, công ty công nghệ AI (thị trường Việt Nam).

Đây là bản dựng thử để **chốt hướng thiết kế**, không phải bản production.

## Xem demo

Mở `index.html` trực tiếp, hoặc:

```bash
python3 -m http.server 8899
# → http://localhost:8899
```

## 4 hiệu ứng signature

| # | Hiệu ứng | Kỹ thuật |
|---|----------|----------|
| ① | Agent graph (hero) | Canvas 2D — node/edge + packet chạy, node sáng khi nhận request |
| ② | Exploded AI stack | DOM layers + scroll-driven `transform` |
| ③ | Data → Order | Canvas 2D — 1.558 điểm tụ từ hỗn loạn thành biểu đồ |
| ④ | Demo scrub | Canvas 2D — pipeline RAG 5 bước, tua bằng scroll |

## Đặc điểm kỹ thuật

- **1 file HTML duy nhất**, không thư viện ngoài, không build step
- Không dùng WebGL — toàn bộ hiệu ứng bằng Canvas 2D + DOM/SVG
- `IntersectionObserver` để chỉ chạy animation khi trong viewport
- Có đường `prefers-reduced-motion`
- Canvas tự resize theo container, cap DPR ở 2

## Trạng thái

⚠️ **Số liệu trong trang (24 / 98% / 6 tuần) là số mẫu**, phải thay bằng số thật trước khi công bố.

Bước tiếp theo dự kiến: chuyển sang Astro project, tách thành component, rồi mới polish và deploy.

## Tham chiếu

Ý tưởng kỹ thuật học từ teardown `unitedcarriers.com`: họ dùng ảnh ghép lớp + canvas 2D +
frame-sequence cho phần lớn hiệu ứng, chỉ 2 chỗ dùng WebGL thật. Prototype này đi theo hướng
"rẻ mà vẫn đẹp" — bỏ WebGL, giữ cảm giác.
