---
title: 商務用 Skype Server 的後端伺服器高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 瞭解商務用 Skype Server 支援的後端伺服器高可用性選項，包括 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例、資料庫鏡像，以及 SQL 容錯移轉叢集。
ms.openlocfilehash: 4c814e525b3a1d0900e7162255ec4d7e86d79605
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888612"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>商務用 Skype Server 的後端伺服器高可用性
 
瞭解商務用 Skype Server 支援的後端伺服器高可用性選項，包括 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例、資料庫鏡像，以及 SQL 容錯移轉叢集。
  
若要提升後端伺服器的高可用性，您有四個選項：
  
- 資料庫鏡像
    
- AlwaysOn 可用性群組
    
- AlwaysOn 容錯移轉叢集實例（FCI）
    
- SQL 容錯移轉叢集
    
使用其中一個解決方案是選用的，但建議維持貴組織的業務連續性。 否則，只有單一資料庫伺服器會出現問題，才能導致大量的商務用 Skype 伺服器資料遺失。 
  
您可以使用 [拓撲產生器] 來設定資料庫鏡像。 針對 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例或 SQL 容錯移轉叢集，您可以使用 SQL Server 建立高可用性方案，然後您就可以使用拓撲產生器將它與前端池建立關聯。
  
如果您在與其他用於災難復原的前端池搭配使用後端伺服器高可用性，您應該在兩個池中使用相同的後端高可用性方案。 
  
## <a name="database-mirroring"></a>資料庫鏡像

商務用 Skype 伺服器支援使用下列資料庫軟體進行鏡像：
  
- SQL Server 2019 （企業版和標準版）

- SQL Server 2017 （企業版和標準版）

- SQL Server 2016 （企業版和標準版）

- SQL Server 2014 （企業版和標準版）
    
- SQL Server 2012 SP2 與 CU2 （企業版和標準版）
    

> [!NOTE]
> 在商務用 Skype Server 2015 中提供 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。 在商務用 Skype Server 2019 中，AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例（FCI）和 SQL 容錯移轉叢集方法都是唯一受支援的選項。
    
商務用 Skype Server 的後端伺服器高可用性不支援非同步資料庫鏡像。 在本檔的其餘部分中，資料庫鏡像代表同步資料庫鏡像，除非明確指出。 
  
當您在前臺文件庫中部署資料庫鏡像時，會對池中的所有商務用 Skype 伺服器資料庫進行鏡像，包括中央管理儲存體（如果它位於此池中），以及回應群組應用程式資料庫及通話駐留應用程式資料庫（如果那些應用程式正在池中執行）。 
  
使用資料庫鏡像，您不需要針對伺服器使用共用儲存空間。 每個伺服器都會在本機儲存空間中保留自己的資料庫複本。 
  
您可以選擇部署含或不含見證的資料庫鏡像。 我們建議使用見證，因為它可讓後端伺服器的容錯移轉自動進行。 否則，系統管理員必須手動喚醒呼叫容錯移轉。 請注意，即使已部署見證，系統管理員也可以在必要時手動呼叫後端伺服器容錯移轉。
  
如果您使用見證，您可以針對多對後端伺服器使用單一見證。 Witnesses 和對後端伺服器之間沒有嚴格的1:1 對應。 針對多對後端伺服器使用單一見證伺服器的部署，不具彈性，因為每個後端伺服器對都有單獨的見證。 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>規劃後端伺服器鏡像的指導方針

一般來說，在具有見證的兩台後端伺服器之間設定 SQL 鏡像需要下列事項：
  
- 主伺服器版本的 SQL Server 必須支援 SQL 鏡像。
    
- [主要]、[鏡像] 和 [見證伺服器] （如果已部署）必須有相同版本的 SQL Server。 
    
- 主要和鏡像必須擁有相同版本的 SQL Server。 見證可能會有不同的版本。
    
