---
title: Lync Server 2013： 使用安裝程式命令列選項
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
ms.openlocfilehash: aacaa402b325fbefe13d70dea4f3e74af1d896cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Setup 命令列選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

在 Office 安裝程式操作很少使用 Setup.exe 命令列。 而不是使用安裝程式命令列選項，您通常會針對產品安裝程式和功能自訂使用 Office 自訂工具和 Config.xml 檔案。

Office Setup.exe 命令列可辨識下表所述的命令列選項。

### <a name="office-setup-command-line-options"></a>Office 安裝程式命令列選項

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>安裝程式命令列選項</th>
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
<td><p>指定在安裝過程中，安裝程式所使用的 Config.xml 檔案。 /Config 選項可用於指定例如 Lync 2013 的安裝中，為自訂的 Config.xml 檔案：<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/ 修改 Lync</p></td>
<td><p>與修改的 Config.xml 檔案搭配使用，即可在維護模式中執行安裝程式，並對現有的 Office 安裝進行變更。 例如，您可以使用 / 修改選項來新增或移除 Lync 功能。</p></td>
</tr>
<tr class="odd">
<td><p>/ 修復 Lync</p></td>
<td><p>會從以修復 Lync 使用者的電腦執行安裝程式。</p></td>
</tr>
<tr class="even">
<td><p>解除安裝 Lync /</p></td>
<td><p>執行安裝程式，從使用者電腦移除 Lync。</p></td>
</tr>
</tbody>
</table>


如需使用安裝程式命令列選項的詳細資訊，請參閱<http://go.microsoft.com/fwlink/p/?linkid=267515>。

</div>

<span> </span>

</div>

</div>

</div>

