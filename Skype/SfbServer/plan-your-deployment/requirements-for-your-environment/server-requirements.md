---
title: 商務用 Skype Server 2015 的伺服器需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 摘要：使用本主題準備商務用 Skype Server 2015 伺服器。 硬體、作業系統、資料庫、軟體、所有系統需求與建議都在這裡，以協助確保您的伺服器伺服器陣列已成功安裝和部署。
ms.openlocfilehash: f806137b5972968332723a370092724bd9680697
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801883"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的伺服器需求
 
**摘要：** 使用本主題準備商務用 Skype Server 2015 伺服器。 硬體、作業系統、資料庫、軟體、所有系統需求與建議都在這裡，以協助確保您的伺服器伺服器陣列已成功安裝和部署。

如果您正在尋找環境需求（例如 Active Directory、DNS 或憑證），您可以查看[商務用 Skype Server 2015 檔的環境需求](environmental-requirements.md)。
  
您可能會在開始部署商務用 Skype Server 2015 之前進行一些準備。 本文將逐步引導您規劃下列各項：
  
- [商務用 Skype Server 2015 的硬體](server-requirements.md#Hardware)
  
- [商務用 Skype Server 2015 的作業系統](server-requirements.md#OS)
  
- [可搭配商務用 Skype Server 2015 使用的後端資料庫](server-requirements.md#DBs)
  
- [在商務用 Skype Server 2015 部署之前必須安裝的軟體](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的硬體
<a name="Hardware"> </a>

現在您已將拓朴分解（如果沒有，您可以查看[商務用 Skype Server 2015 主題的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)），那就是思考伺服器的時機。 商務用 Skype Server 2015 伺服器將需要64位的硬體。 我們的硬體建議如下。 這些不是要求，而是會反映最佳效能所需的需求。 我們有容量規劃檔，可根據您的情況，協助判斷您是否需要更多。
  
適用于前端伺服器、後端伺服器、標準版伺服器及持久聊天伺服器的建議硬體：
  
|**硬體元件**|**採用**|
|:-----|:-----|
|CPU  <br/> |64位雙處理器、hex 核、2.26 ghz （GHz）或更高版本。  <br/> 商務用 Skype Server 2015 角色不支援 Intel 安騰處理器。  <br/> |
|儲存體  <br/> |32千百萬位元組（GB）。  <br/> |
|光碟  <br/> |兩側  <br/> •8個或以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間（使用 RAID 1 和6的兩個磁片）。  <br/> 或  <br/> •固態硬碟（SSDs）能夠提供與 8 10000 RPM 機械磁片磁碟機相同的可用空間和類似的效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡、1 Gbps 或更新版本（2個網路介面卡可用，但必須使用單一 MAC 位址和單一 IP 位址進行分組）。  <br/> 前端伺服器、後端伺服器、標準版伺服器及持久聊天伺服器**不**支援雙或多穴設定。 <br/> 只要客戶不會向作業系統公開，而且是用來監視及管理伺服器硬體，您就可以有帶外管理系統（例如 DRAC 或 ILO）。 這個案例不構成多穴伺服器，而且受到支援。  <br/> |
   
適用于 Edge 伺服器、獨立轉送伺服器、視頻交互操作伺服器和控制器的建議硬體：
  
|**硬體元件**|**採用**|
|:-----|:-----|
|CPU  <br/> |64位雙處理器、四核、2.26 十億位元（GHz）或更高版本。  <br/> 商務用 Skype Server 2015 角色不支援 Intel 安騰處理器。  <br/> |
|儲存體  <br/> |16 gb。  <br/> |
|光碟  <br/> |兩側  <br/> •4個以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間（磁片應該是 2x RAID 1 設定）。  <br/> 或  <br/> •固態硬碟（SSDs）能夠提供與 4 10000 RPM 機械磁片磁碟機相同的可用空間和類似的效能。  <br/> |
|網路  <br/> |1個雙埠網路介面卡、1 Gbps 或更新版本（2個網路介面卡可用，但必須使用單一 MAC 位址和單一 IP 位址進行分組）。  <br/> 對於視頻交互操作伺服器和控制器，**不**支援雙或多穴設定。 <br/> Edge 伺服器需要兩個雙埠網路介面卡、1 Gbps 或更高（或兩個成對式網路介面卡）的網路介面，每個配對都是以單一 MAC 位址與單一 IP 位址組成兩個組。  <br/> 在獨立的轉送伺服器上，安裝額外的網路介面卡（Nic），以允許設定特定 PSTN IP 位址。  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的作業系統
<a name="OS"> </a>

硬體就緒之後，您必須安裝作業系統（OS）。 這些是可讓您安裝並成功使用商務用 Skype Server 2015 的作業系統。
  
|||
|:-----|:-----|
|Windows Server 2019 （您需要商務用 Skype 累計更新9或更新版本）。 <br/> |Windows Server 2016 （您需要商務用 Skype 累計更新5或更新版本）。 如需詳細資訊，請參閱[KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)）  <br/> ||
|Windows Server 2012 R2 Datacenter OS，已安裝所有必要的更新。  <br/> |Windows Server 2012 R2 標準作業系統已安裝所有必要的更新。  <br/> |
|Windows Server 2012 Datacenter OS，已安裝所有必要的更新。  <br/> |Windows Server 2012 標準作業系統已安裝所有必要的更新。  <br/> |
   
如果它不在此清單中，就無法正常運作，請不要嘗試在新安裝的商務用 Skype Server 2015 中使用。 請注意，Lync Server 2013 不支援就地升級作業系統。  您必須部署個別的 [池]，並將使用者遷移到具有不同作業系統的新池。
  
> [!NOTE]
> 您可能已經注意到 Windows Server 2008 R2 不在此清單中。 這是因為我們建議將所有新伺服器的 Windows Server 2012 R2 用於 SFB。 您應該只有在已安裝 Lync Server 2013 的現有伺服器，且您想要進行就地升級時，才能使用 Windows Server 2008 R2。 Windows Server 2008 R2 已達到1/13/2015 上主流支援週期的結尾，並將于其在1/14/2020 的支援週期終點結束。
  
除了最新的 service pack 之外，您還會想要確保安裝下列與您相關的更新：
  
- 若為 Windows Server 2012，請先安裝知識庫文章2858668，然後再升級。 請[在這裡找到](https://support.microsoft.com/kb/2858668/)。
    
- 如果您有 Windows Server 2012 R2，請先安裝知識庫文章2982006，然後再升級。 可[在此找到](https://support.microsoft.com/kb/2982006/)。
    
- 如果您是在 Windows Server 2008 R2 方塊上升級（請參閱上述注意事項），那麼您將需要先安裝知識庫文章2533623。 [它在這個連結](https://support.microsoft.com/kb/2533623/)中。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>可搭配商務用 Skype Server 2015 使用的後端資料庫
<a name="DBs"> </a>


安裝商務用 Skype Server 2015 標準版時，您會同時自動安裝 SQL Server 2014 Express （64位版本）。
  
商務用 Skype Server 2015 企業版不復雜，但以下是受支援的清單（一切都是64位版本，您會注意到，請不要使用32位版本）：
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise （64位版本），我們建議使用最新的 service pack 執行。 <br/> |Microsoft SQL Server 2017 Enterprise （64位版本），我們建議使用最新的 service pack 執行。 <br/> |Microsoft SQL Server 2016 企業版（64位版本） Service Pack 1 或更新版本，且您必須在商務用 Skype 累積更新7或更新版本中執行（[下載商務用 Skype 累計更新](https://support.microsoft.com/help/3061064)）。  <br/> |Microsoft SQL Server 2014 Enterprise （64位版本），而且您必須以累積更新6或更新版本（[下載累加更新 6](https://support.microsoft.com/kb/3031047/)）執行。  <br/> |Microsoft SQL Server 2012 Enterprise （64位版本），我們建議使用最新的 service pack 執行。  <br/> |
|Microsoft SQL Server 2019 標準版（64位版本），我們建議使用最新的 service pack 執行。 <br/> |Microsoft SQL Server 2017 標準版（64位版本），我們建議使用最新的 service pack 執行。 <br/> |Microsoft SQL Server 2016 Standard （64位版本） Service Pack 1 或更新版本，且您必須在商務用 Skype 累積更新7或更新版本中執行（[下載商務用 Skype 累計更新](https://support.microsoft.com/help/3061064)）。  <br/> |Microsoft SQL Server 2014 標準版（64位版本），而且您必須以累積更新6或更新版本（[下載累加更新 6](https://support.microsoft.com/kb/3031047/)）執行。  <br/> |Microsoft SQL Server 2012 標準版（64位版本），我們建議使用最新的 service pack 執行。  <br/> |
   
如果您沒有看到想要使用的 SQL Server 版本，則無法使用。
  
- 您也需要為監視伺服器角色安裝 SQL Server Reporting Services。
- 如果是連接良好的 SQL 後端，則與商務用 Skype 前端的連線應該是「本機」，而不是穿過低速連結。 
- 不支援在兩個或多個池之間共用 SQL back 結束。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 儲存空間
會議內容檔案（例如 PowerPoint 簡報）會封存為附件。 如果您想要將商務用 Skype 封存資料儲存在 Exchange 合規性資料中，您必須使用 Exchange 進行 Exchange 部署，並確保最大儲存空間大小支援儲存會議內容檔案。 您必須先使用 Microsoft Exchange 整合選項部署並啟用封存，才能部署 Exchange。 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中封存的硬體與軟體需求
  
封存不是已定義的伺服器角色，您不需要安裝個別的伺服器來進行封存。 整合的資料收集代理程式是在每個企業版前端池及每個標準版伺服器上自動安裝及啟用。 您將需要使用拓撲建立器來啟用和發佈您的封存拓撲。
    
封存使用商務用 Skype Server 檔案儲存空間儲存會議內容檔案，因此您不需要設定個別的檔案存放區來進行封存。
    
不需要 Microsoft 訊息佇列。
    
您將需要設定儲存空間的基礎結構。 這包括使用 SQL Server 選擇 Exchange 或歸檔儲存空間。   商務用 skype 伺服器的存檔基礎結構需求與部署商務用 Skype Server 的需求相同。 如需詳細資訊，請參閱[商務用 Skype 環境的需求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> 若要支援不是駐留在 Exchange 伺服器上的使用者，或者不想使用 Microsoft Exchange 整合選項，您必須使用64位的 SQL Server 資料庫部署封存儲存空間。 
    
您必須先設定 SQL Server 平臺，然後才能部署並啟用封存。 如果要用來發佈拓朴的帳戶具有適當的管理員權力和許可權，您可以在發佈拓撲時建立封存資料庫（LcsLog）。 您也可以在稍後建立資料庫，並將它納入安裝程式的一部分。 如需 SQL Server 的詳細資料，請參閱[Sql server 檔](https://go.microsoft.com/fwlink/p/?linkID=129045)。
    
歸檔的負載增加可能相當重要。 因此，您應該確保啟用封存的前端伺服器有足夠的磁碟空間。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 鏡像、SQL 聚集及 SQL Alwayson

您可以透過商務用 Skype Server 2015 使用 SQL 鏡像或 SQL 群集，這是受支援的功能。 在商務用 Skype Server 拓撲建立器中設定 SQL 鏡像。 如果您想要設定 SQL 群集，請在 SQL Server 中完成。
  
請確定您有適用于 SQL 群集的主動/被動設定，因為這是支援的是。 不要與任何其他的 SQL 實例共用被動節點。
  
您可以針對容錯移轉叢集進行下列作業：
  
雙節點：
  
- Microsoft SQL Server 2019 標準版（64位版本），我們建議使用最新的 service pack 執行。

- Microsoft SQL Server 2017 標準版（64位版本），我們建議使用最新的 service pack 執行。

- Microsoft SQL Server 2016 Standard （64位版本） Service Pack 1 或更新版本。 我們建議您使用最新的 service pack 執行。

- Microsoft SQL Server 2014 標準版（64位版本），我們建議使用最新的 service pack 執行。
    
-  Microsoft SQL Server 2012 標準版（64位版本），我們建議使用最新的 service pack 執行。

十六節點：

- Microsoft SQL Server 2019 Enterprise （64位版本），我們建議使用最新的 service pack 執行。

- Microsoft SQL Server 2017 Enterprise （64位版本），我們建議使用最新的 service pack 執行。

- Microsoft SQL Server 2016 企業版（64位版本） Service Pack 1 或更新版本。 我們建議您使用最新的 service pack 執行。
  
- Microsoft SQL Server 2014 Enterprise （64位版本），我們建議使用最新的 service pack 執行。
    
- Microsoft SQL Server 2012 Enterprise （64位版本），我們建議使用最新的 service pack 執行。

> [!IMPORTANT]
> 若是升級，我們想要確保您的前端伺服器上至少已安裝 SQL Server 2012 SP1，然後再升級。 如果您想立即下載，[以下是 SP1 的連結](https://www.microsoft.com/download/details.aspx?id=35575)。
  
如果您需要進一步瞭解 SQL 鏡像，我們在商務用 Skype Server 2015 主題中有一個後端伺服器高可用性。 針對商務用 Skype Server 2015 設定 SQL Server 群集，具有取得群集準備的步驟。 針對 SQL、 [2014](https://technet.microsoft.com/library/hh231721.aspx)、 [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)和[2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)的容錯移轉叢集還有進一步的連結。
  
> [!NOTE]
> 2015版本的新功能支援 SQL Alwayson。 支援它，您可以在[商務用 Skype server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)主題中，進一步瞭解它在後端伺服器的高可用性。

> [!NOTE]
> 在商務用 Skype Server 2015 中提供 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。 使用商務用 Skype Server 2019 時，AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例（FCI）和 SQL 容錯移轉叢集方法都是可取的。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>在商務用 Skype Server 2015 部署之前必須安裝的軟體
<a name="Software"> </a>

在任何執行商務用 Skype Server 2015 的伺服器，都會需要安裝或設定一些事項，如下所示。 在特定伺服器角色的其他需求之後。
  
> [記事！]商務用 Skype server 2015 不支援 .NET Framework 4.8。
  
 **所有伺服器：**
  
|**軟體/角色**|**詳細資料**|
|:-----|:-----|
|Windows PowerShell 3。0  <br/> |所有商務用 Skype 伺服器伺服器都需要安裝 Windows PowerShell 3.0。  <br/> •如果您是在 Windows Server 2012 或 Windows Server 2012 R2 上執行安裝，則您已設定，因為已經在那裡了。  <br/> •如果您是在 Windows Server 2008 R2 上執行升級，您可以下載[Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595)來取得更新。 <br/> **秘訣：** 當您在該處有正確的 PowerShell 之後，請移至 PowerShell 提示，然後輸入`$PSVersionTable`，確認 BuildVersion 6.2.9200.0 或更新版本。 這應該會顯示您所需的資訊。  <br/> |
|Microsoft .NET Framework  <br/> |WCF 服務是以 Windows 功能方式安裝的**功能**，在 [**伺服器管理員**] 底下，不需要下載。 <br/> •您必須確認安裝此功能時，或者如果已安裝此功能，且您正在進行檢查，否則也會檢查並安裝**HTTP 啟用**選項，如下所示： <br/> ![螢幕擷取畫面顯示 .NET Framework 4.5 功能下的 HTTP 啟用選項。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)如果您有額外的快顯說明，請不要擔心需要安裝一些其他事項，才能安裝 HTTP 啟用。 那是標準模式，請按一下 [確定]，然後移至最前面。 如果您沒有看到此快顯畫面，請假設已安裝這些專案，然後繼續進行。  <br/> 安裝 Windows Server 2012 R2 或 Windows Server 2016 時，通常會安裝 Microsoft .NET Framework。 商務用 Skype 伺服器可搭配下列 Microsoft .NET Framework 版本使用：  <br/> • .NET 3。5  <br/> • .NET 4。5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 （適用于商務用 Skype Server CU 5 或更新版本）  <br/>  在您的 Windows Server 2008 R2 電腦上，可能會預設安裝 .NET Framework 3.5 （請務必先檢查，然後再升級），但實際上不會出現在 Windows Server 2012/Windows Server 2012 R2 伺服器（適用于新安裝）。 若要將它新增到中，您需要存取您的安裝磁片磁碟機或媒體（安裝 Windows Server 的位置，或安裝檔案目前的位置）。 接著，將它安裝為伺服器管理員的功能，並在要求時，指向安裝媒體（特別是**\sources\sxs**資料夾），然後繼續安裝。 <br/> |
|媒體基礎  <br/> |如果您使用的是 Windows Server 2016，Windows Server 2012 和 Windows Server 2012 R2 Windows Media 格式執行時間會以 Microsoft 媒體基礎進行安裝。  <br/> 所有適用于會議的前端伺服器和標準版伺服器，都需要 Windows Media 格式執行時間來執行 Windows Media 音訊（.wma）檔案，這些檔案是通話駐留、宣告及回應群組應用程式，可供您使用通知和音樂進行播放。  <br/> |
|Windows 身分識別基礎  <br/> |我們需要 Windows 身分識別基礎3.5，以支援商務用 Skype Server 2015 的伺服器對伺服器驗證案例。  <br/> •適用于 Windows Server 2012 和 Windows Server 2012 R2，不需要下載任何內容。 開啟 [**伺服器管理員**]，然後移至 [**新增角色及功能] 嚮導**。 **Windows 身分識別基礎 3.5**列在 [**功能**] 區段底下。 如果已核取，您就好了。 否則選取它，然後按一下 [下一步] 以移至 [**安裝**] 按鈕。 <br/> |
|遠端伺服器管理工具  <br/> |角色管理工具： AD DS 和 AD LDS 工具  <br/> |
   
 **前端伺服器與標準版伺服器也需要：**
  
|**軟體/角色**|**詳細資料**|
|:-----|:-----|
|網際網路資訊服務（IIS）  <br/> |在所有前端伺服器以及所有標準版伺服器上，都需要有 IIS，且已選取下列模組：  <br/> •常見的 HTTP 功能： [預設檔]、[HTTP 錯誤]、[靜態內容]  <br/> •健康與診斷： HTTP 記錄、記錄工具、追蹤  <br/> •效能：靜態內容壓縮，動態內容壓縮  <br/> •安全性：要求篩選、用戶端憑證對應驗證、Windows 驗證  <br/> •應用程式開發： .NET 擴充性3.5、.NET 擴充性4.5、ASP.NET 3.5、ASP.NET 4.5、ISAPI 延伸、ISAPI 篩選  <br/> •管理工具： IIS 管理主控台、IIS 管理腳本與工具  <br/> 我們也應該注意，您也需要使用匿名存取，但您在安裝 IIS 時會收到，因此您沒有在清單中選取該元件的位置。  <br/> |
|Windows Media 格式執行時間  <br/> | 針對 Windows Server 2016、Windows Server 2012 和 Windows Server 2012 R2，您必須在**Server Manager**中安裝**媒體基礎**功能。 現在，您實際可以在沒有這個安裝的情況下，啟動商務用 Skype Server 2015 安裝，但在商務用 Skype Server 2015 安裝繼續之前，系統會提示您安裝它，然後重新開機伺服器。 最好提前完成。 <br/> |
|Silverlight  <br/> |您可以在[此連結](https://www.microsoft.com/silverlight/)上安裝最新版本的 Silverlight。  <br/> |
   
> [!NOTE] 
> 如果您使用的是負載平衡器，您可能也需要啟用 [瀏覽目錄]。 否則，空白頁會載入負載平衡器可能會考慮失敗的情況。 

為了協助您完成，您可以執行以下範例 PowerShell 腳本來自動化此程式：

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 命令會以特定順序尋找來源檔案。 如果您是在線上，命令會存取 Windows Update。 不過，如果您處於離線狀態，您必須確認來源檔案可供命令使用。 如需有關使用 PowerShell 安裝角色和功能的詳細資訊，請參閱[安裝或卸載角色、角色服務或功能](https://technet.microsoft.com/library/hh831809.aspx)之後，請不要忘記在安裝必備元件之後再次執行 Windows Update，即使您使用的是 PowerShell 命令也一樣。

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **持續聊天伺服器也需要：**
  
[訊息佇列]，也稱為 [MSMQ]。 它是 Windows Server 元件，您可以將它安裝在伺服器管理員中的 [功能] 區段底下。 如果您想要進一步瞭解此資訊，請參閱[安裝和管理訊息佇列](https://technet.microsoft.com/library/cc771474.aspx)。
  
 **上次想法：**
  
請勿安裝任何 Microsoft 網際網路安全性與加速（ISA） Server 用戶端軟體，或任何其他 Winsock 層次服務提供者（LSP）軟體（這裡將提供任何協力廠商的防火牆或防病毒網路檢查軟體）您的任何前端伺服器或獨立的轉送伺服器。 在軟體已安裝時，會出現較差的媒體流量效能。
  

