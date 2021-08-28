---
title: 在商務用 Skype Server 中將監控存放區與前端集區產生關聯
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 摘要：瞭解如何將前端集區與商務用 Skype Server 所使用的監控存放區產生關聯。
ms.openlocfilehash: cff7c2d7bc85916e7e79f4f78005c81f798bcbf7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601888"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>在商務用 Skype Server 中將監控存放區與前端集區產生關聯 
**摘要：** 瞭解如何將前端集區與商務用 Skype Server 所使用的監控存放區產生關聯。
  
在商務用 Skype Server 中，監控資料只能收集在已與監控存放區產生關聯的前端集區上，當您在拓撲產生器中定義前端集區時，通常會執行的工作。
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>建立監視存放區與前端集區的關聯

 若要將監控存放區與新的前端集區產生關聯，請務必在 [定義新的前端集區] 嚮導的 [**選取功能**] 頁面上，選取 [**監視 (的詳細資料記錄及記錄品質的) 統計** 資料] 選項。 請注意，如果您選取此選項，您也必須指定 SQL 儲存區，才可完成該嚮導; 請參閱。不過，當您執行該嚮導時，不需要有這種存放區。 這表示您可以先將集區與監控存放區產生關聯，然後再安裝及設定該儲存區。
  
或者，您可以完成下列程式，將現有的前端集區與新的或不同的監視存放區產生關聯：
  
1. 依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server 2015**]，然後按一下 [**商務用 Skype Server 拓撲** 產生器]。
    
2. 在 **[拓撲產生器]** 對話方塊中，選取 **[從現有的部署下載拓撲]**，然後按一下 **[確定]**。
    
3. 在 [ **另存** 新檔] 對話方塊中，輸入目前拓撲的檔案名，然後按一下 [ **儲存**]。 當新的拓撲發生問題時，可在以後檢索並重新發佈已儲存的拓撲。
    
4. 在 [拓撲產生器] 中，展開 [**商務用 Skype Server**]，展開包含前端集區的網站名稱，然後按一下 [展開 **Enterprise Edition 前端** 集區]。
    
5. 以滑鼠右鍵按一下要與監視存放區產生關聯的集區名稱，然後按一下 [ **編輯屬性**]。
    
6. 在 [**編輯** 內容] 對話方塊的 [**一般**] 索引標籤上，選取 [**監視] (CDR 和 QoE) 計量**]，然後從 [**監控 SQL Server 儲存區**] 下拉式清單中選取現有的 SQL Server 資料庫。  (或按一下 [**新增**]，將集區與新的資料庫存放區產生關聯。 ) 如果您選擇使用新的資料庫存放區，請在 [**定義新的 SQL 儲存區**] 對話方塊中，于 [ **SQL Server FQDN** ] 方塊中輸入 SQL Server 電腦的完整功能變數名稱。 如果您想要使用該儲存區的預設 SQL Server 實例，請選取 [**預設實例**];否則，請選取 [**命名實例**]，並在 [**命名實例**] 方塊中輸入實例名稱。
    
    [**編輯** 內容] 對話方塊也可讓您選擇為監控資料庫建立 SQL 鏡像 (SQL 鏡像可讓您維護監控資料庫的兩個複本，一個副本儲存在監控存放區電腦上，另一個則儲存在「SQL 鏡像」電腦) 。 若要啟用鏡像，請選取 [T **他的 SQL 實例為鏡像關係**]，然後在 [**鏡像埠號碼**] 方塊中輸入鏡像伺服器的埠號碼。
    
7. 在 [ **編輯屬性** ] 對話方塊中，按一下 **[確定]**。
    
將監控儲存區與前端集區關聯之後，您必須先發行新的拓撲，變更才會生效。 若要發佈新的拓撲，請在拓撲產生器中完成下列步驟：
  
1. 按一下 [ **動作**]，指向 [ **拓撲**]，然後按一下 [ **發佈**]。
    
2. 在 [發佈拓撲] 嚮導的 [ **發行拓撲** ] 頁面上，按 **[下一步]**。
    
3. 在 **[發行精靈完成]** 頁面上，按一下 **[完成]**。
    
發行拓撲之後，您就可以在將裝載監控存放區的電腦上安裝監控資料庫。 您可以使用商務用 Skype Server 管理命令介面和 Windows PowerShell 安裝監控資料庫。 若要在本機安裝資料庫 (也就是說，若要在執行商務用 Skype Server 管理命令介面) 的同一部電腦上安裝資料庫，請在適當的電腦上啟動管理命令介面，然後輸入下列命令，然後按 enter：
  
```powershell
Install-CsDatabase -LocalDatabases
```

當您執行上述命令時，Install-CsDatabase 會讀取目前的商務用 Skype Server 拓撲，判斷哪些資料庫需要安裝在本機電腦上，然後自動安裝和設定每一個資料庫。
  
若要在遠端電腦上安裝資料庫 (也就是執行管理命令介面之電腦之外的電腦) 您必須至少包含兩個參數： ConfiguredDatabases 參數和 SqlServerFqdn 參數。 這些參數會告訴 Install-CsDatabase Cmdlet 取得商務用 Skype Server 拓撲，然後在 SqlServerFqdn 參數所指定的電腦上安裝及設定所需的資料庫。 SqlServerFqdn 參數必須使用參數值，代表要安裝資料庫之電腦的完整功能變數名稱。
  
例如，此命令會在電腦 atl-sql-001.litwareinc.com 上安裝監視資料庫：
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

或者，您也可以在將裝載監控存放區的電腦上執行商務用 Skype Server 部署嚮導，以安裝監控資料庫。 若要這麼做，請登入適當的電腦，並完成下列程式：
  
1. 依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server 2015**]，然後按一下 [**商務用 Skype Server 部署嚮導]**。
    
2. 在 [部署嚮導] 中，按一下 [**安裝或更新商務用 Skype Server 系統**]。
    
3. 在 [**部署**] 頁面的 [**步驟2：安裝或移除商務用 Skype Server 元件**] 底下，按一下 [**再執行一次**]。
    
4. 在 [安裝程式商務用 Skype Server 元件] 嚮導的 [**安裝商務用 Skype Server 元件**] 頁面上，按 **[下一步]**。
    
5. 在 [**指定要 MSIs 的路徑**] 頁面上，輸入檔案 Ocscore.msi (包含商務用 Skype Server 安裝媒體) 的檔案，然後按 **[下一步]**。
    
6. 在 **[執行命令]** 頁面上，按一下 **[完成]**。
    
若要確認所有必要的商務用 Skype Server 服務均已啟動，請在 [**部署**] 頁面的 [**步驟4：啟動服務**] 下，按一下 [**執行**]。
  

