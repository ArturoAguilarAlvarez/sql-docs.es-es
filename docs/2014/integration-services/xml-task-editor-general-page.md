---
title: Editor de la tarea XML (página General) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmltask.general.f1
helpviewer_keywords:
- XML Task Editor
ms.assetid: b9622c48-3243-4408-a1de-9ba20e32ff70
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 6e37e5a540d452b745bc4a533d3a523b5484eca1
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48134335"
---
# <a name="xml-task-editor-general-page"></a>Editor de la tarea XML (página General)
  Use el **Nodo general** del cuadro de diálogo **Editor de la tarea XML** para especificar el tipo de operación y configurar la operación.  
  
 Para obtener información acerca de esta tarea, vea [XML Task](control-flow/xml-task.md). Para obtener información acerca de cómo trabajar con datos y documentos XML, vea el artículo sobre el[uso de XML en .NET Framework](http://go.microsoft.com/fwlink/?LinkId=56214)en MSDN Library.  
  
## <a name="static-options"></a>Opciones estáticas  
 **OperationType**  
 Seleccione un tipo de operación de la lista. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Validar**|Valida el documento XML según una definición de tipo de documento (DTD) o un esquema de definición de esquema XML (XSD). Seleccione esta opción para mostrar las opciones dinámicas de la sección **Validar**.|  
|**XSLT**|Realiza transformaciones XSL en documentos XML. Seleccione esta opción para mostrar las opciones dinámicas de la sección **XSLT**.|  
|**XPATH**|Realiza consultas y evaluaciones XPath. Seleccione esta opción para mostrar las opciones dinámicas de la sección **XPATH**.|  
|**Mezcla**|Combina dos documentos XML. Seleccione esta opción para mostrar las opciones dinámicas de la sección **Mezclar**.|  
|**Diferencias**|Compara dos documentos XML. Seleccione esta opción para mostrar las opciones dinámicas de la sección **Comparación**.|  
|**Revisión**|Aplica la salida de la operación de comparación para crear un nuevo documento. Seleccione esta opción para mostrar las opciones dinámicas de la sección **Revisión**.|  
  
 **Tipo de origen**  
 Seleccione el tipo de origen del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Entrada directa**|Establezca el origen para un documento XML.|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **Source**  
 Si **Source** está establecido en **Entrada directa**, escriba el código XML o haga clic en el botón de puntos suspensivos **(…)** y luego proporcione el XML en el cuadro de diálogo **Editor de origen del documento**.  
  
 Si **Source** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **Source** está establecido en **Variable**, seleccione una variable existente o haga clic en **\<Nueva variable...>** para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
## <a name="operationtype-dynamic-options"></a>Opciones dinámicas de OperationType  
  
### <a name="operationtype--validate"></a>OperationType = Validar  
 Especifique las opciones de la operación Validar.  
  
 **SaveOperationResult**  
 Especifique si desea que la tarea XML guarde el resultado de la operación Validar.  
  
 **OverwriteDestination**  
 Especifique si desea sobrescribir el archivo o variable de destino.  
  
 **Destino**  
 Seleccione un administrador de conexiones de archivos existente o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 **DestinationType**  
 Seleccione el tipo de destino del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **ValidationType**  
 Seleccione el tipo de validación. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**DTD**|Use una definición de tipo de documento (DTD).|  
|**XSD**|Use un esquema de definición de esquema XML (XSD). Seleccione esta opción para mostrar las opciones dinámicas de la sección **ValidationType**.|  
  
 **FailOnValidationFail**  
 Especifique si desea que se produzca un error en la operación si se produce un error al validar el documento.  
  
 **ValidationDetails**  
 Proporciona una salida de error enriquecida cuando el valor de esta propiedad es true. Para obtener más información, vea [Validate XML with the XML Task](control-flow/validate-xml-with-the-xml-task.md).  
  
### <a name="validationtype-dynamic-options"></a>Opciones dinámicas de ValidationType  
  
#### <a name="validationtype--xsd"></a>ValidationType = XSD  
 **SecondOperandType**  
 Seleccione el tipo de origen del segundo documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Entrada directa**|Establezca el origen para un documento XML.|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperand**  
 Si **SecondOperandType** está establecido en **Entrada directa**, escriba el código XML o haga clic en el botón de puntos suspensivos **(…)** y proporcione el XML en el cuadro de diálogo **Editor de origen**.  
  
 Si **SecondOperandType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **XPathStringSourceType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
### <a name="operationtype--xslt"></a>OperationType = XSLT  
 Especifique las opciones de la operación XSLT.  
  
 **SaveOperationResult**  
 Especifique si desea que la tarea XML guarde el resultado de la operación XSLT.  
  
 **OverwriteDestination**  
 Especifique si desea sobrescribir el archivo o variable de destino.  
  
 **Destino**  
 Si **DestinationType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **DestinationType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Seleccione el tipo de destino del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperandType**  
 Seleccione el tipo de origen del segundo documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Entrada directa**|Establezca el origen para un documento XML.|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperand**  
 Si **SecondOperandType** está establecido en **Entrada directa**, escriba el código XML o haga clic en el botón de puntos suspensivos **(…)** y proporcione el XML en el cuadro de diálogo **Editor de origen**.  
  
 Si **SecondOperandType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **XPathStringSourceType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
### <a name="operationtype--xpath"></a>OperationType = XPATH  
 Especifique las opciones de la operación XPath.  
  
 **SaveOperationResult**  
 Especifique si desea que la tarea XML guarde el resultado de la operación XPath.  
  
 **OverwriteDestination**  
 Especifique si desea sobrescribir el archivo o variable de destino.  
  
 **Destino**  
 Si **DestinationType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **DestinationType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Seleccione el tipo de destino del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperandType**  
 Seleccione el tipo de origen del segundo documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Entrada directa**|Establezca el origen para un documento XML.|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperand**  
 Si **SecondOperandType** está establecido en **Entrada directa**, escriba el código XML o haga clic en el botón de puntos suspensivos **(…)** y proporcione el XML en el cuadro de diálogo **Editor de origen**.  
  
 Si **SecondOperandType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **XPathStringSourceType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
 **PutResultInOneNode**  
 Especifique si desea escribir el resultado en un único nodo.  
  
 **XPathOperation**  
 Seleccione el tipo de resultado XPath. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Evaluation**|Devuelve los resultados de una función XPath.|  
|**Lista de nodos**|Devuelve los nodos seleccionados como un fragmento de XML.|  
|**Valores**|Devuelve el valor de texto interno de todos los nodos seleccionados concatenado en una cadena.|  
  
### <a name="operationtype--merge"></a>OperationType = Mezclar  
 Especifique las opciones de la operación Mezclar.  
  
 **XPathStringSourceType**  
 Seleccione el tipo de origen del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Entrada directa**|Establezca el origen para un documento XML.|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **XPathStringSource**  
 Si **XPathStringSourceType** está establecido en **Entrada directa**, escriba el código XML o haga clic en el botón de puntos suspensivos **(…)** y proporcione el XML en el cuadro de diálogo **Editor de origen del documento**.  
  
 Si **XPathStringSourceType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **XPathStringSourceType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)  
  
 Al utilizar una instrucción XPath para identificar la ubicación de la combinación en el documento de origen, se espera que esta instrucción devuelva un único nodo. Si la instrucción devuelve varios nodos, solo se utiliza el primero. El contenido del segundo documento se combina bajo el primer nodo que devuelve la consulta de XPath.  
  
 **SaveOperationResult**  
 Especifique si desea que la tarea XML guarde el resultado de la operación Mezclar.  
  
 **OverwriteDestination**  
 Especifique si desea sobrescribir el archivo o variable de destino.  
  
 **Destino**  
 Si **DestinationType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **DestinationType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Seleccione el tipo de destino del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperandType**  
 Seleccione el tipo de destino del segundo documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Entrada directa**|Establezca el origen para un documento XML.|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperand**  
 Si **SecondOperandType** está establecido en **Entrada directa**, escriba el código XML o haga clic en el botón de puntos suspensivos **(…)** y proporcione el XML en el cuadro de diálogo **Editor de origen del documento** .  
  
 Si **SecondOperandType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **SecondOperandType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)  
  
