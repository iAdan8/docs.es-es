---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: ad4f2cc3b03111854d10d6a1c1128f090a629a07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490987"
---
# <a name="mtommessageencodingbindingelement"></a>MtomMessageEncodingBindingElement
MtomMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase MtomMessageEncodingBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase MtomMessageEncodingBindingElement tiene las propiedades siguientes:  
  
### <a name="encoding"></a>Codificación  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.  
  
### <a name="readerquotas"></a>ReaderQuotas  
 Tipo de datos: XmlDictionaryReaderQuotas  
  
 Tipo de acceso: De sólo lectura  
  
 Las cuotas de los lectores.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
