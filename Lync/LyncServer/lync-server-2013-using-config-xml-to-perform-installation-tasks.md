---
title: Lync Server 2013：使用 Config.xml 執行安裝任務
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
ms.openlocfilehash: 5b6e037f2c69e963e8ca5963a71dabe80f9c75fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>使用 Config.xml 在 Lync Server 2013 中執行安裝工作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

雖然 Office 自訂工具（OCT）是自訂安裝的主要工具，但系統管理員可以使用 Config.xml 檔案來指定不在 OCT 中提供的其他安裝指示。 下列自訂功能只能使用 Config.xml 檔案來進行：

  - 指定網路安裝點的路徑。

  - 選取要安裝的產品。

  - 設定記錄，以及安裝程式自訂檔案和軟體更新的位置。

  - 指定安裝選項，例如 [使用者名稱]。

  - 將本機安裝來源（.LIS）複製到使用者的電腦，但不安裝 Office。

  - 新增或移除安裝的語言。

建議您使用 Config.xml 檔案來設定 Lync 2013 無訊息安裝。

根據預設，儲存在核心產品資料夾中的 Config.xml 檔案（例如 [產品]） \\。WW）指示安裝程式安裝該產品。 例如，下列資料夾中的 Config.xml 檔案會安裝 Lync 2013：

  - \\\\伺服器\\共用\\Lync15\\Lync WW \\.xml

下表列出最常用於 Lync 2013 安裝的 Config.xml 元素。

### <a name="configxml-elements"></a>Config .xml 元素

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuration</p></td>
<td><p>高層元素（必要）。 包含 Product 屬性，例如： Product = Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>指定安裝期間特定產品功能的處理方式。 使用下列屬性來避免安裝 Business Connectivity Service，包括干擾 Outlook 2010 的共用元件：</p>
<ul>
<li><p>識別碼 =&quot;LOBiMain&quot;</p></li>
<li><p>State =&quot;不存在&quot;</p></li>
<li><p>子級 =&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>顯示幕</p></td>
<td><p>安裝程式顯示給使用者的 UI 層級。 一般屬性包括下列各項：</p>
<ul>
<li><p>CompletionNotice =&quot;是&quot; | &quot;否&quot;（預設值）</p></li>
<li><p>AcceptEula =&quot;是&quot; | &quot;否&quot;（預設值）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>記錄</p></td>
<td><p>安裝程式所執行之記錄類型的選項。 一般屬性包括下列各項：</p>
<ul>
<li><p>輸入 =&quot;Off&quot; | &quot;標準&quot;（預設值） |&quot;詳細資訊&quot;</p></li>
<li><p>Template = "filename .txt" （記錄檔的名稱）</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>正在</p></td>
<td><p>指定 Windows 安裝程式屬性的值。 一般屬性包括下列各項：</p>
<ul>
<li><p>設定識別碼 =&quot;Name&quot; （Windows Installer 屬性的名稱）</p></li>
<li><p>值 =&quot;value&quot; （要指派給屬性的值）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>要執行安裝的網路安裝點的完整路徑。 包括 Location 屬性：</p>
<ul>
<li><p>位置 = "path"</p></li>
</ul></td>
</tr>
</tbody>
</table>


下列範例顯示 Lync 2013 典型無訊息安裝的 Config.xml 檔案。

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

有關使用 Config.xml 檔案來執行 Office 安裝與維護工作的詳細資訊，請參閱<http://go.microsoft.com/fwlink/p/?linkid=267514>。

<div>

## <a name="to-customize-the-configxml-file"></a>自訂 Config.xml 檔案

1.  使用文字編輯器工具（例如記事本）來開啟 Config.xml 檔案。

2.  找出包含您要變更之元素的線條。

3.  使用您要使用的緘默選項來修改元素專案。 請務必移除批註分隔符號 "\<\!--" 和 "--\>"。 例如，使用下列語法：
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  儲存 Config.xml 檔案。

</div>

</div>

<span> </span>

</div>

</div>

</div>

