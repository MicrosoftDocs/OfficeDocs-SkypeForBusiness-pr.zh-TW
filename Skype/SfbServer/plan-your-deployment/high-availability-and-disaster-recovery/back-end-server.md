---
title: 商務用 Skype Server 中的後端伺服器高可用性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 深入瞭解商務用 Skype Server 中支援的後端伺服器高可用性選項，包括 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 31ec37d898bd1f04c07142de1849928656f3238e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119372"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>商務用 Skype Server 中的後端伺服器高可用性
 
深入瞭解商務用 Skype Server 中支援的後端伺服器高可用性選項，包括 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例、資料庫鏡像及 SQL 容錯移轉叢集。
  
為增強後端伺服器的高可用性，您有四個選項：
  
- 資料庫鏡像
    
- AlwaysOn 可用性群組
    
- AlwaysOn (FCI 的容錯移轉叢集實例) 
    
- SQL 容錯移轉叢集
    
使用其中一種解決方案是選用的，但建議維護貴組織的業務持續性。 否則，擁有單一資料庫伺服器會導致大量商務用 Skype Server 資料遺失。 
  
您可以使用 [拓撲產生器] 來設定資料庫鏡像。 針對 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例或 SQL 容錯移轉叢集，您可以使用 SQL Server 建立高可用性解決方案，然後您就可以使用拓撲產生器，將其與前端集區建立關聯。
  
如果您在與另一個前端集區配對的前端集區上使用後端伺服器高可用性，以進行嚴重損壞修復，您應該在兩個集區中使用相同的後端高可用性解決方案。 
  
## <a name="database-mirroring"></a>資料庫鏡像

商務用 Skype 伺服器支援鏡像下列資料庫軟體：
  
- SQL Server 2019，Enterprise Edition 和 Standard Edition

- SQL Server 2017，Enterprise Edition 和 Standard Edition

- SQL Server 2016，Enterprise Edition 和 Standard Edition

- SQL Server 2014，Enterprise Edition 和 Standard Edition
    
- SQL Server 2012 SP2 和 CU2，Enterprise Edition 和 Standard Edition
    

> [!NOTE]
> 在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) 及 SQL 容錯移轉叢集方法是商務用 Skype Server 2019 唯一支援的選項。
    
商務用 Skype Server 中的後端伺服器高可用性不支援非同步資料庫鏡像。 在本文的其餘部分中，資料庫鏡像是指同步資料庫鏡像，除非明確指出。 
  
當您在前端集區中部署資料庫鏡像時，集區中的所有商務用 Skype Server 資料庫都會進行鏡像，包括中央管理存放區（如果位於此集區中）以及回應群組應用程式資料庫及通話駐留應用程式資料庫（如果集區中執行這些應用程式）。 
  
使用資料庫鏡像，您不需要使用伺服器的共用儲存區。 每一部伺服器都會在本機儲存區中保留其資料庫複本。 
  
您可以選擇使用或不使用見證來部署資料庫鏡像。 我們建議使用見證，因為它可讓後端伺服器的容錯移轉成為自動。 否則，管理員必須手動呼叫容錯移轉。 請注意，即使部署見證，管理員也可以手動叫用後端伺服器容錯移轉（如有必要）。
  
如果您使用見證，您可以對多組的後端伺服器使用單一見證。 Witnesses 和後端伺服器對之間沒有嚴格的1:1 對應。 對多對後端伺服器使用單一見證的部署，並不像拓撲搭配每一組後端伺服器對具有個別的見證。 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>規劃後端伺服器鏡像的指導方針

一般而言，使用見證伺服器在兩個後端伺服器間設定 SQL 鏡像，需要下列各項：
  
- 主伺服器的 SQL Server 版本必須支援 SQL 鏡像。
    
- 主要、鏡像與見證伺服器 (若已部署) 必須具有相同的 SQL Server 版本。 
    
- 主要與鏡像伺服器必須具有相同的 SQL Server 版本，見證伺服器可能有不同的版本。
    
如需有關見證角色支援哪些 SQL 版本的 SQL 最佳作法，請參閱 MSDN Library 中的「  [資料庫鏡像見證](/sql/database-engine/database-mirroring/database-mirroring-witness) 」。
  
設定伺服器鏡像之前，必須先正確設定 SQL 資料庫許可權。 如需詳細資訊，請參閱  [設定資料庫鏡像的登入帳戶或 AlwaysOn 可用性群組 (SQL Server) ]](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)。
  
有了 SQL 鏡像，資料庫復原模式會一律設為 **[完整]**，這表示您必須密切監控交易紀錄的大小並定期備份交易紀錄，以避免用盡後端伺服器上的磁碟機空間。交易記錄的備份頻率取決於記錄的成長率，即根據使用者在前端集區上活動所發生的資料庫交易。建議您針對 Lync 部署工作負載判斷交易記錄的預期成長率，以便進行相應的規劃。下列文章提供 SQL 備份以及記錄管理的其他資訊：
  
