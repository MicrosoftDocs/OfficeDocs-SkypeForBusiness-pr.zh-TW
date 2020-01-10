---
title: 在商務用 Skype Server 中，將監控存放區與前端池建立關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 摘要：瞭解如何將前端池與商務用 Skype 伺服器所使用的監視存放區建立關聯。
ms.openlocfilehash: 17f7cbf7d8725fc3d1c23f161060d9bb386cea19
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001223"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>在商務用 Skype Server 中，將監控存放區與前端池建立關聯 
**摘要：** 瞭解如何將前端池與商務用 Skype 伺服器所使用的監視存放區建立關聯。
  
在商務用 Skype Server 中，只能在與監視存放區相關聯的前端池上收集監視資料，當您在拓撲建立器中定義 [前端] 池時，通常會執行一個工作。
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>將監視存放區與 [前端] 池建立關聯

 若要將監視存放區與新的前端池建立關聯，請務必在 [定義新的前端池] 嚮導的 [**選取功能**] 頁面上，選取 [**監視] （呼叫詳細資料記錄及記錄品質統計資料）** 的選項。 請注意，如果您選取此選項，您也必須指定 SQL store 才能完成嚮導;不過，此存放區在您執行此嚮導時不一定要存在。 這表示您可以先將一個池與監視存放區建立關聯，然後再設定該存放區。
  
或者，您也可以透過完成下列程式，將現有的前端池與新的或不同的監視存放區建立關聯：
  
1. 按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype server 2015**]，然後按一下 [**商務用 skype server 拓撲**建立器]。
    
2. 在 [**拓撲**建立器] 對話方塊中，選取 [**從現有的部署下載拓撲結構**]，然後按一下 **[確定]**。
    
3. 在 [**另存**新檔] 對話方塊中，輸入目前拓撲的檔案名，然後按一下 [**儲存**]。 在新拓撲發生問題時，可以稍後檢索並重新發佈已儲存的拓撲。
    
4. 在 [拓撲建立器] 中，展開 [**商務用 Skype 伺服器**]，展開包含 [前端] 池的網站名稱，然後按一下 [展開**企業版前端池**]。
    
5. 以滑鼠右鍵按一下要與 [監視] 存放區相關聯的池子名稱，然後按一下 [**編輯屬性**]。
    
6. 在 [**編輯屬性**] 對話方塊的 [**一般**] 索引標籤上，選取 [**監視] （CDR 與 QoE 度量）** ，然後從 [**監視 SQL server store** ] 下拉式清單中選取現有的 SQL server 資料庫。 （或者，按一下 [**新增**] 以將池與新的資料庫存放區建立關聯）。如果您選擇使用新的資料庫存放區，請在 [**定義新的 SQL store** ] 對話方塊中，于 [ **sql server FQDN** ] 方塊中輸入 sql server 電腦的完整功能變數名稱。 如果您想要使用該存放區的預設 SQL Server 實例，請選取 [**預設實例**];否則，請選取 [**命名實例**]，然後在 [**命名實例**] 方塊中輸入實例名稱。
    
    [**編輯屬性**] 對話方塊也可讓您選擇為監視資料庫建立 SQL 鏡像（sql mirror 可讓您維護監視資料庫的兩份複本，一個複本儲存在監視儲存電腦上，另一個則在 SQL 鏡像電腦上）。 若要啟用 [鏡像]，請選取 [T**他的 SQL 實例是在鏡像關聯中**]，然後在 [**鏡像埠號碼**] 方塊中輸入鏡像伺服器的埠號碼。
    
7. 在 [**編輯屬性**] 對話方塊中，按一下 **[確定]**。
    
將監視存放區與前端池關聯之後，您必須發佈新的拓撲，變更才會生效。 若要發佈新的拓撲，請在拓撲建立器中完成下列步驟：
  
1. 按一下 [**動作**]，指向 [**拓撲**]，然後按一下 [**發佈**]。
    
2. 在 [發佈拓撲嚮導] 的 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。
    
3. 在 [**發佈嚮導完成]** 頁面上，按一下 **[完成]**。
    
在拓撲發佈之後，您就可以在要主持監視存放區的電腦上安裝監視資料庫。 您可以使用商務用 Skype Server Management 命令介面和 Windows PowerShell 來安裝監視資料庫。 若要在本機安裝資料庫（也就是在執行商務用 Skype Server 管理命令介面的同一部電腦上安裝資料庫），請在適當的電腦上啟動管理命令介面，然後輸入下列命令，然後按 ENTER：
  
```powershell
Install-CsDatabase -LocalDatabases
```

當您執行上述命令時，安裝 CsDatabase 會讀取目前的商務用 Skype 伺服器拓撲，判斷需要在本機電腦上安裝哪些資料庫，然後自動安裝並設定每個資料庫。
  
若要在遠端電腦（也就是執行管理命令介面之電腦以外的電腦）上安裝資料庫，您必須至少包含兩個參數： ConfiguredDatabases 參數和 SqlServerFqdn 參數。 這些參數會告訴 CsDatabase Cmdlet 來檢索商務用 Skype Server 拓撲，然後在 SqlServerFqdn 參數所指定的電腦上安裝並設定所需的資料庫。 SqlServerFqdn 參數必須使用代表要安裝資料庫之電腦之完整功能變數名稱的參數值。
  
例如，這個命令會在電腦 atl-sql-001.litwareinc.com 上安裝監視資料庫：
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

或者，您也可以在將主持監視存放區的電腦上執行商務用 Skype Server 部署嚮導來安裝監視資料庫。 若要這樣做，請登入適當的電腦並完成下列程式：
  
1. 按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype server 2015**]，然後按一下 [**商務用 skype server 部署嚮導]**。
    
2. 在 [部署嚮導] 中，按一下 [**安裝或更新商務用 Skype Server 系統**]。
    
3. 在 [**部署**] 頁面的 [**步驟2：設定] 或 [移除商務用 Skype Server 元件**] 底下，再次按一下 [**執行**]。
    
4. 在 [設定商務用 Skype Server 元件] 嚮導中，按一下 [**設定商務用 Skype 伺服器元件**] 頁面上的 **[下一步**]。
    
5. 在 [**指定路徑至 MSIs** ] 頁面上，輸入檔案 Ocscore 的路徑（隨附于商務用 Skype Server 安裝媒體中的檔案），然後按 **[下一步]**。
    
6. 在 [**執行命令**] 頁面上，按一下 **[完成]**。
    
若要確保所有需要的商務用 Skype Server 服務都已開始，請在 [**部署**] 頁面上按一下 [標題] 下的 [**執行**] **： [啟動服務**]
  

