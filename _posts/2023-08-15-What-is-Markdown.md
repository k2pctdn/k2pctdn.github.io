---
title: Markdown
tags:
- markdown
- tutorial
---

Bài viết này nhằm mục đích giới thiệu ngắn gọn về Markdown, một Light Markup Language (LML) hiện rất phổ biến trên Internet. 

# Markdown là gì?

Markdown là một Lightweight Markup Language-LML, tạm dịch là _ngôn ngữ đánh dấu nhẹ_ (vì chưa có một bản dịch đủ hay cho cụm từ Lightweight Markup Language nên tác giả xin giữ nguyên thuật ngữ tiếng Anh). Để hiểu cụm từ Lightweight Markup Language thì ta có thể phân tách nó ra làm hai phần là "Markup Language" và "Lightweight". Markup Language (ngôn ngữ đánh dấu) là một hệ thống chuyển đổi văn bản (text-encoding system) trên máy tính, nó sử dụng một số ký tự và cú pháp đặc biệt để đánh dấu văn bản và chỉ cho máy tính biết được định dạng của văn bản[^1]. Thật sự thì với người dùng đại chúng cách diễn đạt này là khó hiểu. Ta có thể đơn giản hóa nó thông qua ví dụ sau.

Trong trình xử lí văn bản (word processing application) rất phổ biến ở Việt Nam là Microsoft Word, để in đậm (bold) một đoạn văn bản thì ta thường thực hiện như sau:
- Chọn (select) đoạn văn bản cần in đậm.
- Bấm tổ hợp phím `Ctrl + B` hoặc nhấn vào nút `Bold` trên thanh công cụ (Tool bar).

Đoạn văn bản ngay lập tức sẽ được hiển thị là đã in đậm. Trên thực tế thì ta vừa "mark" (đánh dấu) đoạn văn bản đó và máy tính, hay cụ thể là Microsoft Word hiểu rằng, với mark (dấu) này thì đoạn văn bản đó phải được hiển thị ở dạng in đậm (bold). 
Microsoft Word là một trình xử lí văn bản theo dạng _WYSIWYG_ (viết tắt các chữ cái đầu của _What You See Is What You Get_) nên ta không thấy được sự _đánh dấu_ này mà chỉ thấy được kết quả cuối cùng là đoạn văn bản đã được in đậm.
Một vấn đề của các trình xử lí văn bản dạng WYSIWYG là ta không biết đoạn văn bản đã được mark như thế nào mà chỉ thấy kết quả cuối cùng. Ví dụ, một đoạn văn (paragraph) trong Word được mark để giãn dòng với khoảng cách `1.15 pt`, một đoạn văn khác lại được mark là giãn dòng `1.151 pt`. Khi hiển thị thì hai đoạn văn này gần như giống hệt nhau nhưng rõ ràng là khoảng cách giữa hai dòng đang khác nhau và ta không thể biết được khoảng cách này là bao nhiêu cho đến khi định dạng lại đoạn văn (format paragraph). Dễ thấy khi copy văn bản giữa các nguồn khác nhau và paste vào trong Word thì ta thấy các định dạng lộn xộn và không rõ thông số của định dạng.

Các markup language, ví dụ như Markdown, không ẩn đi các mark này mà hiển thị rõ để ta biết đoạn văn bản đã được mark để hiển thị với thông số như thế nào. Ví dụ, trong Markdown, để **in đậm** một từ, cụm từ, hay đoạn văn nào đó thì cú pháp "đánh dấu" là đặt đoạn văn dó ở giữa hai cặp dấu hoa thị `**`, hoặc giữa hai cặp dấu gạch chân `__` (đây là hai dấu `_` được viết liên tiếp).

```
**đoạn văn bản cần in đậm**

hoặc

__đoạn văn bản cần in đậm__
```

Vậy mỗi khi thấy một đoạn văn bản nào được mark bằng hai cặp dấu hoa thị `**` thì ta biết chắc chắn đoạn văn bản đó đang được in đậm. Một ưu điểm rõ ràng của các markup language là nó cho người viết kiểm soát một cách rõ ràng định dạng của văn bản đang viết, hoàn toàn không có các định dạng ẩn đi như các trình xử lí văn bản dạng WYSIWYG. Tuy nhiên, các văn bản viết bằng markup language cũng có một nhược điểm lớn là do các mark không bị ẩn đi, nên với các văn bản có rất nhiều mark thì ta rất dễ rối. 

> **Markup Language**
> Vậy tóm tắt lại, markup language là các "ngôn ngữ" sử dụng các "mark" (dấu) để chỉ cho máy tính biết đoạn văn bản nào đó cần được định dạng (format) như thế nào.

> **Markup**
> Từ markup trong lĩnh vực điện toán (computing) được giải thích theo từ điển Oxford là "the symbols used in computer documents that give information about the structure of the document and tell the computer how it is to appear on the computer screen, or how it is to appear when printed"[^2].

[^1]: [Wikipedia - Markup Language](https://en.wikipedia.org/wiki/Markup_language)
[^2]: [Definition of markup noun from the Oxford Advanced Learner's Dictionary](https://www.oxfordlearnersdictionaries.com/definition/english/markup?q=markup)
