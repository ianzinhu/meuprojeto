<html>
<head>
    
    <title> formulario para validar email</title>

    <script language="Javascript">
        function validacaoEmail(field) {
            usuario = field.value.substring(0, field.value.indexOf("@"));
            dominio = field.value.substring(field.value.indexOf("@") + 1, field.value.length);
            if ((usuario.length >= 1) &&
                (dominio.length >= 3) &&
                (usuario.search("@") == -1) &&
                (dominio.search("@") == -1) &&
                (usuario.search(" ") == -1) &&
                (dominio.search(" ") == -1) &&
                (dominio.search(".") != -1) &&
                (dominio.indexOf(".") >= 1) &&
                (dominio.lastIndexOf(".") < dominio.length - 1)) {
                document.getElementById("msgemail").innerHTML = "<font color='green'>E-mail válido </font>";
                alert("email válido");
            }
            else {
                document.getElementById("msgemail").innerHTML = "<font color='red'>E-mail inválido, certifique-se de que seu email possui o seguinte formato; email@gmail.com </font>";
                alert("E-mail invalido");
            }
        }
    </script>
</head>

<body>
    <form name="f1">
        <h3> Validar E-mail </h3>
        <hr color='green'>
        <table>
            <tr>
                <td>
                    E-mail:
                    <input type="text" name="email" onblur="validacaoEmail(f1.email)" maxlength="30" size='29'>
                    <button style="background-color: green;" aria-label=""
                        title="clique aqui para validar seu email">enviar</button>
                </td>
                <td>
                    <div id="msgemail"></div>
                </td>
            </tr>
        </table>
        <hr color='green'>

</html>
