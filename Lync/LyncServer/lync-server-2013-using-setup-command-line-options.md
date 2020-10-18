---
title: Lync Server 2013：使用安裝程式命令列選項
description: Lync Server 2013：使用安裝程式命令列選項。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15c3490ead090766462ce83cb13ffe62355032cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580239"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a>在 Lync Server 2013 中使用安裝程式命令列選項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Setup.exe 命令列將用於 Office 安裝中非常少的作業。 您通常會使用 Office 自訂工具和 Config.xml 檔案進行產品安裝和功能自訂，而不是使用安裝程式的命令列選項。

Office Setup.exe 命令列會識別下表所述的命令列選項。

### <a name="office-setup-command-line-options"></a>Office 安裝程式 Command-Line 選項

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>安裝 Command-Line 選項</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>執行 Office 自訂工具，以建立安裝程式自訂檔案 (.msp 檔案)。</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>將指定的安裝程式自訂檔案套用至安裝。您可以指定特定自訂檔案 (.msp 檔案) 的路徑，或是儲存自訂檔案的資料夾路徑。</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>指定在安裝過程中，安裝程式所使用的 Config.xml 檔案。 使用 [/config] 選項可指定您針對 Lync 2013 安裝所自訂的 Config.xml 檔案，例如： <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>與修改的 Config.xml 檔案搭配使用，即可在維護模式中執行安裝程式，並對現有的 Office 安裝進行變更。 例如，您可以使用/modify 選項來新增或移除 Lync 功能。</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>從使用者的電腦執行安裝程式，以修復 Lync。</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>執行安裝程式以從使用者的電腦中移除 Lync。</p></td>
</tr>
</tbody>
</table>


如需使用安裝程式命令列選項的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?linkid=267515> 。

</div>

<span> </span>

</div>

</div>

</div>

