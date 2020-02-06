---
title: 管理商務用 Skype Server 的服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文說明如何管理在商務用 Skype Server 拓朴中執行的服務。
ms.openlocfilehash: f730f095bdbf88af68afa0cd93568b1bf35ebdd9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817572"
---
# <a name="manage-services-for-skype-for-business-server"></a>管理商務用 Skype Server 的服務

本文說明如何管理在商務用 Skype Server 拓朴中執行的服務。
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看執行商務用 Skype Server 的電腦清單
<a name="view_list"> </a>

您可以使用商務用 Skype Server [控制台] 來查看在您的拓撲中執行商務用 Skype 伺服器的所有電腦清單，並查看每個電腦的服務狀態。 您可以依電腦、池或網站排序清單。 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>若要查看執行商務用 Skype Server 的電腦清單

1. 從指派給商務用 Skype Server 任何預先定義之系統管理角色的使用者帳戶，登入內部部署中的任何電腦。 如需有關商務用 Skype Server 中可用的預先定義管理角色的詳細資訊，請參閱**規劃角色式存取控制**。   
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。   
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。   
4. 在 [**狀態**] 頁面上，視需要執行下列任何一項操作：
   - 按一下 [**電腦**]、[**池**] 或 [**網站**欄] 標題，然後按一下向上箭號或向下箭號，即可排序清單。 
   - 按一下 **[** 重新整理]，以查看最新的清單。  
   - 在搜尋欄位中輸入電腦名稱稱，以搜尋特定電腦。
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>查看在商務用 Skype 伺服器上執行的服務狀態
<a name="view-status"> </a>

您可以使用商務用 Skype Server [控制台] 來查看所有在商務用 Skype Server 拓撲中的特定電腦上執行的服務，並查看每個服務的狀態。
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>若要查看電腦上執行的服務狀態

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
3. 在左側導覽列中，按一下 [**拓撲**]。 
4. 在 [**狀態**] 頁面上，根據需要排序或搜尋清單，以尋找您感興趣的電腦，然後按一下該電腦的名稱。
5. 請執行下列任何一項操作：
   - 若要查看電腦上執行的服務的最新狀態，請按一下 [**取得服務狀態**]。
   - 若要查看電腦上執行的特定服務清單，以及每個服務的狀態，請按一下 [**屬性**]，然後按一下 [**關閉**] 以返回清單。
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>使用 Windows Powershell Cmdlet 查看服務狀態

您也可以使用 Windows PowerShell 和**CsWindowsService** Cmdlet 來查看服務狀態。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。
  
### <a name="to-view-service-status"></a>若要查看服務狀態

若要在電腦上查看服務狀態，請在商務用 Skype Server 管理命令介面中輸入類似以下的命令，然後按 Enter：
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

這個命令會傳回如下所示的資訊：
  
|**擁有個**|**狀態值**|
|:-----|:-----|
|W3SVC  <br/> |進行  <br/> |
|{CentralManagement}  <br/> | 進行 <br/> |
|{ClsAgent}  <br/> |進行  <br/> |
|{註冊機構、UserServer、EdgeServer}  <br/> |進行  <br/> |
|{ApplicationServer}  <br/> |進行  <br/> |
|{ConferencingServer}  <br/> |進行  <br/> |
|{MediationServer}  <br/> |進行  <br/> |
   
如需詳細資訊，請參閱[CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。
  
## <a name="view-details-about-a-service"></a>查看服務的詳細資料
<a name="view_details"> </a>

您可以使用商務用 Skype Server 的 [控制台] 來查看在拓撲中特定電腦上執行的每個服務的詳細資料。 您可以查看每個服務的狀態，以及相關聯的資料庫、埠和相依服務等詳細資料。
  
### <a name="to-view-details-for-a-service"></a>若要查看服務的詳細資料

1. 從指派給商務用 Skype Server 任何預先定義之系統管理角色的使用者帳戶，登入內部部署中的任何電腦。 如需有關商務用 Skype Server 中可用的預先定義管理角色的詳細資訊，請參閱**規劃角色式存取控制**。
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [**狀態**] 頁面中，排序或搜尋清單，然後按一下您要查看的電腦。
5. 按一下 [**屬性**]。
6. 如有需要，請在 [**查看電腦詳細資料**] 視窗中排序服務清單，然後按一下您要查看的服務。
7. 視需要執行下列任何一項操作：
   - 若要查看該特定服務的最新狀態，請按一下 [**取得服務狀態**]。
   - 若要查看該特定服務的詳細資料，請按一下 [**屬性**]，然後按一下 [**關閉**]。
   - 若要返回拓撲中所有電腦的清單，請按一下 [**關閉**]。
    
## <a name="start-or-stop-skype-for-business-server-services"></a>啟動或停止商務用 Skype Server 服務
<a name="StartStop"> </a>

您可以使用商務用 Skype Server [控制台] 來啟動或停止在特定電腦上執行的所有商務用 Skype Server 服務，或是啟動或停止特定服務。
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>在電腦上啟動或停止所有商務用 Skype 服務

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦. 您可以執行如下所示的命令來判斷您是否已獲指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。
5. 按一下 [**動作**]。
6. 按一下 [**啟動所有服務**] 或 [**停止所有服務**]。
    
### <a name="to-start-or-stop-a-specific-service"></a>啟動或停止特定服務

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。
5. 按一下 [**屬性**]。
6. 如有需要，請排序服務清單，然後按一下您要開始或停止的服務。
7. 按一下 [**動作**]。
8. 按一下 [**開始服務**] 或 [**停止服務**]。
9. 按一下 [**關閉**]。
    
## <a name="prevent-sessions-for-services"></a>防止服務的工作階段
<a name="prevent_session"> </a>

您可以使用商務用 Skype Server 的 [控制台] 來避免在特定電腦上執行的所有商務用 Skype Server 服務的新會話，或避免特定商務用 Skype Server 服務的新會話。
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>若要避免電腦上所有商務用 Skype 服務的新會話

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您想要防止新會話之服務的電腦，然後按一下該電腦。
5. 按一下 [**動作**]。
6. 按一下 [**防止所有服務的新會話**]。
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>若要防止特定服務的新會話

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。 
5. 按一下 [**屬性**]。
6. 如有需要，請排序服務清單，然後按一下您要防止新會話的服務。
7. 按一下 [**動作**]。
8. 按一下 [**避免新的服務會話**]。
9. 按一下 [**關閉**]。
    

