<h1 align="center">Les injections SQL</h1>


<h4>Tout d'abord, nous allons définir qu'est-ce qu'une injection SQL ? </h4>

<div align="center">
  <img height="200px" src="https://user-images.githubusercontent.com/96829109/197344367-fb89fd6d-6a77-4a7b-9413-045a39b87d97.jpg">
</div>


<a>Une injection SQL est une vulnérabilité sur un site web permettant à un attaquant de se connecter et de voler des données.</a>
<a>Grâce à l'utilisation de Payload, il est possible de bypass la requête SQL.</a>
<a>Prenons par exemple, une requête SQL pour ce connecter à un panel Admin : </a>

<h4>SELECT * FROM users WHERE identifiants='admin' AND password=''</h4>

<a>Pour accéder au panel, il faut connaitre le mot de passe du compte. Pour cela nous allons Bypass le mot de passe. </a>
<a>Nous allons utiliser une condition qui sera toujours valable par exemple 1 = 1.</a>
<a>Néanmoins, Il faut  avoir des bases en SQLi pour comprendre le fonctionnement des requêtes.</a>

<a>Nous avons un panel mise à disposition :</a>

<div align="center">
  <img height="400px" src="https://user-images.githubusercontent.com/96829109/197343235-428b6e19-5240-4670-b110-5f12c3967da7.PNG">
</div>

<a>Nous allons injecter notre Payload (1=1) entre l'identifiant et le password.</a>
<a>Pour injecter le payload, nous allons utiliser la condition OR afin de mettre notre condition.</a>
<a>A noté que l'injection ne fonctionnera que si nous connaissons l'identifiant du compte qui à accès au panel.</a>
<a>Dans notre cas, il s'agit de chicosdu2.</a>

<a>Nous allons modifier la requête en : </a>

<h4>SELECT * FROM users WHERE identifiants='chicosdu2' OR '1' = '1' AND password='1234'</h4>

<a>Le OR va être exécuté avant le AND ce qui permet de Bypass le mot de passe.</a>
<a>La variable 1=1 est toujours valide ce qui nous permets de rentrer sur le panel sans le mot de passe.</a>

<div align="center">
  <img height="400px" src="https://user-images.githubusercontent.com/96829109/197344084-d8dbf24e-e613-4e0f-ac5e-6c511c982530.PNG">
</div>

<a>Et nous voila connecté au panel !</a>

<a>je vous laisse essayer le payload : https://chicosdu2.fr/PiscineRennes/admin/</a>


<table>
    <tr>
      <th>Type D'injection</th>
    </tr>
    <tr>
      <td>In-Band SQLi</td>
    </tr>
    <tr>
      <td>Error-based SQLi</td>
    </tr>
    <tr>
        <td>Union-based SQLi</td>
      </tr>
      <tr>
        <td>Boolean-based SQLi</td>
      </tr>
      <tr>
        <td>time-based SQLi</td>
      </tr>
      <tr>
        <td>Inferential SQLi</td>
      </tr>
      <tr>
        <td>Out-of-band SQLi</td>
      </tr>
  </table>
