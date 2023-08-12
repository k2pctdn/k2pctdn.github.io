---
title: "Concept của Likelihood và ứng dụng của nó"
excerpt: Bài viết này dịch lại một paper của tác giả Etz về khái niệm likelihood (sự hợp lý) trong lý thuyết xác suất, đồng thời trình bày một số ứng dụng cơ bản của khái niệm này.
tags: 
- mathematics
- probability
---

> 📓 Paper gốc:
> 
> Etz A. Introduction to the Concept of Likelihood and Its Applications. Advances in Methods and Practices in Psychological Science. 2018;1(1):60-69. doi:10.1177/2515245917744314

Likelihood (hợp lý) không phải là xác suất (probability) mà là một đại lượng tỷ lệ với xác suất. Sự hợp lý của một giả thuyết $H$ (the likelihood of a hypothesis) khi biết một số dữ liệu liên quan $D$ (given some data) tỷ lệ với xác suất nhận được $D$ nếu $H$ là một giả thuyết đúng. Gọi $L$ là hàm likelihood thì $L(H)$ đánh giá độ hợp lý của giả thuyết $H$:

$$
L(H) = K \times \Pr(D \mid H)
$$

Vì likelihood không phải là xác suất nên nó thường không tuân theo các quy tắc của xác suất, một trong số đó là likelihoods không cần phải có tổng hay tích phân bằng 1.

Một điểm khác biệt quan trọng giữa probability và likelihood là những đại lượng được cố định và những đại lượng biến thiên trong công thức của likelihood.
- Trong công thức xác suất có điều kiện $\Pr(D \mid H)$ thì giả thuyết $H$ là cố định, nhưng dữ liệu $D$ có thể thay đổi tùy ý.
- Nhưng trong $L(H)$ thì hypothesis $H$ có thể thay đổi tùy ý còn data $D$ thì cố định.

# Tiên đề về likelihood

> __The Law of Likelihood__
> 
> within the framework of a statistical model, a particular set of data supports one statistical hypothesis better than another if the likelihood of the first hypothesis, on the data, exceeds the likelihood of the second hypothesis

Giả sử có một tập data $D$, ta có hai giả thuyết về nguồn gốc sinh ra $D$ là $H_1$ và $H_2$. Giả thuyết $H_1$ được cho là hợp lý hơn giả thuyết $H_2$ còn lại nếu xác suất xảy ra $D$ dựa trên giả thuyết này cao hơn giả thuyết còn lại: $\Pr(D \mid H_1) > \Pr(D \mid H_2)$. Nếu dấu bằng xảy ra thì ta không có căn cứ (evidence) nào về việc $H_1$ hợp lý hơn $H_2$.

Một đại lượng đánh giá sự hợp lý về mặt thống kê giữa $H_1$ và $H_2$ là tỷ số của sự hợp lý của chúng (chú ý hằng số $K$ trong công thức của $L(H)$ bị khử):

$$
\mathrm{LR}(H_1, H_2) = \frac{L(H_1)}{L(H_2)} = \frac{\Pr(D \mid H_1)}{\Pr(D \mid H_2)}
$$

> __Likelihood được dùng để so sánh__

Không như probability, có thể được sử dụng trực tiếp để đánh giá khả năng xảy ra của một biến cố, likelihood khi đứng một mình thì nó không thể hiện được điều gì nhiều. Chỉ khi có sự so sánh giữa hai hoặc nhiều likelihood với nhau thì likelihood mới có ý nghĩa.

__Ví dụ kinh điển__

Binomial distribution: hai tham số $n$ và $p$: số lần phép thử thành công với xác suất $p$ trong $n$ lần thử.

Hàm khối xác suất probability mass function (PMF): $p^k$ xác suất thành công $k$ lần, $(1-p)^{n-k}$, xác suất không thành công trong $n-k$ lần thử, có $\binom{n}{k}$ thí nghiệm cho ra $k$ lần thành công và $n-k$ lần thử. 

$$
f(k;n,p) = \Pr(k;n,p) = \Pr(X=k) = \binom{n}{k}p^k(1-p)^{n-k}
$$

Giả sử một đồng xu được tung $n$ lần và ta thấy có $x$ lần mặt ngửa (head) xuất hiện và $n-x$ lần mặt xấp xuất hiện. Xác suất để có $x$ mặt ngửa trong $n$ lần tung đồng xu tuân theo phân phối Binomial

$$
\Pr(X=x;n,p)=\binom{n}{x}p^x(1-p)^{n-x}
$$

với $p$ là xác suất xuất hiện mặt ngửa.
Giả sử đồng xu công bằng (xác suất xuất hiện của mỗi mặt là $p=0.5$), xác suất để có $06$ mặt ngửa xuất hiện trong $10$ lần thử là 

$$
\Pr(X=6;n=10, p=0.5) = \frac{10!}{6! \times 4!}0.5^6 \times 0.5^4 \approx 0.21.
$$

Nếu đồng xu đã bị làm gian lận với xác suất suất hiện mặt ngửa là $p = 0.75$, lúc này xác suất để xuất hiện mặt ngửa 06 lần trong 10 lần thử là

$$
\Pr(X=6;n=10, p=0.75) = \frac{10!}{6! \times 4!}0.75^6 \times 0.25^4 \approx 0.15.
$$

Lúc này ta có hai giả thuyết:
- $H_1$: đồng xu công bằng với $p = 0.5$.
- $H_2$: đồng xu gian lận với $p=0.75$.

Với cùng một dữ liệu là mặt ngửa xuất hiện 06 lần trong số 10 lần thực hiện, ta có:

$$
\begin{aligned}
L(H_1) &= \Pr(X=6 \mid p = 0.5),\\
L(H_2) &= \Pr(X=6 \mid p = 0.75).
\end{aligned}
$$

Lúc này likelihood ratio sẽ là $\displaystyle  LR(H_1,H_2) \approx \frac{0.21}{0.15} \approx 1.4$.
