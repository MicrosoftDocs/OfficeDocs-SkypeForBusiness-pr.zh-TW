---
title: Lync Server 2013： IIS 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c2dd96b45105eabe644b86ba5ab3af099ea8e8f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Lync Server 2013 中的 IIS 設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-17_

若要順利完成此程式，您應該至少登入至本機系統管理員和網域使用者的伺服器。

設定及安裝 Lync Server 2013、Standard Edition 或集區中第一部前端伺服器的前端伺服器之前，請先針對 Internet information Services (IIS) 安裝及設定伺服器角色和 Web 服務。

<div class=" ">


> [!IMPORTANT]  
> 如果您的組織需要在系統磁片磁碟機以外的磁片磁碟機上找到 [IIS] 和 [所有 Web 服務]，您可以在初次安裝 Lync Server 2013 系統管理工具時，在 [安裝程式] 對話方塊中，變更 [Lync Server 2013 檔案] 的安裝位置路徑。 安裝 IIS 之前，請先安裝系統管理工具。 若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他的 Lync Server 2013 檔案也會同時部署至此磁片磁碟機。 如需 dtails，請參閱<A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 系統管理工具</A>。 如需如何重新置放 Windows Server Manager 在安裝 IIS 時所部署之 INETPUB 的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。



</div>

下表指出必要的 IIS 7.5 角色服務。

### <a name="iis-75-role-services"></a>IIS 7.5 角色服務

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>角色標題</th>
<th>角色服務</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>已安裝常見的 HTTP 功能</p></td>
<td><p>靜態內容</p></td>
</tr>
<tr class="even">
<td><p>已安裝常見的 HTTP 功能</p></td>
<td><p>預設檔</p></td>
</tr>
<tr class="odd">
<td><p>已安裝常見的 HTTP 功能</p></td>
<td><p>HTTP 錯誤</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 也需要 ASP。 NET 4。5</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>.NET 擴充性</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>網際網路伺服器 API (ISAPI) 擴充</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>ISAPI 篩選</p></td>
</tr>
<tr class="even">
<td><p>健康情況及診斷</p></td>
<td><p>HTTP 記錄</p></td>
</tr>
<tr class="odd">
<td><p>健康情況及診斷</p></td>
<td><p>記錄工具</p></td>
</tr>
<tr class="even">
<td><p>健康情況及診斷</p></td>
<td><p>跟蹤</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>預設會安裝並啟用匿名驗證 () </p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>Windows 驗證</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>用戶端憑證對應驗證</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>要求篩選</p></td>
</tr>
<tr class="odd">
<td><p>效能</p></td>
<td><p>靜態內容壓縮</p>
<p>動態內容壓縮</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理主控台</p></td>
</tr>
<tr class="odd">
<td><p>管理工具</p></td>
<td><p>IIS 管理指令碼及工具</p></td>
</tr>
</tbody>
</table>


在 Windows Server 2008 R2 SP1 x64 作業系統上，您可以使用 Windows PowerShell 2.0。 您必須先匯入 ServerManager 模組，然後安裝 IIS 7.5 角色和角色服務。

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> 預設會以 IIS 伺服器角色安裝匿名驗證。 您可以在安裝 IIS 之後管理匿名驗證。 如需詳細資訊，請參閱的「啟用匿名驗證 (IIS 7) 」 <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> 。



</div>

下表指出 Windows Server 2012 和 Windows Server 2012 R2 所需的 IIS 8.0 和 IIS 8.5 角色服務。

<div class=" ">


> [!NOTE]  
> 若為 Windows Server 2012 和 Windows Server 2012 R2，Add-WindowsFeature Cmdlet 已由 Install-WindowsFeature Cmdlet 所取代。 如需詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>。



</div>

