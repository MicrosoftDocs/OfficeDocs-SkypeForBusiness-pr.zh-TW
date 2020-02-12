---
title: 商務用 Skype Server 2019 的系統需求
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: 摘要：使用本主題準備商務用 Skype Server 2019 伺服器及網域基礎結構。 硬體、作業系統、資料庫、軟體、所有系統需求與建議，以及憑證 DNS、檔案共用及 Active Directory 資訊，都在這裡協助確保您的伺服器伺服器陣列已成功安裝及部署。
ms.openlocfilehash: fbfb66d24b3e3fbc07ac5fa798b372cc1bf4a268
ms.sourcegitcommit: 5e2dc3430e63bc0a17b87a63fa36ac93d96d8134
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41889372"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的系統需求
 
**摘要：** 使用本主題準備安裝商務用 Skype Server 2019。 這裡涵蓋硬體、OS、軟體、資料庫、憑證、使用中的 Diretory、DNS 及 fileshares。 我們將在此處提供所有系統需求與建議，以協助確保您的伺服器群安裝成功並部署。
  
您可能會在開始部署商務用 Skype Server 2019 之前進行一些準備。 本文將逐步引導您規劃下列各項：
  
- [硬體](system-requirements.md#Hardware)
  
- [作業系統](system-requirements.md#OS)
  
- [軟體](system-requirements.md#Software)

- [後端 SQL 資料庫](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [網功能變數名稱稱系統（DNS）](system-requirements.md#DNS)
  
- [證書](system-requirements.md#Certs)
  
- [檔案共用](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的硬體
<a name="Hardware"> </a>

當您的拓撲向下（如果您不是，請參閱[商務用 Skype Server 2019 主題的拓撲結構基礎](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)），現在就可以思考伺服器的情況。 商務用 Skype Server 2019 伺服器需要64位的硬體。 我們的硬體建議如下。 這些不是要求，而是會反映最佳效能所需的需求。 我們有容量規劃檔，可根據您的情況，協助判斷您是否需要更多。
  
標準版伺服器的建議硬體：

|**硬體元件**|**採用**|
|:-----|:-----|
|CPU  <br/> |英特爾至強 E5-2673 v3 雙處理器、6核、2.4 兆赫（GHz）或更高版本。  <br/> 商務用 Skype Server 2019 角色不支援 Intel 安騰處理器。  <br/> |
|儲存體  <br/> |32千百萬位元組（GB）。  <br/> |
|光碟  <br/> |兩側  <br/> •8個或以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間（使用 RAID 1 和6的兩個磁片）。  <br/> 或  <br/> •固態硬碟（SSDs）能夠提供與 8 10000 RPM 機械磁片磁碟機相同的可用空間和類似的效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡、1 Gbps 或更新版本（2個網路介面卡可用，但必須使用單一 MAC 位址和單一 IP 位址進行分組）。  <br/> 前端伺服器、後端伺服器和標準版伺服器**不**支援雙或多穴設定。 <br/> 只要客戶不會向作業系統公開，而且是用來監視及管理伺服器硬體，您就可以有帶外管理系統，例如 DRAC 或 ILO。 這個案例不構成多穴伺服器，而且受到支援。  <br/> |


適用于前端伺服器和後端伺服器的建議硬體：
  
|**硬體元件**|**採用**|
|:-----|:-----|
|CPU  <br/> |英特爾至強 E5-2673 v3 雙處理器、6核、2.4 兆赫（GHz）或更高版本。 <br/> 商務用 Skype Server 2019 角色不支援 Intel 安騰處理器。  <br/> |
|儲存體  <br/> |64千百萬位元組（GB）。  <br/> |
|光碟  <br/> |兩側  <br/> •8個或以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間（使用 RAID 1 和6的兩個磁片）。  <br/> 或  <br/> •固態硬碟（SSDs）能夠提供與 8 10000 RPM 機械磁片磁碟機相同的可用空間和類似的效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡、1 Gbps 或更新版本（2個網路介面卡可用，但必須使用單一 MAC 位址和單一 IP 位址進行分組）。  <br/> 前端伺服器、後端伺服器和標準版伺服器**不**支援雙或多穴設定。 <br/> 只要客戶不會向作業系統公開，而且是用來監視及管理伺服器硬體，您就可以有帶外管理系統，例如 DRAC 或 ILO。 這個案例不構成多穴伺服器，而且受到支援。  <br/> |
   
適用于 Edge 伺服器、獨立轉送伺服器和控制器的建議硬體：
  
|**硬體元件**|**採用**|
|:-----|:-----|
|CPU  <br/> |英特爾至強 E5-2673 v3 雙處理器、6核、2.4 兆赫（GHz）或更高版本。  <br/> 商務用 Skype Server 2019 角色不支援 Intel 安騰處理器。  <br/> |
|儲存體  <br/> |32 gb。  <br/> |
|光碟  <br/> |兩側  <br/> •4個以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間（磁片應該是 2x RAID 1 設定）。  <br/> 或  <br/> •固態硬碟（SSDs）能夠提供與 4 10000 RPM 機械磁片磁碟機相同的可用空間和類似的效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡、1 Gbps 或更新版本（2個網路介面卡可用，但必須使用單一 MAC 位址和單一 IP 位址進行分組）。  <br/> 對於視頻交互操作伺服器和控制器，**不**支援雙或多穴設定。 <br/> Edge 伺服器需要兩個雙埠網路介面卡、1 Gbps 或更高（或兩個成對式網路介面卡）的網路介面，每個配對都是以單一 MAC 位址與單一 IP 位址組成兩個組。  <br/> 在獨立的轉送伺服器上，安裝其他網路介面卡（Nic）來允許設定特定 PSTN IP 位址的支援。  <br/> |


> [!NOTE]
> 無論伺服器角色為何，我們也建議針對商務用 Skype Server 2019 執行下列硬體設定（視您購買的硬體品牌而定，請參閱製造商檔以瞭解詳細資訊）：
> - BIOS config-應該設定成從 NUMA 開始。
> - 啟用超執行緒。
> - [RSS 佇列] 設定應設定為 [8 個佇列]。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的作業系統
<a name="OS"> </a>

當您有適當的硬體之後，您將需要安裝作業系統（OS），才能讓您安裝並成功使用商務用 Skype Server 2019。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
此處所列作業系統以外的任何專案將無法正常運作;請不要嘗試安裝商務用 Skype Server 2019。 例如，[伺服器核心] 選項並未列出，因此不受支援。  注意： Lync Server 2013 不支援 OS 就地升級。  您必須部署個別的 [池]，並將使用者遷移到具有不同 OS 的新池。

> [!NOTE]
> 
> 如果您在 Windows Server 2019 電腦上安裝 Windows 系統管理中心2019，系統會提示您輸入偵聽埠。 您可以在 liklihood 中選擇埠443，但如果該電腦上已安裝商務用 Skype Server 2019，或想要安裝商務用 Skype Server 2019，則您必須選擇不同的埠號碼。
> 
>為什麼如此？ 如果 Windows 系統管理中心2019是在埠443上執行，您將無法使用商務用 Skype 控制台連線至伺服器（也就是您無法連線至在伺服器上執行的任何內部 web 服務（通訊錄 Web 服務）。、自動探索服務、WebTicket 服務等）。  事實上，您將無法連線到任何內部 Web 服務 URL。 如有需要，請選擇不同的埠，或者想要將 Windows 系統管理中心2019放在使用商務用 Skype Server 2019 的伺服器上。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>在商務用 Skype Server 2019 部署之前必須安裝的軟體
<a name="Software"> </a>

在任何執行商務用 Skype Server 2019 的伺服器，都需要安裝或設定一些事項。 如下所示，後面接著特定伺服器角色的其他需求。

> [!IMPORTANT]
> 商務用 Skype 2019 支援 .Net Framework 4.8。 
  
 **所有伺服器：**
  
|**軟體/角色**|**詳細資料**|
|:-----|:-----|
|Windows PowerShell 3。0  <br/> |所有商務用 Skype 伺服器伺服器都需要安裝 Windows PowerShell 3.0。  <br/> •此預設應該與 Windows Server 2016 一起安裝。<br/> |
|Microsoft .NET Framework  <br/> |WCF 服務是以 Windows 功能安裝的**功能**，在 [**伺服器管理員**] 底下，最初不需要下載。 <br/> •您必須確認安裝此功能時，或者如果已安裝此功能，且您正在進行檢查，否則也會檢查並安裝**HTTP 啟用**選項，如下所示： <br/> ![螢幕擷取畫面顯示 .NET Framework 4.5 功能下的 HTTP 啟用選項。](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> 如果您有額外的快顯說明，請不要擔心需要安裝一些其他事項，才能安裝 HTTP 啟用。 這是正常的，按一下 [確定]，然後移至前面。 如果您沒有看到此快顯畫面，您可以假設這些專案已經安裝並繼續進行。  <br/> 安裝 Windows Server 2016 時，通常會安裝 Microsoft .NET Framework。 不過，商務用 Skype Server 需要 Microsoft .NET Framework 4.7 或4.8，因此您可能需要更新它。 您可以在[這裡](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)找到更新<br/> |
|媒體基礎  <br/> |針對 Windows Server 2016，Windows Media 格式設定執行時間會與 Microsoft 媒體基礎一起安裝。  <br/> 所有適用于會議的前端伺服器和標準版伺服器，都需要 Windows Media 格式執行時間來執行 Windows Media 音訊（.wma）檔案，這些檔案是通話駐留、宣告及回應群組應用程式，可供您使用通知和音樂進行播放。  <br/> |
|Windows 身分識別基礎  <br/> |我們需要 Windows 身分識別基礎3.5，以支援商務用 Skype Server 2019 的伺服器對伺服器驗證案例。  <br/> •如果您是 Windows Server 2016，就不需要下載任何內容。 開啟 [**伺服器管理員**]，然後移至 [**新增角色及功能] 嚮導**。 **Windows 身分識別基礎 3.5**列在 [**功能**] 區段底下。 如果已選取，您就大功告成了。 否則選取它，然後按一下 **[下一步]** 以移至 [**安裝**] 按鈕。 <br/> |
|遠端伺服器管理工具  <br/> |角色管理工具： AD DS 和 AD LDS 工具  <br/> |
   
 **前端伺服器與標準版伺服器也需要：**
  
|**軟體/角色**|**詳細資料**|
|:-----|:-----|
|網際網路資訊服務（IIS）  <br/> |在所有前端伺服器以及所有標準版伺服器上，都需要有 IIS，且已選取下列模組：  <br/> •常見的 HTTP 功能： [預設檔]、[HTTP 錯誤]、[靜態內容]  <br/> •健康與診斷： HTTP 記錄、記錄工具、追蹤  <br/> •效能：靜態內容壓縮，動態內容壓縮  <br/> •安全性：要求篩選、用戶端憑證對應驗證、Windows 驗證  <br/> •應用程式開發： .NET 擴充性3.5、.NET 擴充性4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 延伸、ISAPI 篩選  <br/> •管理工具： IIS 管理主控台、IIS 管理腳本與工具  <br/> 請注意，您也需要匿名存取，但您在安裝 IIS 時會收到，因此您沒有在清單中選取它的位置。  <br/> |
|Windows Media 格式執行時間  <br/> | 若是 Windows Server 2016，您將需要在**伺服器管理員**中安裝**媒體基礎**功能。 您實際可以啟動商務用 Skype Server 2019 安裝，但不需要這麼做，但在商務用 Skype Server 2019 安裝繼續進行之前，系統會提示您安裝它，然後重新開機伺服器。 最好提前完成。 <br/> |
|Silverlight  <br/> |您可以在[此](https://www.microsoft.com/silverlight/)安裝最新版本的 Silverlight。  <br/> |
   
為了協助您完成，您可以執行以下範例 PowerShell 腳本來自動化此程式：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **董事也需要：**
  
IIS 中，已選取下列模組：
  
- 常見的 HTTP 功能
    
  - 預設檔
    
  - HTTP 錯誤
    
  - 靜態內容
    
- 健康與診斷
    
  - HTTP 記錄
    
  - 記錄工具
    
  - 診斷
    
- 提高
    
  - 靜態內容壓縮
    
- 安全性
    
  - 要求篩選
    
  - 用戶端憑證對應驗證
    
  - Windows 驗證
    
- 應用程式開發
    
  - .NET 擴充性3。5
    
  - .NET 擴充性4。5
    
  - ASP.NET 3。5
    
  - ASP.NET 4。5
    
  - ISAPI 延伸
    
  - ISAPI 篩選
    
（如果您想知道，它是與前端伺服器和標準版伺服器相同的模組集，而且動態內容壓縮與管理工具會保持不變。）
  
另外，以下是一些 PowerShell 程式碼：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>可搭配商務用 Skype Server 2019 使用的後端資料庫
<a name="DBs"> </a>

安裝商務用 Skype Server 2019 標準版時，您會擁有 SQL Server 2016 Express （64位版本）。

商務用 Skype Server 2019 企業版會需要完整的 SQL Server，如下所示（只有64位版本; 請不要使用32位版本）：
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 （64位版本），而且您必須使用最新的更新執行。  <br/> |Microsoft SQL Server 2017 （64位版本），而且您必須使用最新的更新執行。  <br/> |
Microsoft SQL Server 2016 （64位版本），而且您必須使用最新的更新執行。|
 |

如果您沒有看到想要使用的 SQL Server 版本，則無法使用。
  
> [!NOTE]
> 您也需要安裝監視伺服器角色的 SQL Server Reporting Services。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL 群集及 SQL Alwayson

支援使用商務用 Skype Server 2019 的 SQL 群集。 如果您想要設定 SQL 群集，請在 SQL Server 中完成。
  
請確定您有支援 SQL 群集的主動/被動設定。 不要與任何其他的 SQL 實例共用被動節點。
  
您可以針對容錯移轉叢集進行下列作業：
  
雙節點：
  
- Microsoft SQL Server 2019 標準版（64位版本），我們建議使用最新的 service pack 執行。
- Microsoft SQL Server 2017 標準版（64位版本），我們建議使用最新的 service pack 執行。
- Microsoft SQL Server 2016 標準版（64位版本），我們建議使用最新的 service pack 執行。

十六節點：
  
- Microsoft SQL Server 2019 Enterprise （64位版本），我們建議使用最新的 service pack 執行。
- Microsoft SQL Server 2017 Enterprise （64位版本），我們建議使用最新的 service pack 執行。
- Microsoft SQL Server 2016 Enterprise （64位版本），我們建議使用最新的 service pack 執行。

支援 SQL Alwayson，您可以在[商務用 Skype server 2019 的後端伺服器高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)中深入閱讀。
  

###  <a name="additional-server-installation-recommendations"></a>其他伺服器安裝建議：
  
請勿安裝任何 Microsoft 網際網路安全性與加速（ISA） Server 用戶端軟體，或任何其他 Winsock 層次服務提供者（LSP）軟體（這裡將提供任何協力廠商的防火牆或防病毒網路檢查軟體）您的任何前端伺服器或獨立的轉送伺服器。 在安裝軟體時，會出現較差的媒體流量效能。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

雖然伺服器和服務的許多配置資料都儲存在商務用 Skype Server 2019 中央管理儲存體中，但仍有一些專案儲存在 Active Directory 中：
  
|**Active Directory 物件**|**物件類型**|
|:-----|:-----|
|架構延伸  <br/> |使用者物件延伸  <br/> |
||商務用 Skype Server 2015 和 Lync Server 2013 延伸，以維持與先前支援版本的向後相容性  <br/> |
|資料  <br/> |使用者 SIP URI 和其他使用者設定  <br/> |
||應用程式的連絡人物件（例如回應群組應用程式和會議助理應用程式）  <br/> |
||針對向後相容性發佈的資料  <br/> |
||中央管理儲存體的服務控制點（SCP）  <br/> |
||Kerberos 驗證帳戶（選擇性電腦物件）  <br/> |
   
### <a name="os-for-domain-controllers"></a>網網域控制站的作業系統

您可以使用下列網網域控制站作業系統：
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
您部署商務用 Skype Server 2019 的任何網域的網域功能層級，以及您部署商務用 Skype Server 2019 的任何目錄林功能層級，都必須是下列其中一項：
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
在這些環境中，您可以有唯讀的網網域控制站嗎？ 只要有可用的可寫入網網域控制站，就能確定。
  
請務必瞭解商務用 Skype Server 2019 不支援單一標示的網域。 他們是什麼？ 如果您有一個標示為 [contoso. 當地] 的根網域，那將會有任何問題。 如果您的根網域剛剛命名為 local，即表示不起作用，因此結果不支援此功能。 我們已[在這個知識庫文章中](https://support.microsoft.com/kb/300684/)撰寫了更多相關資訊。
  
商務用 Skype Server 2019 也不支援重新命名網域。 如果您確實需要重新命名網域，您必須卸載商務用 Skype Server 2019、執行網域重新命名，然後重新安裝商務用 Skype Server 2019。
  
最後，您可能會使用鎖定的 AD DS 環境來處理網域，這樣就可以了。 我們有更多關於如何在部署檔中將商務用 Skype Server 2019 部署到鎖定的 AD DS 環境的資訊。
  
### <a name="ad-topologies"></a>廣告拓朴

商務用 Skype Server 2019 支援的拓撲為：
  
- 單一目錄林與單一網域
    
- 具有單一樹狀結構和多個網域的單一目錄林
    
- 具有多個樹和不連續命名空間的單一目錄林
    
- 中央目錄林拓撲中的多個林
    
- 資原始目錄林拓朴中的多個目錄林
    
- 在商務用 Skype 資原始目錄林拓朴中有多個森林與 Exchange Online
    
- 包含商務用 Skype Online 和 Azure Active Directory Connect 的資原始目錄林拓撲中的多個林
    
我們有一些圖表和描述，可協助您判斷您的環境中有何種拓撲，或在安裝商務用 Skype Server 2019 之前，您可能需要進行的設定。 若要保持簡單，我們也會包含一個按鍵：
  
![是用於商務用 Skype 拓撲圖之圖示的索引鍵](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>單一目錄林與單一網域

![含有單一網域的 Active Directory 單一目錄林圖表](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不會比這個更簡單;它是單一網域林，通用拓撲。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具有單一樹狀結構和多個網域的單一目錄林

![單一目錄林、單一樹狀結構及 mutiple 網域圖表](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
這個圖表會再次顯示單一目錄林，但它也有一個或多個子網域（在這個特定範例中，有三個）。 因此，建立使用者的網域可能與部署到的網域商務用 Skype Server 2019 不同。 為什麼要擔心這個問題？ 請務必記住，當您部署商務用 Skype Server 前端池時，該池中的所有伺服器必須在單一網域中。 您可以透過商務用 Skype 伺服器支援 Windows 通用系統管理員群組，以進行跨網域的管理。
  
在上述圖表中，您可以看到一個網域中的使用者能夠從同一個網域或不同的網域存取商務用 Skype Server pool，即使這些使用者位於子域中也一樣。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具有多個樹和不連續命名空間的單一目錄林

![單一目錄林、多個樹和不連續的命名空間圖表](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
您可能會有類似此圖表的拓撲，您有一個目錄林，但在該樹林中是多個網域，有個別的 AD 命名空間。 在這種情況下，此圖表是一個很好的圖例，因為它包含可存取商務用 Skype Server 2019 的三個不同網域中的使用者。 實線表示他們要存取自己網域中的商務用 Skype 伺服器池，而虛線則表示它們將會在不同的樹狀結構中完全移至池中。
  
如您所見，同一個網域中的使用者、相同的樹狀結構，或者甚至是不同的樹狀結構，都能順利存取池。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央目錄林拓撲中的多個林

![中央目錄林拓撲圖中的多個目錄林](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
商務用 Skype Server 2019 支援在中央林拓撲中設定多個林。 如果您不確定這是您所擁有的，拓撲結構中的中央目錄林會使用其中的物件來代表其他林中的使用者，並為樹林中的任何使用者承載使用者帳戶。
  
這會如何運作？ 目錄同步處理產品（例如 Forefront Identity Manager 或 FIM）會管理貴組織的使用者帳戶。 當您在林中建立或刪除帳戶時，該變更會同步處理到中央林中的對應連絡人。
  
顯然，如果您的廣告基礎結構已就緒，移至此拓撲可能並不容易，但如果您已經存在，或仍在規劃您的林基礎結構，這可能是一個不錯的選擇。 您可以將商務用 Skype Server 2019 部署集中在單一目錄林中，使用者可以在任何林中搜尋、溝通及查看其他使用者的目前狀態。 所有使用者連絡人更新都會自動使用同步處理軟體來處理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>商務用 Skype 資原始目錄林拓朴中的多個目錄林
<a name="BKMK_multipleforestopology"> </a>

![資原始目錄林拓撲圖中的多個目錄林](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
也支援資源林拓朴;這是林專用於執行伺服器應用程式的位置，例如 Microsoft Exchange Server 和商務用 Skype Server 2019。 此資原始目錄林也會託管作用中使用者物件的同步表示，但沒有登入的使用者帳戶。 因此，資原始目錄林是使用者物件所駐留之其他目錄林的共用服務環境，而且與資原始目錄林有一個林層級的信任關係。
  
請注意，Exchange Server 可以部署在與商務用 Skype 伺服器相同的資源林中，或在不同的林中。
  
若要在這種類型的拓朴中部署商務用 Skype Server 2019，您可以在資原始目錄林中為使用者林中的每個使用者帳戶建立一個停用的使用者物件（如果 Microsoft Exchange Server 已經在環境中，這可能會為您完成）。 接著，您需要目錄同步處理工具（例如 Forefront Identity Manager 或 FIM），以透過其生命週期管理使用者帳戶。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>在商務用 Skype 資原始目錄林拓朴中有多個森林與 Exchange Online
<a name="BKMK_multipleforestopology"> </a>

這個拓朴與[商務用 Skype 資原始目錄林拓朴中多個林內](system-requirements.md#BKMK_multipleforestopology)所述的拓撲類似。
  
在此拓撲中，有一個或多個使用者目錄林，而商務用 Skype 伺服器則是在專用的資原始目錄林中部署。 Exchange Server 可以在內部部署的同一資原始目錄林中或不同的林中，且已設定為與 Exchange Online 混合式，或者電子郵件服務可能會以 Exchange Online 專為內部部署帳戶提供。 沒有適用于此拓朴的圖表。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>包含商務用 Skype Online 和 Azure Active Directory Connect 的資原始目錄林拓撲中的多個林
<a name="BKMK_multipleforestopology"> </a>

![顯示兩個 AD 目錄林、一個使用者目錄林和一個資原始目錄林。 兩個目錄林具有信任關係。 它們會與 Office 365 （使用 Azure AD Connect）同步處理。 所有使用者都可透過 Office 365 啟用商務用 Skype。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
在這個案例中，有多個目錄林內部部署，有一個資原始目錄林拓撲。 Active Directory 目錄林之間有完全信任關係。 Azure Active Directory Connect 工具是用來同步處理內部部署使用者目錄林與 Office 365 之間的帳戶。
  
 組織也有 Office 365，並使用[Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)將其內部部署帳戶與 Office 365 同步處理。 啟用商務用 Skype 的使用者可透過 Office 365 和商務用 Skype Online 來啟用。 商務用 Skype Server 未部署于內部部署。
  
單一登入驗證是由位於使用者林中的 Active Directory 同盟服務群所提供。
  
在這種情況下，支援部署 Exchange 內部部署、Exchange Online、混合式 Exchange 解決方案，或是根本不部署 Exchange。 （圖表只會顯示 Exchange 內部部署，但也完全支援其他 Exchange 解決方案）。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>使用混合式商務用 Skype 的資原始目錄林拓撲結構中的多個目錄林
<a name="BKMK_multipleforestopology"> </a>

在此案例中，有一個或多個內部部署使用者目錄林，且商務用 Skype 是在專用的資原始目錄林中部署，且是針對商務用 Skype Online 設定混合式模式。 Exchange Server 可以在同一資原始目錄林或不同的林中部署內部部署，而且可以針對 Exchange Online 進行混合式設定。 或者，電子郵件服務可能會以 Exchange Online 專為內部部署帳戶提供。
  
如需詳細資訊，請參閱[設定混合式商務用 Skype 的多林環境](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>網功能變數名稱稱系統（DNS）
<a name="DNS"> </a>

商務用 Skype Server 2019 需要 DNS，原因如下：
  
- DNS 可讓商務用 Skype Server 2019 探索內部伺服器或池，以便進行伺服器對伺服器的通訊。
    
- DNS 可讓用戶端電腦探索要用於 SIP 交易的前端池或標準版伺服器。
    
- 它會將會議的簡單 Url 與主持這些會議的伺服器進行關聯。
    
- DNS 允許外部使用者與用戶端電腦連線到您的邊緣伺服器，或 HTTP 反向 proxy （適用于立即訊息（IM）或會議）。
    
- 它可讓未登入的整合通訊（UC）裝置探索可執行裝置更新 web 服務的前端池或標準版伺服器來取得更新及傳送記錄。
    
- 使用 DNS 可讓行動用戶端自動探索 web 服務資源，而不需要使用者在其裝置設定中手動輸入 Url。
    
- 它是在 DNS 負載平衡中使用。
    
請務必注意，商務用 Skype Server 2019 不支援國際化功能變數名稱（IDNs）。
  
切記，請務必記住，DNS 中的任何名稱都與商務用 Skype Server 2019 所使用的任何伺服器上設定的電腦名稱稱相同。 具體說來，在環境中不能有任何短名稱，且必須有 [拓撲建立器] 的 Fqdn。
  
這看起來對已加入網域的任何電腦而言都是合乎邏輯的，但如果您有沒有加入網域的邊緣伺服器，則它可能會有一個短名稱的預設值，沒有網域尾碼。 在 DNS 或邊緣伺服器上，或在任何商務用 Skype Server 2019 server 或 pool 中，請確定這種情況不是如此。
  
絕對不要使用 Unicode 字元或底線。 外部 DNS 和公用憑證授權單位支援標準字元（A-z、a-z、0-9 及連字號），因此您需要記住證書中的 SN.EXE，所以請務必記住，如果您要命名，您將會有許多問題。從開頭開始，請記住這一點。
  
如需進一步瞭解網路的 DNS 需求，請參閱我們規劃檔的 [[網路](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)] 區段。
  
## <a name="certificates"></a>證書
<a name="Certs"> </a>

在部署前，您可以執行的其中一個最重要的動作就是確定您的憑證有序。 商務用 Skype Server 2019 需要傳輸層安全性（TLS）和相互傳輸層安全性（MTLS）連線的公開金鑰基礎結構（PKI）。 一般來說，若要以標準化的方式安全地通訊，商務用 Skype Server 會使用由憑證授權單位（Ca）頒發的憑證。
  
以下是商務用 Skype Server 2019 使用憑證的一些事項：
  
- 用戶端與伺服器之間的 TLS 連接
    
- 伺服器之間的 MTLS 連線
    
- 使用合作夥伴自動 DNS 探索的同盟
    
- 立即訊息（IM）的遠端使用者存取權
    
- 外部使用者存取音訊/視頻（AV）會話、應用程式共用和會議
    
- 與 web 應用程式和 Outlook Web Access （OWA）交談
    
因此，必須擁有認證規劃。 現在，讓我們來看看要求證書時必須牢記的一些事項清單：
  
- 所有伺服器憑證都必須支援伺服器授權（伺服器 EKU）。
    
- 所有伺服器憑證都必須包含 CRL 發佈點（CDP）。
    
- 所有憑證都必須使用作業系統支援的簽名演算法進行簽署。 商務用 Skype Server 2019 支援 SHA-1 和 SHA-1 組成的摘要大小（224、256、384和512位），並符合或超過作業系統需求。
    
- 運行商務用 Skype Server 2019 的內部伺服器支援自動註冊。
    
- 商務用 Skype Server 2019 Edge 伺服器不支援自動註冊。
    
> [!NOTE]
> 不支援使用 RSASSA-PSS 簽章演算法，而且可能會導致登入和來電轉接問題等錯誤，以及其他問題。 
  
- 支援1024、2048和4096的加密金鑰長度。 建議使用2048和更大的金鑰長度。
    
- 預設摘要（即雜湊簽章）演算法是 RSA。 也支援 ECDH_P256、ECDH_P384 及 ECDH_P521 演算法。
    
這就是您要考慮的一點，而且從 CA 申請憑證的方式有很多。 我們將在下方提供一些進一步的指導方針，讓您的規劃盡可能順利進行。
  
### <a name="certificates-for-your-internal-servers"></a>內部伺服器的憑證

您將需要大多數內部伺服器的憑證，而且最可能的是，您可以從內部 CA 取得它們（這是位於網域中的 CA）。 如果您想要的話，您可以從外部 CA （位於網際網路的一級）要求這些憑證。 如果您不知道應該移至哪個公用 CA，您可以查看 [[整合通訊憑證合作夥伴](/SkypeForBusiness/certification/services-ssl)] 清單。
  
當商務用 Skype Server 2019 與其他應用程式和伺服器通訊時（例如 Microsoft Exchange Server），您也會需要證書。 這顯然會需要成為這些其他 app 和伺服器能夠以受支援的方式來使用的憑證。 商務用 Skype Server 2019 和其他 Microsoft 產品都支援「開啟授權（OAuth）」通訊協定，以進行伺服器對伺服器驗證和授權。 如果您對此感興趣，我們會針對 OAuth 和商務用 Skype Server 2019 進行額外的規劃文章。
  
商務用 Skype Server 2019 也包含使用 SHA-256 加密雜湊函數簽署（不需要）憑證的支援。 若要使用 SHA-256 支援外部存取，外部憑證必須由使用 SHA-256 的公用 CA 頒發。
  
為了讓事情保持簡單明瞭，我們已將標準版伺服器、前端池及其他角色的憑證需求放在下清單格中，並在範例中使用虛構的 contoso.com （您可能會用到其他東西）。您的環境）。 這些都是所有標準的 web 伺服器憑證，其中包含無法匯出的私用金鑰。 需要注意的一些其他事項：
  
- 當您使用 [憑證] 嚮導來申請證書時，系統會自動設定 [伺服器增強型金鑰用法（EKU）]。
    
- 每個證書易記名稱在電腦存放區中都必須是唯一的。
    
- 根據下面的範例名稱，如果您已在 DNS 中設定 sipinternal.contoso.com 或 sipexternal.contoso.com，則需要將它們新增至證書的消費者備用名稱（SAN）。
    
標準版伺服器的憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|**批註**|
|:-----|:-----|:-----|:-----|:-----|
|設置  <br/> |池的 FQDN  <br/> |伺服器的 [池] 和 [FQDN] FQDN  <br/> 如果您有多個 SIP 網域，且已啟用自動用戶端設定，證書嚮導會偵測並新增每個支援的 SIP 網域 Fqdn。  <br/> 如果此池是用戶端的自動登入伺服器，且在群組原則中需要嚴格的網域名稱系統（DNS）相符，您也需要 sipdomain （適用于您擁有的每個 SIP 網域）中的專案。  <br/> |SN = se01;SAN = se01  <br/> 如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com  <br/> |在標準版伺服器上，伺服器 FQDN 與 [池 FQDN] 相同。  <br/> 此嚮導會偵測您在安裝期間指定的任何 SIP 網域，並自動將其新增到 [使用中] 替換名稱。  <br/> 您也可以使用此憑證進行伺服器對伺服器驗證。  <br/> |
|網頁內部  <br/> |伺服器的 FQDN  <br/> |下列各項：  <br/> •內部網頁 FQDN （與伺服器的 FQDN 相同）  <br/> 還  <br/> •符合簡單的 Url  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = se01;SAN = se01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com  <br/> 使用萬用字元憑證：  <br/> SN = se01;SAN = se01;SAN =\*. contoso.com  <br/> |您無法在拓撲建立器中覆寫內部網頁 FQDN。  <br/> 如果您有多個符合簡單的 Url，您必須將它們全部包含為 SANs。  <br/> 簡單的 URL 專案支援萬用字元專案。  <br/> |
|網頁外部  <br/> |伺服器的 FQDN  <br/> |下列各項：  <br/> •外部 web FQDN  <br/> 還  <br/> •撥入式簡易 URL  <br/> •符合每個 SIP 網域的簡單 Url  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = se01;SAN = webcon01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com  <br/> 使用萬用字元憑證：  <br/> SN = se01;SAN = webcon01;SAN =\*. contoso.com  <br/> |如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。  <br/> 簡單的 URL 專案支援萬用字元專案。  <br/> |
   
前端池中的前端伺服器憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|**批註**|
|:-----|:-----|:-----|:-----|:-----|
|設置  <br/> |池的 FQDN  <br/> |伺服器的 [池] 和 [FQDN] FQDN  <br/> 如果您有多個 SIP 網域，且已啟用自動用戶端設定，證書嚮導會偵測並新增每個支援的 SIP 網域 Fqdn。  <br/> 如果此池是用戶端的自動登入伺服器，且在群組原則中需要嚴格的網域名稱系統（DNS）相符，您也需要 sipdomain （適用于您擁有的每個 SIP 網域）中的專案。  <br/> |SN = eepool;SAN = eepool;SAN = ee01  <br/> 如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com  <br/> |此嚮導會偵測您在安裝期間指定的任何 SIP 網域，並自動將其新增到 [使用中] 替換名稱。  <br/> 您也可以使用此憑證進行伺服器對伺服器驗證。  <br/> |
|網頁內部  <br/> |池的 FQDN  <br/> |下列各項：  <br/> •內部網頁 FQDN （與伺服器的 FQDN 不同）  <br/> •伺服器 FQDN  <br/> •商務用 Skype 池 FQDN  <br/> 還  <br/> •符合簡單的 Url  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = ee01;SAN = ee01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com  <br/> 使用萬用字元憑證：  <br/> SN = ee01;SAN = ee01;SAN =\*. contoso.com  <br/> |如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。  <br/> 簡單的 URL 專案支援萬用字元專案。  <br/> |
|網頁外部  <br/> |池的 FQDN  <br/> |下列各項：  <br/> •外部 web FQDN  <br/> 還  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = ee01;SAN = webcon01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com  <br/> 使用萬用字元憑證：  <br/> SN = ee01;SAN = webcon01;SAN =\*. contoso.com  <br/> |如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。  <br/> 簡單的 URL 專案支援萬用字元專案。  <br/> |
   
主管的憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|設置  <br/> |主管池  <br/> |主管的 FQDN，控制器池的 FQDN。  <br/> 如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 sipdomain （針對您擁有的每個 SIP 網域）輸入的專案。  <br/> |pool.contoso.com;SAN = dir01  <br/> 如果此主管池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com  <br/> |
|網頁內部  <br/> |伺服器的 FQDN  <br/> |下列各項：  <br/> •內部網頁 FQDN （與伺服器的 FQDN 相同）  <br/> •伺服器 FQDN  <br/> •商務用 Skype 池 FQDN  <br/> 還  <br/> •符合簡單的 Url  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |SN = dir01;SAN = dir01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com  <br/> 使用萬用字元憑證：  <br/> SN = dir01;SAN = dir01 =\*. contoso.com  <br/> |
|網頁外部  <br/> |伺服器的 FQDN  <br/> |下列各項：  <br/> •外部 web FQDN  <br/> 還  <br/> •符合每個 SIP 網域的簡單 Url  <br/> •撥入式簡易 URL  <br/> 或  <br/> •簡單 Url 的萬用字元專案  <br/> |控制器外部 web FQDN 必須與前端池或前端伺服器不同。  <br/> SN = dir01;SAN = directorwebcon01 （contoso .com） SAN = 符合 contoso;SAN = 符合 fabrikam .com;SAN = 撥入. .com  <br/> 使用萬用字元憑證：  <br/> SN = dir01;SAN = directorwebcon01 =\*. contoso.com  <br/> |
   
獨立中繼伺服器的憑證：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|設置  <br/> |池的 FQDN  <br/> |池的 FQDN  <br/> 池成員伺服器的 FQDN  <br/> |SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01  <br/> |
   
Survivable 分支裝置的憑證（特別是適用于商務用 Skype Server 2019 的 Survivable 分支裝置2015）：
  
|**憑證**|**消費者名稱/通用名稱**|**消費者替換名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|設置  <br/> |裝置的 FQDN  <br/> |呼吸.\<sipdomain\> （每個 SIP 網域只需要一個專案）  <br/> |SN = sba01;SAN = sip. .com;SAN = sip. .com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部使用者存取權的憑證（邊緣）

商務用 Skype Server 2019 支援使用**單一公用憑證**來存取和網路會議 Edge 外部介面，加上 a/V 驗證服務，這一切都是透過 Edge 伺服器提供。 您的邊緣內部介面通常會使用內部 CA 所頒發的私人憑證，但如果您想要的話，您也可以使用公用憑證（如果它來自受信任的 CA）。
  
您的反向 proxy （RP）也會使用公用憑證，並使用 HTTP （或更精確地說是 HTTP 上的 TLS），將來自您的 RP 的通訊加密到用戶端，以及 RP 到內部伺服器。
  
### <a name="certificates-for-mobility"></a>行動性憑證

如果您要部署行動裝置，且支援行動用戶端的自動探索，您必須在您的憑證上加入一些其他的主題替換名稱專案，以支援行動用戶端的安全連線。
  
您需要在下列憑證上自動探索的 SAN 名稱：
  
- 主管池
    
- 前端集區
    
- 反向 Proxy
    
這些詳細資訊列在下表中。
  
在這種情況下，您可以進行少量預先規劃，但有時候您已部署商務用 Skype Server 2019，而不想要部署行動，且稍後當您在您的環境中已經有憑證時會出現這種情況。 透過內部 CA 重新頒發它們通常相當簡單，但使用公用 CA 的公用憑證，可能會有更多的 pricy。
  
如果這是您要查看的內容，而且如果您有許多 SIP 網域（這會增加 SAN 的費用），您可以設定您的反向 proxy，將 HTTP 用於初始自動探索服務要求，而不是使用 HTTPS （這是預設值）。配置）。 [行動方案](../../SfbServer/plan-your-deployment/mobility.md)文章的規劃有更多相關資訊。
  
主管池與前端池的憑證需求：
  
|**描述**|**SAN 專案**|
|:-----|:-----|
|內部自動探索服務 URL  <br/> |SAN = lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自動探索服務 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
您也可以使用 SAN =\*。\<sipdomain\>
  
反向 Proxy （公用 CA）證書需求：
  
|**描述**|**SAN 專案**|
|:-----|:-----|
|外部自動探索服務 URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
這個 SAN 需要指派給您在反向 proxy 上指派給 SSL 偵聽程式的憑證。
  
> [!NOTE]
> 您的反向 proxy 偵聽程式將會有適用于您外部 Web 服務 URL 的 SANs。 例如，如果您已部署 Director （選擇性），一些範例就會是 SAN = skypewebextpool01 和 dirwebexternal.contoso.com。 
  
## <a name="file-share"></a>檔案共用
<a name="Fileshare"> </a>

商務用 Skype Server 2019 可以使用相同的檔案共用來儲存所有檔案。 您必須牢記下列事項：
  
- 檔案共用必須是直接附加的儲存空間（DAS）或儲存區域網路（SAN），這包括分散式檔案系統（DFS），以及檔案存放區的獨立磁碟容錯陣列（RAID）。 如需 Windows Server 2012 DFS 的進一步閱讀，請參閱[此 DFS 頁面](https://technet.microsoft.com/library/jj127250.aspx)。
    
- 我們建議使用共用的群集來共用檔案。 如果您已經在使用其中一個，就應該群集 Windows Server 2012 或更高版本

> [!Note]
> **為什麼是最新的 Windows？** 較舊的版本可能不具備啟用所有功能的適當許可權。 您可以使用 [群集管理員] 來建立檔案共用。 如需詳細資訊，請參閱此支援文章[如何在群集上建立檔案共用](https://support.microsoft.com/help/224967)。
    
> [!CAUTION]
> 您應該知道，不支援使用 network 附加儲存空間（NAS）作為檔案共用，所以請使用上述其中一個選項。 這項支援限制是由 NAS 裝置的變數設計所造成，必須針對存取裝置共用檔案系統的 Windows Server 電腦提供檔案系統適應性。
  