> [!IMPORTANT]
> 只有當主要、鏡像及)  (見證伺服器都屬於相同的網域時，才支援使用拓撲產生器或 Cmdlet 來設定及移除 SQL 鏡像。 若要在不同網域的伺服器間設定 SQL 鏡像，請參閱 SQL Server 文件。 

> [!NOTE]
> 在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及使用商務用 Skype Server 2019 的首選 SQL 容錯移轉叢集方法。
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>使用資料庫鏡像的自動後端伺服器容錯移轉的復原時間

若要使用資料庫鏡像進行自動後端容錯移轉，恢復時間目標的工程目標 (RTO) 為5分鐘。 由於同步資料庫鏡像，在後端伺服器失敗的情況下，不會預見到資料遺失，但在伺服器間移動資料時，一般情況下，當前端伺服器和後端伺服器都同時停機時，並不會發生很少的情況。 復原點目標的工程目標 (RPO) 為5分鐘。
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>使用資料庫鏡像的後端伺服器失敗期間的使用者體驗

失敗期間的使用者經驗取決於失敗的性質和拓撲。
  
如果您使用資料庫鏡像並已設定見證，但主體失敗，則後端伺服器容錯移轉會自動且快速地進行。 作用中使用者應該不會注意到其持續進行的會話中斷很大的狀態。
  
若未設定見證，系統管理員必須花一些時間來手動呼叫容錯移轉。 在這段時間內，作用中的使用者可能會受到影響。 他們會將其會話繼續正常等候30分鐘。 若主伺服器仍未還原，或系統管理員尚未容錯移轉至備份，使用者會切換至復原模式，也就是說，他們無法執行在 Lync Server (（例如新增連絡人) ）上需要持續變更的工作。
  
如果主體和鏡像的後端伺服器失敗，或其中一個伺服器和見證失敗，則即使是仍在運作) 主體，後端伺服器也會無法使用 (。 在此情況下，作用中的使用者會在一段時間後切換至復原模式。
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn 可用性群組和 AlwaysOn 容錯移轉叢集實例

商務用 Skype 伺服器僅支援 AlwaysOn 可用性群組為主動/被動，非主動/主動。 
  
若要使用 AlwaysOn 可用性群組或 AlwaysOn 容錯移轉叢集實例，您必須先使用 SQL Server 來設定及設定高可用性解決方案。 然後您就可以使用拓撲產生器，將它與前端集區產生關聯。

商務用 Skype Server 支援下列資料庫軟體的 AlwaysOn：

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition 具有限制，請參閱以下附注

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition 具有限制，請參閱以下附注

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition 具有限制，請參閱以下附注

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 和 CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019、2017及2016是商務用 Skype Server 2019 所支援的唯一版本。

> [!NOTE]
> 在 SQL 2016、2017及 2019 Standard Edition 中， **不** 支援 Always On 可用性群組，但您可以使用 Always On 容錯移轉叢集實例。 若要深入瞭解，請參閱 [SQL Server 2016 的版本及支援的功能](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) 。
  
> [!IMPORTANT]
> 多個 AlwaysOn 可用性群組實例的實例名稱必須相同。 
  
如需部署 AlwaysOn 可用性群組的步驟，請參閱 [在商務用 Skype server 中的後端伺服器上部署 AlwaysOn 可用性群組](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。
  
## <a name="sql-server-failover-clustering"></a>SQL Server 容錯移轉叢集

商務用 Skype Server 支援具有下列資料庫軟體的 SQL Server 容錯移轉叢集：
  
- SQL Server 2019，Enterprise Edition 和 Standard Edition

- SQL Server 2017，Enterprise Edition 和 Standard Edition

- SQL Server 2016，Enterprise Edition 和 Standard Edition

- SQL Server 2014，Enterprise Edition 和 Standard Edition
    
- SQL Server 2012 SP2 和 CU2，Enterprise Edition 和 Standard Edition

若要使用 SQL 容錯移轉叢集，您應該先安裝及設定 SQL Server 叢集，再部署前端集區。 如需 SQL Server 2012 中容錯移轉叢集的最佳作法和設定指示，請參閱 [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。

> [!NOTE]
> SQL Server 2019、2017及 SQL Server 2016 是商務用 Skype Server 2019 所支援的唯一版本。
    
若要使用 SQL 容錯移轉叢集，您應該先安裝及設定 SQL Server 叢集，再部署前端集區。 如需 SQL Server 2014 和2016中容錯移轉叢集的最佳作法和設定指示，請參閱 [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。 如需 SQL Server 2008 中的容錯移轉叢集，請參閱 [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) 。
  
在安裝 SQL Server 時，應安裝 SQL Server Management Studio 以管理資料庫的位置與記錄檔位置。 您在安裝 SQL Server 時，可以選用性元件的形式安裝 SQL Server Management Studio。
