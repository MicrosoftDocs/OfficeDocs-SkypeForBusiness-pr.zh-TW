---
title: 在商務用 Skype Server 中將監控報告與鏡像資料庫相關聯
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 摘要：瞭解如何將監控報告與商務用 Skype Server 所使用的鏡像資料庫產生關聯。
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802163"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>在商務用 Skype Server 中將監控報告與鏡像資料庫相關聯 
 
**摘要：** 瞭解如何將監控報告與商務用 Skype Server 所使用的鏡像資料庫產生關聯。
  
## <a name="monitor-reports-with-a-mirror-database"></a>監視含鏡像資料庫的報表

[！注意] 如果您為監控資料庫設定鏡像，則在發生容錯移轉時，鏡像資料庫將會以主資料庫的方式接管。 不過，如果您使用商務用 Skype Server 監控報告，而且發生容錯移轉，您可能會發現監控報告未連接至鏡像資料庫。 這是因為，當您安裝監控報告時，只會指定主要資料庫的位置;您不會指定鏡像資料庫的位置。
  
若要取得監控報告自動容錯移轉至鏡像資料庫，您必須將鏡像資料庫新增為「容錯移轉協力廠商」，以供監視報告 (一個資料庫用於通話詳細資料記錄資料，另一個用於 (經驗品質 QoE) 資料) 。  (請注意，安裝監控報告之後，應該執行此步驟。 ) 您可以手動編輯這兩個資料庫所使用的連線字串值，以新增容錯移轉夥伴資訊。 若要執行這項作業，請完成下列程序：
  
1. 使用 Internet Explorer 開啟 [ **SQL Server Reporting Services** ] 首頁。 Reporting Services 首頁 URL 包含：
    
   - **Http：** 前置詞。
    
   - 安裝 Reporting Services 之電腦的完整功能變數名稱 (FQDN)  (例如， **atl-sql-001.litwareinc.com**) 。
    
   - 字元字串 **/Reports_**。
    
   - 安裝監視報告的資料庫實例名稱 (例如， **而 archinst**) 。
    
     例如，如果已在電腦 atl-sql-001.litwareinc.com 上安裝 SQL Server Reporting Services，且監控報告使用資料庫實例而 archinst，則首頁 URL 會如下所示：
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. 存取 Reporting Services 首頁之後，請按一下 [ **ServerReports**]，然後按一下 [ **Reports_Content**]。 這將帶您前往商務用 Skype Server Monitoring Reports 的 **Reports_Content** 頁面。
    
3. 在 [ **Reports_Content** ] 頁面上，按一下 [ **CDRDB** ] 資料來源。
    
4. 在 [ **CDRDB** ] 頁面的 [ **屬性** ] 索引標籤上，尋找標示為 [連線 **字串**] 的文字方塊。 目前的連接字串將如下所示：
    
    資料來源 = (local) \archinst; 初始目錄 = LcsCDR
    
5. 編輯連接字串，以包含鏡像資料庫的伺服器名稱和資料庫實例。 例如，如果伺服器命名為 atl-001，且鏡像資料庫位於而 archinst 實例中，您將需要使用下列語法來新增以指定鏡像資料庫：
    
    容錯移轉 Partner = atl-mirror-001\archinst
    
    您已編輯的連接字串看起來如下所示：
    
    資料來源 = (local) \archinst;容錯移轉夥伴 = atl-mirror-001\archinst; 初始目錄 = LcsCDR
    
6. 更新連接字串後 **，按一下 [** 套用]。
    
7. 在 [ **CDRDB** ] 頁面上，按一下 [ **Reports_Content** ] 連結。 按一下 [ **QMSDB** ] 資料來源，然後編輯 QoE 資料庫的連接字串。 例如：
    
    資料來源 = (local) \archinst;容錯移轉夥伴 = atl-mirror-001\archinst; 初始目錄 = QoEMetrics
    
8. 按一下 **[套用]**。
    
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中安裝監視報告](install-monitoring-reports.md)
  
[在商務用 Skype Server 中使用監控報告](../../manage/health-and-monitoring/monitoring-reports.md)
