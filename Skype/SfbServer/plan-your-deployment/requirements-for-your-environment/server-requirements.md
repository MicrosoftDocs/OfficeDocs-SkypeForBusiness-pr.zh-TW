---
title: 商務用 Skype Server 2015 的伺服器需求
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 摘要：使用本主題準備您的商務用 Skype Server 2015 server。 硬體、作業系統、資料庫、軟體、所有系統需求與建議，以協助確保成功安裝及部署您的伺服器陣列。
ms.openlocfilehash: 36b9731602dc5fd753dbc2d0ca54e88cb212c5ad
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398717"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的伺服器需求
 
**總結：** 使用本主題準備您的商務用 Skype Server 2015 server。 硬體、作業系統、資料庫、軟體、所有系統需求與建議，以協助確保成功安裝及部署您的伺服器陣列。

如果您正在尋找環境需求（例如 Active Directory、DNS 或憑證），您可以查看商務用 Skype Server 2015 doc 檔的[環境需求](environmental-requirements.md)。
  
如您所料，您可以在開始部署商務用 Skype Server 2015 之前做一些準備。 本文將引導您規劃下列各項：
  
- [商務用 Skype Server 2015 的硬體](server-requirements.md#Hardware)
  
- [商務用 Skype Server 2015 的作業系統](server-requirements.md#OS)
  
- [可搭配商務用 Skype Server 2015 的後端資料庫](server-requirements.md#DBs)
  
- [在商務用 Skype Server 2015 部署之前應該安裝的軟體](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的硬體
<a name="Hardware"> </a>

現在，您已將拓撲 (，但如果您不是，您可以查看[商務用 Skype Server 2015 主題的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)，) ，那就是思考伺服器的時間。 商務用 Skype Server 2015 伺服器將需要64位硬體。 以下是硬體的建議。 這些不是必要條件，但它們會反映出最佳效能所需的需求。 我們有容量規劃檔，可協助您判斷是否需要超過這種情況，視情況而定。
  
前端伺服器、後端伺服器、Standard Edition 伺服器及持久聊天伺服器的建議硬體：
  
|硬體元件|建議|
|:-----|:-----|
|CPU   |64位雙處理器、六角-核心、2.26 ghz (GHz) 或更高版本。  <br/> 商務用 Skype Server 2015 角色不支援 Intel Itanium 處理器。   |
|記憶體   |32 gb (GB) 。   |
|磁片   |可  <br/> •8個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁片磁碟機， (兩個磁片使用 raid 1 和6，使用 RAID 10) 。  <br/> 或  <br/> •固態磁片磁碟機 (Ssd) 能夠為 8 10000 RPM 機械磁片磁碟機提供相同的可用空間及類似的效能。   |
|網路   |1個雙埠網路介面卡，可使用 1 Gbps 或以上 (2 網路介面卡，但必須以單一 MAC 位址和單一 IP) 位址進行分組。  <br/> 前端伺服器、後端伺服器、Standard Edition 伺服器及 Persistent Chat server **不** 支援雙重或多穴設定。 <br/> 只要未對作業系統公開，而且正用來監視和管理伺服器硬體，您就可以使用無頻帶管理系統，例如 DRAC 或 ILO。 此案例不會組成多穴伺服器，而且支援此案例。   |
   
Edge Server、獨立轉送伺服器、影片 Interop 伺服器及 Director 的建議硬體：
  
|硬體元件|建議|
|:-----|:-----|
|CPU   |64位雙處理器、四核心、2.26 ghz (GHz) 或更高版本。  <br/> 商務用 Skype Server 2015 角色不支援 Intel Itanium 處理器。   |
|記憶體   |16 gb。   |
|磁片   |可  <br/> •4個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間 (磁片應該位於2倍的 RAID 1 設定) 中。  <br/> 或  <br/> •固態磁片磁碟機 (Ssd) 能夠為 4 10000 RPM 機械磁片磁碟機提供相同的可用空間及類似的效能。   |
|網路   |1個雙埠網路介面卡，可使用 1 Gbps 或以上 (2 網路介面卡，但必須以單一 MAC 位址和單一 IP) 位址進行分組。  <br/> 視頻 Interop 伺服器及 Director **不** 支援雙重或多穴設定。 <br/> Edge server 需要兩個網路介面為雙埠網路介面卡、1 Gbps 或更高的 (或兩個配對的網路介面卡（總共四個），每一組都是以單一 MAC 位址和單一 IP 位址組成，每個組的總數都是兩對) 。  <br/> 在獨立轉送伺服器上，安裝額外的網路介面卡 (Nic) 以允許設定特定 PSTN IP 位址的支援。   |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的作業系統
<a name="OS"> </a>

硬體就緒之後，您必須在作業系統 (作業系統) 上安裝作業系統。 這些是可讓您安裝及順利使用商務用 Skype Server 2015 的作業系統。
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Windows Server 2019 (您需要商務用 Skype 累積更新9或更新版本) 。  |Windows Server 2016 (需要商務用 Skype 累計更新5或更新版本。 如需詳細資訊，請檢查 [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))    |
|Windows Server 2012 已安裝所有必要更新的 R2 資料中心作業系統。   |Windows Server 2012 已安裝所有必要更新的 R2 Standard OS。   |
|安裝所有必要更新的 Windows Server 2012 Datacenter 作業系統。   |安裝所有必要更新的 Windows Server 2012 Standard 作業系統。   |
   
如果不在此清單上，則不會正確運作，請不要嘗試商務用 Skype Server 2015 的新安裝。

> [!NOTE]
> Lync Server 2013 不支援就地升級作業系統。 您必須部署個別的集區，並將使用者遷移至具有不同作業系統的新集區。 集區中的所有伺服器都必須具有相同的 OS 版本。
  
> [!NOTE]
> 您可能已注意到 Windows Server 2008 R2 不在此清單上。 這是因為建議您 Windows Server 2012 R2 用於 SFB 的所有新伺服器。 當您已安裝具有 Lync Server 2013 的現有伺服器時，您應該只使用 Windows Server 2008 R2，而且您要進行就地升級。 Windows Server 2008 R2 已達1/13/2015 的主流支援週期結束，並會在1/14/2020 上達到其支援生命週期的結尾。
  
除了最新的 service pack 之外，您還需要確定已安裝下列更新（如有相關的更新）：
  
- 若為 Windows Server 2012，請在升級之前安裝 KB 文章2858668。 請在[這裡取得](https://support.microsoft.com/kb/2858668/)。
    
- 如果您有 Windows Server 2012 R2，請先安裝 KB 文章2982006，再進行升級。 可[在這裡找到](https://support.microsoft.com/kb/2982006/)。
    
- 如果您是在 Windows Server 2008 R2 box 上進行升級 (請參閱上述附注) ，然後您將需要先安裝 KB 文章2533623。 [其位於此連結](https://support.microsoft.com/kb/2533623/)。
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>可搭配商務用 Skype Server 2015 的後端資料庫
<a name="DBs"> </a>


安裝商務用 Skype Server 2015 Standard Edition 時，您會同時自動安裝 SQL Server 2014 Express (64 位版本) 。
  
商務用 Skype Server 2015 Enterprise Edition 稍複雜一些，但支援的清單如下 (所有是64位版本，您會注意到，請勿使用32位版本) ：
  
|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-位版本) ，我們建議使用最新的 service pack 來執行。  |Microsoft SQL Server 2017 Enterprise (64-位版本) ，我們建議使用最新的 service pack 來執行。  |Microsoft SQL Server 2016 Enterprise (64-位版本) Service Pack 1 或更新版本，且您必須使用商務用 Skype 累計更新7或更新版本執行 ([下載商務用 Skype 累計更新](https://support.microsoft.com/help/3061064)) 。   |Microsoft SQL Server 2014 Enterprise (64-位版本) ，您必須以累積更新6或更新版本執行 ([下載累計更新 6](https://support.microsoft.com/kb/3031047/)) 。   |Microsoft SQL Server 2012 Enterprise (64-位版本) ，我們建議使用最新的 service pack 來執行。   |
|Microsoft SQL Server 2019 Standard (64-bit edition) ，我們建議使用最新的 service pack 來執行。  |Microsoft SQL Server 2017 Standard (64-bit edition) ，我們建議使用最新的 service pack 來執行。  |Microsoft SQL Server 2016 Standard (64-bit edition) Service Pack 1 或更新版本，且您必須商務用 Skype 累積更新7或更新版本執行 ([下載商務用 Skype 累計更新](https://support.microsoft.com/help/3061064)) 。   |Microsoft SQL Server 2014 Standard (64-bit edition) ，必須以累積更新6或更新版本執行 ([下載累計更新 6](https://support.microsoft.com/kb/3031047/)) 。   |Microsoft SQL Server 2012 Standard (64-bit edition) ，我們建議使用最新的 service pack 來執行。   |
   
如果您沒有看到您想要使用的 SQL Server 版本，則無法使用它。
  
- 您也需要安裝監控伺服器角色的 SQL Server Reporting Services。
- 在連接良好的 SQL 後端，與商務用 Skype 前端的連線應該是本機的，而不是穿過低速連結。 
- 不支援在兩個以上的集區之間共用 SQL 後端。

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 儲存
會議內容檔案（例如 PowerPoint 簡報）會封存為附件。 如果您想要將商務用 Skype 封存資料儲存 Exchange 相容性資料，您必須使用 Exchange 進行 Exchange 部署，並確保儲存大小上限支援會議內容檔案的儲存。 使用 Microsoft Exchange 整合選項部署及啟用封存之前，必須先部署 Exchange。 
    
如果您選擇使用 Exchange 儲存區，除非您有商務用 Skype 的使用者不在 Exchange 伺服器上，否則不需要部署個別的 SQL Server 資料庫進行封存。 如果您使用 Microsoft Exchange 整合選項部署封存，商務用 Skype 封存資料只會儲存在 Exchange 伺服器上之使用者的 Exchange 相容性資料。 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中封存的硬體和軟體需求
  
封存並非定義的伺服器角色，您不需要安裝個別的伺服器進行封存。 在每個 Enterprise Edition 前端集區和每一部 Standard Edition 伺服器上，會自動安裝及啟用統一資料收集代理程式。 您必須使用拓撲產生器來啟用及發行您的封存拓撲。
    
封存使用商務用 Skype Server 檔案存放區來暫時儲存會議內容檔案，所以您不會設定個別的檔案存放區進行封存。
    
不需要 Microsoft Message 佇列。
    
您將需要設定封存儲存的基礎結構。 這包括使用 SQL Server 選擇 Exchange 或封存儲存區。   商務用 Skype Server 的封存基礎結構需求與部署商務用 Skype Server 相同。 如需詳細資訊，請參閱[商務用 Skype 環境的需求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
> [!NOTE]
> 若要支援非位於 Exchange server 上的使用者，或是不想要使用 Microsoft Exchange 整合選項，您必須使用64位 SQL Server 資料庫部署封存儲存區。 
    
在部署及啟用封存之前，您必須先設定 SQL Server 平臺。 若要用來發行拓撲的帳戶具有適當的系統管理員許可權，您可以在發行拓撲時，建立封存資料庫 (LcsLog) 。 您也可以稍後再建立資料庫（包括安裝程式的一部分）。 如需 SQL Server 的詳細資訊，請參閱[SQL Server 檔](/sql/sql-server/)。
    
封存的負載增加可能會很大。 因此，您應該確定啟用封存之前端伺服器的磁碟空間已夠用。

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 鏡像、SQL 集群及 SQL Always On

您可以使用 SQL 鏡像或 SQL 使用商務用 Skype Server 2015 的叢集，支援此功能。 SQL 鏡像是透過商務用 Skype Server 拓撲產生器來設定。 如果您想要設定 SQL 叢集，請在 SQL Server 中完成。
  
請確定您有 SQL 叢集的主動/被動設定，如此一來，what's 支援。 請勿與其他任何 SQL 實例共用被動節點。
  
您可以針對容錯移轉叢集進行下列作業：
  
雙節點：
  
- Microsoft SQL Server 2019 Standard (64-bit edition) ，我們建議使用最新的 service pack 來執行。

- Microsoft SQL Server 2017 Standard (64-bit edition) ，我們建議使用最新的 service pack 來執行。

- Microsoft SQL Server 2016 Standard (64-bit edition) Service Pack 1 或更新版本。 我們建議使用最新的 service pack 執行。

- Microsoft SQL Server 2014 Standard (64-bit edition) ，我們建議使用最新的 service pack 來執行。
    
-  Microsoft SQL Server 2012 Standard (64-bit edition) ，我們建議使用最新的 service pack 來執行。

十六節點：

- Microsoft SQL Server 2019 Enterprise (64-位版本) ，我們建議使用最新的 service pack 來執行。

- Microsoft SQL Server 2017 Enterprise (64-位版本) ，我們建議使用最新的 service pack 來執行。

- Microsoft SQL Server 2016 Enterprise (64-位版本) Service Pack 1 或更新版本。 我們建議使用最新的 service pack 執行。
  
- Microsoft SQL Server 2014 Enterprise (64-位版本) ，我們建議使用最新的 service pack 來執行。
    
- Microsoft SQL Server 2012 Enterprise (64-位版本) ，我們建議使用最新的 service pack 來執行。

> [!IMPORTANT]
> 若要進行升級，我們確實想要在升級之前，至少要有 SQL Server 2012 SP1 安裝的服務。 如果您想要立即下載它，以下是 SP1[的連結](https://www.microsoft.com/download/details.aspx?id=35575)。
  
如果您需要深入瞭解 SQL 鏡像，我們有商務用 Skype Server 2015 主題的後端伺服器高可用性。 設定商務用 Skype Server 2015 SQL Server 叢集的步驟，讓群集做好準備。 在 SQL 的容錯移轉叢集中也有進一步的連結，針對[2014](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation)、 [2012](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))及[2008](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105))。
  
> [!NOTE]
> 2015版本的新功能支援 SQL Always On。 您也可以在[商務用 Skype Server 2015 主題的後端伺服器高可用性中](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)閱讀相關資訊。

> [!NOTE]
> SQL 鏡像可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) 及 SQL 容錯移轉叢集方法，都是商務用 Skype Server 2019 的首選。  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>在商務用 Skype Server 2015 部署之前應該安裝的軟體
<a name="Software"> </a>

您需要針對執行商務用 Skype Server 2015 的任何伺服器安裝或設定某些事項，如下所列。 之後是特定伺服器角色的其他需求。

  
 **所有伺服器：**
  
|軟體/角色|詳細資料|
|:-----|:-----|
|Windows PowerShell 3.0   |所有商務用 Skype Server 伺服器都需要安裝 Windows PowerShell 3.0。  <br/> •如果您是在 Windows Server 2012 或 Windows Server 2012 R2 上進行安裝，您已設定，因為已存在。  <br/> •如果您是在 Windows Server 2008 R2 上進行升級，您可以下載[Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595)以取得。 <br/> **提示：** 當您在該 PowerShell 上有正確的，請移至 PowerShell 提示字元並輸入 `$PSVersionTable` ，以確認 BuildVersion 6.2.9200.0 或更新版本。 這應該會顯示您需要的資訊。   |
|Microsoft .NET Framework   |WCF 服務是安裝成 Windows 功能的 **功能**，在 [**伺服器管理員**] 下，不需要下載。 <br/> •您必須確定當您安裝此功能時，或是否已安裝此功能，也會檢查並安裝 **HTTP 啟用** 選項，如下所示： <br/> ![顯示 [.NET Framework 4.5 功能] 底下的 [HTTP 啟用] 選項的螢幕擷取畫面。](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> 如果您還有其他的彈出提示，請不要擔心，您必須安裝一些其他事項，才能安裝 HTTP 啟用。 這是正常的，請按一下 [確定] 並繼續。 如果您未看到此快顯視窗，請假設已安裝這些專案，然後繼續。  <br/> 安裝 Windows Server 2012 R2 或 Windows Server 2016 時，通常會安裝 Microsoft .NET Framework。 商務用 Skype Server 與下列 Microsoft .NET Framework 版本搭配使用：  <br/> • .NET 3。5  <br/> • .NET 4。5  <br/> • .NET 4.6 x  <br/> •適用于商務用 Skype Server CU 5 或更新版本的 .net 4.7.1 ()   <br/> •適用于商務用 Skype Server CU 6 或更新版本的 .net 4.7.2 版 ()   <br/>  •適用于商務用 Skype Server CU 9 或更新版本的 .net 4.8 ()  <br/>  .NET Framework 3.5 可能預設會安裝在您的 Windows Server 2008 R2 電腦上 (在升級) 之前，請務必檢查，但實際上不會在 Windows Server 2012/Windows Server 2012 R2 server (上安裝) 的新安裝。 若要將其加入，您必須存取安裝磁片磁碟機或媒體 (Windows 伺服器安裝所在的位置，或是現在) 安裝檔。 接下來，將其安裝為伺服器管理員的功能，並指向安裝媒體 (特別是在要求時) **\sources\sxs** 資料夾，然後繼續安裝。  |
|媒體基礎   |Windows Server 2016，請 Windows Server 2012 和 Windows Server 2012 R2 Windows 媒體格式執行時間與 Microsoft Media Foundation 一起安裝。  <br/> 用於會議的所有前端伺服器和 Standard Edition 伺服器都必須 Windows 媒體格式執行時間，才能執行 Windows 媒體音訊 () 。通話駐留、宣告及回應群組應用程式會對宣告和音樂播放的檔案。   |
|Windows Identity Foundation  <br/> |我們需要 Windows 身分識別 Foundation 3.5，以支援商務用 Skype Server 2015 的伺服器對伺服器驗證案例。  <br/> •針對 Windows Server 2012 和 Windows Server 2012 R2，不需要下載任何專案。 開啟 [ **伺服器管理員**]，然後移至 [ **新增角色及功能] 嚮導**。 **Windows 身分識別 Foundation 3.5** 會列于 [**功能**] 區段中。 如果已勾選，表示您已是好的。 否則選取它，然後按一下 [下一步] 進入 [ **安裝** ] 按鈕。  |
|遠端伺服器管理工具   |角色管理工具： AD DS 和 AD LDS 工具   |
   
 **前端伺服器和 Standard Edition 伺服器也需要：**
  
|軟體/角色|詳細資料|
|:-----|:-----|
|Internet Information Services (IIS)   |所有前端伺服器及所有 Standard Edition 伺服器都需要有 IIS，且選取下列模組：  <br/> •常見的 HTTP 功能：預設檔、HTTP 錯誤、靜態內容  <br/> •健康情況與診斷： HTTP 記錄、記錄工具、追蹤  <br/> •效能：靜態內容壓縮，動態內容壓縮  <br/> •安全性：要求篩選，用戶端憑證對應驗證，Windows 驗證  <br/> •應用程式開發： .net 擴充性3.5，.net 擴充性4.5，ASP.NET 3.5，ASP.NET 4.5，isapi Extensions，isapi 篩選器  <br/> •管理工具： IIS 管理主控台、IIS 管理腳本及工具  <br/> 我們也應注意，您也需要進行匿名存取，但是當您安裝 IIS 時，您沒有在清單中選取的位置。   |
|Windows Media Format Runtime   | 若為 Windows Server 2016、Windows Server 2012 及 Windows Server 2012 R2，您必須在 **伺服器管理員** 中安裝 **Media Foundation** 功能。 現在，您實際上可以在沒有此安裝的情況下啟動商務用 Skype Server 2015 安裝，但在商務用 Skype Server 2015 安裝繼續之前，系統會提示您安裝它，然後重新開機伺服器。 在一段時間後最好這樣做。  |
|Silverlight   |您可以在 [此連結](https://www.microsoft.com/silverlight/)上安裝最新版的 Silverlight。   |
   
> [!NOTE] 
> 如果您使用負載平衡器，您可能也需要啟用瀏覽目錄功能。 否則，空白頁面會載入負載平衡器可能會考慮失敗的情況。 

為了協助您完成，您可以執行下列範例 PowerShell 腳本，以自動化此程式：

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 命令會尋找特定順序的來源檔案。 如果您是線上，命令就會存取 Windows 更新。 不過，如果您已離線，您必須確定可在命令中使用的來源檔案。 如需使用 PowerShell 來安裝角色及功能的詳細資訊，請參閱安裝[或卸載角色、角色服務或功能](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11))。在您安裝必要條件之後，請不要忘記執行 Windows 更新，即使您使用 PowerShell 命令也是一樣。

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
    
 (如果您想知道，它就是與前端伺服器及 Standard Edition 伺服器相同的模組，並將動態內容壓縮和管理工具保留在一起。 ) 
  
以下為此，我們也有一些 PowerShell 程式碼：
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Persistent Chat Servers 也需要：**
  
訊息佇列，也稱為 MSMQ。 這是 Windows 伺服器元件，您可以在 [伺服器管理員] 的 [功能] 區段中安裝它。 若要進一步閱讀此資訊，請參閱 [安裝和管理訊息佇列](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11))。
  
 **最後思維：**
  
請不要安裝任何 Microsoft Internet Security and 加速 (ISA) Server 用戶端軟體或任何其他 Winsock 分層服務提供者 (LSP) 軟體 (任何協力廠商防火牆或防病毒網路檢查軟體會包含在任何前端伺服器或獨立轉送伺服器上) 。 安裝軟體時，看到的媒體流量效能不良。
