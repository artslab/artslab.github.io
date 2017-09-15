---
title: "Контактная форма"
id: 34
date: '2007-07-24 04:55:34 +0200'
author: serEga
layout: page
guid: http://artslab.info/?page_id=34
permalink: "/contact/"
prosmotr:
- 335
dsq_thread_id:
- 1785868422
---

<div id="contact-form">
  <input type="email" name="_replyto" placeholder="Ваша почта для ответа" class="contact-form-title">
  <textarea name="message" placeholder="Сообщение" class="contact-form-text"></textarea>
  <input type="submit" class="btn-send-email" value="Отправить">
</div>

<div id="message-success" style="display:none;"><p><b>Спасибо!</b> Ваше сообщение было отправлено!</p></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
<script type="text/javascript">
$('.btn-send-email').on('click', () => {
     $.ajax({
        url: "https://formspree.io/dev@artslab.info", 
        method: "POST",
        data: {message: $('.contact-form-text').val(), email: $('.contact-form-title').val()},
        dataType: "json"
     });
		 $('#contact-form').hide();
		 $('#message-success').show();
 });
</script>