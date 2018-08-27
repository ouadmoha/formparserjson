 **formparserjson**
--------------

Install:



    sudo cpan JSON && git clone https://github.com/ouadmoha/formparserjson && cd formparserjson


Usage:

    perl formparserjson < document.html

Example:

**test.html** 

    <!DOCTYPE html>
    <html lang="en">
      <head></head>
      <body>
      	<h1>hello my friend!</h1>
      	<a>unless tag</a>
      	<form enctype="multipart/form-data" action="/process.php" method="POST">
      		<input type="text" name="name" id="name_field" />
      		<input type="text" name="email" id="email_field" maxlength="88" value="username@example.com" />
      		<input type="submit" name="send_data" value="Send" />
      	</form>
      </body>
    </html>

**command:**

    perl formparserjson < test.html


**result:**

    {
       "form1" : {
          "_metodo" : "POST",
          "filed2" : {
             "valore" : "username@example.com",
             "maxlength" : "88",
             "tipo_campo" : "TEXT",
             "name_field" : "email"
          },
          "filed3" : {
             "tipo_campo" : "SUBMIT",
             "name_field" : "send_data",
             "valore" : "Send"
          },
          "_codifica" : "multipart/form-data",
          "filed1" : {
             "valore" : "",
             "name_field" : "name",
             "tipo_campo" : "TEXT"
          },
          "_action" : "/process.php"
       }
    }
