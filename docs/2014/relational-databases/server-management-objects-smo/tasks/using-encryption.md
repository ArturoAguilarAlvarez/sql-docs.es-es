---
title: Uso del cifrado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- database master key [SMO]
- cryptography [SMO]
- cryptography [SQL Server], SMO
- encryption keys [SMO]
- encryption [SQL Server], SMO
- encryption [SMO]
- certificates [SMO]
- service master key [SMO]
ms.assetid: 405e0ed7-50a9-430e-a343-471f54b4af76
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 95a0323cc5362ec2fd780c5ee28926b3b78aa755
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48198525"
---
# <a name="using-encryption"></a>Utilizar el cifrado
  En SMO, la clave maestra de servicio se representa mediante el <xref:Microsoft.SqlServer.Management.Smo.ServiceMasterKey> objeto. Esto se hace referencia mediante el <xref:Microsoft.SqlServer.Management.Smo.Server.ServiceMasterKey%2A> propiedad de la <xref:Microsoft.SqlServer.Management.Smo.Server> objeto. Se puede regenerar utilizando el <xref:Microsoft.SqlServer.Management.Smo.ServiceMasterKey.Regenerate%2A> método.  
  
 La clave maestra de base de datos está representada por la <xref:Microsoft.SqlServer.Management.Smo.MasterKey> objeto. El <xref:Microsoft.SqlServer.Management.Smo.MasterKey.IsEncryptedByServer%2A> propiedad indica si se cifra la clave maestra de base de datos utilizando la clave maestra de servicio. La copia cifrada en la base de datos maestra se actualiza automáticamente siempre que se cambia la clave maestra de base de datos.  
  
 Es posible quitar el cifrado de clave de servicio utilizando el <xref:Microsoft.SqlServer.Management.Smo.MasterKey.DropServiceKeyEncryption%2A> método y cifrar la clave maestra de base de datos con una contraseña. En esa situación, tendrá que abrir explícitamente la clave maestra de base de datos antes de tener acceso a las claves privadas que ha protegido.  
  
 Cuando se adjunta una base de datos a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], debe proporcionar la contraseña para la clave maestra de base de datos o ejecutar el <xref:Microsoft.SqlServer.Management.Smo.MasterKey.AddServiceKeyEncryption%2A> método para hacer una copia no cifrada de la clave maestra de base de datos disponibles para el cifrado con el servicio clave maestra. Se recomienda este paso para evitar la necesidad de abrir explícitamente la clave maestra de base de datos.  
  
 El <xref:Microsoft.SqlServer.Management.Smo.MasterKey.Regenerate%2A> método vuelve a generar la clave maestra de base de datos. Si se vuelve a generar la clave maestra de base de datos, todas las claves cifradas con ella se descifran y, a continuación, vuelve a cifrarlas con la nueva clave maestra de base de datos. El <xref:Microsoft.SqlServer.Management.Smo.MasterKey.DropServiceKeyEncryption%2A> método quita el cifrado de la clave maestra de base de datos mediante la clave maestra de servicio. <xref:Microsoft.SqlServer.Management.Smo.MasterKey.AddServiceKeyEncryption%2A> hace que se cifre una copia de la clave maestra utilizando la clave maestra de servicio y la almacena en la base de datos actual y en la base de datos maestra.  
  
 En SMO, los certificados se representan mediante el <xref:Microsoft.SqlServer.Management.Smo.Certificate> objeto. La <xref:Microsoft.SqlServer.Management.Smo.Certificate> objeto tiene propiedades que especifican la clave pública, el nombre del asunto, el período de validez e información sobre el emisor. Permiso para tener acceso al certificado se controla mediante el uso de la `Grant`, `Revoke` y `Deny` métodos.  
  
## <a name="example"></a>Ejemplo  
 Para el siguiente ejemplo de código, deberá seleccionar el entorno de programación, la plantilla de programación y el lenguaje de programación en los que crear su aplicación. Para obtener más información, consulte [crear un proyecto de Visual Basic SMO en Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) y [crear un Visual C&#35; proyecto SMO en Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="adding-a-certificate-in-visual-basic"></a>Agregar un certificado en Visual Basic  
 En el ejemplo de código se crea un certificado simple con una contraseña de cifrado. A diferencia de otros objetos, el <xref:Microsoft.SqlServer.Management.Smo.Certificate.Create%2A> método tiene varias sobrecargas. La sobrecarga utilizada en el ejemplo crea un nuevo certificado con una contraseña de cifrado.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCertificate1](SMO How to#SMO_VBCertificate1)]  -->  
  
## <a name="adding-a-certificate-in-visual-c"></a>Agregar un certificado en Visual C#  
 En el ejemplo de código se crea un certificado simple con una contraseña de cifrado. A diferencia de otros objetos, el <xref:Microsoft.SqlServer.Management.Smo.Certificate.Create%2A> método tiene varias sobrecargas. La sobrecarga utilizada en el ejemplo crea un nuevo certificado con una contraseña de cifrado.  
  
```  
{  
            //Connect to the local, default instance of SQL Server.   
            {  
                Server srv = new Server();  
  
                //Reference the AdventureWorks2012 database.   
                Database db = srv.Databases["AdventureWorks2012"];  
  
                //Define a Certificate object variable by supplying the parent database and name in the constructor.   
                Certificate c = new Certificate(db, "Test_Certificate");  
  
                //Set the start date, expiry date, and description.   
                System.DateTime dt;  
                DateTime.TryParse("January 01, 2010", out dt);  
                c.StartDate = dt;  
                DateTime.TryParse("January 01, 2015", out dt);  
                c.ExpirationDate = dt;  
                c.Subject = "This is a test certificate.";  
                //Create the certificate on the instance of SQL Server by supplying the certificate password argument.   
                c.Create("pGFD4bb925DGvbd2439587y");  
            }  
        }   
```  
  
## <a name="adding-a-certificate-in-powershell"></a>Agregar un certificado en PowerShell  
 En el ejemplo de código se crea un certificado simple con una contraseña de cifrado. A diferencia de otros objetos, el <xref:Microsoft.SqlServer.Management.Smo.Certificate.Create%2A> método tiene varias sobrecargas. La sobrecarga utilizada en el ejemplo crea un nuevo certificado con una contraseña de cifrado.  
  
```  
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = get-item AdventureWorks2012  
  
#Create a certificate  
  
$c = New-Object -TypeName Microsoft.SqlServer.Management.Smo.Certificate -argumentlist $db, "Test_Certificate"  
$c.StartDate = "January 01, 2010"  
$c.Subject = "This is a test certificate."  
$c.ExpirationDate = "January 01, 2015"  
  
#Create the certificate on the instance of SQL Server by supplying the certificate password argument.  
$c.Create("pGFD4bb925DGvbd2439587y")  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Uso de claves de cifrado](using-encryption.md)  
  
  
