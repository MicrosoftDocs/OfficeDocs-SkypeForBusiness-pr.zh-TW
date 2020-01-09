---
title: Lync Server 2013：IIS 組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b9803fdb6c4a048fdf072b5ba2e5722b863640
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Lync Server 2013 中的 IIS 組態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-17_

若要成功完成此程式，您應該以本機管理員和網域使用者的身分登入伺服器。

在將 Lync Server 2013、標準版或第一個前端伺服器的前端伺服器設定並安裝到池中之前，您必須安裝並設定網際網路資訊服務（IIS）的伺服器角色和 Web 服務。

<div class=" ">


> [!IMPORTANT]  
> 如果您的組織要求您在系統磁片磁碟機以外的磁片磁碟機上找到 IIS 和所有 Web 服務，您可以在初次安裝 Lync Server 2013 時，在 [設定] 對話方塊中變更 Lync Server 2013 檔案的安裝位置路徑[管理工具]。 安裝 IIS 之前，請先安裝 [管理工具]。 如果您將安裝檔案安裝到此路徑（包括 OCSCore），其餘的 Lync Server 2013 檔案也會部署到這個磁片磁碟機。 如需 dtails，請參閱<A href="lync-server-2013-install-lync-server-administrative-tools.md">安裝 Lync Server 2013 系統管理工具</A>。 如需有關如何在安裝 IIS 時重新置放由 Windows Server Manager 部署的 INETPUB 的<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>詳細資訊，請參閱。



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
<p>Windows Server 2012 也需要 ASP. NET 4。5</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>.NET 擴充性</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>網際網路伺服器 API （ISAPI）延伸</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>ISAPI 篩選</p></td>
</tr>
<tr class="even">
<td><p>健康與診斷</p></td>
<td><p>HTTP 記錄</p></td>
</tr>
<tr class="odd">
<td><p>健康與診斷</p></td>
<td><p>記錄工具</p></td>
</tr>
<tr class="even">
<td><p>健康與診斷</p></td>
<td><p>診斷</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>匿名驗證（預設為已安裝和啟用）</p></td>
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
<td><p>提高</p></td>
<td><p>靜態內容壓縮</p>
<p>動態內容壓縮</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理主控台</p></td>
</tr>
<tr class="odd">
<td><p>管理工具</p></td>
<td><p>IIS 管理腳本與工具</p></td>
</tr>
</tbody>
</table>


在 Windows Server 2008 R2 SP1 x64 作業系統上，您可以使用 Windows PowerShell 2.0。 您必須先匯入 ServerManager 模組，然後再安裝 IIS 7.5 角色和角色服務。

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> 預設會安裝匿名驗證與 IIS 伺服器角色。 您可以在安裝 IIS 之後管理匿名驗證。 如需詳細資訊，請參閱「啟用匿名驗證（IIS 7 <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>）」。



</div>

下表顯示 Windows Server 2012 和 Windows Server 2012 R2 所需的 IIS 8.0 和 IIS 8.5 角色服務。

<div class=" ">


> [!NOTE]  
> 針對 Windows Server 2012 和 Windows Server 2012 R2，Add-windowsfeature Cmdlet 已由 Install Cmdlet 取代。 如需詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=392274">安裝程式</A>。



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
<td><p>Web 服務器（IIS）</p></td>
<td><p>網頁伺服器</p></td>
</tr>
<tr class="even">
<td><p>常見的 HTTP 功能</p></td>
<td><p>預設檔</p></td>
</tr>
<tr class="odd">
<td><p>常見的 HTTP 功能</p></td>
<td><p>瀏覽目錄</p></td>
</tr>
<tr class="even">
<td><p>常見的 HTTP 功能</p></td>
<td><p>HTTP 錯誤</p></td>
</tr>
<tr class="odd">
<td><p>常見的 HTTP 功能</p></td>
<td><p>靜態內容</p></td>
</tr>
<tr class="even">
<td><p>常見的 HTTP 功能</p></td>
<td><p>HTTP 重新導向</p></td>
</tr>
<tr class="odd">
<td><p>健康與診斷</p></td>
<td><p>HTTP 記錄</p></td>
</tr>
<tr class="even">
<td><p>健康與診斷</p></td>
<td><p>記錄工具</p></td>
</tr>
<tr class="odd">
<td><p>健康與診斷</p></td>
<td><p>要求監視器</p></td>
</tr>
<tr class="even">
<td><p>健康與診斷</p></td>
<td><p>診斷</p></td>
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
<td><p>ISAPI 延伸</p></td>
</tr>
<tr class="even">
<td><p>應用程式開發</p></td>
<td><p>ISAPI 篩選</p></td>
</tr>
<tr class="odd">
<td><p>應用程式開發</p></td>
<td><p>伺服器端包含</p></td>
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
<td><p>IIS 管理腳本與工具</p></td>
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
<td><p>背景智慧傳送服務</p></td>
<td><p>IIS 伺服器延伸</p></td>
</tr>
<tr class="odd">
<td><p>筆跡與手寫服務</p></td>
<td><p>筆跡與手寫服務</p></td>
</tr>
<tr class="even">
<td><p>媒體基礎</p></td>
<td><p>媒體基礎</p></td>
</tr>
<tr class="odd">
<td><p>使用者介面與基礎結構</p></td>
<td><p>圖形管理工具與基礎結構</p></td>
</tr>
<tr class="even">
<td><p>使用者介面與基礎結構</p></td>
<td><p>桌面體驗</p></td>
</tr>
<tr class="odd">
<td><p>使用者介面與基礎結構</p></td>
<td><p>伺服器圖形命令介面</p></td>
</tr>
<tr class="even">
<td><p>Windows 身分識別 Foundation 3。5</p></td>
<td><p>Windows 身分識別 Foundation 3。5</p></td>
</tr>
<tr class="odd">
<td><p>Windows Process Activation Service</p></td>
<td><p>處理模型</p></td>
</tr>
<tr class="even">
<td><p>Windows Process Activation Service</p></td>
<td><p>配置 Api</p></td>
</tr>
</tbody>
</table>


在 Windows Server 2012 和 Windows Server 2012 R2 中，您可以使用 Windows PowerShell 3.0 來安裝 IIS 需求。 使用 Windows PowerShell 3.0 中的 ServerManager 模組，請輸入：

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Windows Server 2012 的新功能是 [來源] 參數，可定義可找到 Windows Server 2012 來源媒體的位置。 媒體可以定義為 DVD 光碟機（例如，D:\Sources\Sxs），或複製媒體檔案的網路共用（例如， \\fileserver\windows2012\sources\Sxs）。



</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的前端集區與 Standard Edition Server 的 IIS 需求](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

