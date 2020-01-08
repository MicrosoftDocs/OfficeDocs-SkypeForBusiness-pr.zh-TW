---
title: Lync Server 2013：使用安裝程式命令列選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5087c8ac777e5e2fd3259f925a4217a4d47dd800
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>使用 Lync Server 2013 中的安裝程式命令列選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Setup.exe 命令列適用于 Office 設定中的極少作業。 您通常會使用 Office 自訂工具和 Config.xml 檔案來進行產品設定和功能自訂，而不是使用 [設定] 命令列選項。

Office Setup.exe 命令列會辨識下表所述的命令列選項。

### <a name="office-setup-command-line-options"></a>Office 設定命令列選項

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>設定命令列選項</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>執行 Office 自訂工具來建立安裝程式自訂檔（.msp 檔案）。</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>將指定的安裝程式自訂檔案套用到安裝。 您可以指定特定自訂檔案（.msp 檔案）或儲存自訂檔案的資料夾路徑。</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>指定安裝程式在安裝期間使用的 Config.xml 檔案。 使用/config 選項指定您針對 Lync 2013 安裝自訂的 Config.xml 檔案，例如：<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>與已修改的 Config.xml 檔案搭配使用，可在維護模式中執行安裝程式，並變更現有的 Office 安裝。 例如，您可以使用/modify 選項來新增或移除 Lync 功能。</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>從使用者的電腦執行安裝程式來修復 Lync。</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>執行安裝程式，從使用者的電腦中移除 Lync。</p></td>
</tr>
</tbody>
</table>


如需有關使用 setup 命令列選項的詳細資訊， <http://go.microsoft.com/fwlink/p/?linkid=267515>請參閱。

</div>

<span> </span>

</div>

</div>

</div>

