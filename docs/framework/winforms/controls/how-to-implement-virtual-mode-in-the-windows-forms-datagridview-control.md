---
title: Реализация виртуального режима в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: f8612a808ac5c9facee55d820529945f481a2cea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736511"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms
В примере кода ниже показано, как управлять большими наборами данных с помощью элемента управления <xref:System.Windows.Forms.DataGridView>, свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> которого присвоено значение `true`.  
  
 Полное описание этого примера кода см. в разделе [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Оптимизация производительности элемента управления DataGridView в Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Виртуальный режим элемента управления DataGridView в Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
