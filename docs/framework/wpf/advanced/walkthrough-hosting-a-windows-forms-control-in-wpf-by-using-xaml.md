---
title: 'Tutorial: Hospedar un Control de Windows Forms en WPF mediante XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 7e5984edfc081427214220eadf190282846b1c44
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640736"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Tutorial: Hospedar un Control de Windows Forms en WPF mediante XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona numerosos controles con un conjunto de características enriquecidas. Sin embargo, es posible que a veces desea utilizar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a los controles de su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] páginas. Por ejemplo, puede tener una inversión sustancial en existente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles, o bien puede tener un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control que ofrece una funcionalidad única.  
  
 En este tutorial se muestra cómo hospedar un formulario Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Para obtener una lista de código completo de las tareas mostradas en este tutorial, vea [hospedar un Control de Windows Forms en WPF by Using XAML Sample](https://go.microsoft.com/fwlink/?LinkID=160000).  
  
## <a name="prerequisites"></a>Requisitos previos  

Necesita Visual Studio para completar este tutorial.  
  
## <a name="hosting-the-windows-forms-control"></a>Hospedar el control de Windows Forms  
  
#### <a name="to-host-the-maskedtextbox-control"></a>Para hospedar el control MaskedTextBox  
  
1.  Cree un proyecto de aplicación WPF denominado `HostingWfInWpfWithXaml`.  
  
2.  Agregue referencias a los ensamblados siguientes.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Abra MainWindow.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  En el <xref:System.Windows.Window> elemento, agregue la siguiente asignación de espacio de nombres. El `wf` asignación del espacio de nombres establece una referencia al ensamblado que contiene el control Windows Forms.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  En el <xref:System.Windows.Controls.Grid> elemento Agregar el XAML siguiente.  
  
     El <xref:System.Windows.Forms.MaskedTextBox> control se crea como un elemento secundario de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  Presione F5 para compilar y ejecutar la aplicación.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un Control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Tutorial: Hospedar un Control compuesto de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un Control compuesto de WPF en Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Controles de Windows Forms y controles equivalentes de WPF](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)
- [Hospedar un Control de Windows Forms en WPF mediante XAML de ejemplo](https://go.microsoft.com/fwlink/?LinkID=160000)
