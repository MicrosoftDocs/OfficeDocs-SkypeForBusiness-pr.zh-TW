---
title: 管理商務用 Skype Server 的服務
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文說明如何管理在商務用 Skype Server 拓朴中執行的服務。
ms.openlocfilehash: 6ef87e9dfba890e36a0a00fb9d7fd1161ca2f04d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768691"
---
# <a name="manage-services-for-skype-for-business-server"></a>管理商務用 Skype Server 的服務

本文說明如何管理在商務用 Skype Server 拓朴中執行的服務。
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看執行商務用 Skype Server 的電腦清單
<a name="view_list"> </a>

您可以使用商務用 Skype Server 控制台，以查看拓撲中所有執行商務用 Skype Server 的電腦清單，並查看每個電腦的服務狀態。 您可以依電腦、集區或網站來排序清單。 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>若要查看執行商務用 Skype Server 的電腦清單

1. 從指派為商務用 Skype Server 之任何預先定義之管理角色的使用者帳戶，登入內部部署中的任何電腦。 如需商務用 Skype Server 中所提供的預先定義管理角色的詳細資訊，請參閱 **規劃 Role-Based 存取控制**。   
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。   
3. 在左導覽列中，按一下 **[拓撲]**，再按一下 **[狀態]**。   
4. 在 **[狀態]** 頁面上，視需要執行下列任何動作：
   - 按一下 **[電腦]**、**[集區]** 或 **[網站]** 欄標題，然後按一下向上箭頭或向下箭頭來排序清單。 
   - 按一下 **[重新整理]** 檢視最新清單。  
   - 在搜尋欄位中輸入電腦名稱來搜尋特定電腦。
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>查看在商務用 Skype 伺服器上執行的服務狀態
<a name="view-status"> </a>

您可以使用商務用 Skype Server 控制台，以查看您商務用 Skype Server 拓撲中特定電腦上執行的所有服務，並查看每個服務的狀態。
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>若要查看電腦上執行的服務狀態

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
3. 在左側導覽列中，按一下 [拓撲]。 
4. 在 [ **狀態** ] 頁面上，視需要排序或搜尋清單，以尋找您所感興趣的電腦，然後按一下電腦名稱稱。
5. 執行下列任一項作業：
   - 若要查看電腦上執行之服務的最新狀態，請按一下 [ **取得服務狀態**]。
   - 若要查看電腦上執行的特定服務清單，以及每項服務的 **狀態，請按一下 [** 內容]，然後按一下 [ **關閉** ] 以回到清單。
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>使用 Windows Powershell Cmdlet 來查看服務狀態

您也可以使用 Windows PowerShell 和 **Get-CsWindowsService** Cmdlet 來查看服務狀態。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。
  
### <a name="to-view-service-status"></a>若要查看服務狀態

若要在電腦上查看服務狀態，請在商務用 Skype Server 管理命令介面中輸入類似下列的命令，然後按 enter：
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

此命令會傳回與下列相似的資訊：
  
|**擁有**|**狀態**|
|:-----|:-----|
|{W3SVC}  <br/> |正在執行  <br/> |
|{CentralManagement}  <br/> | 正在執行 <br/> |
|{ClsAgent}  <br/> |正在執行  <br/> |
|{註冊機構，UserServer，Edgeserver atl-edge}  <br/> |正在執行  <br/> |
|{ApplicationServer}  <br/> |正在執行  <br/> |
|{ConferencingServer}  <br/> |正在執行  <br/> |
|{MediationServer}  <br/> |正在執行  <br/> |
   
如需詳細資訊，請參閱 [Get-CsWindowsService](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。
  
## <a name="view-details-about-a-service"></a>查看服務的詳細資料
<a name="view_details"> </a>

您可以使用商務用 Skype Server 控制台，以查看拓撲中特定電腦上執行之每個服務的詳細資料。 您可以查看每個服務的狀態，以及相關聯的資料庫、埠和相依服務等詳細資訊。
  
### <a name="to-view-details-for-a-service"></a>若要查看服務的詳細資料

1. 從指派為商務用 Skype Server 之任何預先定義之管理角色的使用者帳戶，登入內部部署中的任何電腦。 如需商務用 Skype Server 中所提供的預先定義管理角色的詳細資訊，請參閱 **規劃 Role-Based 存取控制**。
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
3. 在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。
4. 在 [ **狀態** ] 頁面中，排序或搜尋清單，然後按一下您要查看的電腦。
5. 按一下 **[內容]**。
6. 在 [ **View Computer Detail] （詳細資料** ）視窗中，根據需要排序服務清單，然後按一下您要查看的服務。
7. 請視需要執行下列任何動作：
   - 若要查看該特定服務的最新狀態，請按一下 [ **取得服務狀態**]。
   - 若要查看該特定服務的詳細資料，請按一下 [ **屬性** ]，然後按一下 [ **關閉**]。
   - 若要回到拓撲中的所有電腦清單，請按一下 [ **關閉**]。
    
## <a name="start-or-stop-skype-for-business-server-services"></a>啟動或停止商務用 Skype Server 服務
<a name="StartStop"> </a>

您可以使用商務用 Skype Server 控制台來啟動或停止特定電腦上執行的所有商務用 Skype Server 服務，或是啟動或停止特定的服務。
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>啟動或停止電腦上的所有商務用 Skype 服務

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。 您可以執行類似下列的命令，判斷是否已指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
3. 在左導覽列中，按一下 **[拓撲]**，再按一下 **[狀態]**。
4. 在 **[狀態]** 頁面上，視需要排序或搜尋清單，找到正在執行您要啟動或停止之服務的電腦，然後按一下該電腦。
5. 按一下 **[動作]**。
6. 按一下 **[啟動所有服務]** 或 **[停止所有服務]**。
    
### <a name="to-start-or-stop-a-specific-service"></a>啟動或停止特定服務

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
3. 在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。
4. 在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。
5. 按一下 **[內容]**。
6. 視需要排序服務清單，然後按一下您要啟動或停止的服務。
7. 按一下 **[動作]**。
8. 按一下 **[啟動服務]** 或 **[停止服務]**。
9. 按一下 **[關閉]**。
    
## <a name="prevent-sessions-for-services"></a>防止服務的工作階段
<a name="prevent_session"> </a>

您可以使用商務用 Skype Server 控制台，以防止在特定電腦上執行的所有商務用 Skype Server 服務的新會話，或阻止特定商務用 Skype Server 服務的新會話。
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>若要防止電腦上所有商務用 Skype 服務的新會話

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
3. 在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。
4. 在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。
5. 按一下 **[動作]**。
6. 按一下 **[阻止對所有服務的新工作階段]**。
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服務的新工作階段

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
3. 在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。
4. 在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。 
5. 按一下 **[內容]**。
6. 視需要排序服務清單，然後按一下要阻止新工作階段的服務。
7. 按一下 **[動作]**。
8. 按一下 **[阻止對服務的新工作階段]**。
9. 按一下 **[關閉]**。
