---
title: Procedimiento Enlazar datos a elementos de Windows Presentation Foundation (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
ms.openlocfilehash: 559857ab647d6a1e6d2ae7ffcc344e7583b48553
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066183"
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>Procedimiento Enlazar datos a elementos de Windows Presentation Foundation (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede enlazar elementos Windows Presentation Foundation (WPF) como un <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ComboBox> a una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601>, que controla los eventos generados por los controles para mantener la <xref:System.Data.Services.Client.DataServiceContext> sincronizada con los cambios realizados en los datos en los controles. Para obtener más información, consulte [enlazar datos a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean cuando se completa la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente es de la página de código subyacente de una página de lenguaje XAML que define la ventana `SalesOrders` en WPF. Cuando se carga la ventana, se crea una <xref:System.Data.Services.Client.DataServiceCollection%601> dependiendo del resultado de una consulta que devuelve los clientes filtrados por país. Se cargan todas las páginas de este resultado paginado, junto con los pedidos relacionados, y se enlazan a la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de <xref:System.Windows.Controls.StackPanel> que es el control de diseño raíz para la ventana de WPF. Para obtener más información, consulte [cargar contenido diferido](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente XAML define la ventana `SalesOrders` en WPF del ejemplo anterior.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente es de la página de código subyacente de una página de lenguaje XAML que define la ventana `SalesOrders` en WPF. Cuando se carga la ventana, se crea una <xref:System.Data.Services.Client.DataServiceCollection%601> dependiendo del resultado de una consulta que devuelve los clientes con objetos relacionados, filtrados por país. Este resultado se enlaza a la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de <xref:System.Windows.Controls.StackPanel> que es el control de diseño raíz para la ventana de WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>Ejemplo  
 El siguiente XAML define la ventana `SalesOrders` en WPF del ejemplo anterior.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
