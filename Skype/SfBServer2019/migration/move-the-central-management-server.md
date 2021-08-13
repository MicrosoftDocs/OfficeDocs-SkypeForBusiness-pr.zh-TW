---
title: 移動中央管理伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在遷移至商務用 Skype Server 2019 之後，您必須將中央管理伺服器移至商務用 Skype Server 2019 前端伺服器或集區，才能移除舊版伺服器。
ms.openlocfilehash: 0c5ee756a52d61008498e50df5d3bf64fbe20f8c4ef1ee96e4e7528c2a3bd820
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300599"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>將舊版中央管理伺服器移至商務用 Skype Server 2019

在遷移至商務用 Skype Server 2019 之後，而且可以移除舊版伺服器之前，您必須將中央管理伺服器移至商務用 Skype Server 2019 前端伺服器或集區。 
  
中央管理伺服器是單一主/多個複本系統，其中包含中央管理伺服器的前端伺服器會持有資料庫的讀/寫副本。 拓撲中的每一部電腦（包括包含中央管理伺服器的前端伺服器）在安裝和部署期間，) 安裝于電腦上的 SQL Server 資料庫 (中，都有中央管理存放區資料的唯讀副本。 本機資料庫會透過在所有電腦上以服務方式執行的商務用 Skype Server 複本複製器代理程式來接收復本更新。 中央管理伺服器及本機複本上之實際資料庫的名稱是 XDS，這是由 XDS 及 XDS 檔所組成。 Master 資料庫位置是由 Active Directory 網域服務中 (SCP) 的服務控制點所參照。 所有使用中央管理伺服器來管理及設定商務用 Skype Server 的工具，都使用 SCP 來尋找中央管理存放區。
  
順利移動中央管理伺服器後，應從原始前端伺服器移除中央管理伺服器資料庫。 如需移除中央管理伺服器資料庫的詳細資訊，請參閱[移除前端集區的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)。
  
您可以使用商務用 Skype Server 管理命令介面中的 Windows PowerShell Cmdlet **Move-CsManagementServer** ，將資料庫從舊版 install SQL Server 資料庫移至商務用 Skype Server 2019 SQL Server 資料庫，然後將 SCP 更新為指向商務用 Skype Server 2019 中央管理伺服器位置。 
  
在移動中央管理伺服器之前，請使用本節中的程式來準備商務用 Skype Server 2019 前端伺服器。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>準備 Enterprise Edition 前端集區

1. 在您想要重新放置中央管理伺服器的商務用 Skype Server 2019 Enterprise Edition 前端集區上，登入安裝商務用 Skype Server 管理命令介面的電腦，做為 **RTCUniversalServerAdmins** 群組的成員。 您也必須在您要安裝中央管理存放區的資料庫上，有 SQL Server 資料庫 sysadmin 使用者權利和許可權。 
    
2. 開啟 [商務用 Skype Server 管理命令介面]。
    
3. 若要在商務用 Skype Server 2019 SQL Server 資料庫中建立新的中央管理存放區，請在商務用 Skype Server 管理命令介面中輸入：
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. 確認 **商務用 Skype Server 前端** 服務的狀態為 [已 **啟動**]。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>準備 Standard Edition 前端伺服器

1. 在您想要重新放置中央管理伺服器的商務用 Skype Server 2019 Standard Edition 前端伺服器上，登入安裝商務用 Skype Server 管理命令介面的電腦，做為 **RTCUniversalServerAdmins** 群組的成員。 
    
2. 開啟 [商務用 Skype Server 部署] 嚮導。
    
3. 在 [商務用 Skype Server 部署] 嚮導中，按一下 [**準備第一 Standard Edition 伺服器**]。
    
4. 在 [**執行命令**] 頁面上，SQL Server Express 已安裝為中央管理伺服器。 已建立所需的防火牆規則。 在完成資料庫和必要軟體的安裝時，請按一下 **[完成]**。
    
    > [!NOTE]
    > 如果命令輸出摘要畫面沒有可見的更新，則初始安裝可能需要一些時間。 這是因為 SQL Server Express 的安裝。 如果您需要監控資料庫的安裝，請使用 [工作管理員] 來監控安裝程式。 
  
5. 若要在商務用 Skype Server 2019 Standard Edition 前端伺服器上建立新的中央管理存放區，請在商務用 Skype Server 管理命令介面中輸入： 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. 確認 **商務用 Skype Server 前端** 服務的狀態為 [已 **啟動**]。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>將舊版安裝中央管理伺服器移至商務用 Skype Server 2019

1. 在將成為中央管理伺服器的商務用 Skype Server 2019 伺服器上，以 **RTCUniversalServerAdmins** 群組成員的身分，登入已安裝商務用 Skype Server 管理命令介面的電腦。 您也必須具有 SQL Server 資料庫管理員使用者權限。 
    
2. 開啟商務用 Skype Server 管理命令介面 (以系統管理員身分) 執行。
    
3. 在商務用 Skype Server 管理命令介面中輸入： 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 若 `Enable-CsTopology` 未成功，請解決問題，使命令無法完成，再繼續進行。 如果 **Enable-CsTopology** 不成功，移動會失敗，而且可能會使拓撲處於沒有中央管理存放區的狀態。 
  
4. 在商務用 Skype Server 2019 前端伺服器或前端集區上，于商務用 Skype Server 管理命令介面中輸入： 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. 商務用 Skype Server管理命令介面會顯示伺服器、檔案存放區、資料庫儲存區，以及目前狀態和建議狀態的服務連線點。 請詳細閱讀資訊，並確認預期的來源與目的地是否無誤。 輸入 [Y] 繼續或 [N] 停止移動。 
    
6. 檢閱由 **Move-CsManagementServer** 命令所產生的任何警告或錯誤，並加以解決。 
    
7. 在商務用 Skype Server 2019 伺服器上，開啟商務用 Skype Server 部署嚮導。 
    
8. 在商務用 Skype Server 部署嚮導中，按一下 [**安裝或更新商務用 Skype Server 系統**]，按一下 [**步驟2：設定或移除商務用 Skype Server 元件**]，按 **[下一步]**，查看摘要，然後按一下 **[完成]**。 
    
9. 在舊版安裝伺服器上，開啟部署嚮導。 
    
10. 在商務用 Skype Server 部署嚮導中，按一下 [**安裝或更新商務用 Skype Server 系統**]，按一下 [**步驟2：設定或移除商務用 Skype Server 元件**]，按 **[下一步]**，查看摘要，然後按一下 **[完成]**。 
    
11. 重新開機商務用 Skype Server 2019 Server。 因為存取中央管理伺服器資料庫的群組成員資格變更，所以需要這麼做。
    
12. 若要確認有新中央管理存放區的複寫發生，請在商務用 Skype Server 管理命令介面中輸入： 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > 複寫可能要花一些時間來更新所有目前的複本。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>移動之後移除舊版安裝中央管理存放區檔案

1. 在舊版安裝伺服器上，以 **RTCUniversalServerAdmins** 群組成員的身分，登入安裝商務用 Skype Server 管理命令介面的電腦。 您也必須具有 SQL Server 資料庫管理員使用者權限。 
    
2. 開啟商務用 Skype Server 管理命令介面
    
    > [!CAUTION]
    > 請先確認複寫已完成且狀態穩定後，再繼續移除之前的資料庫檔案。 若要在完成複寫之前移除檔案，您會中斷複寫處理常式，並將新移動的中央管理伺服器保持在未知的狀態。 請使用 **Get-CsManagementStoreReplicationStatus** Cmdlet 來確認複寫狀態。 
  
3. 若要從舊版安裝中央管理伺服器移除中央管理存放區資料庫檔案，請輸入：
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    例如：
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    其中，在 _\<FQDN of SQL Server\>_ Enterprise Edition 部署中為舊版安裝後端伺服器，或 Standard Edition 伺服器的 FQDN。 
    

