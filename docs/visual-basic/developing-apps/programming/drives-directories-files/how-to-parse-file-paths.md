---
title: Procedimiento para analizar rutas de acceso a archivos en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
ms.openlocfilehash: 2b31dedbdd33ddfb3c15863a45b93148fd722faa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707757"
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a>Procedimiento para analizar rutas de acceso a archivos en Visual Basic
El objeto <xref:Microsoft.VisualBasic.FileIO.FileSystem> ofrece una serie de métodos útiles al analizar rutas de acceso a archivos.  
  
-   El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> toma dos rutas de acceso y devuelve una ruta de acceso combinada con el formato correcto.  
  
-   El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> devuelve la ruta de acceso absoluta del elemento primario de la ruta de acceso proporcionada.  
  
-   El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> devuelve un objeto <xref:System.IO.FileInfo> que se puede consultar para determinar las propiedades del archivo, como el nombre y la ruta de acceso.  
  
 No tome ninguna decisión sobre el contenido del archivo basándose en la extensión del nombre de archivo. Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.  
  
### <a name="to-determine-a-files-name-and-path"></a>Para determinar el nombre y la ruta de acceso de un archivo  
  
-   Use las propiedades <xref:System.IO.FileInfo.DirectoryName%2A> y <xref:System.IO.FileInfo.Name%2A> del objeto <xref:System.IO.FileInfo> para determinar el nombre y la ruta de acceso de un archivo. Este ejemplo determina el nombre y la ruta de acceso, y los muestra.  
  
     [!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a>Para combinar el nombre y el directorio de un archivo para crear la ruta de acceso completa  
  
-   Use el método `CombinePath` , y proporcione el directorio y el nombre. En este ejemplo se toman las cadenas `folderPath` y `fileName` creadas en el ejemplo anterior, se combinan y se muestra el resultado.  
  
     [!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>
- <xref:System.IO.FileInfo>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>
- [Cómo: Obtener la colección de archivos de un directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