### <a name="iis-80-and-iis-85-role-services"></a>IIS 8.0 和 IIS 8.5 角色服務

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>角色標題</th>
<th>角色服務</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>網頁伺服器 (IIS) </p></td>
<td><p>網頁伺服器</p></td>
</tr>
<tr class="even">
<td><p>一般 HTTP 功能</p></td>
<td><p>預設文件</p></td>
</tr>
<tr class="odd">
<td><p>一般 HTTP 功能</p></td>
<td><p>瀏覽目錄</p></td>
</tr>
<tr class="even">
<td><p>一般 HTTP 功能</p></td>
<td><p>HTTP 錯誤</p></td>
</tr>
<tr class="odd">
<td><p>一般 HTTP 功能</p></td>
<td><p>靜態內容</p></td>
</tr>
<tr class="even">
<td><p>一般 HTTP 功能</p></td>
<td><p>HTTP 重新導向</p></td>
</tr>
<tr class="odd">
<td><p>健康情況及診斷</p></td>
<td><p>HTTP 記錄</p></td>
</tr>
<tr class="even">
<td><p>健康情況及診斷</p></td>
<td><p>記錄工具</p></td>
</tr>
<tr class="odd">
<td><p>健康情況及診斷</p></td>
<td><p>要求監視器</p></td>
</tr>
<tr class="even">
<td><p>健康情況及診斷</p></td>
<td><p>跟蹤</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>要求篩選</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>基本驗證</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>用戶端憑證對應驗證</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>Windows 驗證</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>.Net 擴充性3。5</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>.Net 擴充性4。5</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>ASP.Net 3。5</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>ASP.Net 4。5</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>ISAPI 擴充程式</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>ISAPI 篩選器</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>伺服器端包括</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理主控台</p></td>
</tr>
<tr class="odd">
<td><p>管理工具</p></td>
<td><p>IIS 6 元資料庫相容性</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理指令碼及工具</p></td>
</tr>
<tr class="odd">
<td><p>.Net 3.5 Framework 功能</p></td>
<td><p>.Net 3.5 Framework</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>.Net Framework 4。5</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>ASP.Net 4。5</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>HTTP 啟用</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>TCP 埠共用</p></td>
</tr>
<tr class="even">
<td><p>背景智慧傳輸服務</p></td>
<td><p>IIS 伺服器擴充</p></td>
</tr>
<tr class="odd">
<td><p>筆跡及手寫服務</p></td>
<td><p>筆跡及手寫服務</p></td>
</tr>
<tr class="even">
<td><p>媒體基礎</p></td>
<td><p>媒體基礎</p></td>
</tr>
<tr class="odd">
<td><p>使用者介面和基礎結構</p></td>
<td><p>圖形管理工具和基礎結構</p></td>
</tr>
<tr class="even">
<td><p>使用者介面和基礎結構</p></td>
<td><p>桌面體驗</p></td>
</tr>
<tr class="odd">
<td><p>使用者介面和基礎結構</p></td>
<td><p>伺服器圖形命令介面</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3。5</p></td>
<td><p>Windows Identity Foundation 3。5</p></td>
</tr>
<tr class="odd">
<td><p>Windows 進程啟用服務</p></td>
<td><p>進程模型</p></td>
</tr>
<tr class="even">
<td><p>Windows 進程啟用服務</p></td>
<td><p>設定 APIs</p></td>
</tr>
</tbody>
</table>


在 Windows Server 2012 和 Windows Server 2012 R2 中，您可以使用 Windows PowerShell 3.0 來安裝 IIS 需求。 使用 Windows PowerShell 3.0 中的 ServerManager 模組，輸入：

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Windows Server 2012 的新增功能是定義可在何處找到 Windows Server 2012 來源媒體的–來源參數。 媒體可以定義為 DVD 磁片磁碟機 (例如，D:\Sources\Sxs) 或網路共用（媒體檔案已複製） (例如， \\ fileserver\windows2012\sources\Sxs) 。



</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中前端集區與 Standard Edition server 的 IIS 需求](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

