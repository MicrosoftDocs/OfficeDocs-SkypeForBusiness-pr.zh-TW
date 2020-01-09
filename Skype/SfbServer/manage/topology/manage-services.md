---
title: 管理商務用 Skype Server 中的服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 瞭解如何查看服務狀態、啟動和停止服務，以及防範服務的會話。
ms.openlocfilehash: 90acd45675277dad0f63db342217cf914c97109a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991518"
---
# <a name="manage-services-in-skype-for-business-server"></a>管理商務用 Skype Server 中的服務

您可以使用商務用 Skype Server 的 [控制台] 來查看在您的拓撲中執行商務用 Skype 伺服器的所有電腦清單、查看服務狀態、開始或停止服務，以及防止服務的會話。

- [查看執行商務用 Skype Server 的電腦清單](#view-a-list-of-computers-running-skype-for-business-server)
- [在商務用 Skype 中查看電腦上執行的服務狀態](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [啟動或停止商務用 Skype 服務](#start-or-stop-skype-for-business-services)
- [防止服務的工作階段](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看執行商務用 Skype Server 的電腦清單

使用商務用 Skype Server [控制台] 來查看在您的拓撲中執行商務用 Skype 的所有電腦清單，並查看每個電腦的服務狀態。 您可以依電腦、池或網站排序清單。 

1. 從指派給商務用 Skype Server 任何預先定義之系統管理角色的使用者帳戶，登入內部部署中的任何電腦。 如需詳細資訊，請參閱[商務用 Skype Server 的角色式存取控制（RBAC）](../../plan-your-deployment/security/role-based-access-control-rbac.md)。
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊，請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [狀態] 頁面上，視需要執行下列其中一項操作：
    - 按一下 [**電腦**]、[**池**] 或 [**網站**欄] 標題，然後按一下向上箭號或向下箭號，即可排序清單。
    - 按一下 **[** 重新整理]，以查看最新的清單。
    - 在搜尋欄位中輸入電腦名稱稱，以搜尋特定電腦。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>在商務用 Skype 中查看電腦上執行的服務狀態

使用商務用 Skype Server 的 [控制台] 來查看所有在商務用 Skype Server 拓撲中的特定電腦上執行的服務，並查看每個服務的狀態。

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊，請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 在左側導覽列中，按一下 [**拓撲**]。
4. 在 [狀態] 頁面上，根據需要排序或搜尋清單，以尋找您感興趣的電腦，然後按一下該電腦的名稱。
5. 請執行下列其中一項操作：
    - 若要查看電腦上執行的服務的最新狀態，請按一下 [**取得服務狀態**]。
    - 若要查看電腦上執行的特定服務清單，以及每個服務的狀態，請按一下 [**屬性**]，然後按一下 [**關閉**] 以返回清單。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看服務狀態

您也可以使用 Windows PowerShell 和 CsWindowsService Cmdlet 來查看服務狀態。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需詳細資訊，請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。

**若要查看服務狀態**

若要在電腦上查看服務狀態，請在商務用 Skype Server Management Shell 中輸入類似以下的命令，然後按 Enter：

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

這個命令會傳回如下所示的資訊：

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

如需詳細資訊，請參閱[CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)。

## <a name="start-or-stop-skype-for-business-services"></a>啟動或停止商務用 Skype 服務

使用商務用 Skype Server 的 [控制台] 來啟動或停止在特定電腦上執行的所有商務用 Skype Server 服務，或是啟動或停止特定服務。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>在電腦上啟動或停止所有商務用 Skype Server 服務

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦. 您可以執行如下所示的命令來判斷您是否已獲指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊，請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [狀態] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。
5. 按一下 [**動作**]。
6. 按一下 [**啟動所有服務**] 或 [**停止所有服務**]。

### <a name="start-or-stop-a-specific-service"></a>啟動或停止特定服務

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
2. 開啟瀏覽器視窗，然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊，請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [狀態] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。
5. 按一下 [**屬性**]。
6. 如有需要，請排序服務清單，然後按一下您要開始或停止的服務。
7. 按一下 [**動作**]。
8. 按一下 [**開始服務**] 或 [**停止服務**]。
9. 按一下 [**關閉**]。


## <a name="prevent-sessions-for-services"></a>防止服務的工作階段

使用商務用 Skype 的 [控制台] 來避免在特定電腦上執行所有商務用 Skype Server 服務的新會話，或避免特定服務的新會話。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>避免電腦上所有商務用 Skype Server 服務的新會話

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
2. 開啟瀏覽器視窗，然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊，請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 在 [狀態] 頁面上，視需要排序或搜尋清單，以尋找執行您想要防止新會話之服務的電腦，然後按一下該電腦。
5. 按一下 [**動作**]。
6. 按一下 [**防止所有服務的新會話**]。

### <a name="prevent-new-sessions-for-a-specific-service"></a>防止特定服務的新會話

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
2. 開啟瀏覽器視窗，然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊，請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
4. 按一下 [**屬性**]。
5. 如有需要，請排序服務清單，然後按一下您要防止新會話的服務。
6. 按一下 [**動作**]。
7. 按一下 [**避免新的服務會話**]。
8. 按一下 [**關閉**]。
