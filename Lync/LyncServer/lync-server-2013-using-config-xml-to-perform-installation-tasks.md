---
title: Lync Server 2013：使用 Config.xml 執行安裝工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901d95797955c6f545c0d305e2c855829c92addf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535780"
---
# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Config.xml 執行安裝工作

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

雖然 Office 自訂工具 (OCT) 是自訂安裝的主要工具，但是系統管理員可以使用 Config.xml 檔案來指定 OCT 中所沒有的其他安裝指示。下列自訂只能使用 Config.xml 檔案來進行：

  - 指定網路安裝點的路徑。

  - 選取所要安裝的產品。

  - 設定安裝程式自訂檔案和軟體更新的記錄及位置。

  - 指定安裝選項，例如使用者名稱。

  - 將本機安裝來源 (LIS) 複製到使用者的電腦，而不安裝 Office。

  - 在安裝中新增或移除語言。

建議您使用 Config.xml 檔案來設定 Lync 2013 無訊息安裝。

根據預設，在核心產品資料夾中儲存的 Config.xml 檔案 (例如 \\ product。WW) 指示安裝程式安裝該產品。 例如，下列資料夾中的 Config.xml 檔會安裝 Lync 2013：

  - \\\\伺服器 \\ 共用 \\ Lync15 \\ Lync \\Config.xml

下表列出最常用於 Lync 2013 安裝的 Config.xml 元素。

### <a name="configxml-elements"></a>Config.xml 元素

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>元素</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>組態</p></td>
<td><p>最上層元素 (必要)。包含 Product 屬性，例如：Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>指定在安裝期間如何處理特定的產品功能。 使用下列屬性可防止安裝 Business Connectivity Services，其中包含干擾 Outlook 2010 的共用元件：</p>
<ul>
<li><p>識別碼 = &quot; LOBiMain&quot;</p></li>
<li><p>State = 不 &quot; 存在&quot;</p></li>
<li><p>子系 = &quot; 強制&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>顯示器</p></td>
<td><p>安裝程式向使用者顯示的 UI 層級。一般屬性包括：</p>
<ul>
<li><p>CompletionNotice= &quot; 是 &quot;  |  &quot; 否 &quot; (預設) </p></li>
<li><p>AcceptEula= &quot; 是 &quot;  |  &quot; 否 &quot; (預設) </p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>記錄</p></td>
<td><p>安裝程式執行之記錄類型的選項。一般屬性包括：</p>
<ul>
<li><p>Type = &quot; Off &quot;  |  &quot; Standard &quot; (default) | &quot;詳細&quot;</p></li>
<li><p>Template=”檔案名稱.txt” (記錄檔名稱)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>設定</p></td>
<td><p>指定 Windows Installer 內容的值。一般屬性包括：</p>
<ul>
<li><p>設定識別碼 = &quot; name &quot; (Windows Installer 屬性的名稱) </p></li>
<li><p>Value = &quot; value &quot; (要指派給屬性的值) </p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>要執行安裝之網路安裝點的完整路徑。包括 Location 屬性：</p>
<ul>
<li><p>Location = "path"</p></li>
</ul></td>
</tr>
</tbody>
</table>


下列範例顯示 Lync 2013 一般無訊息安裝的 Config.xml 檔案。

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

您可以在使用 Config.xml 檔案執行 Office 安裝及維護工作的詳細資訊 <https://go.microsoft.com/fwlink/p/?linkid=267514> 。

<div>

## <a name="to-customize-the-configxml-file"></a>自訂 Config.xml 檔案

1.  使用文字編輯器工具來開啟 Config.xml 檔案，例如 [記事本]。

2.  找到包含您要變更之元素的那幾行。

3.  以您要使用的無訊息選項來修改元素項目。 請務必移除批註定界符 " \<\!--" and "--\> "。 例如，使用下列語法：
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  儲存 Config.xml 檔案。

</div>

</div>

<span> </span>

</div>

</div>

</div>

