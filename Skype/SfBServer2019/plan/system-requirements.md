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
description: 摘要：使用本主題準備商務用 Skype Server 2019 伺服器及網域基礎結構。 在這裡，硬體、作業系統、資料庫、軟體、所有系統需求與建議，以及憑證 DNS、檔案共用和 Active Directory 資訊，都是為了協助確保成功安裝及部署您的伺服器陣列。
ms.openlocfilehash: 8bb12fa9f5d0cd0144604f21d311c50f7f63b0f4
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232374"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的系統需求
 
**摘要：** 使用本主題準備安裝商務用 Skype Server 2019。 在此涵蓋硬體、OS、軟體、資料庫、憑證、使用中 Diretory、DNS 及 fileshares。 您可以在這裡獲得所有的系統需求與建議，以協助確保成功安裝及部署您的伺服器陣列。
  
如您所料，您可以在開始部署商務用 Skype Server 2019 之前做一些準備工作。 本文將引導您規劃下列各項：
  
- [硬體](system-requirements.md#Hardware)
  
- [作業系統](system-requirements.md#OS)
  
- [軟體](system-requirements.md#Software)

- [後端 SQL 資料庫](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Domain Name System (DNS)](system-requirements.md#DNS)
  
- [憑證](system-requirements.md#Certs)
  
- [檔案共用](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的硬體
<a name="Hardware"> </a>

在您將拓撲重新排列後（如果您不是，您可以查看「[商務用 Skype Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) 」主題的拓撲基礎），請思考伺服器的相關資訊。 商務用 Skype Server 2019 伺服器需要64位硬體。 以下是硬體的建議。 這些不是必要條件，但它們會反映出最佳效能所需的需求。 我們有容量規劃檔，可協助您判斷是否需要超過這種情況，視情況而定。
  
Standard Edition server 的建議硬體：

|**硬體元件**|**建議**|
|:-----|:-----|
|CPU  <br/> |Intel 至強 E5 2673 v3 雙處理器，6核心，2.4 ghz （GHz）或更高版本。  <br/> 商務用 Skype Server 2019 角色不支援 Intel Itanium 處理器。  <br/> |
|記憶體  <br/> |32 gb。  <br/> |
|磁片  <br/> |可  <br/> •8個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間（使用 RAID 1 和6的兩個磁片使用 RAID 10）。  <br/> OR  <br/> •固態硬碟（Ssd）能夠提供與 8 10000 RPM 機械磁片磁碟機相同的可用空間及類似效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡、1 Gbps 或更高（2個網路介面卡可使用，但必須以單一 MAC 位址和單一 IP 位址進行分組）。  <br/> 前端伺服器、後端伺服器及 Standard Edition server**不**支援雙重或多穴設定。 <br/> 只要未對作業系統公開，而且正用來監視和管理伺服器硬體，您就可以使用帶外管理系統，例如 DRAC 或 ILO。 此案例不會組成多穴伺服器，而且支援此案例。  <br/> |


前端伺服器及後端伺服器的建議硬體：
  
|**硬體元件**|**建議**|
|:-----|:-----|
|CPU  <br/> |Intel 至強 E5 2673 v3 雙處理器，6核心，2.4 ghz （GHz）或更高版本。 <br/> 商務用 Skype Server 2019 角色不支援 Intel Itanium 處理器。  <br/> |
|記憶體  <br/> |64 gb。  <br/> |
|磁片  <br/> |可  <br/> •8個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間（使用 RAID 1 和6的兩個磁片使用 RAID 10）。  <br/> OR  <br/> •固態硬碟（Ssd）能夠提供與 8 10000 RPM 機械磁片磁碟機相同的可用空間及類似效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡、1 Gbps 或更高（2個網路介面卡可使用，但必須以單一 MAC 位址和單一 IP 位址進行分組）。  <br/> 前端伺服器、後端伺服器及 Standard Edition server**不**支援雙重或多穴設定。 <br/> 只要未對作業系統公開，而且正用來監視和管理伺服器硬體，您就可以使用帶外管理系統，例如 DRAC 或 ILO。 此案例不會組成多穴伺服器，而且支援此案例。  <br/> |
   
Edge Server、獨立轉送伺服器及 Director 的建議硬體：
  
|**硬體元件**|**建議**|
|:-----|:-----|
|CPU  <br/> |Intel 至強 E5 2673 v3 雙處理器，6核心，2.4 ghz （GHz）或更高版本。  <br/> 商務用 Skype Server 2019 角色不支援 Intel Itanium 處理器。  <br/> |
|記憶體  <br/> |32 gb。  <br/> |
|磁片  <br/> |可  <br/> •4個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間（磁片應該是2倍的 RAID 1 設定）。  <br/> OR  <br/> •固態硬碟（Ssd）能夠提供與 4 10000 RPM 機械磁片磁碟機相同的可用空間及類似效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡、1 Gbps 或更高（2個網路介面卡可使用，但必須以單一 MAC 位址和單一 IP 位址進行分組）。  <br/> 視頻 Interop 伺服器及 Director**不**支援雙重或多穴設定。 <br/> Edge server 需要兩個網路介面為雙埠網路介面卡、1 Gbps 或更高（或兩個成對網路介面卡，共四組），每一組都是以單一 MAC 位址和單一 IP 位址組成，共兩對。  <br/> 在獨立的轉送伺服器上，您可以安裝額外的網路介面卡（Nic），以支援設定特定 PSTN IP 位址。  <br/> |


> [!NOTE]
> 不論伺服器角色為何，我們也建議您為商務用 Skype Server 2019 執行下列硬體設定（這可能會因您購買的硬體品牌而異）。請參閱製造商檔中的詳細資訊）：
> - BIOS config-應設定為從 NUMA 開始設定為平面。
> - 啟用超執行緒。
> - [RSS 佇列] 設定應該設定為8個佇列。

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>商務用 Skype Server 2019 的作業系統
<a name="OS"> </a>

準備好硬體之後，您將需要安裝作業系統（OS），讓您安裝及成功使用商務用 Skype Server 2019。
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
任何不是這裡列出的作業系統都無法正常運作;請不要嘗試安裝商務用 Skype Server 2019。 例如，未列出伺服器核心選項，因此不受支援。

> [!NOTE]
> Lync Server 2013 不支援就地升級作業系統。 您必須部署個別的集區，並將使用者遷移至具有不同作業系統的新集區。 集區中的所有伺服器都必須具有相同的 OS 版本。

> [!NOTE]
> 
> 如果您要在 Windows Server 2019 電腦上安裝 Windows 系統管理中心2019，它會提示您輸入要接聽的埠。 有 liklihood 您可以選擇埠443，但是如果該機器上已安裝商務用 Skype Server 2019，或要在其上安裝商務用 Skype Server 2019，則必須選擇不同的埠號碼。
> 
>為何如此？ 如果在埠443上執行 Windows 系統管理中心2019，您將無法使用商務用 Skype 控制台連線至伺服器，也無法連線至伺服器上執行的任何內部 web 服務（通訊錄 Web 服務、自動探索服務、WebTicket 服務等等）。  實際上，您將無法連接至任何內部 Web 服務 URL。 如有需要，請選擇不同的埠，或想要在使用商務用 Skype Server 2019 的伺服器上放入 Windows Admin Center 2019。
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>在商務用 Skype Server 2019 部署之前應安裝的軟體
<a name="Software"> </a>

您需要針對執行商務用 Skype Server 2019 的任何伺服器安裝或設定某些事項。 如下所列，接著提供特定伺服器角色的其他需求。

> [!IMPORTANT]
> 商務用 Skype 2019 支援 .Net Framework 4.8。 
  
 **所有伺服器：**
  
|**軟體/角色**|**詳細資料**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |所有商務用 Skype Server 伺服器都需要安裝 Windows PowerShell 3.0。  <br/> •使用 Windows Server 2016 時，應依預設安裝這種方式。<br/> |
|Microsoft .NET Framework  <br/> |WCF 服務是一種安裝為 Windows 功能的**功能**，在 [**伺服器管理員**] 下，最初不需要下載。 <br/> •您必須確定當您安裝此功能時，或是否已安裝，且您正在進行檢查，也會檢查並安裝**HTTP 啟用**選項，如下所示： <br/> ![顯示 .NET Framework 4.5 功能底下的 HTTP 啟用選項的螢幕擷取畫面。](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> 如果您還有其他的彈出提示，請不要擔心，您必須安裝一些其他事項，才能安裝 HTTP 啟用。 這是正常的;按一下 [確定] 並繼續。 如果您未看到此快顯視窗，您可以假設已經安裝並繼續進行這些專案。  <br/> 安裝 Windows Server 2016 時，通常會安裝 Microsoft .NET Framework。 商務用 Skype 伺服器需要 Microsoft .NET Framework 4.7 或4.8，但您可能需要更新它。 您可以在[這裡](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)找到更新<br/> |
|媒體基礎  <br/> |若為 Windows Server 2016，Windows Media Format Runtime 會隨 Microsoft Media Foundation 一起安裝。  <br/> 所有供會議使用的前端伺服器和 Standard Edition 伺服器，都需要 Windows Media Format Runtime 執行 Windows Media Audio （.wma）檔案，該檔案會對宣告和音樂播放通話駐留、宣告及回應群組應用程式。  <br/> |
|Windows Identity Foundation  <br/> |我們需要 Windows Identity Foundation 3.5，以支援商務用 Skype Server 2019 的伺服器對伺服器驗證案例。  <br/> •針對 Windows Server 2016，您不需要下載任何專案。 開啟 [**伺服器管理員**]，然後移至 [**新增角色及功能] 嚮導**。 **Windows Identity Foundation 3.5**會列于 [**功能**] 區段中。 如果已選取此選項，表示您已是好的。 否則選取它，然後按一下 **[下一步]** 進入 [**安裝**] 按鈕。 <br/> |
|遠端伺服器管理工具  <br/> |角色管理工具： AD DS 和 AD LDS 工具  <br/> |
   
 **前端伺服器和 Standard Edition server 也需要：**
  
|**軟體/角色**|**詳細資料**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |在所有前端伺服器及所有 Standard Edition 伺服器上，都需要有 IIS，且選取下列模組：  <br/> •常見的 HTTP 功能：預設檔、HTTP 錯誤、靜態內容  <br/> •健康情況與診斷： HTTP 記錄、記錄工具、追蹤  <br/> •效能：靜態內容壓縮，動態內容壓縮  <br/> •安全性：要求篩選，用戶端憑證對應驗證，Windows 驗證  <br/> •應用程式開發： .NET 擴充性3.5，.NET 擴充性4.5，ASP.NET 3.5，ASP.NET 4.5，ISAPI Extensions，ISAPI 篩選器  <br/> •管理工具： IIS 管理主控台、IIS 管理腳本及工具  <br/> 請注意，您也需要匿名存取，但是當您安裝 IIS 時，就會收到，所以您沒有在清單中選取它的位置。  <br/> |
|Windows Media Format Runtime  <br/> | 若為 Windows Server 2016，您必須在**伺服器管理員**中安裝**Media Foundation**功能。 您實際上可以啟動商務用 Skype Server 2019 安裝，但不需要這麼做，但在商務用 Skype Server 2019 安裝繼續之前，系統會提示您安裝它，然後重新開機伺服器。 這項工作的執行效果最好。 <br/> |
|Silverlight  <br/> |您可以在[這裡](https://www.microsoft.com/silverlight/)安裝最新版的 Silverlight。  <br/> |
   
為了協助您完成，您可以執行下列範例 PowerShell 腳本，以自動化此程式：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **Director 也需要：**
  
IIS，選取下列模組：
  
- 一般 HTTP 功能
    
  - 預設文件
    
  - HTTP 錯誤
    
  - 靜態內容
    
- 健康情況及診斷
    
  - HTTP 記錄
    
  - 記錄工具
    
  - 跟蹤
    
- 效能
    
  - 靜態內容壓縮
    
- 安全性
    
  - 要求篩選
    
  - 用戶端憑證對應驗證
    
  - Windows 驗證
    
- 應用程式開發
    
  - .NET 擴充性3。5
    
  - .NET 擴充性 4.5
    
  - ASP.NET 3。5
    
  - ASP.NET 4。5
    
  - ISAPI 擴充
    
  - ISAPI 篩選
    
（如果您想知道，它與前端伺服器和 Standard Edition 伺服器的模組設定相同，動態內容壓縮和管理工具會保持不變）。
  
以下為此，我們也有一些 PowerShell 程式碼：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>可搭配商務用 Skype Server 2019 的後端資料庫
<a name="DBs"> </a>

安裝商務用 Skype Server 2019 Standard Edition 時，您將擁有 SQL Server 2016 Express （64位版本）。

商務用 Skype Server 2019 Enterprise Edition 會需要完整的 SQL Server，如下所示（只是64位版本; 請不要使用32位版本）：
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 （64-bit edition），您必須使用最新的更新來執行。  <br/> |Microsoft SQL Server 2017 （64-bit edition），您必須使用最新的更新來執行。  <br/> |
Microsoft SQL Server 2016 （64-bit edition），您必須使用最新的更新來執行。|
 |

如果您沒有看到您想要使用的 SQL Server 版本，您無法使用它。
  
> [!NOTE]
> 您也需要安裝 SQL Server Reporting Services 的監控伺服器角色。 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL 叢集和 SQL Always On

支援使用商務用 Skype Server 2019 的 SQL 叢集。 如果您想要設定 SQL 叢集，請在 SQL Server 中完成。
  
請確定您有支援 SQL 叢集的主動/被動設定。 不要與任何其他 SQL 實例共用被動節點。
  
您可以針對容錯移轉叢集進行下列作業：
  
雙節點：
  
- Microsoft SQL Server 2019 Standard （64-bit edition），我們建議使用最新的 service pack 來執行。
- Microsoft SQL Server 2017 Standard （64-bit edition），我們建議使用最新的 service pack 來執行。
- Microsoft SQL Server 2016 Standard （64-bit edition），我們建議使用最新的 service pack 來執行。

十六節點：
  
- Microsoft SQL Server 2019 Enterprise （64-bit edition），我們建議使用最新的 service pack 來執行。
- Microsoft SQL Server 2017 Enterprise （64-bit edition），我們建議使用最新的 service pack 來執行。
- Microsoft SQL Server 2016 Enterprise （64-bit edition），我們建議使用最新的 service pack 來執行。

支援 SQL Always On，您可以在[商務用 Skype Server 2019 的後端伺服器高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)中深入閱讀。
  

###  <a name="additional-server-installation-recommendations"></a>其他伺服器安裝建議：
  
請不要在任何前端伺服器或獨立轉送伺服器上安裝任何 Microsoft Internet 安全性和加速（ISA） Server 用戶端軟體或任何其他 Winsock 分層服務提供者（LSP）軟體（這裡會包含任何協力廠商防火牆或防病毒網路檢查軟體）。 安裝軟體時，看到的媒體流量效能不良。
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

雖然伺服器和服務的大部分設定資料都儲存在商務用 Skype Server 2019 中央管理存放區中，但仍有一些專案會儲存在 Active Directory 中：
  
|**Active Directory 物件**|**物件類型**|
|:-----|:-----|
|架構擴充  <br/> |使用者物件擴充  <br/> |
||商務用 Skype Server 2015 和 Lync Server 2013 的分機號碼，以維持先前支援版本的回溯相容性  <br/> |
|資料  <br/> |使用者 SIP URI 及其他使用者設定  <br/> |
||應用程式的連絡人物件（如回應群組應用程式和會議助理應用程式）  <br/> |
||為回溯相容性發佈的資料  <br/> |
||中央管理存放區的服務控制點（SCP）  <br/> |
||Kerberos 驗證帳戶（選擇性的電腦物件）  <br/> |
   
### <a name="os-for-domain-controllers"></a>網域控制站的作業系統

您可以使用下列的網域控制站作業系統：
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
您部署商務用 Skype Server 2019 的任何網域的網域功能層級，以及您部署商務用 Skype Server 2019 的任何樹系的樹系功能等級，都必須是下列其中一項：
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
在這些環境中，是否可以擁有唯讀的網域控制站？ 請確定，只要還有可用的可寫入網域控制站。
  
請務必知道商務用 Skype Server 2019 不支援單一標示的網域。 它們是什麼？ 如果您有一個標示為 contoso 的根網域，就會正常。 如果您擁有的根功能變數名稱只有命名為 [本機]，就不會使用，因此不支援此功能。 您還可以[在此知識庫文章中](https://support.microsoft.com/kb/300684/)寫入這項資訊。
  
商務用 Skype Server 2019 也不支援重新命名網域。 如果您確實需要重新命名您的網域，必須先卸載商務用 Skype Server 2019，再進行網域重新命名，然後重新安裝商務用 Skype Server 2019。
  
最後，您可能會使用鎖定的 AD DS 環境處理網域，而且這很好。 關於如何將商務用 Skype Server 2019 的詳細資訊，請參閱部署檔中的鎖定的 AD DS 環境。
  
### <a name="ad-topologies"></a>AD 拓撲

商務用 Skype Server 2019 支援的拓撲包括：
  
- 具單一網域的單一樹系
    
- 具單一樹狀結構和多個網域的單一樹系
    
- 具多重樹狀結構和斷續命名空間的單一樹系
    
- 中央樹系拓撲中的多重樹系
    
- 資源樹系拓撲中的多重樹系
    
- 使用 Exchange Online 的商務用 Skype 資源樹系拓撲中的多個樹系
    
- 具有商務用 Skype Online 和 Azure Active Directory Connect 之資源樹系拓撲中的多個樹系
    
我們有圖表和描述，可協助您決定環境中所具備的拓撲，或在安裝商務用 Skype Server 2019 之前必須設定的專案。 為了簡化，我們也包含重要：
  
![為商務用 Skype 拓朴圖表所用的圖示的索引鍵](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>具單一網域的單一樹系

![具有單一網域之 Active Directory 單一樹系圖表](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
它不會變得更容易。通用拓撲是單一網域樹系。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>具單一樹狀結構和多個網域的單一樹系

![單一樹系、單一樹系和 mutiple 網域圖表](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
這個圖表會再次顯示單一樹系，但也有一個或多個子網域（此特定範例中有三個）。 因此，使用者建立所在的網域可能與將商務用 Skype Server 2019 部署在不同的網域。 為什麼要擔心呢？ 請務必記住，當您部署商務用 Skype Server 前端集區時，該集區中的所有伺服器都必須在單一網域中。 您可以透過商務用 Skype Server 支援 Windows 通用管理員群組，以進行跨網域管理。
  
在上圖中，您可以看到來自某個網域的使用者可以從相同網域或不同網域存取商務用 Skype 伺服器集區，即使這些使用者位於子網域中也是一樣。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>具多重樹狀結構和斷續命名空間的單一樹系

![單一樹系、多樹系和脫節命名空間圖表](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
您的拓撲可能類似于此圖表，其中您有一個樹系，但在該樹系中是多個網域，具有不同的 AD 命名空間。 在此情況下，此圖表是一個很好的圖解，因為它包含存取商務用 Skype Server 2019 的三個不同網域中的使用者。 實線表示他們在自己的網域中存取商務用 Skype 伺服器集區，而虛線表示他們只會進入其他樹狀目錄中的集區。
  
如您所見，相同網域中的使用者、相同的樹狀目錄，甚至不同的樹狀目錄都可以成功存取集區。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央樹系拓撲中的多重樹系

![中央樹系拓撲圖表中的多個樹系](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
商務用 Skype Server 2019 不支援在中央樹系拓撲中設定多個樹系。 如果您不確定這是您擁有的內容，拓撲中的中央樹系會使用其中的物件來代表其他樹系中的使用者，並為樹系中的任何使用者主控使用者帳戶。
  
這是如何運作的？ 目錄同步處理產品（例如 Forefront Identity Manager 或 FIM）會管理組織的使用者帳戶，使其成為現有的使用者帳戶。 建立或刪除樹系中的帳戶時，此變更會同步到中央樹系中的對應連絡人。
  
顯然，如果您的 AD 基礎結構已到位，移至此拓撲可能並不容易，但是如果您已存在，或仍在規劃樹系基礎結構，則這是一個不錯的選擇。 您可以在單一樹系中將商務用 Skype Server 2019 部署集中在一起，使用者可以搜尋、通訊和查看任何樹系中的其他使用者的目前狀態。 所有使用者連絡人更新都會以同步處理軟體自動進行處理。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>商務用 Skype 資源樹系拓撲中的多個樹系
<a name="BKMK_multipleforestopology"> </a>

![資源樹系拓撲圖表中的多個樹系](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
也支援資源樹系拓撲;這是樹系專用於執行伺服器應用程式（如 Microsoft Exchange Server 和商務用 Skype Server 2019）的所在位置。 這個資源樹系也會主控作用中使用者物件的同步標記法，但沒有啟用登入的使用者帳戶。 因此，資源樹系是使用者物件所在之其他樹系的共用服務環境，而且與資源樹系具有樹系層級的信任關係。
  
請注意，Exchange Server 可以部署在與商務用 Skype 伺服器相同的資源樹系中，也可以部署在不同的樹系中。
  
若要在此類型的拓撲中部署商務用 Skype Server 2019，您可以針對使用者樹系中的每個使用者帳戶，在資源樹系中建立一個已停用的使用者物件（如果 Microsoft Exchange Server 已經在環境中，可能會為您完成）。 然後，您需要目錄同步處理工具（如 Forefront Identity Manager 或 FIM）以透過生命週期管理使用者帳戶。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>使用 Exchange Online 的商務用 Skype 資源樹系拓撲中的多個樹系
<a name="BKMK_multipleforestopology"> </a>

此拓撲類似于[商務用 Skype 資源樹系拓撲中的多個](system-requirements.md#BKMK_multipleforestopology)樹系中所述的拓撲。
  
在此拓撲中，有一或多個使用者樹系，但商務用 Skype 伺服器部署在專屬的資源樹系中。 Exchange Server 可以在相同的資源樹系或不同的樹系中部署，也可以在不同的樹系中部署，也可以設定為搭配 Exchange Online 使用，Exchange Online 可提供電子郵件服務，以供內部部署帳戶使用。 沒有此拓撲的可用圖表。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>具有商務用 Skype Online 和 Azure Active Directory Connect 之資源樹系拓撲中的多個樹系
<a name="BKMK_multipleforestopology"> </a>

![顯示兩個 AD 樹系、一個使用者樹系及一個資源樹系。 這兩個樹系具有信任關係。 使用 Azure AD Connect 與 Microsoft 365 同步處理。 所有使用者都透過 Microsoft 365 為商務用 Skype 啟用。](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
使用此案例時，會有多個樹系內部部署，具有資源樹系拓撲。 Active Directory 樹系之間有完全信任關係。 使用 Azure Active Directory Connect 工具，可同步處理內部部署使用者樹系與 Microsoft 365 或 Office 365 之間的帳戶。
  
 組織也有 Microsoft 365 或 Office 365，並使用[Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) ，將其內部部署帳戶與 Microsoft 365 或 office 365 同步處理。 已啟用商務用 Skype 的使用者可透過 Microsoft 365 或 Office 365 和商務用 Skype Online 啟用。 商務用 Skype Server 不會部署在內部部署。
  
單一登入驗證是由位於使用者樹系中的 Active Directory Federation Services 伺服器陣列所提供。
  
在此案例中，支援部署 Exchange 內部部署、Exchange Online、混合式 Exchange 解決方案，或根本不部署 Exchange。 （圖表只顯示 Exchange 內部部署，但也完全支援另一種 Exchange 解決方案。）
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>具有混合式商務用 Skype 的資源樹系拓撲中的多個樹系
<a name="BKMK_multipleforestopology"> </a>

在此案例中，有一或多個內部部署使用者樹系，但商務用 Skype 是部署在專屬的資源樹系中，並設定為搭配商務用 Skype Online 的混合模式。 Exchange Server 可以在相同的資源樹系或不同的樹系中部署內部部署，也可以設定為搭配 Exchange Online 進行混合。 或者，電子郵件服務可由 Exchange Online 專門提供給內部部署帳戶。
  
如需詳細資訊，請參閱[設定混合式商務用 Skype 的多樹系環境](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

商務用 Skype Server 2019 需要 DNS，原因如下：
  
- DNS 可讓商務用 Skype Server 2019 探索內部伺服器或集區，允許伺服器對伺服器的通訊。
    
- DNS 允許用戶端電腦探索用於 SIP 交易的前端集區或 Standard Edition server。
    
- 它會將會議的簡易 URLs 與主控這些會議的伺服器產生關聯。
    
- DNS 允許外部使用者和用戶端電腦連線至 Edge Server 或 HTTP 反向 proxy，以進行立即訊息（IM）或會議。
    
- 它可讓未登入的整合通訊（UC）裝置探索執行裝置更新 web 服務的前端集區或 Standard Edition server，以取得更新及傳送記錄。
    
- 使用 DNS 可讓行動用戶端自動探索 web 服務資源，而不需要使用者在其裝置設定中手動輸入 URLs。
    
- 在 DNS 負載平衡中使用。
    
請務必注意，商務用 Skype Server 2019 不支援國際化功能變數名稱（Idn）。
  
因此，請務必記住，DNS 中的任何名稱與商務用 Skype Server 2019 所使用之任何伺服器上設定的電腦名稱稱相同。 具體而言，在環境中不能有任何短名稱，而且拓撲產生器必須具有 Fqdn。
  
這似乎是任何已加入網域的電腦都是合乎邏輯的，但是如果您有未加入至網域的 Edge Server，它可能會有預設的短名稱，但沒有網域尾碼。 在此情況下，請確定不是在 DNS 或 Edge Server 上，或任何商務用 Skype Server 2019 server 或集區的情況。
  
絕對不使用 Unicode 字元或底線。 標準字元（可以是 A-Z、a-z、0-9 和連字號）是由外部 DNS 及公開的憑證授權單位所支援（您需要將 Fqdn 指派給憑證中的 SN，所以請務必記住），這樣一來，當您從開始著手考慮，您將會有許多麻煩。
  
如需聯網的 DNS 需求的進一步閱讀，請參閱規劃檔中的 [[網路](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md)] 區段。
  
## <a name="certificates"></a>憑證
<a name="Certs"> </a>

部署之前您可以執行的最重要的其中一個工作是，請確定您的憑證有序。 商務用 Skype Server 2019 需要公開金鑰基礎結構（PKI），以用於傳輸層安全性（TLS）和相互傳輸層安全性（MTLS）連線。 一般來說，若要以標準化的方式安全地通訊，商務用 Skype 伺服器會使用憑證授權單位（Ca）所發出的憑證。
  
以下是商務用 Skype Server 2019 使用憑證的一些事項：
  
- 用戶端與伺服器之間的 TLS 連線
    
- 伺服器之間的 MTLS 連線
    
- 使用自動探索協力廠商 DNS 的同盟連線
    
- 遠端使用者存取即時訊息 (IM)
    
- 外部使用者存取音訊/視頻（AV）會話、應用程式共用和會議
    
- 與 web 應用程式和 Outlook Web Access （OWA）交談
    
因此，必須使用憑證規劃。 現在，讓我們看一下要求憑證時必須注意的一些事項清單：
  
- 所有的伺服器憑證必須支援伺服器授權 (伺服器 EKU)。
    
- 所有的伺服器憑證必須包含一個 CRL 發佈點 (CDP)。
    
- 所有憑證必須使用作業系統支援的簽署演算法進行簽署。 商務用 Skype Server 2019 支援摘要大小的 SHA-1 和 SHA-2 套件（224、256、384和512位），並符合或超過作業系統需求。
    
- 對執行商務用 Skype Server 2019 的內部伺服器支援自動註冊。
    
- 商務用 Skype Server 2019 Edge Server 不支援自動註冊。
    
> [!NOTE]
> 不支援使用 RSASSA-PSS 簽名演算法，而且可能會導致登入和來電轉接問題的錯誤，以及其他問題。 
  
- 支援加密金鑰長度（1024、2048及4096）。 建議使用的金鑰長度2048和更大。
    
- 預設摘要（或雜湊簽署）演算法為 RSA。 也支援 ECDH_P256、ECDH_P384 及 ECDH_P521 演算法。
    
這是我們所要考慮的一點，而且從 CA 要求憑證的程度很高。 我們將提供下列進一步的指導，讓您的計畫盡可能順利。
  
### <a name="certificates-for-your-internal-servers"></a>內部伺服器的憑證

您將需要大部分內部伺服器的憑證，而且您很可能會從內部 CA （即網域中的 CA）取得憑證。 如有需要，您可以從外部 CA 要求這些憑證（位於網際網路上的憑證）。 如果您不想要移至哪一個公用 CA，您可以查看「[整合通訊憑證合作夥伴](/SkypeForBusiness/certification/services-ssl)」清單。
  
當商務用 Skype Server 2019 與其他應用程式和伺服器（例如 Microsoft Exchange Server）通訊時，您也會需要憑證。 這顯然會需要成為其他應用程式和伺服器可以以支援的方式使用的憑證。 商務用 Skype Server 2019 和其他 Microsoft 產品支援「開放授權」（OAuth）通訊協定，以進行伺服器對伺服器驗證和授權。 如果您想要這樣做，我們有其他的 OAuth 和商務用 Skype Server 2019 的規劃文章。
  
商務用 Skype Server 2019 也包含對（不需要）使用 SHA-256 加密雜湊函數簽署憑證的支援。 若要使用 SHA-256 支援外部存取，使用 SHA-256 公用 CA 必須發行外部憑證。
  
為了讓事情保持直接，我們已將 Standard Edition server、前端集區和其他角色的憑證需求，放入下表，並使用虛構 contoso.com （您的環境可能會使用其他內容）。 這些都是標準網頁伺服器憑證，具有不可匯出的私密金鑰。 需要注意的一些其他事項：
  
- 當您使用憑證嚮導要求憑證時，會自動設定 Server 增強金鑰使用方式（EKU）。
    
- 每個憑證好記的名稱在電腦存放區中必須是唯一的。
    
- 根據下列範例名稱，如果您已在 DNS 中設定 sipinternal.contoso.com 或 sipexternal.contoso.com，則必須將它們新增至憑證的主體替代名稱（SAN）。
    
Standard Edition server 的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|預設  <br/> |集區的 FQDN  <br/> |伺服器集區的 FQDN 和伺服器的 FQDN  <br/> 如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN  <br/> 如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格網域名稱系統 (DNS) 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。  <br/> |SN = se01，SAN = se01  <br/> 如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com  <br/> |在 Standard Edition server 上，伺服器 FQDN 與集區 FQDN 相同。  <br/> 精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。  <br/> 您也可以使用此憑證進行 Server-to-Server 驗證。  <br/> |
|Web 內部  <br/> |伺服器的 FQDN  <br/> |下列每一項：  <br/> •內部 web FQDN （與伺服器的 FQDN 相同）  <br/> AND  <br/> •符合簡易 URLs  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = se01，SAN = se01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com  <br/> 使用萬用字元憑證：  <br/> SN = se01，SAN = se01;SAN = \* contoso.com  <br/> |您無法在拓撲產生器中覆寫內部 web FQDN。  <br/> 如果您有多個符合簡易的 URLs，您必須將它們全部包含為 SANs。  <br/> 簡單 URL 項目支援萬用字元項目。  <br/> |
|Web 外部  <br/> |伺服器的 FQDN  <br/> |下列每一項：  <br/> •外部 web FQDN  <br/> AND  <br/> •撥入式簡易 URL  <br/> •符合每個 SIP 網域的簡易 URLs  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = se01，SAN = webcon01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com  <br/> 使用萬用字元憑證：  <br/> SN = se01，SAN = webcon01;SAN = \* contoso.com  <br/> |若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。  <br/> 簡單 URL 項目支援萬用字元項目。  <br/> |
   
前端集區中前端伺服器的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|預設  <br/> |集區的 FQDN  <br/> |伺服器集區的 FQDN 和伺服器的 FQDN  <br/> 如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN  <br/> 如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格網域名稱系統 (DNS) 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。  <br/> |SN = eepool，SAN = eepool;SAN = ee01  <br/> 如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com  <br/> |精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。  <br/> 您也可以使用此憑證進行 Server-to-Server 驗證。  <br/> |
|Web 內部  <br/> |集區的 FQDN  <br/> |下列每一項：  <br/> •內部 web FQDN （與伺服器的 FQDN 不同）  <br/> •伺服器 FQDN  <br/> •商務用 Skype 集區 FQDN  <br/> AND  <br/> •符合簡易 URLs  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = ee01，SAN = ee01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com  <br/> 使用萬用字元憑證：  <br/> SN = ee01，SAN = ee01;SAN = \* contoso.com  <br/> |若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。  <br/> 簡單 URL 項目支援萬用字元項目。  <br/> |
|Web 外部  <br/> |集區的 FQDN  <br/> |下列每一項：  <br/> •外部 web FQDN  <br/> AND  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = ee01，SAN = webcon01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com  <br/> 使用萬用字元憑證：  <br/> SN = ee01，SAN = webcon01;SAN = \* contoso.com  <br/> |若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。  <br/> 簡單 URL 項目支援萬用字元項目。  <br/> |
   
Director 的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|預設  <br/> |Director pool  <br/> |Director 的 FQDN （Director 集區的 FQDN）。  <br/> 如果此集區是用戶端的自動登入伺服器，且群組原則中需要嚴格 DNS 比對，則您也需要 microsoft.rtc.management.xds.sipdomain （適用于每個 SIP 網域）的專案。  <br/> |pool.contoso.com;SAN = dir01  <br/> 如果此 Director 集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com  <br/> |
|Web 內部  <br/> |伺服器的 FQDN  <br/> |下列每一項：  <br/> •內部 web FQDN （與伺服器的 FQDN 相同）  <br/> •伺服器 FQDN  <br/> •商務用 Skype 集區 FQDN  <br/> AND  <br/> •符合簡易 URLs  <br/> •撥入式簡易 URL  <br/> •系統管理員簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |SN = dir01，SAN = dir01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com  <br/> 使用萬用字元憑證：  <br/> SN = dir01，SAN = dir01 SAN = \* 。 contoso.com  <br/> |
|Web 外部  <br/> |伺服器的 FQDN  <br/> |下列每一項：  <br/> •外部 web FQDN  <br/> AND  <br/> •符合每個 SIP 網域的簡易 URLs  <br/> •撥入式簡易 URL  <br/> OR  <br/> •簡單 URLs 的萬用字元專案  <br/> |Director 外部 web FQDN 必須不同于前端集區或前端伺服器。  <br/> SN = dir01，SAN = directorwebcon01 SAN = "contoso .com"，SAN = 符合 fabrikam .com;SAN = 撥入 .com  <br/> 使用萬用字元憑證：  <br/> SN = dir01，SAN = directorwebcon01 SAN = \* 。 contoso.com  <br/> |
   
獨立轉送伺服器的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|預設  <br/> |集區的 FQDN  <br/> |集區的 FQDN  <br/> 集區成員伺服器的 FQDN  <br/> |SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01  <br/> |
   
適用于商務用 Skype Server 2019 的 Survivable Branch 裝置（特別是 Survivable Branch 裝置2015）的憑證：
  
|**認證**|**主體名稱/一般名稱**|**主體替代名稱**|**範例**|
|:-----|:-----|:-----|:-----|
|預設  <br/> |Appliance 的 FQDN  <br/> |SIP。 \<microsoft.rtc.management.xds.sipdomain \> （每個 SIP 網域只需要一個專案）  <br/> |SN = sba01SAN = sip .com;SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>外部使用者存取的憑證（Edge）

商務用 Skype Server 2019 支援使用**單一公用憑證**進行 access 和 Web 會議 Edge 外部介面，以及 A/V 驗證服務，這是透過 Edge Server 所提供的。 您的 Edge 內部介面一般會使用您的內部 CA 所發出的私人憑證，但是如果您願意，也可以使用公用憑證，如果是來自信任的 CA。
  
反向 proxy （RP）也會使用公用憑證，並使用 HTTP （或更確切地說是 TLS over HTTP），將您的 RP 中的通訊加密到用戶端，並將 RP 加密為內部伺服器。
  
### <a name="certificates-for-mobility"></a>行動的憑證

如果您正在部署行動性，且支援行動用戶端的自動探索，您必須在憑證上加入一些額外的主體替代名稱專案，以支援行動用戶端的安全連線。
  
您將需要 SAN 名稱，才能自動探索下列憑證：
  
- Director pool
    
- 前端集區
    
- 反向 Proxy
    
如下表所列的詳細資料。
  
在此情況下，有些預先規劃很好，但是有時候您已部署商務用 Skype Server 2019，而不是想要部署行動性，當您已在您的環境中已有憑證之後又會出現。 透過內部 CA 重新發起它們通常相當簡單，但有來自公用 CA 的公用憑證，則可能會有一點的 pricy。
  
如果這是您所看到的專案，而且如果您有許多 SIP 網域（這會增加 SAN 的成本），您可以設定反向 proxy，以使用 HTTP 做為初始自動探索服務要求，而不是使用 HTTPS （預設設定）。 [行動性](../../SfbServer/plan-your-deployment/mobility.md)文章的計畫具有這方面的詳細資訊。
  
Director 集區和前端集區憑證需求：
  
|**描述**|**SAN 專案**|
|:-----|:-----|
|內部自動探索服務 URL  <br/> |SAN = lyncdiscoverinternal。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
|外部自動探索服務 URL  <br/> |SAN = lyncdiscover。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
   
您也可以使用 SAN = \* 。 \<microsoft.rtc.management.xds.sipdomain\>
  
反向 Proxy （公用 CA）憑證需求：
  
|**描述**|**SAN 專案**|
|:-----|:-----|
|外部自動探索服務 URL  <br/> |SAN = lyncdiscover。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
   
此 SAN 必須指派給反向 proxy 上的 SSL 攔截器所指派的憑證。
  
> [!NOTE]
> 您的反向 proxy 接聽程式即將擁有您的外部 Web 服務 URL 的 SANs。 例如，如果您已部署 Director （這是選用），則某些範例會是 SAN = skypewebextpool01 .com 和 dirwebexternal.contoso.com。 
  
## <a name="file-share"></a>檔案共用
<a name="Fileshare"> </a>

商務用 Skype Server 2019 可以將相同的檔案共用用於所有檔案存放區。 您必須謹記下列各項：
  
- 檔案共用必須位於直接附加儲存裝置（DAS）或儲存區域網路（SAN）上，而且這包括分散式檔案系統（DFS），以及檔案存放區的獨立磁碟容錯陣列（RAID）。 如需有關 Windows Server 2012 的 DFS 的進一步閱讀，請參閱[此 DFS 頁面](https://technet.microsoft.com/library/jj127250.aspx)。
    
- 我們建議使用共用叢集進行檔案共用。 如果您已經在使用其中一個，則應將 Windows Server 2012 或更高版本聚簇。

> [!Note]
> **為什麼是最新的視窗？** 舊版本可能沒有適當的許可權可啟用所有功能。 您可以使用 [群集管理員] 來建立檔案共用。 如需詳細資訊，請參閱這項支援文章[如何在集群上建立檔案共用](https://support.microsoft.com/help/224967)。
    
> [!CAUTION]
> 您應該知道，不支援使用網路連接儲存（NAS）做為檔案共用，所以請使用以上所列的其中一個選項。 這項支援限制是由 NAS 裝置的變化設計所造成，該裝置必須對存取裝置共用檔案系統的 Windows Server 電腦提供檔案系統適應性。
  