### <a name="operationtype--diff"></a>OperationType = Comparación  
 Especifique las opciones de la operación de comparación.  
  
 **DiffAlgorithm**  
 Seleccione el algoritmo de comparación que desea utilizar para comparar los documentos. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Automático**|Permita que la tarea XML determine si es necesario utilizar el algoritmo rápido o preciso.|  
|**Rápido**|Utilice un algoritmo de comparación rápido, aunque menos preciso.|  
|**Preciso**|Utilice un algoritmo de comparación preciso.|  
  
 **Opciones de comparación**  
 Establezca las opciones de comparación de la operación de comparación. Las opciones se muestran en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**IgnoreXMLDeclaration**|Especifique si desea comparar la declaración XML.|  
|**IgnoreDTD**|Especifique si desea ignorar la definición de tipo de documento (DTD).|  
|**IgnoreWhiteSpaces**|Especifique si se omitirán las diferencias en la cantidad de espacios en blanco al comparar documentos.|  
|**IgnoreNameSpaces**|Especifique si desea comparar el identificador uniforme de recursos (URI) de espacio de nombres de un elemento y los nombres de atributo.<br /><br /> Nota: Si esta opción se establece en `True`, dos elementos que tienen el mismo equipo local nombre pero distintos espacios de nombres se consideran idénticos.|  
|**IgnoreProcessingInstructions**|Especifique si desea comparar las instrucciones de procesamiento.|  
|**IgnoreOrderOf ChildElements**|Especifique si desea comparar el orden de los elementos secundarios.<br /><br /> Nota: Si esta opción se establece en `True`, los elementos secundarios que solo difieren en su posición en una lista de elementos del mismo nivel se consideran idénticos.|  
|**IgnoreComments**|Especifique si desea comparar los nodos de comentario.|  
|**IgnorePrefixes**|Especifique si desea comparar los prefijos de los nombres de elemento y atributo.<br /><br /> Nota: Si establece esta opción en `True`, dos elementos que tienen el mismo nombre local, pero otro URI de espacio de nombres y prefijos, se consideran idénticos.|  
  
 **FailOnDifference**  
 Especifique si desea que se produzca un error en la tarea si se produce un error en la operación de comparación.  
  
 **SaveDiffGram**  
 Especifique si desea guardar el resultado de comparación en un documento DiffGram.  
  
 **SaveOperationResult**  
 Especifique si desea que la tarea XML guarde el resultado de la operación de comparación.  
  
 **OverwriteDestination**  
 Especifique si desea sobrescribir el archivo o variable de destino.  
  
 **Destino**  
 Si **DestinationType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **DestinationType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Seleccione el tipo de destino del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperandType**  
 Seleccione el tipo de destino del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Entrada directa**|Establezca el origen para un documento XML.|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperand**  
 Si **SecondOperandType** está establecido en **Entrada directa**, escriba el código XML o haga clic en el botón de puntos suspensivos **(…)** y proporcione el XML en el cuadro de diálogo **Editor de origen del documento** .  
  
 Si **SecondOperandType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **SecondOperandType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)  
  
