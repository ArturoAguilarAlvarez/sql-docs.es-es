---
title: Particiones de modelos tabulares | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: ca9ea54ace50740acf9f0be0ec923b86d1667683
ms.sourcegitcommit: 7fe14c61083684dc576d88377e32e2fc315b7107
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2018
ms.locfileid: "50146290"
---
# <a name="tabular-model-partitions"></a>Particiones de modelos tabulares 
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  Las particiones dividen una tabla en partes lógicas. A continuación, cada partición se puede procesar (actualizar) de forma independiente de las demás particiones. Las particiones definidas para un modelo durante la creación de modelos se duplican en un modelo implementado. Una vez realizada la implementación, puede administrar esas particiones y crear algunas nuevas mediante el cuadro de diálogo **Particiones** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o mediante un script. La información proporcionada en este tema describe las particiones de una base de datos de modelos tabulares implementada. Para obtener más información sobre cómo crear y administrar particiones durante la creación de modelos, vea [particiones](../../analysis-services/tabular-models/partitions-ssas-tabular.md).  
  
 Secciones de este tema:  
  
-   [Ventajas](#bkmk_benefits)  
  
-   [Permisos](#bkmk_permissions)  
  
-   [Procesar particiones](#bkmk_process_partitions)  
  
-   [Procesamiento paralelo](#bkmk_parallelProc)  
  
-   [Tareas relacionadas](#bkmk_related_tasks)  
  
##  <a name="bkmk_benefits"></a> Ventajas  
 Un diseño de modelos eficientes usa particiones para eliminar el procesamiento innecesario y la subsiguiente carga del procesador en los servidores de Analysis Services, asegurándose al mismo tiempo de que los datos se procesan y actualizan con la frecuencia suficiente para reflejar los datos más recientes de los orígenes de datos.  
  
 Por ejemplo, un modelo tabular puede tener una tabla de ventas que incluya los datos de ventas del año fiscal 2011 actual y de cada uno de los años fiscales anteriores. La tabla de ventas del modelo tiene las tres particiones siguientes:  
  
|Partición|Datos de|  
|---------------|---------------|  
|Sales2011|Año fiscal actual|  
|Sales2010-2001|Años fiscales 2001, 2002, 2003, 2004, 2005, 2006. 2007, 2008, 2009, 2010|  
|SalesOld|Todos los años fiscales anteriores a los diez últimos años.|  
  
 A medida que se agregan nuevos datos de ventas al año fiscal 2011 actual, dichos datos se deben procesar diariamente para que se reflejen correctamente en el análisis de los datos de ventas del año fiscal actual, por lo que la partición Sales2011 se procesa cada noche.  
  
 No es necesario procesar los datos de la partición Sales2010-2001 cada noche; sin embargo, dado que los datos de ventas correspondientes a los diez años fiscales anteriores pueden cambiar ocasionalmente debido a devoluciones de productos y otros ajustes, sigue siendo necesario procesarlos periódicamente, aunque en este caso se hará mensualmente. Los datos de la partición SalesOld nunca cambian, por lo que se procesarán anualmente.  
  
 Al entrar en el año fiscal 2012, se agregará una nueva partición Sales2012 a la tabla de ventas del modelo. A continuación, la partición Sales2011 se podrá mezclar con la partición Sales2010-2001, cambiando su nombre por el de Sales2011-2002. Los datos correspondientes al año fiscal 2001 se eliminarán de la nueva partición Sales2011-2002 y pasarán a la partición SalesOld. Por último, se procesarán todas las particiones para reflejar los cambios.  
  
 La forma de implementar una estrategia de partición para los modelos tabulares de la organización dependerá en gran medida de las necesidades específicas de procesamiento de datos de los modelos y de los recursos disponibles.  
  
##  <a name="bkmk_permissions"></a> Permissions  
 Para crear, administrar y procesar particiones en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], es necesario disponer de los permisos adecuados de Analysis Services definidos en un rol de seguridad. Cada rol de seguridad tiene uno de los siguientes permisos:  
  
|Permiso|Acciones|  
|----------------|-------------|  
|Administrador|Leer, procesar, crear, copiar, mezclar, eliminar|  
|Procesar|Leer, procesar|  
|Solo lectura|Lectura|  
  
 Para más información sobre cómo crear roles durante la creación del modelo mediante el uso de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], consulte [Roles](../../analysis-services/tabular-models/roles-ssas-tabular.md). Para más información sobre cómo administrar los miembros del rol para implementar roles de modelos tabulares mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], consulte [Roles de modelos tabulares](../../analysis-services/tabular-models/tabular-model-roles-ssas-tabular.md).  
  
##  <a name="bkmk_parallelProc"></a> Procesamiento paralelo  
Analysis Services incluye procesamiento en paralelo para las tablas con dos o más particiones, aumentar el rendimiento del procesamiento. No hay valores de configuración para el procesamiento en paralelo (vea las notas). El procesamiento en paralelo se produce de forma predeterminada al procesar una tabla o seleccionar varias particiones para la misma tabla y proceso. Todavía puede procesar las particiones de tablas por separado.  
  
> [!NOTE]  
>  Para especificar si las operaciones de actualización se ejecutan de manera secuencial o en paralelo, puede usar la opción de la propiedad **maxParallism** con el [Comando Sequence (TMSL)](https://docs.microsoft.com/bi-reference/tmsl/sequence-command-tmsl).

> [!NOTE]  
>  Si se detecta la recodificación, el procesamiento paralelo puede producir el aumento del uso de recursos del sistema. Esto es porque es necesario interrumpir varias operaciones de partición y reiniciarlas con la nueva codificación en paralelo.  
  
##  <a name="bkmk_process_partitions"></a> Procesar particiones  
 Las particiones se pueden procesar (actualizar) de forma independiente de las demás particiones con el cuadro de diálogo **Particiones** de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] o con un script. Existen las opciones siguientes de procesamiento:  
  
|Mode|Descripción|  
|----------|-----------------|  
|Proceso predeterminado|Detecta el estado de proceso de un objeto de partición y realiza el procesamiento necesario para devolver objetos de partición sin procesar o procesados parcialmente a un estado de procesamiento completo. Se cargan los datos de las tablas vacías y las particiones; se generan o se vuelven a generar las jerarquías, las columnas calculadas y las relaciones.|  
|Proceso completo|Procesa un objeto de partición y todos los objetos que contiene. Cuando se ejecuta Proceso completo en un objeto que ya se ha procesado, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] quita todos los datos del objeto y, a continuación, lo procesa. Este tipo de procesamiento es necesario cuando se ha realizado un cambio estructural en un objeto.|  
|Procesar datos|Carga datos en una partición o en una tabla sin volver a generar las jerarquías o las relaciones, ni volver a calcular las columnas calculadas y las medidas.|  
|Procesar borrado|Quita todos los datos de una partición.|  
|Procesar adición|Actualiza la partición con nuevos datos de forma incremental.|  
  
##  <a name="bkmk_related_tasks"></a> Tareas relacionadas  
  
|Tarea|Descripción|  
|----------|-----------------|  
|[Crear y administrar particiones de modelos tabulares](../../analysis-services/tabular-models/create-and-manage-tabular-model-partitions-ssas-tabular.md)|Describe cómo crear y administrar particiones en un modelo tabular implementado mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].|  
|[Procesar particiones de modelos tabulares](../../analysis-services/tabular-models/process-tabular-model-partitions-ssas-tabular.md)|Describe cómo procesar particiones en un modelo tabular implementado mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].|  
  
  
