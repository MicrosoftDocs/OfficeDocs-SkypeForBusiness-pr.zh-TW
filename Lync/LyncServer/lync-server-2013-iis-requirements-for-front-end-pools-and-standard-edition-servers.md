---
title: 前端集區與 Standard Edition Server 的 IIS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d804df614eab49eeabe82cca9d304e082d9ced3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013 中的前端集區與 Standard Edition Server 的 IIS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-19_

針對標準版伺服器和前端伺服器以及控制器，Lync Server 2013 安裝程式會在網際網路資訊服務（IIS）中建立虛擬目錄，以進行下列用途：

  - 若要讓使用者能夠從通訊錄服務下載檔案

  - 啟用用戶端以取得更新

  - 若要啟用會議

  - 讓使用者能夠下載會議內容

  - 若要讓使用者能夠展開通訊群組

  - 若要啟用電話會議

  - 啟用回應群組功能

此外，Lync Server 2010 的累加更新：2011年11月安裝程式會在 IIS 中建立虛擬目錄，以進行下列用途：

  - 在前端伺服器或標準版伺服器上，支援行動裝置上的行動功能（例如立即訊息（IM）與目前狀態）

  - 在前端伺服器或標準版伺服器以及控制器上，讓行動裝置能夠自動探索行動資源



> [!NOTE]
> 如果您要部署行動性，建議您使用 IIS 7.5。 Lync Server 行動服務安裝程式會設定一些 ASP.NET 標誌來改善效能。 預設會在 Windows Server 2008 R2 上安裝 IIS 7.5，且行動服務安裝程式會自動變更 ASP.NET 設定。 如果您在 Windows Server 2008 上使用 IIS 7.0，您必須手動變更這些設定。



Lync Server 需要安裝下列 IIS 模組：


> [!IMPORTANT]
> 如果您的組織要求您在系統磁片磁碟機以外的磁片磁碟機上找到 [IIS] 和 [所有 Web 服務]，您可以在 [設定] 對話方塊中變更 Lync Server 檔案的安裝位置路徑。 如果您將安裝檔案安裝到此路徑，包括 OCSCore，則其餘的 Lync Server 檔案也將會部署到此磁片磁碟機。 如需有關如何在安裝 IIS 時重新置放由 Windows Server Manager 部署的 INETPUB 的<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>詳細資訊，請參閱。


  - 靜態內容

  - 預設檔

  - HTTP 錯誤

  - ASP.NET

  - .NET 擴充性

  - 網際網路伺服器 API （ISAPI）延伸

  - ISAPI 篩選

  - HTTP 記錄

  - 記錄工具

  - 診斷

  - Windows 驗證

  - 要求篩選

  - 靜態內容壓縮

  - 動態內容壓縮

  - IIS 管理主控台

  - IIS 管理腳本與工具

  - 匿名驗證（在安裝 IIS 時預設為已安裝）

  - 用戶端憑證對應驗證

下表列出內部存取虛擬目錄的 Uri，以及它們所參照的檔案系統資源。

### <a name="virtual-directories-for-internal-access"></a>內部存取的虛擬目錄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>功能</th>
<th>虛擬目錄 URI</th>
<th>參照</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>通訊錄服務器</p></td>
<td><p>HTTPs://&lt;內部 FQDN&gt;/ABS/int/Handler</p></td>
<td><p>內部使用者的通訊錄服務器下載檔案的位置。</p></td>
</tr>
<tr class="even">
<td><p>自動探索服務</p></td>
<td><p>HTTPs://&lt;內部 FQDN&gt;/Autodiscover</p></td>
<td><p>Lync Server 自動探索服務的位置，可為內部行動裝置使用者找到行動資源。</p></td>
</tr>
<tr class="odd">
<td><p>用戶端更新</p></td>
<td><p>HTTP://&lt;內部 FQDN&gt;/AutoUpdate/Int</p></td>
<td><p>內部電腦式用戶端的更新檔案位置。</p></td>
</tr>
<tr class="even">
<td><p>會議</p></td>
<td><p>HTTP://&lt;內部 FQDN&gt;/Conf/Int</p></td>
<td><p>內部使用者的會議資源位置。</p></td>
</tr>
<tr class="odd">
<td><p>裝置更新</p></td>
<td><p>HTTP://&lt;內部 FQDN&gt;/DeviceUpdateFiles_Int</p></td>
<td><p>內部 UC 裝置的整合通訊（UC）裝置更新檔案的位置。</p></td>
</tr>
<tr class="even">
<td><p>要求</p></td>
<td><p>HTTP://&lt;內部 FQDN&gt;/etc/place/null</p></td>
<td><p>內部使用者的會議內容位置。</p></td>
</tr>
<tr class="odd">
<td><p>行動服務</p></td>
<td><p>HTTPs://&lt;內部 FQDN&gt;/Mcx</p></td>
<td><p>內部行動裝置使用者的行動服務資源位置。</p></td>
</tr>
<tr class="even">
<td><p>群組展開和通訊錄網頁查詢服務</p></td>
<td><p>HTTP://&lt;內部 FQDN&gt;/GroupExpansion/int/service.asmx</p></td>
<td><p>針對內部使用者啟用群組延伸的 Web 服務的位置。 此外，提供全域通訊清單資訊給內部 Lync Mobile Microsoft Lync 2010 行動用戶端的通訊錄 Web 查詢服務的位置。</p></td>
</tr>
<tr class="odd">
<td><p>電話會議</p></td>
<td><p>HTTP://&lt;內部 FQDN&gt;/PhoneConferencing/Int</p></td>
<td><p>內部使用者的電話會議資料位置。</p></td>
</tr>
<tr class="even">
<td><p>裝置更新</p></td>
<td><p>HTTP://&lt;內部 FQDN&gt;/RequestHandler</p></td>
<td><p>裝置更新 Web 服務要求處理常式的位置，可讓內部 UC 裝置上傳記錄並檢查更新。</p></td>
</tr>
<tr class="odd">
<td><p>回應群組應用程式</p></td>
<td><p>HTTP://&lt;內部 FQDN&gt;/RgsConfig</p>
<p>HTTP://&lt;內部 FQDN&gt;/RgsClients</p></td>
<td><p>[回應群組設定] 工具的位置。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 針對整合式設定中的前端池，您必須先部署 IIS，才能將伺服器新增至池中。


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" />安全性注意事項：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>您必須使用 [IIS 管理] 管理單元來指派 IIS 網頁元件伺服器所使用的憑證。</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

