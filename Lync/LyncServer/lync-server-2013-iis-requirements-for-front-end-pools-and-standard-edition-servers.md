---
title: 前端集區及 Standard Edition 伺服器的 IIS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>前端集區和 Standard Edition server 在 Lync Server 2013 中的 IIS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-19_

Standard Edition 伺服器和前端伺服器和 Director，Lync Server 2013 安裝程式會建立虛擬目錄中網際網路資訊服務 (IIS) 基於下列目的：

  - 若要讓使用者能夠從通訊錄服務下載檔案

  - 若要讓用戶端取得更新

  - 若要啟用會議

  - 若要讓使用者能夠下載會議內容

  - 若要讓使用者能夠擴充通訊群組

  - 若要啟用電話會議

  - 若要啟用回應群組功能

此外，Lync Server 2010 的累計更新： 11 月 2011年安裝程式會建立虛擬目錄在 IIS 中用於下列用途：

  - 在前端伺服器或 Standard Edition 伺服器，以支援行動裝置上的行動功能，例如立即訊息 (IM) 和目前狀態

  - 在前端伺服器或 Standard Edition 伺服器和 Director 上，讓行動裝置能夠自動探索行動性資源



> [!NOTE]
> 如果您正在部署行動性，建議您使用 IIS 7.5。 Lync Server Mobility Service 安裝程式會設定某些 ASP.NET 旗標，以改善效能。 依預設，IIS 7.5 會安裝在 Windows Server 2008 R2 上，而且 Mobility Service 安裝程式會自動變更 ASP.NET 設定。 如果您在 Windows Server 2008 上使用 IIS 7.0，則需要手動變更這些設定。



Lync 伺服器上需要安裝下列 IIS 模組：


> [!IMPORTANT]
> 如果貴組織需要在非系統磁碟機的磁碟機上尋找 IIS 和所有 Web 服務，您可以變更設定] 對話方塊中的 Lync Server 檔案的安裝位置路徑。 如果您將安裝檔案安裝到此路徑，包括 OCSCore.msi，Lync Server 檔案的其餘部分將會部署至這個磁碟機。 如需如何重新放置部署 Windows Server 管理員安裝 IIS 時 INETPUB 的詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>。


  - 靜態內容

  - 預設文件

  - HTTP 錯誤

  - ASP.NET

  - .NET 擴充性

  - 網際網路伺服器 API (ISAPI) 延伸模組

  - ISAPI 篩選

  - HTTP 記錄

  - 記錄工具

  - 追蹤

  - Windows 驗證

  - 要求篩選

  - 靜態內容壓縮

  - 動態內容壓縮

  - IIS 管理主控台

  - IIS 管理指令碼與工具

  - 匿名驗證 （預設安裝安裝 IIS 時）

  - 用戶端憑證對應驗證

下表列出內部存取與它們所參考的檔案系統資源的虛擬目錄的 Uri。

### <a name="virtual-directories-for-internal-access"></a>供內部存取的虛擬目錄

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
<th>參照到</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Address Book Server</p></td>
<td><p>https://&lt;內部 FQDN&gt;/ABS/int/Handler</p></td>
<td><p>位置的 Address Book Server 下載檔案，供內部使用者。</p></td>
</tr>
<tr class="even">
<td><p>自動探索服務</p></td>
<td><p>https://&lt;內部 FQDN&gt;/Autodiscover</p></td>
<td><p>尋找內部行動裝置使用者的行動性資源 Lync Server 自動探索服務的位置。</p></td>
</tr>
<tr class="odd">
<td><p>用戶端更新</p></td>
<td><p>http://&lt;內部 FQDN&gt;/AutoUpdate/Int</p></td>
<td><p>內部電腦為基礎的用戶端更新檔案的位置。</p></td>
</tr>
<tr class="even">
<td><p>Conf</p></td>
<td><p>http://&lt;內部 FQDN&gt;/Conf/Int</p></td>
<td><p>供內部使用者的會議資源的位置。</p></td>
</tr>
<tr class="odd">
<td><p>裝置更新</p></td>
<td><p>http://&lt;內部 FQDN&gt;/DeviceUpdateFiles_Int</p></td>
<td><p>供內部 UC 裝置的整合的通訊 (UC) 裝置更新檔案的位置。</p></td>
</tr>
<tr class="even">
<td><p>會議</p></td>
<td><p>http://&lt;內部 FQDN&gt;/etc/place/null</p></td>
<td><p>內部使用者的會議內容位置。</p></td>
</tr>
<tr class="odd">
<td><p>Mobility Service</p></td>
<td><p>https://&lt;內部 FQDN&gt;/Mcx</p></td>
<td><p>內部行動裝置使用者的 Mobility Service 資源的位置。</p></td>
</tr>
<tr class="even">
<td><p>群組擴充和通訊錄 Web 查詢服務</p></td>
<td><p>http://&lt;內部 FQDN&gt;/GroupExpansion/int/service.asmx</p></td>
<td><p>可讓內部使用者的群組擴充的 Web 服務的位置。 此外，全域通訊清單資訊提供給內部 Lync Mobile Microsoft Lync 2010 Mobile 用戶端通訊錄 Web 查詢服務位置。</p></td>
</tr>
<tr class="odd">
<td><p>電話會議</p></td>
<td><p>http://&lt;內部 FQDN&gt;/PhoneConferencing/Int</p></td>
<td><p>供內部使用者的電話會議資料的位置。</p></td>
</tr>
<tr class="even">
<td><p>裝置更新</p></td>
<td><p>http://&lt;內部 FQDN&gt;/RequestHandler</p></td>
<td><p>裝置更新 Web 服務，可讓內部 UC 裝置上傳記錄並檢查更新的要求處理常式的位置。</p></td>
</tr>
<tr class="odd">
<td><p>回應群組應用程式</p></td>
<td><p>http://&lt;內部 FQDN&gt;/RgsConfig</p>
<p>http://&lt;內部 FQDN&gt;/RgsClients</p></td>
<td><p>回應群組組態工具的位置。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 合併設定中的前端集區，您必須部署 IIS 才能您可以將伺服器新增至集區。


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" />安全性附註：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>您必須使用 IIS 系統管理嵌入式管理單元來指派 IIS web 元件伺服器所使用的憑證。</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

