---
title: 移動中央管理伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 遷移到商務用 Skype Server 2019 之後，您必須先將中央管理伺服器移至商務用 Skype Server 2019 前端伺服器或池，才能移除舊版伺服器。
ms.openlocfilehash: 6f78a242ce42a3dca56cc1e4e1f2fa604611d68c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813241"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>將舊版中央管理伺服器移至商務用 Skype Server 2019

遷移至商務用 Skype Server 2019 之後，且您必須先將中央管理伺服器移至商務用 Skype Server 2019 前端伺服器或池，然後才能移除舊版伺服器。 
  
[中央管理伺服器] 是單一主要/多重複本系統，其中資料庫的讀/寫複本是由包含中央管理伺服器的前端伺服器所保留。 拓朴中的每個電腦（包括包含中央管理伺服器的前端伺服器）在安裝期間都有在電腦上安裝的 SQL Server 資料庫中的中央管理儲存資料（預設為 RTCLOCAL）的唯讀複本部署. 本機資料庫會透過商務用 Skype Server 複製複製器代理程式（在所有電腦上以服務的方式）來接收復本更新。 中央管理伺服器上的實際資料庫名稱與局部複本是 XDS，這是由 XDS 和 XDS 檔案組成。 主資料庫位置是由 Active Directory 網域服務中的服務控制點（SCP）所參照。 使用中央管理伺服器來管理和設定商務用 Skype Server 的所有工具，都使用 SCP 來尋找中央管理儲存區。
  
成功移動中央管理伺服器之後，您應該從原始前端伺服器移除中央管理伺服器資料庫。 如需有關移除中央管理伺服器資料庫的詳細資訊，請參閱[移除前端池的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)。
  
您可以在商務用 Skype Server Management Shell 中使用 Windows PowerShell Cmdlet **CsManagementServer** ，將資料庫從舊版安裝 SQL server 資料庫移至商務用 skype SERVER 2019 sql server 資料庫，然後更新 SCP 以指向商務用 skype Server 2019 中央管理伺服器位置。 
  
在移動中央管理伺服器之前，請使用本節中的程式來準備商務用 Skype Server 2019 前端伺服器。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>準備企業版前端池

1. 在您要重設中央管理伺服器位置的 [商務用 Skype Server 2019 企業版] 前端池上，登入將商務用 Skype Server Management Shell 安裝為**RTCUniversalServerAdmins**群組成員的電腦。 您也必須在您要安裝中央管理儲存區的資料庫上，同時擁有 SQL Server 資料庫系統管理員的使用者權利和許可權。 
    
2. 開啟商務用 Skype Server 管理命令介面。
    
3. 若要在商務用 Skype Server 2019 SQL Server 資料庫中建立新的中央管理存放區，請在商務用 Skype Server 管理命令介面中，鍵入：
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. 確認**已啟動****商務用 Skype Server 前端**服務的狀態。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>準備標準版的前端伺服器

1. 在您想要重新置放中央管理伺服器的商務用 Skype Server 2019 標準版前端伺服器上，登入商務用 Skype Server Management Shell 安裝為**RTCUniversalServerAdmins**群組成員的電腦。 
    
2. 開啟商務用 Skype Server 部署嚮導。
    
3. 在商務用 Skype Server 部署嚮導中，按一下 [**準備第一個標準版 server Server**]。
    
4. 在 [**執行命令**] 頁面上，SQL Server Express 已安裝為中央管理伺服器。 已建立必要的防火牆規則。 完成資料庫與必備軟體的安裝後，按一下 **[完成]**。
    
    > [!NOTE]
    > 初始安裝可能需要一些時間，且 [命令輸出摘要] 畫面沒有顯示更新。 這是由 SQL Server Express 的安裝所導致。 如果您需要監視資料庫的安裝，請使用 [工作管理員] 來監視設定。 
  
5. 若要在商務用 Skype Server 2019 標準版前端伺服器上建立新的中央管理存放區，請在商務用 Skype Server 管理命令介面中，鍵入： 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. 確認**已啟動****商務用 Skype Server 前端**服務的狀態。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>將舊版安裝中央管理伺服器移至商務用 Skype Server 2019

1. 在將是中央管理伺服器的商務用 Skype Server 2019 伺服器上，登入將商務用 Skype Server Management Shell 安裝為**RTCUniversalServerAdmins**群組成員的電腦。 您也必須具備 SQL Server 資料庫管理員的使用者權限和許可權。 
    
2. 開啟商務用 Skype Server 管理命令介面（以系統管理員身分執行）。
    
3. 在商務用 Skype Server Management 命令介面中，鍵入： 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 如果`Enable-CsTopology`未成功，請解決導致命令無法完成的問題，然後再繼續進行。 如果**啟用-CsTopology**未成功，移動就會失敗，而且可能會讓您的拓撲處於沒有中央管理儲存區的狀態。 
  
4. 在商務用 Skype Server 2019 前端伺服器或 [前端] 池中，在商務用 Skype Server 管理命令介面中，鍵入： 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. 商務用 Skype Server 管理命令介面會顯示目前狀態和建議狀態的伺服器、檔案儲存區、資料庫儲存區及服務連接點。 仔細閱讀資訊並確認這是您想要的來源和目的地。 鍵入**Y**繼續，或輸入**N**以停止移動。 
    
6. 查看**移動流覽 CsManagementServer**命令產生的任何警告或錯誤，並加以解決。 
    
7. 在商務用 Skype Server 2019 server 上，開啟商務用 Skype Server 部署嚮導。 
    
8. 在商務用 Skype Server 部署嚮導中，按一下 [**安裝或更新商務用 Skype Server System**]，按一下 [**步驟2：設定] 或 [移除商務用 Skype server 元件**]，按一下 **[下一步]**，查看摘要，然後按一下 **[完成]**。 
    
9. 在舊版安裝伺服器上，開啟 [部署] 嚮導。 
    
10. 在商務用 Skype Server 部署嚮導中，按一下 [**安裝或更新商務用 Skype Server System**]，按一下 [**步驟2：設定] 或 [移除商務用 Skype server 元件**]，按一下 **[下一步]**，查看摘要，然後按一下 **[完成]**。 
    
11. 重新開機商務用 Skype Server 2019 伺服器。 這是必要的，因為群組成員資格變更為 access 中央管理伺服器資料庫。
    
12. 若要確認正在進行與新中央管理儲存體的複製，請在商務用 Skype Server Management Shell 中輸入： 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > 複製可能需要一些時間來更新所有目前的複本。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>若要在移動後移除舊版安裝中央管理儲存檔案

1. 在舊版安裝伺服器上，登入將商務用 Skype Server Management Shell 安裝為**RTCUniversalServerAdmins**群組成員的電腦。 您也必須具備 SQL Server 資料庫管理員的使用者權限和許可權。 
    
2. 開啟商務用 Skype Server 管理命令介面
    
    > [!CAUTION]
    > 在複製完成且穩定之前，請勿繼續移除先前的資料庫檔案。 如果您在完成複製之前移除檔案，您將會中斷複製程式，並將新移動的中央管理伺服器保持在未知狀態。 使用 Cmdlet **CsManagementStoreReplicationStatus**來確認複製狀態。 
  
3. 若要從舊版安裝中央管理伺服器移除中央管理儲存資料庫檔案，請輸入：
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    例如：
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    其中， _ \<SQL Server\>的 FQDN_是企業版部署中的舊版安裝後端伺服器，或是標準版 Server 的 fqdn。 
    

