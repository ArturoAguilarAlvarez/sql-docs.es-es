---
title: Buscar la versión del esquema de definición de informe (SSRS) | Microsoft Docs
ms.date: 05/30/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: reports
ms.topic: conceptual
helpviewer_keywords:
- XML schemas [Reporting Services]
- Report Definition Language, XML schema
- schemas [Reporting Services]
ms.assetid: 67954419-1b61-4481-a3b9-23b4ba7a5624
author: markingmyname
ms.author: maghan
ms.openlocfilehash: eff18cf56e606aa8cea96bd8828a7daaca27c0f4
ms.sourcegitcommit: 9ece10c2970a4f0812647149d3de2c6b75713e14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2018
ms.locfileid: "51813958"
---
# <a name="find-the-report-definition-schema-version-ssrs"></a>Buscar la versión del esquema de definición de informe (SSRS)

Un archivo de definición de informe especifica el espacio de nombres RDL para la versión del esquema de definición de informe que se utiliza para validar el archivo rdl. Cuando se abre un archivo .rdl en un entorno de creación de informes, como por ejemplo, el Diseñador de informes en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o el Generador de informes, si el informe se ha creado para un espacio de nombres anterior, se crea automáticamente un archivo de copia de seguridad y se actualiza el informe al espacio de nombres actual. Si se guarda la definición de informe actualizada, se ha guardado el archivo .rdl convertido. Esta es la única manera para actualizar una definición de informe. La definición de informe en sí misma no se actualiza en un servidor de informes. El informe de compilación se actualiza en un servidor de informes. Para más información, consulte [Upgrade Reports](../../reporting-services/install-windows/upgrade-reports.md).  
  
### <a name="how-to-identify-the-rdl-schema-version-of-a-report"></a>Identificar la versión de esquema RDL de un informe  
  
1.  Abra el archivo .rdl de informe en una aplicación como Bloc de notas o XML Notepad 2007 en la que pueda ver el xml.  
  
     El elemento de informe XML especifica el espacio de nombres del esquema. Por ejemplo, el elemento de informe siguiente especifica el espacio de nombres para el Diseñador de informes y el espacio de nombres para la definición de informe.  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     La dirección URL siguiente especifica el espacio de nombres para la definición de informe: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.  
  
### <a name="how-to-identify-the-rdl-schema-version-of-report-designer"></a>Identificar la versión de esquema RDL del Diseñador de informes  
  
1.  Abra un proyecto nuevo. La versión del proyecto que elija determina la versión del esquema RDL. En SQL Server, se admite más de una versión de esquema. Para más información, vea [Implementación y compatibilidad de versiones en SQL Server Data Tools](../../reporting-services/tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).  
  
2.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Se abre el cuadro de diálogo **Agregar nuevo elemento** .  
  
3.  En el panel **Plantillas** , haga clic en **Informe**.  
  
4.  En **Nombre**, escriba un nombre para el informe o acepte el valor predeterminado.  
  
5.  Haga clic en **Agregar**. El Diseñador de informes abre un nuevo informe en blanco en la vista Diseño.  
  
6.  En el menú **Ver** , haga clic en **Código**. La definición de informe se muestra como un archivo XML.  
  
     El elemento de informe XML especifica el espacio de nombres del esquema. Por ejemplo, el elemento de informe siguiente especifica el espacio de nombres para el Diseñador de informes y el espacio de nombres para la definición de informe.  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner  
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     La dirección URL siguiente especifica el espacio de nombres para la definición de informe: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`  
  
### <a name="how-to-identify-the-rdl-schema-version-on-the-report-server"></a>Identificar la versión de esquema RDL en el servidor de informes  
  
-   En el Administrador de informes, escriba la siguiente dirección URL para el servidor de informes. Por ejemplo, la dirección URL siguiente especifica un servidor de informes en el equipo local:  
  
     `https://localhost/reportserver/reportdefinition.xsd`  
  
     Se abre el archivo .xsd en el explorador.  
  
     El elemento de esquema XML especifica el espacio de nombres del esquema. Por ejemplo, el elemento de esquema siguiente especifica tres espacios de nombres: la referencia de targetNamespace usada internamente por [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], la referencia de xsd para el propio esquema (xsd) y la referencia de la definición de informe.  
  
    ```  
    <xsd:schema   
    targetNamespace="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    xmlns:xsd="https://www.w3.org/2001/XMLSchema"   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    elementFormDefault="qualified">  
    ```  
  
     La dirección URL siguiente especifica el espacio de nombres para la definición de informe: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`  

## <a name="next-steps"></a>Pasos siguientes

[Actualizar informes](../../reporting-services/install-windows/upgrade-reports.md)   
[Lenguaje RDL (Report Definition Language)](../../reporting-services/reports/report-definition-language-ssrs.md)  

¿Tiene alguna pregunta más? [Puede plantear sus dudas en el foro de Reporting Services](https://go.microsoft.com/fwlink/?LinkId=620231).
