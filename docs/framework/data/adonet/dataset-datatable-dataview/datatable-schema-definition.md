---
title: Определение схемы таблицы данных
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: d18af8001fd24f3b21c3e7fd13f9dabb2587b322
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786388"
---
# <a name="datatable-schema-definition"></a>Определение схемы таблицы данных
Схема, или структура, таблицы представляется столбцами и ограничениями. Схема <xref:System.Data.DataTable> определяется с использованием объектов <xref:System.Data.DataColumn>, а также объектов <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>. Столбцы таблицы могут сопоставляться со столбцами источника данных, содержать вычисляемые значения выражений, автоматически увеличивать значения или содержать значения первичного ключа.  
  
 В ссылках по имени на столбцы, связи и ограничения таблицы учитывается регистр. Поэтому в таблице могут существовать столбцы, связи и ограничения, имеющие одинаковое имя, но отличающиеся регистром. Например, можно использовать **col1** и **col1**. В таком случае ссылка на один из столбцов по имени должна точно соответствовать регистру столбца; в противном случае возникает исключение. Например, если таблица **MyTable** содержит столбцы **col1** и **col1**, то вы бы ссылались на **col1** по имени как **MyTable. Columns ["col1"]** и **col1** в качестве **MyTable. Columns ["col1"]** . Попытка ссылки на любой из столбцов как **MyTable. Columns ["col1"]** приведет к созданию исключения.  
  
 Правило учета регистра не применяется, если существует только один столбец, одна связь или ограничение с конкретным именем. Это означает, что если в таблице нет другого объекта столбца, связи или ограничения, имя которого совпадает с именем этого конкретного объекта столбца, связи или ограничения, то на объект можно ссылаться по имени, используя любой регистр, и исключение в этом случае не возникает. Например, если таблица имеет только **col1**, можно ссылаться на нее с помощью **My. Столбцы ["COL1"]** .  
  
> [!NOTE]
> Свойство объекта DataTable не влияет на это поведение. <xref:System.Data.DataTable.CaseSensitive%2A> Свойство **CaseSensitive** применяется к данным в таблице и влияет на сортировку, поиск, фильтрацию, применение ограничений и т. д., но не на ссылки на столбцы, связи и ограничения.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Добавление столбцов в DataTable](adding-columns-to-a-datatable.md)  
 Описывает, как определить столбцы таблицы с помощью объектов **DataColumn** .  
  
 [Создание столбцов выражений](creating-expression-columns.md)  
 Объясняет, как свойство **Expression** столбца может использоваться для вычисления значений на основе значений из других столбцов в строке.  
  
 [Создание столбцов AutoIncrement](creating-autoincrement-columns.md)  
 Описывает, как для столбца может быть установлено автоматическое увеличение числовых значений для обеспечения уникального значения столбца в строке.  
  
 [Определение первичных ключей](defining-primary-keys.md)  
 Описывает, как указать первичный ключ таблицы из одного или нескольких объектов **DataColumn** .  
  
 [Ограничения DataTable](datatable-constraints.md)  
 Описывает, как определить внешний ключ и ограничения уникальности для столбцов в таблице.  
  
## <a name="see-also"></a>См. также

- [DataTables](datatables.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
