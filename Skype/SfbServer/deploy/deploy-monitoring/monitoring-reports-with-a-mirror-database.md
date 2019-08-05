---
title: 在商務用 Skype Server 中將監控報告與鏡像資料庫建立關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '摘要: 瞭解如何將監視報告與商務用 Skype 伺服器所使用的鏡像資料庫建立關聯。'
ms.openlocfilehash: 0727a278b87edd0b3666b04d169dcd3460c8215c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186592"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>在商務用 Skype Server 中將監控報告與鏡像資料庫建立關聯 
 
**摘要:** 瞭解如何將監視報告與商務用 Skype 伺服器所使用的鏡像資料庫建立關聯。
  
## <a name="monitor-reports-with-a-mirror-database"></a>使用鏡像資料庫監控報表

如果您為監視資料庫設定鏡像, 則在發生容錯移轉時, 鏡像資料庫將會作為主要資料庫。 不過, 如果您使用商務用 Skype Server Monitoring 報告, 且發生容錯移轉, 您可能會發現監視報告無法連線到鏡像資料庫。 這是因為, 當您安裝監視報告時, 只會指定主要資料庫的位置;您不會指定鏡像資料庫的位置。
  
若要取得監視報告以自動容錯移轉到鏡像資料庫, 您必須將鏡像資料庫新增為「容錯移轉夥伴」, 以供監視報告所使用的兩個資料庫 (一個資料庫用於呼叫詳細資料記錄資料, 另一個資料庫的品質為體驗 (QoE) 資料)。 (請注意, 在您安裝監控報告之後, 應該執行此步驟)。您可以手動編輯這兩個資料庫所使用的連線字串值, 以新增容錯移轉合作夥伴資訊。 若要這樣做, 請完成下列程式:
  
1. 使用 Internet Explorer 開啟 [ **SQL Server Reporting Services** ] 首頁。 [報表服務] 首頁 URL 包括:
    
   - [ **Http:** prefix]。
    
   - 安裝 Reporting Services 的電腦的完整功能變數名稱 (FQDN) (例如, **atl-sql-001.litwareinc.com**)。
    
   - 字元字串 **/Reports_**。
    
   - 安裝監視報告的資料庫實例名稱 (例如, **archinst**)。
    
     例如, 如果 SQL Server Reporting Services 已安裝在電腦 atl-sql-001.litwareinc.com 上, 而監視報告使用資料庫實例 archinst, 則首頁 URL 看起來會像這樣:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. 在您存取完 [報表服務] 首頁之後, 按一下 [ **ServerReports**], 然後按一下 [ **Reports_Content**]。 這會將您帶到商務用 Skype Server 監視報告的**Reports_Content**頁面。
    
3. 在 [ **Reports_Content** ] 頁面上, 按一下 [ **CDRDB**資料來源]。
    
4. 在 [ **CDRDB** ] 頁面的 [**屬性**] 索引標籤上, 尋找標示為 [**連接字串**] 的文字方塊。 目前的連接字串看起來會像這樣:
    
    資料來源 = (local) \archinst; 初始目錄 = LcsCDR
    
5. 編輯連接字串, 以包含鏡像資料庫的伺服器名稱和資料庫實例。 例如, 如果伺服器已命名為 atl-001 且鏡像資料庫位於 archinst 實例中, 您將需要新增才能使用下列語法來指定鏡像資料庫:
    
    容錯移轉合作夥伴 = atl-mirror-001\archinst
    
    您編輯的連線字串看起來會像這樣:
    
    資料來源 = (local) \archinst;容錯移轉合作夥伴 = atl-mirror-001\archinst; 初始目錄 = LcsCDR
    
6. 更新連接字串之後, 按一下 [ **** 套用]。
    
7. 在 [ **CDRDB** ] 頁面上, 按一下 [ **Reports_Content** ] 連結。 按一下 [ **QMSDB**資料來源], 然後編輯 QoE 資料庫的連線字串。 例如：
    
    資料來源 = (local) \archinst;容錯移轉合作夥伴 = atl-mirror-001\archinst; 初始目錄 = QoEMetrics
    
8. 按一下****[套用]。
    
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中安裝監視報告](install-monitoring-reports.md)
  
[在商務用 Skype Server 中使用監視報告](../../manage/health-and-monitoring/monitoring-reports.md)
