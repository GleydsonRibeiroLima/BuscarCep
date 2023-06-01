<!DOCTYPE html> 

<html> 

<head> 

    <title>Consulta de CEP</title> 

    <script src=https://code.jquery.com/jquery-3.6.0.min.js></script> 

</head> 

<body> 

    <h1>Consulta de CEP</h1> 

 

    <label for=”cep”>CEP:</label> 

    <input type=”text” id=”cep” placeholder=”Digite o CEP”> 

 

    <button onclick=”consultarCEP()”>Consultar</button> 

 

    <div id=”resultado”></div> 

 

    <script> 

        function consultarCEP() { 

            Var cep = document.getElementById(‘cep’).value; 

            Var url = ‘https://viacep.com.br/ws/’ + cep + ‘/json/’; 

 

            $.getJSON(url, function(data) { 

                If (!data.erro) { 

                    Var resultado = ‘’; 

                    resultado += ‘<p><strong>CEP:</strong> ‘ + data.cep + ‘</p>’; 

                    resultado += ‘<p><strong>Logradouro:</strong> ‘ + data.logradouro + ‘</p>’; 

                    resultado += ‘<p><strong>Complemento:</strong> ‘ + data.complemento + ‘</p>’; 

                    resultado += ‘<p><strong>IBGE:</strong> ‘ + data.ibge + ‘</p>’; 

                    resultado += ‘<p><strong>Bairro:</strong> ‘ + data.bairro + ‘</p>’; 

                    resultado += ‘<p><strong>Cidade/UF:</strong> ‘ + data.localidade + ‘/’ + data.uf + ‘</p>’; 

 

                    Document.getElementById(‘resultado’).innerHTML = resultado; 

                } else { 

                    Document.getElementById(‘resultado’).innerHTML = ‘<p>CEP não encontrado.</p>’; 

                } 

            }); 

        } 

    </script> 

</body> 

</html> 
