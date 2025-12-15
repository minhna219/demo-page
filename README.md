# Github Pages

[GitHub Pages](https://pages.github.com/) is designed to host your personal, organization, or project pages from a GitHub repository.

## 1. General

Có 2 loại Github Pages là:
- `Deploy from a branch`: Deploy chính xác từ code của 1 nhánh, thường dùng với các Webiste tĩnh chạy HTML, CSS và JavaScript, ... thông thường
- `Github Actions`: Deploy phần output từ code của 1 nhánh, thường dùng với các Webiste tĩnh chạy ReactJS, VueJS và NextJS, ... Cách này sẽ giúp người dùng giữ source code trên nhánh, và chỉ đẩy file đã build lên Webiste

## 2. Visibility

Bình thường thì repo phải public thì mới có thể cấu hình Github Pages, và Website sẽ public đối với tất cả mọi người

Tuy nhiên, có thể giới hạn access cho Github Pages, giúp cho Website chỉ có thể truy cập từ 1 số Github user nhất định, nhưng tính năng này là dành cho Github enterprise

<div align="left">
  <img src='./0pics/visible.png' width="800">
</div>

## 3. Steps đối với source là `Deploy from a branch`

Dùng GitHub Pages để host web tĩnh theo 1 trong 2 cách sau

### 3.1. Cách 1 (Recommended): Project site

Vào link [này](https://pages.github.com/) rồi click chọn: Project site > Start from scratch

Sau đó làm theo hướng dẫn

--> Vào: **Settings** > **Pages** > **Dưới phần Branch**, rồi chọn `main`. Cuối cùng là ấn **Save**

<div align="left">
  <img src='./0pics/setting.png' width="800">
</div>

--> Sau đó truy cập URL:
```
https://minhna219.github.io/demo-page/

(tức là https://<GITHUB_USER>.github.io/<REPO_NAME>/)
```

<div align="left">
  <img src='./0pics/result.png' width="800">
</div>

### 3.2. Cách 2: User or organization site

Vào link [này](https://pages.github.com/) rồi click chọn: User or organization site

Sau đó làm theo hướng dẫn

## 4. Steps đối với source là `Github Actions`

Chọn như hình dưới và chọn 1 workflow phù hợp

<div align="left">
  <img src='./0pics/gha.png' width="800">
</div>

--> Nếu Github Pages dùng Mkdocs thì sẽ dùng file [này](https://github.com/minhna219/demo-page-mkdocs/blob/main/.github/workflows/deploy-pages-mkdocs.yml) cho Github Actions bằng cách thay thế vào code trong hình dưới
<div align="left">
  <img src='./0pics/gha-mk1.png' width="800">
</div>

--> Có push lên nhánh `master` thì sẽ tự động chạy Github Actions và deploy lên Github Pages
<div align="left">
  <img src='./0pics/gha-mk2.png' width="800">
</div>

--> Xong quay trở lại màn cấu hình Github Pages thì sẽ thấy URL là:
```
https://minhna219.github.io/demo-page-mkdocs/

(tức là https://<GITHUB_USER>.github.io/<REPO_NAME>/)
```

## 5. Custom domain

Để cấu hình custom domain cho Github Pages, ta làm như sau:

Đầu tiên là tạo record trong Route 53 Hosted zone:
- Type: `CNAME`
- Name: `ghp.testblogforthesis.link`
- Value: `minhna219.github.io` (`<GITHUB_USER>.github.io`)
- TTL: `3600`

<div align="left">
  <img src='./0pics/domain1.png' width="800">
</div>

Đợi 1 lát, rồi vào trang cấu hình Github Pages, điền domain `ghp.testblogforthesis.link` và chọn "Save".

Sau 1-2' sẽ hiện như dưới:
<div align="left">
  <img src='./0pics/domain2.png' width="800">
</div>

--> Kết quả
<div align="left">
  <img src='./0pics/domain3.png' width="800">
</div>

--> URL bây giờ sẽ là `https:// ghp.testblogforthesis.link`, không phải là `https://minhna219.github.io/demo-page/` nữa

--> Nếu truy cập URL `https://minhna219.github.io/demo-page/` thì sẽ tự động nhảy sang URL `https:// ghp.testblogforthesis.link`

Tiếp tục đợi 1 lát, rồi chọn `Enforce HTTPS`. Bằng cách này, kết nối đến domain sẽ luôn là kết nối HTTPS
<div align="left">
  <img src='./0pics/domain4.png' width="800">
</div>

--> Thử truy cập

--> Thành công
<div align="left">
  <img src='./0pics/domain5.png' width="800">
</div>

## 6. References

> https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
> 
> https://viblo.asia/p/tao-trang-web-voi-github-pages-obA46v1G4Kv
> 
> https://www.youtube.com/watch?v=e5AwNU3Y2es
> 
> https://www.youtube.com/watch?v=o5g-lUuFgpg
> 
> https://www.youtube.com/watch?app=desktop&v=nAXfd184JqE
> 
> https://www.youtube.com/watch?v=OltY8JIaP-4
> 
> https://www.youtube.com/watch?app=desktop&v=JdK-tYs3G8Y 
