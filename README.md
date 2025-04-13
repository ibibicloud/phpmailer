# PHPMailer
基于 https://github.com/PHPMailer/PHPMailer/tree/v6.9.3

## 安装
~~~
composer require ibibicloud/phpmailer
~~~

## 文档
https://github.com/PHPMailer/PHPMailer/tree/v6.9.3?tab=readme-ov-file#a-simple-example

## 示例

```
use PHPMailer\PHPMailer;
use PHPMailer\SMTP;
use PHPMailer\Exception;

$mail = new PHPMailer(true);
try {
    // $mail->SMTPDebug	= SMTP::DEBUG_SERVER;
    $mail->isSMTP();
    $mail->Host			= 'smtp.qiye.aliyun.com';
    $mail->SMTPAuth		= true;
    $mail->Username		= '发件人邮箱账号@nice.day';
    $mail->Password		= '国内邮箱请使用授权码而非密码';
    $mail->SMTPSecure	= PHPMailer::ENCRYPTION_SMTPS;
    $mail->Port			= 465;
    $mail->CharSet		= PHPMailer::CHARSET_UTF8;
    $mail->setFrom('发件人邮箱账号@nice.day', '阿里邮箱');
    $mail->addAddress('收件人邮箱账号@nice.day', 'QQ邮箱');
    $mail->isHTML(true);
    $mail->Subject = '这是邮件标题';
    $mail->Body    = '这是文件内容<br/><b>这是加粗</b><hr><img src="https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png">';
    $mail->send();
    echo 'Message has been sent';
} catch (Exception $e) {
    echo "Message could not be sent. Mailer Error: {$mail->ErrorInfo}";
}
```
