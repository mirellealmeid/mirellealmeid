- <?php

  $nome = $_POST['nome'];
  $email = $_POST['email'];
  $mensagem = $_POST['mensagem'];
  $data_envio = date('d/m/Y');



  $arquivo = "
    <html>
      <p><b>Nome: </b>$nome</p>
      <p><b>E-mail: </b>$email</p>
      <p><b>Numero: </b>$mensagem</p>
      <p>Este e-mail foi enviado em <b>$data_envio</b> às </p>
    </html>
  ";
  
  $destino = "comercial@innovae.com.br";
  $assunto = "Contato pelo Site para Apresentação";

  
  $headers  = "MIME-Version: 1.0\n";
  $headers .= "Content-type: text/html; charset=iso-8859-1\n";
  $headers .= "From: $nome <$email>";

  
  if(mail($destino, $assunto, $arquivo, $headers)){
    echo("Email enviado com sucesso!");
  }else{
    echo("O Email não pode ser enviado");
  }
?>
