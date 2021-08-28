---
title: 在商務用 Skype Server 中管理服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 瞭解如何查看服務狀態、啟動和停止服務，以及防止服務的會話。
ms.openlocfilehash: 8c1f527e32d50624fddc1b4b261f6fbd20e97a47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604818"
---
# <a name="manage-services-in-skype-for-business-server"></a>在商務用 Skype Server 中管理服務

您可以使用商務用 Skype Server 控制台，在拓撲中查看所有執行商務用 Skype Server 的電腦清單、查看服務的狀態、啟動或停止服務，以及阻止服務的會話。

- [查看執行商務用 Skype Server 的電腦清單](#view-a-list-of-computers-running-skype-for-business-server)
- [在商務用 Skype 中查看電腦上執行的服務狀態](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [啟動或停止商務用 Skype 服務](#start-or-stop-skype-for-business-services)
- [防止服務的工作階段](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看執行商務用 Skype Server 的電腦清單

使用商務用 Skype Server 控制台，以查看拓撲中所有執行商務用 Skype 的電腦清單，並查看每個電腦的服務狀態。 您可以依電腦、集區或網站來排序清單。 

1. 從指派為商務用 Skype Server 之任何預先定義之管理角色的使用者帳戶，登入內部部署中的任何電腦。 如需詳細資訊，請參閱[以角色為基礎的存取控制 (RBAC) 商務用 Skype Server](../../plan-your-deployment/security/role-based-access-control-rbac.md)。
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 如需可用於啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱[安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。
4. 在 [狀態] 頁面上，視需要執行下列其中一項動作：
    - 按一下 **[電腦]**、**[集區]** 或 **[網站]** 欄標題，然後按一下向上箭頭或向下箭頭來排序清單。
    - 按一下 **[重新整理]** 檢視最新清單。
    - 在搜尋欄位中輸入電腦名稱來搜尋特定電腦。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>在商務用 Skype 中查看電腦上執行的服務狀態

使用商務用 Skype Server 控制台，以查看您商務用 Skype Server 拓撲中特定電腦上執行的所有服務，並查看每個服務的狀態。

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱[安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左側導覽列中，按一下 [拓撲]。
4. 在 [狀態] 頁面上，視需要排序或搜尋清單，以尋找您所感興趣的電腦，然後按一下電腦名稱稱。
5. 請執行下列其中一項動作：
    - 若要查看電腦上執行之服務的最新狀態，請按一下 [ **取得服務狀態**]。
    - 若要查看電腦上執行的特定服務清單，以及每項服務的 **狀態，請按一下 [** 內容]，然後按一下 [ **關閉** ] 以回到清單。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看服務狀態

您也可以使用 Windows PowerShell 和 Get-CsWindowsService Cmdlet 來查看服務狀態。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 如需詳細資訊，請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。

**若要查看服務狀態**

若要在電腦上查看服務狀態，請在商務用 Skype Server 管理命令介面中輸入類似下列的命令，然後按 enter：

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

此命令會傳回與下列相似的資訊：

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

如需詳細資訊，請參閱 [Get-CsWindowsService](/powershell/module/skype/Get-CsWindowsService)。

## <a name="start-or-stop-skype-for-business-services"></a>啟動或停止商務用 Skype 服務

使用商務用 Skype Server 控制台，以啟動或停止在特定電腦上執行的所有商務用 Skype Server 服務，或是啟動或停止特定的服務。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>啟動或停止電腦上的所有商務用 Skype Server 服務

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。 您可以執行類似下列的命令，判斷是否已指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 如需可用於啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱[安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。
4. 在 [狀態] 頁面上，視需要排序或搜尋清單，找到正在執行您要啟動或停止之服務的電腦，然後按一下該電腦。
5. 按一下 **[動作]**。
6. 按一下 **[啟動所有服務]** 或 **[停止所有服務]**。

### <a name="start-or-stop-a-specific-service"></a>啟動或停止特定服務

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱[安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。
4. 在 [狀態] 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。
5. 按一下 **[內容]**。
6. 視需要排序服務清單，然後按一下您要啟動或停止的服務。
7. 按一下 **[動作]**。
8. 按一下 **[啟動服務]** 或 **[停止服務]**。
9. 按一下 **[關閉]**。


## <a name="prevent-sessions-for-services"></a>防止服務的工作階段

使用商務用 Skype 控制台，以防止在特定電腦上執行的所有商務用 Skype Server 服務的新會話，或阻止特定服務的新會話。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>防止電腦上所有商務用 Skype Server 服務的新會話

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱[安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。
4. 在 [狀態] 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。
5. 按一下 **[動作]**。
6. 按一下 **[阻止對所有服務的新工作階段]**。

### <a name="prevent-new-sessions-for-a-specific-service"></a>防止特定服務的新會話

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱[安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。
4. 按一下 **[內容]**。
5. 視需要排序服務清單，然後按一下要阻止新工作階段的服務。
6. 按一下 **[動作]**。
7. 按一下 **[阻止對服務的新工作階段]**。
8. 按一下 **[關閉]**。