### <a name="operationtype--patch"></a>OperationType = Revisión  
 Especifique las opciones de la operación Revisión.  
  
 **SaveOperationResult**  
 Especifique si desea que la tarea XML guarde el resultado de la operación Revisión.  
  
 **OverwriteDestination**  
 Especifique si desea sobrescribir el archivo o variable de destino.  
  
 **Destino**  
 Si **DestinationType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **DestinationType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md).  
  
 **DestinationType**  
 Seleccione el tipo de destino del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperandType**  
 Seleccione el tipo de destino del documento XML. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**Entrada directa**|Establezca el origen para un documento XML.|  
|**Conexión de archivos**|Seleccione el archivo que contiene el documento XML.|  
|**Variable**|Establezca el origen para la variable que contiene el documento XML.|  
  
 **SecondOperand**  
 Si **SecondOperandType** está establecido en **Entrada directa**, escriba el código XML o haga clic en el botón de puntos suspensivos **(…)** y proporcione el XML en el cuadro de diálogo **Editor de origen del documento** .  
  
 Si **SecondOperandType** se ha establecido en **Conexión de archivos**, seleccione un administrador de conexiones de archivos o haga clic en \<**Nueva conexión...**> para crear un nuevo administrador de conexiones.  
  
 **Temas relacionados:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
 Si **SecondOperandType** está establecido en **Variable**, seleccione una variable existente o haga clic en \<**Nueva variable...**> para crear una nueva.  
  
 **Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)  
  
## <a name="see-also"></a>Vea también  
 [Referencia de mensajes y Error de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Página Expresiones](expressions/expressions-page.md)  
  
  
