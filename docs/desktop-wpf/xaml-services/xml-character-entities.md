---
title: Сущности знаков XML и XAML
ms.date: 03/30/2017
f1_keywords:
- '&'
- '&amp'
- '&gt'
- '&lt'
helpviewer_keywords:
- XAML [XAML Services], special characters
- ampersand (&) [XAML Services]
- special characters [XAML Services]
- apostrophe (') [XAML Services]
- greater-than (>) character [XAML Services]
- XAML [XAML Services], quotation mark (")
- XAML [XAML Services], apostrophe (')
- '& (ampersand) [XAML Services]'
- XAML [XAML Services], & (ampersand)
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- less-than (<) character [XAML Services]
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
ms.openlocfilehash: aff96c5d0ee6bbf2bbe2f9e3b3ae091caa781f7a
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432722"
---
# <a name="xml-character-entities-and-xaml"></a><span data-ttu-id="9108a-102">Сущности знаков XML и XAML</span><span class="sxs-lookup"><span data-stu-id="9108a-102">XML Character Entities and XAML</span></span>

<span data-ttu-id="9108a-103">XAML использует сущности символов, определенные в XML для специальных символов.</span><span class="sxs-lookup"><span data-stu-id="9108a-103">XAML uses character entities defined in XML for special characters.</span></span> <span data-ttu-id="9108a-104">В этом разделе описываются некоторые особые сущности знаков и общие вопросы, связанные с другими концепциями XML в XAML.</span><span class="sxs-lookup"><span data-stu-id="9108a-104">This topic describes some specific character entities and general considerations for other XML concepts in XAML.</span></span>

## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a><span data-ttu-id="9108a-105">Сущности символов и проблемы экранирования, уникальные для XAML</span><span class="sxs-lookup"><span data-stu-id="9108a-105">Character Entities and Escaping Issues That Are Unique to XAML</span></span>

<span data-ttu-id="9108a-106">Разметка XAML обычно использует же сущности символов и escape-последовательности, которые определены в XML.</span><span class="sxs-lookup"><span data-stu-id="9108a-106">XAML markup typically uses the same character entities and escape sequences that are defined in XML.</span></span>

<span data-ttu-id="9108a-107">Главной особенностью является то, фигурные скобки ({ и }) в XAML имеют значение, так как эти они информируют обработчика XAML о том, что последовательность символов, заключенных в фигурные скобки, должна интерпретироваться как расширение разметки.</span><span class="sxs-lookup"><span data-stu-id="9108a-107">The main exception is that braces ({ and }) have significance in XAML because these characters inform a XAML processor that a character sequence enclosed by braces must be interpreted as a markup extension.</span></span> <span data-ttu-id="9108a-108">Дополнительные сведения о расширениях разметки см. в разделе [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9108a-108">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

<span data-ttu-id="9108a-109">Однако можно по-прежнему отобразить фигурные скобки как литеральные символы, используя escape-последовательности, определенные в языке XAML, а не в XML.</span><span class="sxs-lookup"><span data-stu-id="9108a-109">However, you can still display the braces as literal characters by using an escape sequence that is particular to XAML instead of XML.</span></span> <span data-ttu-id="9108a-110">Для получения дополнительной информации [ {} см.](escape-sequence-markup-extension.md)</span><span class="sxs-lookup"><span data-stu-id="9108a-110">For more information, see [{} Escape Sequence - Markup Extension](escape-sequence-markup-extension.md).</span></span>

<span data-ttu-id="9108a-111">Обратите внимание, что\\backslash ( ) не требует последовательности побега, когда он обрабатывается как строка.</span><span class="sxs-lookup"><span data-stu-id="9108a-111">Note that a backslash (\\) does not require an escape sequence when it is handled as a string.</span></span>

## <a name="xml-character-entities"></a><span data-ttu-id="9108a-112">Сущности символов XML</span><span class="sxs-lookup"><span data-stu-id="9108a-112">XML Character Entities</span></span>

<span data-ttu-id="9108a-113">Как упоминалось ранее, большинство сущностей символов и escape-последовательностей, которые обычно используются для написания разметки XAML, определяются XML.</span><span class="sxs-lookup"><span data-stu-id="9108a-113">As mentioned previously, most character entities and escape sequences that are typically used to write XAML markup are defined by XML.</span></span> <span data-ttu-id="9108a-114">Этот раздел не содержит полного списка этих сущностей. Подробные сведения о них можно найти во внешней документации, например в спецификациях XML.</span><span class="sxs-lookup"><span data-stu-id="9108a-114">This topic does not provide the complete list of these entities; a detailed reference for the entities can be found in external documentation, such as in XML specifications.</span></span> <span data-ttu-id="9108a-115">Однако для удобства в этом разделе перечислены некоторые из определенных сущностей символов XML, которые обычно используются в разметке XAML.</span><span class="sxs-lookup"><span data-stu-id="9108a-115">However, for convenience, this topic lists some of the specific XML character entities that are typically used in XAML markup.</span></span>

|<span data-ttu-id="9108a-116">Символ</span><span class="sxs-lookup"><span data-stu-id="9108a-116">Character</span></span>|<span data-ttu-id="9108a-117">Сущность</span><span class="sxs-lookup"><span data-stu-id="9108a-117">Entity</span></span>|<span data-ttu-id="9108a-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="9108a-118">Notes</span></span>|
|---------------|------------|-----------|
|<span data-ttu-id="9108a-119">& (амперсанд)</span><span class="sxs-lookup"><span data-stu-id="9108a-119">& (ampersand)</span></span>|<span data-ttu-id="9108a-120">\&amp;</span><span class="sxs-lookup"><span data-stu-id="9108a-120">\&amp;</span></span>|<span data-ttu-id="9108a-121">Должен использоваться для значений атрибутов и содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="9108a-121">Must be used both for attribute values and for content of an element.</span></span>|
|<span data-ttu-id="9108a-122">> (больше, чем характер)</span><span class="sxs-lookup"><span data-stu-id="9108a-122">> (greater-than character)</span></span>|<span data-ttu-id="9108a-123">\&gt;</span><span class="sxs-lookup"><span data-stu-id="9108a-123">\&gt;</span></span>|<span data-ttu-id="9108a-124">Необходимо использовать значение атрибута, но > приемлемо, поскольку содержание элемента до тех пор, пока < не предшествует ему.</span><span class="sxs-lookup"><span data-stu-id="9108a-124">Must be used for an attribute value, but > is acceptable as the content of an element as long as < does not precede it.</span></span>|
|<span data-ttu-id="9108a-125">< (меньше, чем характер)</span><span class="sxs-lookup"><span data-stu-id="9108a-125">< (less-than character)</span></span>|<span data-ttu-id="9108a-126">\&lt;</span><span class="sxs-lookup"><span data-stu-id="9108a-126">\&lt;</span></span>|<span data-ttu-id="9108a-127">Необходимо использовать для значения атрибута, но \< это приемлемо, поскольку содержимое элемента до тех пор, пока > не следует за ним.</span><span class="sxs-lookup"><span data-stu-id="9108a-127">Must be used for an attribute value, but \< is acceptable as the content of an element as long as > does not follow it.</span></span>|
|<span data-ttu-id="9108a-128">"(прямая кавычка)</span><span class="sxs-lookup"><span data-stu-id="9108a-128">" (straight quotation mark)</span></span>|<span data-ttu-id="9108a-129">\&quot;</span><span class="sxs-lookup"><span data-stu-id="9108a-129">\&quot;</span></span>|<span data-ttu-id="9108a-130">Должен использоваться для значения атрибута, но прямая кавычка (") допустима в качестве содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="9108a-130">Must be used for an attribute value, but a straight quotation mark (") is acceptable as the content of an element.</span></span> <span data-ttu-id="9108a-131">Обратите внимание, что значения атрибутов могут быть заключены в прямые одиночные кавычки (') или прямые двойные кавычки (""). Первый символ определяет оболочку значения атрибута, а альтернативный знак кавычек можно затем использовать в качестве литерала в значении.</span><span class="sxs-lookup"><span data-stu-id="9108a-131">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|
|<span data-ttu-id="9108a-132">' (одиночная прямая кавычка)</span><span class="sxs-lookup"><span data-stu-id="9108a-132">' (single straight quotation mark)</span></span>|<span data-ttu-id="9108a-133">\&apos;</span><span class="sxs-lookup"><span data-stu-id="9108a-133">\&apos;</span></span>|<span data-ttu-id="9108a-134">Должен использоваться для значения атрибута, но прямая одиночная кавычка (') допустима в качестве содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="9108a-134">Must be used for an attribute value, but a single straight quotation mark (') is acceptable as the content of an element.</span></span> <span data-ttu-id="9108a-135">Обратите внимание, что значения атрибутов могут быть заключены в прямые одиночные кавычки (') или прямые двойные кавычки (""). Первый символ определяет оболочку значения атрибута, а альтернативный знак кавычек можно затем использовать в качестве литерала в значении.</span><span class="sxs-lookup"><span data-stu-id="9108a-135">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|
|<span data-ttu-id="9108a-136">(сопоставления цифровых символов)</span><span class="sxs-lookup"><span data-stu-id="9108a-136">(numeric character mappings)</span></span>|<span data-ttu-id="9108a-137">&#*(все же)*; или &*ххех;*</span><span class="sxs-lookup"><span data-stu-id="9108a-137">&#*[integer]*; or &#x *[hex]*;</span></span>|<span data-ttu-id="9108a-138">XAML поддерживает сопоставления числовых символов с активной кодировкой.</span><span class="sxs-lookup"><span data-stu-id="9108a-138">XAML supports numeric character mappings into the encoding that is active.</span></span>|
|<span data-ttu-id="9108a-139">(неразрывный пробел)</span><span class="sxs-lookup"><span data-stu-id="9108a-139">(nonbreaking space)</span></span>|<span data-ttu-id="9108a-140">&\#160; (при условии кодирования UTF-8)</span><span class="sxs-lookup"><span data-stu-id="9108a-140">&\#160; (assuming UTF-8 encoding)</span></span>|<span data-ttu-id="9108a-141">Для элементов потокового документа или элементы, которые принимают текст, например <xref:System.Windows.Controls.TextBox> в WPF, неразрывные пробелы не нормализуются в разметке даже для `xml:space="default"`.</span><span class="sxs-lookup"><span data-stu-id="9108a-141">For flow document elements, or elements that take text such as the WPF <xref:System.Windows.Controls.TextBox>, nonbreaking spaces are not normalized out of the markup, even for `xml:space="default"`.</span></span> <span data-ttu-id="9108a-142">(Для получения дополнительной информации [см. Обработка белого пространства в XAML](white-space-processing.md).)</span><span class="sxs-lookup"><span data-stu-id="9108a-142">(For more information, see [White-space processing in XAML](white-space-processing.md).)</span></span>|

## <a name="xml-comment-format"></a><span data-ttu-id="9108a-143">Формат комментариев XML</span><span class="sxs-lookup"><span data-stu-id="9108a-143">XML Comment Format</span></span>

<span data-ttu-id="9108a-144">XAML использует формат комментариев XML: начало комментария — `<!--`, конец комментария — `-->,`, при этом последовательность `--` не должна входить в комментарий.</span><span class="sxs-lookup"><span data-stu-id="9108a-144">XAML uses the XML comment format: the start of the comment is `<!--`, the end of comment is `-->,` and the sequence `--` must not occur within the comment.</span></span>

## <a name="xml-processing-instructions"></a><span data-ttu-id="9108a-145">Инструкции по обработке XML</span><span class="sxs-lookup"><span data-stu-id="9108a-145">XML Processing Instructions</span></span>

<span data-ttu-id="9108a-146">XAML обрабатывает инструкции по обработке XML в соответствии со спецификациями XML, в которых указано, что инструкции должны передаваться.</span><span class="sxs-lookup"><span data-stu-id="9108a-146">XAML handles XML processing instructions according to XML specifications, which state that the instructions must be passed through.</span></span> <span data-ttu-id="9108a-147">Обработка XAML в .NET XAML Services не использует инструкций по обработке.</span><span class="sxs-lookup"><span data-stu-id="9108a-147">XAML processing in .NET XAML Services  does not use any processing instructions.</span></span> <span data-ttu-id="9108a-148">Другие существующие платформы, использующие XAML, также не применяют инструкции по обработке из XAML.</span><span class="sxs-lookup"><span data-stu-id="9108a-148">Other existing frameworks that use XAML also do not use processing instructions from XAML.</span></span>

## <a name="see-also"></a><span data-ttu-id="9108a-149">См. также</span><span class="sxs-lookup"><span data-stu-id="9108a-149">See also</span></span>

- [<span data-ttu-id="9108a-150">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9108a-150">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="9108a-151">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="9108a-151">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="9108a-152">Грамматика XamlName</span><span class="sxs-lookup"><span data-stu-id="9108a-152">XamlName Grammar</span></span>](xamlname-grammar.md)
- [<span data-ttu-id="9108a-153">Обработка пробелов в XAML</span><span class="sxs-lookup"><span data-stu-id="9108a-153">White-space processing in XAML</span></span>](white-space-processing.md)