如需針對見證角色支援哪些 SQL 版本的 SQL 最佳做法，請參閱 MSDN 文件庫中的「[資料庫鏡像見證](https://go.microsoft.com/fwlink/p/?LinkId=247345)」。
  
在佈建服務器鏡像之前，您必須先正確設定 SQL 資料庫許可權。 如需詳細資訊，請參閱[設定資料庫鏡像或 AlwaysOn 可用性群組的登入帳戶（SQL Server）](https://go.microsoft.com/fwlink/p/?LinkId=268454)」。
  
有了 SQL 鏡像，資料庫復原模式永遠都設為**Full**，這表示您必須密切監視事務日誌大小，並定期備份事務日誌，以免在後端伺服器上耗盡磁碟空間。 事務記錄備份的頻率取決於記錄的增長率，而這取決於前端池中使用者活動所產生的資料庫事務。 我們建議您決定 Lync 部署工作負載預期的事務日誌增長量，讓您可以據此進行規劃。 下列文章提供有關 SQL 備份與記錄管理的其他資訊：
  
> [!IMPORTANT]
> 只有在主要、鏡像和見證（如果需要）伺服器都屬於同一個網域時，才支援使用拓撲建立器或 Cmdlet 來設定及移除 SQL 鏡像。 如果您想要在不同網域中的伺服器之間設定 SQL 鏡像，請參閱您的 SQL Server 檔。 

> [!NOTE]
> 在商務用 Skype Server 2015 中提供 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。 使用商務用 Skype Server 2019 時，AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例（FCI）和 SQL 容錯移轉叢集方法都是可取的。
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>自動後端伺服器容錯移轉與資料庫鏡像的恢復時間

針對資料庫鏡像的自動後端容錯移轉，「恢復時間目標」工程目標（RTO）是5分鐘。 由於同步處理資料庫鏡像，我們不會在回退端伺服器失敗期間預計資料遺失，除非當前端伺服器和後端伺服器在伺服器間移動資料時，在一般情況下，不會發生這種情況。 針對復原點目標（RPO）的工程目標是5分鐘。
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>在後端伺服器失敗時使用資料庫鏡像的使用者體驗

故障期間的使用者體驗取決於失敗的性質，以及拓撲。
  
如果您使用資料庫鏡像且已設定見證伺服器，則主體會失敗，後端伺服器容錯移轉會自動及快速進行。 作用中的使用者不應該注意到他們的日常會話會有太大的中斷。
  
如果沒有設定見證，系統會在管理員手動呼叫容錯移轉時需要一些時間。 在這段時間內，作用中的使用者可能會受到影響。 它們會在大約30分鐘內繼續正常的會話。 如果主版仍未還原，或系統管理員沒有失敗轉移至備份，則使用者會切換到復原模式，這表示他們無法執行需要 Lync 伺服器上的永久變更的工作（例如新增連絡人）。
  
如果主體和鏡像後端伺服器失敗，或其中一個伺服器與見證伺服器發生故障，後端伺服器將變為無法使用（即使是仍在運作的主體）。 在這種情況下，作用中的使用者會在一段時間後切換為復原模式。
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn 可用性群組與 AlwaysOn 容錯移轉叢集實例

商務用 Skype 伺服器支援 AlwaysOn 可用性群組，只能作為主動/被動群組，非作用中/作用中。 
  
若要使用 AlwaysOn 可用性群組或 AlwaysOn 容錯移轉叢集實例，您必須先使用 SQL Server 來設定及設定高可用性方案。 然後，您就可以使用 [拓撲建立器]，將它與 [前端] 池建立關聯。

商務用 Skype 伺服器支援使用下列資料庫軟體的 AlwaysOn：

- SQL Server 2019 企業版

- SQL Server 2019 標準版有限制，請參閱下方的注意事項

- SQL Server 2017 企業版

- SQL Server 2017 標準版有限制，請參閱下方的注意事項

- SQL Server 2016 企業版

- SQL Server 2016 標準版有限制，請參閱下方的注意事項

- SQL Server 2014 企業版
    
- SQL Server 2012 SP2 及 CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019、2017和2016是商務用 Skype Server 2019 所支援的唯一版本。

> [!NOTE]
> 在 SQL 2016、2017和2019標準版中**不**支援 Alwayson 可用性群組，但您可以使用 [永不在容錯移轉叢集] 實例。 若要深入瞭解，請參閱[SQL Server 2016 的版本和支援的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)。
  
> [!IMPORTANT]
> 多個 AlwaysOn 可用性群組實例的實例名稱必須相同。 
  
如需部署 AlwaysOn 可用性群組的步驟，請參閱[在商務用 Skype server 的後端伺服器上部署 AlwaysOn 可用性群組](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。
  
## <a name="sql-server-failover-clustering"></a>SQL Server 容錯移轉叢集

商務用 Skype 伺服器支援使用下列資料庫軟體的 SQL Server 容錯移轉叢集：
  
- SQL Server 2019 （企業版和標準版）

- SQL Server 2017 （企業版和標準版）

- SQL Server 2016 （企業版和標準版）

- SQL Server 2014 （企業版和標準版）
    
- SQL Server 2012 SP2 與 CU2 （企業版和標準版）

若要使用 SQL 容錯移轉叢集，您應該先設定並設定 SQL Server 群集，然後再部署您的前臺端池。 如需 SQL Server 2012 中容錯移轉叢集的最佳做法及設定指示[https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)，請參閱。

> [!NOTE]
> SQL Server 2019、2017和 SQL Server 2016 是商務用 Skype Server 2019 所支援的唯一版本。
    
若要使用 SQL 容錯移轉叢集，您應該先設定並設定 SQL Server 群集，然後再部署您的前臺端池。 如需 SQL Server 2014 和2016中容錯移轉叢集的最佳做法及設定指示[https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)，請參閱。 針對 SQL Server 2008 中的容錯移轉叢集[https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)，請參閱。
  
當您安裝 SQL Server 時，您應該安裝 SQL Server Management Studio 來管理資料庫及記錄檔位置的位置。 當您安裝 SQL Server 時，系統會將 SQL Server Management Studio 作為選用元件進行安裝。
  
